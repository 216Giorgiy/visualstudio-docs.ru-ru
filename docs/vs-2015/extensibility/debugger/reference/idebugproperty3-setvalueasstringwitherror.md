---
title: IDebugProperty3::SetValueAsStringWithError | Документация Майкрософт
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugProperty3::SetValueAsStringWithError
helpviewer_keywords:
- IDebugProperty3::SetValueAsStringWithError
ms.assetid: b378368f-4a45-4b2f-8e3d-3bff7a18ab17
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 58b2c487e0259ec2381638c77608f8773af3e159
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "58979810"
---
# <a name="idebugproperty3setvalueasstringwitherror"></a>IDebugProperty3::SetValueAsStringWithError
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Задает значение этого свойства и возвращает сообщение об ошибке, при необходимости.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetValueAsStringWithError(  
   LPCOLESTR pszValue,  
   DWORD     dwRadix,  
   DWORD     dwTimeout,  
   BSTR*     errorString  
);  
```  
  
```csharp  
int SetValueAsStringWithError(  
   string     pszValue,  
   uint       dwRadix,  
   uint       dwTimeout,  
   out string errorString  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pszValue`  
 [in] Задаваемое значение.  
  
 `dwRadix`  
 [in] Основание системы счисления задаваемое значение.  
  
 `dwTimeout`  
 [in] Продолжительность времени ожидания задать значения (`INFINITE` означает бесконечное ожидание).  
  
 `errorString`  
 [out] Если произошла ошибка при установке значения, содержит причину сбоя.  
  
## <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения возвращает `S_OK`; в противном случае возвращает код ошибки.  
  
## <a name="remarks"></a>Примечания  
 Входящее значение может быть выражение для оценки.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как реализовать этот метод для **CProperty** объекта, который предоставляет [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md) интерфейс.  
  
```cpp#  
HRESULT CProperty::SetValueAsStringWithError(   
    LPCOLESTR in_szValue,  
    DWORD in_RADIX,  
    DWORD in_TIMEOUT,   
    BSTR * out_ERRORTEXT  
)  
{  
    // precondition  
    REQUIRE( NULL != in_szValue );  
  
    if (NULL == in_szValue)  
        return E_INVALIDARG;  
  
    INVARIANT( this );  
    if (!this->ClassInvariant())  
        return E_UNEXPECTED;  
  
    if (NULL == m_pPropertyContext->m_pCEE->m_LanguageSpecificUseCases.pfSetValue)  
        return S_OK;  
  
    // function body  
    DEBUG_PROPERTY_INFO dpInfo,dpInfo2;  
    HRESULT HR = this->GetPropertyInfo(DEBUGPROP_INFO_FULLNAME | DEBUGPROP_INFO_ATTRIB | DEBUGPROP_INFO_TYPE | DEBUGPROP_INFO_VALUE_AUTOEXPAND,  
                                       in_RADIX,  
                                       in_TIMEOUT,  
                                       NULL,  
                                       0,  
                                       &dpInfo);  
  
    if (ENSURE( S_OK == HR ))  
    {  
        REQUIRE( NULL != dpInfo.bstrFullName );  
        REQUIRE( NULL != dpInfo.bstrType );  
  
        REQUIRE( NULL == dpInfo.bstrName );  
        REQUIRE( NULL == dpInfo.bstrValue );  
        REQUIRE( NULL == dpInfo.pProperty );  
  
        BSTR bstrError = NULL;  
  
        UINT ichError = 0;  
        IDebugProperty2* pProperty = NULL;  
        IDebugParsedExpression* pParsedExpression = NULL;  
  
        CComBSTR bstrValue = dpInfo.bstrFullName;  
        bstrValue += L" = ";  
        bstrValue += in_szValue;  
        HR = this->m_pPropertyContext->m_pCEE->  
                Parse(bstrValue, 0, in_RADIX, &bstrError, &ichError, &pParsedExpression);  
        if (S_OK == HR)  
        {  
            REQUIRE( NULL == bstrError );  
            HR = pParsedExpression->EvaluateSync(EVAL_NOEVENTS | EVAL_RETURNVALUE,  
                                                 in_TIMEOUT,  
                                                 m_pPropertyContext->m_pSymbolProvider,  
                                                 m_pPropertyContext->m_pAddress,  
                                                 m_pPropertyContext->m_pBinder,  
                                                 NULL,  
                                                 &pProperty);  
  
            dpInfo2.dwAttrib = DBG_ATTRIB_VALUE_ERROR;  
            if (pProperty)  
            {  
                pProperty->GetPropertyInfo(DEBUGPROP_INFO_ATTRIB | DEBUGPROP_INFO_VALUE,10,in_TIMEOUT,NULL,0,&dpInfo2);  
            }  
            if (DBG_ATTRIB_VALUE_ERROR & dpInfo2.dwAttrib)  
            {  
                HR = E_FAIL;  
                bstrError = dpInfo2.bstrValue;  
            }  
            else  
            {  
                ::SysFreeString(dpInfo.bstrValue);  
            }  
            EXTERNAL_RELEASE(pProperty);  
            EXTERNAL_RELEASE(pParsedExpression);          
        }  
  
        if (bstrError)  
        {  
            if(out_ERRORTEXT)  
            {  
                *out_ERRORTEXT = bstrError;  
                bstrError = NULL;  
            }  
            else  
            {  
                ::SysFreeString(bstrError);  
            }  
        }  
        ::SysFreeString(dpInfo.bstrFullName);  
        ::SysFreeString(dpInfo.bstrType);  
    }  
  
    // postcondition  
    INVARIANT( this );  
  
    return HR;  
}  
```  
  
## <a name="see-also"></a>См. также  
 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)
