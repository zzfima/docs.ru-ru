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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: af90055c0a51e61d4032e45d6fa4a4914ddd045f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54667941"
---
# <a name="cortypeattr-enumeration"></a>Перечисление CorTypeAttr
Содержит значения, указывающие тип метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
  
## <a name="members"></a>Участники  
  
|Член|Описание:|  
|------------|-----------------|  
|`tdVisibilityMask`|Используется для сведения о видимости типа.|  
|`tdNotPublic`|Указывает, что тип не открытую область видимости.|  
|`tdPublic`|Указывает, что тип находится в общей области.|  
|`tdNestedPublic`|Указывает, что тип является вложенным с открытой областью видимости.|  
|`tdNestedPrivate`|Указывает, что тип является вложенным с закрытой областью видимости.|  
|`tdNestedFamily`|Указывает, что тип является вложенным с областью видимости.|  
|`tdNestedAssembly`|Указывает, что тип является вложенным с видимостью сборки.|  
|`tdNestedFamANDAssem`|Указывает, что тип является вложенным с областью видимости семейство и сборка.|  
|`tdNestedFamORAssem`|Указывает, что тип является вложенным с областью видимости семейство или сборка.|  
|`tdLayoutMask`|Получает сведения о структуре для типа.|  
|`tdAutoLayout`|Указывает, что поля этого типа располагаются автоматически.|  
|`tdSequentialLayout`|Указывает, что поля этого типа располагаются последовательно.|  
|`tdExplicitLayout`|Указывает, что этот макет поля задается явно.|  
|`tdClassSemanticsMask`|Получает семантическую информацию о типе.|  
|`tdClass`|Указывает, что данный тип является классом.|  
|`tdInterface`|Указывает, что данный тип является интерфейсом.|  
|`tdAbstract`|Указывает, что данный тип является абстрактным.|  
|`tdSealed`|Указывает, что тип не может быть расширен.|  
|`tdSpecialName`|Указывает, что имя класса является специальным. Указывает его имя как.|  
|`tdImport`|Указывает, что тип импортирован.|  
|`tdSerializable`|Указывает, что тип является сериализуемым.|  
|`tdWindowsRuntime`|Указывает, что этот тип является [!INCLUDE[wrt](../../../../includes/wrt-md.md)] типа.|  
|`tdStringFormatMask`|Получает сведения о способ кодирования и форматирования строк.|  
|`tdAnsiClass`|Указывает, что данный тип интерпретирует LPTSTR как ANSI.|  
|`tdUnicodeClass`|Указывает, что данный тип интерпретирует LPTSTR как Юникод.|  
|`tdAutoClass`|Указывает, что данный тип интерпретирует LPTSTR автоматически.|  
|`tdCustomFormatClass`|Указывает, что тип имеет нестандартной кодировкой, определяемом параметрами `CustomFormatMask`.|  
|`tdCustomFormatMask`|Эта маска используется для получения нестандартной кодировки для взаимодействия с машинным кодом. Смысл значений этих двух бит не определено.|  
|`tdBeforeFieldInit`|Указывает, что тип должен быть инициализирован перед первая попытка получить доступ к статическому полю.|  
|`tdForwarder`|Указывает, что тип экспортирован и метод передачи типа.|  
|`tdReservedMask`|Этот флаг и приведенные ниже флаги используются внутри среда CLR.|  
|`tdRTSpecialName`|Указывает, что среда CLR должна проверять кодировку имени.|  
|`tdHasSecurity`|Указывает, что тип имеет безопасности, связанные с ней.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorHdr.h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
