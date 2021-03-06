---
title: Пошаговое руководство. Использование XSLT IntelliSense | Документация Майкрософт
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: 079d95ac-2eaf-4ae1-9cd3-2c81a961a942
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 45cb15a81f7f8f74ab17bf22ce52aca48a90aea9
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2019
ms.locfileid: "60063105"
---
# <a name="walkthrough-using-xslt-intellisense"></a>Пошаговое руководство. Использование XSLT IntelliSense
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

В этом пошаговом руководстве демонстрируется использование XSLT IntelliSense для автозавершения значения некоторых атрибутов.  
  
### <a name="to-use-intellisense-in-the-name-attribute-of-xslwith-param-and-xslcall-template-elements"></a>Использование IntelliSense в атрибуте name элементов xsl:with-param и xsl:call-template  
  
1. Создайте текстовый XSLT файл и скопируйте в него следующий код:  
  
    ```  
    <xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" version="1.0">  
    <!-- These 2 elements effectively assign  
         $messages = resources/en.xml/<messages>,  
         then $messages is used in the "localized-message" template.  -->  
    <xsl:param name="lang">en</xsl:param>  
    <xsl:variable name="messages"  
          select="document(concat('resources/', $lang, '.xml'))/messages"/>   
  
    <xsl:template name="msg23" match="msg23">  
    </xsl:template>  
  
    <xsl:template name="localized-message">  
      <xsl:param name="msgcode"/>  
      <!-- Show message string. -->  
      <xsl:message terminate="yes">  
        <xsl:value-of select="$messages/message[@name=$msgcode]"/>  
      </xsl:message>  
    </xsl:template>  
    </xsl:stylesheet>  
    ```  
  
2. Вставьте курсор после `<xsl:template name="msg23" match="msg23">` и нажмите клавишу ВВОД. Затем введите следующий элемент `xsl:call-template`:  
  
    ```  
    <xsl:call-template name="localized-message">  
    </xsl:call-template>  
    ```  
  
     При вводе в атрибуте `name=""` элемента `xsl:call-template` появится список имен шаблонов.  
  
3. Вставьте курсор после `<xsl:call-template name="localized-message">` и нажмите клавишу ВВОД. Затем введите следующий элемент `xsl:with-param`:  
  
    ```  
    <xsl:with-param name="msgcode">msg23</xsl:with-param>  
    ```  
  
     При вводе в атрибуте `name=""` элемента `xsl:with-param` появится список имен параметров.  
  
### <a name="to-use-intellisense-in-the-mode-attribute-of-an-xslapply-templates-element"></a>Использование IntelliSense в атрибуте mode элемента xsl:apply-templates  
  
1. Создайте текстовый XSLT файл и скопируйте в него следующий код:  
  
    ```  
    <xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" version="1.0">  
      <xsl:template match="/">  
        <HTML>  
          <BODY>  
            <TABLE>  
              <xsl:apply-templates select="customers/customer">  
                <xsl:sort select="state"/>  
                <xsl:sort select="name"/>  
              </xsl:apply-templates>  
            </TABLE>  
          </BODY>  
        </HTML>  
      </xsl:template>  
      <xsl:template match="customer">  
        <TR>  
          <xsl:apply-templates select="name" />  
          <xsl:apply-templates select="address" />  
          <xsl:apply-templates select="phone" />  
        </TR>  
      </xsl:template>  
      <xsl:template match="name">  
        <TD STYLE="font-size:14pt font-family:serif">  
          <xsl:apply-templates />  
        </TD>  
      </xsl:template>  
      <xsl:template match="address">  
        <TD>  
          <xsl:apply-templates />  
        </TD>  
      </xsl:template>  
      <xsl:template match="phone">  
        <TD>  
          <xsl:apply-templates />  
        </TD>  
      </xsl:template>  
      <xsl:template match="phone" mode="accountNumber">  
        <xsl:param name="Area_Code"/>  
        <TD STYLE="font-style:italic">  
          1-<xsl:value-of select="."/>-001  
        </TD>  
      </xsl:template>  
    </xsl:stylesheet>  
    ```  
  
2. Вставьте курсор после `<xsl:apply-templates select="phone" />` и нажмите клавишу ВВОД. Затем введите следующий элемент `xsl: apply-templates`:  
  
    ```  
    <xsl:apply-templates select="phone"  mode="accountNumber">  
    ```  
  
     При вводе в атрибуте `mode=""` элемента `xsl:apply-templates` появится список режимов шаблона.  
  
### <a name="to-use-intellisense-in-the-stylesheet-prefix-and-result-prefix-attributes-of-an-xslnamespace-alias-element"></a>Использование IntelliSense в атрибутах stylesheet-prefix и result-prefix элемента xsl:namespace-alias  
  
1. Создайте текстовый XSLT файл и скопируйте в него следующий код:  
  
    ```  
    <xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" xmlns:alt="http://www.w3.org/1999/XSL/Transform-alternate"  
    version="1.0">  
      <xsl:param name="browser" select="'InternetExplorer'"/>  
      <xsl:template match="/">  
        <alt:stylesheet>  
          <xsl:choose>  
            <xsl:when test="$browser='InternetExplorer'">  
              <alt:import href="IERoutines.xsl"/>  
              <alt:template match="/">  
                <div>  
                  <alt:call-template name="showTable"/>  
                </div>  
              </alt:template>  
            </xsl:when>  
            <xsl:otherwise>  
              <alt:import href="OtherBrowserRoutines.xsl"/>  
              <alt:template match="/">  
                <div>  
                  <alt:call-template name="showTable"/>  
                </div>  
              </alt:template>  
            </xsl:otherwise>  
          </xsl:choose>  
        </alt:stylesheet>  
      </xsl:template>  
    </xsl:stylesheet>  
    ```  
  
2. Вставьте курсор после `<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" xmlns:alt="http://www.w3.org/1999/XSL/Transform-alternate" version="1.0">` и нажмите клавишу ВВОД. Затем введите следующий элемент `xsl:namespace-alias`:  
  
    ```  
    <xsl:namespace-alias stylesheet-prefix="alt" result-prefix="xsl"/>  
    ```  
  
     Обратите внимание, что в атрибутах `stylesheet-prefix` и `result-prefix` элемента `xsl:namespace-alias` появится список префиксов.  
  
## <a name="see-also"></a>См. также  
 [Возможности IntelliSense редактора XML](../xml-tools/xml-editor-intellisense-features.md)
