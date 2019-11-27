---
title: Перечисление CorTypeAttr
ms.date: 03/30/2017
api_name:
- CorTypeAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorTypeAttr
helpviewer_keywords:
- CorTypeAttr enumeration [.NET Framework metadata]
ms.assetid: 9bede0ec-5fdf-42a2-b5b7-bee64056acb6
topic_type:
- apiref
ms.openlocfilehash: b1586184c91619994ba0dfc9d5dcc277c10f99cf
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436448"
---
# <a name="cortypeattr-enumeration"></a>Перечисление CorTypeAttr
Содержит значения, указывающие тип метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CorTypeAttr {  
  
    tdVisibilityMask        =   0x00000007,  
    tdNotPublic             =   0x00000000,  
    tdPublic                =   0x00000001,  
    tdNestedPublic          =   0x00000002,  
    tdNestedPrivate         =   0x00000003,  
    tdNestedFamily          =   0x00000004,  
    tdNestedAssembly        =   0x00000005,  
    tdNestedFamANDAssem     =   0x00000006,  
    tdNestedFamORAssem      =   0x00000007,  
  
    tdLayoutMask            =   0x00000018,  
    tdAutoLayout            =   0x00000000,  
    tdSequentialLayout      =   0x00000008,  
    tdExplicitLayout        =   0x00000010,  
  
    tdClassSemanticsMask    =   0x00000020,  
    tdClass                 =   0x00000000,  
    tdInterface             =   0x00000020,  
  
    tdAbstract              =   0x00000080,  
    tdSealed                =   0x00000100,  
    tdSpecialName           =   0x00000400,  
  
    tdImport                =   0x00001000,  
    tdSerializable          =   0x00002000,  
    tdWindowsRuntime        =   0x00004000,  
  
    tdStringFormatMask      =   0x00030000,  
    tdAnsiClass             =   0x00000000,  
    tdUnicodeClass          =   0x00010000,  
    tdAutoClass             =   0x00020000,  
    tdCustomFormatClass     =   0x00030000,  
    tdCustomFormatMask      =   0x00C00000,  
  
    tdBeforeFieldInit       =   0x00100000,  
    tdForwarder             =   0x00200000,  
  
    tdReservedMask          =   0x00040800,  
    tdRTSpecialName         =   0x00000800,  
    tdHasSecurity           =   0x00040000,  
  
} CorTypeAttr;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`tdVisibilityMask`|Используется для сведений о видимости типа.|  
|`tdNotPublic`|Указывает, что тип не находится в общедоступной области.|  
|`tdPublic`|Указывает, что тип находится в общедоступной области.|  
|`tdNestedPublic`|Указывает, что тип является вложенным с открытой видимостью.|  
|`tdNestedPrivate`|Указывает, что тип является вложенным с закрытой видимостью.|  
|`tdNestedFamily`|Указывает, что тип является вложенным с видимостью в семействе.|  
|`tdNestedAssembly`|Указывает, что тип является вложенным с видимостью сборки.|  
|`tdNestedFamANDAssem`|Указывает, что тип является вложенным с видимостью в семействе и сборке.|  
|`tdNestedFamORAssem`|Указывает, что тип является вложенным с видимостью семейства или сборки.|  
|`tdLayoutMask`|Возвращает сведения о макете для типа.|  
|`tdAutoLayout`|Указывает, что поля этого типа размещаются автоматически.|  
|`tdSequentialLayout`|Указывает, что поля этого типа располагаются последовательно.|  
|`tdExplicitLayout`|Указывает, что макет поля указан явно.|  
|`tdClassSemanticsMask`|Возвращает семантическую информацию о типе.|  
|`tdClass`|Указывает, что данный тип является классом.|  
|`tdInterface`|Указывает, что данный тип является интерфейсом.|  
|`tdAbstract`|Указывает, что данный тип является абстрактным.|  
|`tdSealed`|Указывает, что тип не может быть расширен.|  
|`tdSpecialName`|Указывает, что имя класса является специальным. Его имя описывает, как это делать.|  
|`tdImport`|Указывает, что тип импортирован.|  
|`tdSerializable`|Указывает, что тип является сериализуемым.|  
|`tdWindowsRuntime`|Указывает, что этот тип является типом среда выполнения Windows.|  
|`tdStringFormatMask`|Получает сведения о кодировке и форматировании строк.|  
|`tdAnsiClass`|Указывает, что этот тип интерпретирует LPTSTR как ANSI.|  
|`tdUnicodeClass`|Указывает, что этот тип интерпретирует LPTSTR как Юникод.|  
|`tdAutoClass`|Указывает, что этот тип интерпретирует LPTSTR автоматически.|  
|`tdCustomFormatClass`|Указывает, что тип имеет нестандартную кодировку, как указано в `CustomFormatMask`.|  
|`tdCustomFormatMask`|Используйте эту маску для получения нестандартных сведений о кодировке для собственного взаимодействия. Значение этих двух битов не определено.|  
|`tdBeforeFieldInit`|Указывает, что тип должен быть инициализирован перед первой попыткой доступа к статическому полю.|  
|`tdForwarder`|Указывает, что тип экспортирован и является пересылкой типа.|  
|`tdReservedMask`|Этот флаг и указанные ниже флаги используются внутри среды CLR.|  
|`tdRTSpecialName`|Указывает, что среда CLR должна проверять кодировку имен.|  
|`tdHasSecurity`|Указывает, что с типом связана безопасность.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Корхдр. h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
