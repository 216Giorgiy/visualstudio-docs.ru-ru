---
title: DBG_ATTRIB_FLAGS | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DBG_ATTRIB_FLAGS
helpviewer_keywords:
- DBGPROP_ATTRIB_FLAGS enumerations
ms.assetid: 2f13e601-dadc-476e-a8ec-01c4515082e7
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 831d1326d88e70ffaba2cc0c242c55d7325be705
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/22/2019
ms.locfileid: "56689334"
---
# <a name="dbgattribflags"></a>DBG_ATTRIB_FLAGS
Описывает различные атрибуты для [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) или [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) интерфейс. Член [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md) структуры.

## <a name="syntax"></a>Синтаксис

```cpp
#define DBG_ATTRIB_NONE                 0x0000000000000000,
#define DBG_ATTRIB_ALL                  0x00000000ffffffff,

// Attributes about the object itself

#define DBG_ATTRIB_OBJ_IS_EXPANDABLE    0x0000000000000001,
#define DBG_ATTRIB_OBJ_HAS_ID           0x0000000000000002,
#define DBG_ATTRIB_OBJ_CAN_HAVE_ID      0x0000000000000004,

// Attributes about the value of the object

#define DBG_ATTRIB_VALUE_READONLY       0x0000000000000010,
#define DBG_ATTRIB_VALUE_ERROR          0x0000000000000020,
#define DBG_ATTRIB_VALUE_SIDE_EFFECT    0x0000000000000040,
#define DBG_ATTRIB_OVERLOADED_CONTAINER 0x0000000000000080,
#define DBG_ATTRIB_VALUE_BOOLEAN        0x0000000000000100,
#define DBG_ATTRIB_VALUE_BOOLEAN_TRUE   0x0000000000000200,
#define DBG_ATTRIB_VALUE_INVALID        0x0000000000000400,
#define DBG_ATTRIB_VALUE_NAT            0x0000000000000800,
#define DBG_ATTRIB_VALUE_AUTOEXPANDED   0x0000000000001000,
#define DBG_ATTRIB_VALUE_TIMEOUT        0x0000000000002000,
#define DBG_ATTRIB_VALUE_RAW_STRING     0x0000000000004000,
#define DBG_ATTRIB_VALUE_CUSTOM_VIEWER  0x0000000000008000,

// Attributes about field access types for the object

#define DBG_ATTRIB_ACCESS_NONE          0x0000000000010000,
#define DBG_ATTRIB_ACCESS_PUBLIC        0x0000000000020000,
#define DBG_ATTRIB_ACCESS_PRIVATE       0x0000000000040000,
#define DBG_ATTRIB_ACCESS_PROTECTED     0x0000000000080000,
#define DBG_ATTRIB_ACCESS_FINAL         0x0000000000100000,
#define DBG_ATTRIB_ACCESS_ALL           0x00000000001f0000,

// Attributes for the storage types of the object

#define DBG_ATTRIB_STORAGE_NONE         0x0000000001000000,
#define DBG_ATTRIB_STORAGE_GLOBAL       0x0000000002000000,
#define DBG_ATTRIB_STORAGE_STATIC       0x0000000004000000,
#define DBG_ATTRIB_STORAGE_REGISTER     0x0000000008000000,
#define DBG_ATTRIB_STORAGE_ALL          0x000000000f000000,

// Attributes for the type modifiers on the object

#define DBG_ATTRIB_TYPE_NONE            0x0000000100000000,
#define DBG_ATTRIB_TYPE_VIRTUAL         0x0000000200000000,
#define DBG_ATTRIB_TYPE_CONSTANT        0x0000000400000000,
#define DBG_ATTRIB_TYPE_SYNCHRONIZED    0x0000000800000000,
#define DBG_ATTRIB_TYPE_VOLATILE        0x0000001000000000,
#define DBG_ATTRIB_TYPE_ALL             0x0000001f00000000,

// Attributes that describe the type of object

#define DBG_ATTRIB_DATA                 0x0000010000000000,
#define DBG_ATTRIB_METHOD               0x0000020000000000,
#define DBG_ATTRIB_PROPERTY             0x0000040000000000,
#define DBG_ATTRIB_CLASS                0x0000080000000000,
#define DBG_ATTRIB_BASECLASS            0x0000100000000000,
#define DBG_ATTRIB_INTERFACE            0x0000200000000000,
#define DBG_ATTRIB_INNERCLASS           0x0000400000000000,
#define DBG_ATTRIB_MOSTDERIVED          0x0000800000000000,
#define DBG_ATTRIB_CHILD_ALL            0x0000ff0000000000,

// Miscellaneous attributes

#define DBG_ATTRIB_MULTI_CUSTOM_VIEWERS 0x0001000000000000

typedef UINT64 DBG_ATTRIB_FLAGS;
```

```csharp
public const int DBG_ATTRIB_NONE                 = 0x0000000000000000,
public const int DBG_ATTRIB_ALL                  = 0x00000000ffffffff,

// Attributes about the object itself

public const int DBG_ATTRIB_OBJ_IS_EXPANDABLE    = 0x0000000000000001,
public const int DBG_ATTRIB_OBJ_HAS_ID           = 0x0000000000000002,
public const int DBG_ATTRIB_OBJ_CAN_HAVE_ID      = 0x0000000000000004,

// Attributes about the value of the object

public const int DBG_ATTRIB_VALUE_READONLY       = 0x0000000000000010,
public const int DBG_ATTRIB_VALUE_ERROR          = 0x0000000000000020,
public const int DBG_ATTRIB_VALUE_SIDE_EFFECT    = 0x0000000000000040,
public const int DBG_ATTRIB_OVERLOADED_CONTAINER = 0x0000000000000080,
public const int DBG_ATTRIB_VALUE_BOOLEAN        = 0x0000000000000100,
public const int DBG_ATTRIB_VALUE_BOOLEAN_TRUE   = 0x0000000000000200,
public const int DBG_ATTRIB_VALUE_INVALID        = 0x0000000000000400,
public const int DBG_ATTRIB_VALUE_NAT            = 0x0000000000000800,
public const int DBG_ATTRIB_VALUE_AUTOEXPANDED   = 0x0000000000001000,
public const int DBG_ATTRIB_VALUE_TIMEOUT        = 0x0000000000002000,
public const int DBG_ATTRIB_VALUE_RAW_STRING     = 0x0000000000004000,
public const int DBG_ATTRIB_VALUE_CUSTOM_VIEWER  = 0x0000000000008000,

// Attributes about field access types for the object

public const int DBG_ATTRIB_ACCESS_NONE          = 0x0000000000010000,
public const int DBG_ATTRIB_ACCESS_PUBLIC        = 0x0000000000020000,
public const int DBG_ATTRIB_ACCESS_PRIVATE       = 0x0000000000040000,
public const int DBG_ATTRIB_ACCESS_PROTECTED     = 0x0000000000080000,
public const int DBG_ATTRIB_ACCESS_FINAL         = 0x0000000000100000,
public const int DBG_ATTRIB_ACCESS_ALL           = 0x00000000001f0000,

// Attributes for the storage types of the object

public const int DBG_ATTRIB_STORAGE_NONE         = 0x0000000001000000,
public const int DBG_ATTRIB_STORAGE_GLOBAL       = 0x0000000002000000,
public const int DBG_ATTRIB_STORAGE_STATIC       = 0x0000000004000000,
public const int DBG_ATTRIB_STORAGE_REGISTER     = 0x0000000008000000,
public const int DBG_ATTRIB_STORAGE_ALL          = 0x000000000f000000,

// Attributes for the type modifiers on the object

public const int DBG_ATTRIB_TYPE_NONE            = 0x0000000100000000,
public const int DBG_ATTRIB_TYPE_VIRTUAL         = 0x0000000200000000,
public const int DBG_ATTRIB_TYPE_CONSTANT        = 0x0000000400000000,
public const int DBG_ATTRIB_TYPE_SYNCHRONIZED    = 0x0000000800000000,
public const int DBG_ATTRIB_TYPE_VOLATILE        = 0x0000001000000000,
public const int DBG_ATTRIB_TYPE_ALL             = 0x0000001f00000000,

// Attributes that describe the type of object

public const int DBG_ATTRIB_DATA                 = 0x0000010000000000,
public const int DBG_ATTRIB_METHOD               = 0x0000020000000000,
public const int DBG_ATTRIB_PROPERTY             = 0x0000040000000000,
public const int DBG_ATTRIB_CLASS                = 0x0000080000000000,
public const int DBG_ATTRIB_BASECLASS            = 0x0000100000000000,
public const int DBG_ATTRIB_INTERFACE            = 0x0000200000000000,
public const int DBG_ATTRIB_INNERCLASS           = 0x0000400000000000,
public const int DBG_ATTRIB_MOSTDERIVED          = 0x0000800000000000,
public const int DBG_ATTRIB_CHILD_ALL            = 0x0000ff0000000000,

// Miscellaneous attributes

public const int DBG_ATTRIB_MULTI_CUSTOM_VIEWERS = 0x0001000000000000
```

## <a name="members"></a>Участники
 DBG_ATTRIB_NONE указывает атрибуты отсутствуют.

 DBG_ATTRIB_ALL указывает все атрибуты.

 DBG_ATTRIB_OBJ_IS_EXPANDABLE указывает, что ссылка или свойство имеет дочерние элементы.

 DBG_ATTRIB_OBJ_HAS_ID указывает, что был создан идентификатор для данного объекта.

 DBG_ATTRIB_OBJ_CAN_HAVE_ID указывает, что можно создать идентификатор для данного объекта.

 DBG_ATTRIB_VALUE_READONLY указывает, что значение только для чтения.

 DBG_ATTRIB_VALUE_ERROR указывает на то, что значение ошибки.

 DBG_ATTRIB_VALUE_SIDE_EFFECT означает, что вычисление имеет побочный эффект.

 DBG_ATTRIB_OVERLOADED_CONTAINER указывает, что это свойство действительно является контейнером перегрузок.

 DBG_ATTRIB_VALUE_BOOLEAN указывает, что значение в `DEBUG_PROPERTY_INFO::bstrValue` является логическое значение.

 DBG_ATTRIB_VALUE_BOOLEAN_TRUE указывает, что значение в `DEBUG_PROPERTY_INFO::bstrValue` является логическим и `TRUE`.

 DBG_ATTRIB_VALUE_INVALID указывает, что значение в `DEBUG_PROPERTY_INFO::bstrValue` является недопустимым.

 DBG_ATTRIB_VALUE_NAT указывает, что значение в `DEBUG_PROPERTY_INFO::bstrValue` — "*не самое*" (NAT). NAT описывает флаг регистра в 64-разрядных процессоров Intel, указывающий отложенного наблюдающей исключения.

 DBG_ATTRIB_VALUE_AUTOEXPANDED указывает, что значение в `DEBUG_PROPERTY_INFO::bstrValue` возможно был развернут автоматически.

 DBG_ATTRIB_VALUE_TIMEOUT указывает, что оценку истекло.

 DBG_ATTRIB_VALUE_RAW_STRING указывает, что значение в `DEBUG_PROPERTY_INFO::bstrValue` может быть представлена необработанной строки.

 DBG_ATTRIB_VALUE_CUSTOM_VIEWER указывает, что это свойство имеет по крайней мере одно пользовательское средство просмотра, связанные с ней.

 DBG_ATTRIB_ACCESS_NONE указывает объект, ни `public`, `private`, ни `protected` тип доступа.

 DBG_ATTRIB_ACCESS_PUBLIC указывает объект, имеющий общий доступ.

 DBG_ATTRIB_ACCESS_PRIVATE указывает объект, имеющий закрытый доступ.

 DBG_ATTRIB_ACCESS_PROTECTED указывает объект, который имеет защищенный доступ.

 DBG_ATTRIB_ACCESS_FINAL указывает объект, имеющий финальный доступ.

 Атрибуты DBG_ATTRIB_ACCESS_ALL маска для извлечения доступ из `DBG_ATTRIB_FLAGS`.

 DBG_ATTRIB_STORAGE_NONE указывает, что отсутствует указанный тип хранилища.

 DBG_ATTRIB_STORAGE_GLOBAL указывает глобальное хранилище.

 DBG_ATTRIB_STORAGE_STATIC указывает статическое хранилище.

 Указывает DBG_ATTRIB_STORAGE_REGISTER хранилища в регистре.

 DBG_ATTRIB_STORAGE_ALL маска для извлечения в хранилище атрибутов из `DBG_ATTRIB_FLAGS`.

 DBG_ATTRIB_TYPE_NONE указывает, что нет никакой модификатор типа.

 DBG_ATTRIB_TYPE_VIRTUAL указывает, что тип объекта является виртуальным.

 DBG_ATTRIB_TYPE_CONSTANT указывает, что тип объекта является константой.

 DBG_ATTRIB_TYPE_SYNCHRONIZED указывает, что тип объекта синхронизации.

 DBG_ATTRIB_TYPE_VOLATILE указывает, что тип объекта является временным.

 Атрибуты DBG_ATTRIB_TYPE_ALL маска для извлечения типа из `DBG_ATTRIB_FLAGS`.

 DBG_ATTRIB_DATA указывает на то, что этот объект поля данных.

 DBG_ATTRIB_METHOD указывает, что этот объект является методом.

 DBG_ATTRIB_PROPERTY указывает, что этот объект является свойством.

 DBG_ATTRIB_CLASS указывает на то, что этот объект класса.

 DBG_ATTRIB_BASECLASS указывает на то, что этот объект базового класса.

 DBG_ATTRIB_INTERFACE указывает, что этот объект является интерфейсом.

 DBG_ATTRIB_INNERCLASS указывает на то, что этот объект внутреннего класса.

 DBG_ATTRIB_MOSTDERIVED указывает, что этот объект является "*самого дальнего*". Термин "*самого дальнего*" означает фактический тип объекта, а не тип ссылки.

 Указывает маску, DBG_ATTRIB_CHILD_ALL `DBG_ATTRIB_DATA` через `DBG_ATTRIB_MOSTDERIVED`.

 DBG_ATTRIB_MULTI_CUSTOM_VIEWERS указывает, что объект имеет несколько пользовательских средств просмотра, связанные с ней.

## <a name="remarks"></a>Примечания

> [!NOTE]
>  Значения в этом перечислении фактически не определенные в сборке для C#. Вместо этого необходимо скопировать определения в файле исходного кода.

 Эти флаги также используются для фильтрации дочерних элементов объекта, например, при передаче в качестве аргумента для [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md). Значения могут объединяться с побитовым объектом `OR`.

 `DBG_ATTRIB_VALUE_CUSTOM_VIEWER` Флаг, чтобы указать для [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] для получения [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md) интерфейс из [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) интерфейс и вызов [GetCustomViewerList](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md) список пользовательских средств просмотра.

## <a name="requirements"></a>Требования
 Header: msdbg.h

 Пространство имен: Microsoft.VisualStudio.Debugger.Interop

 Сборка: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>См. также
- [Перечисления](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)
- [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)
- [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)
- [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md)