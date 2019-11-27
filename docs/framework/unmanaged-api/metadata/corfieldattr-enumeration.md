---
title: Перечисление CorFieldAttr
ms.date: 03/30/2017
api_name:
- CorFieldAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorFieldAttr
helpviewer_keywords:
- CorFieldAttr enumeration [.NET Framework metadata]
ms.assetid: 6ae2c4be-212c-4e74-9288-40a11dc26522
topic_type:
- apiref
ms.openlocfilehash: d28a0c8b7ee85f023026dde6f3cc8f3a8406aa64
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450314"
---
# <a name="corfieldattr-enumeration"></a>Перечисление CorFieldAttr
Содержит значения, описывающие метаданные поля.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CorFieldAttr {  
  
    fdFieldAccessMask           =   0x0007,  
    fdPrivateScope              =   0x0000,  
    fdPrivate                   =   0x0001,  
    fdFamANDAssem               =   0x0002,  
    fdAssembly                  =   0x0003,  
    fdFamily                    =   0x0004,  
    fdFamORAssem                =   0x0005,  
    fdPublic                    =   0x0006,  
  
    fdStatic                    =   0x0010,  
    fdInitOnly                  =   0x0020,  
    fdLiteral                   =   0x0040,  
    fdNotSerialized             =   0x0080,  
  
    fdSpecialName               =   0x0200,  
  
    fdPinvokeImpl               =   0x2000,  
  
    fdReservedMask              =   0x9500,  
    fdRTSpecialName             =   0x0400,  
    fdHasFieldMarshal           =   0x1000,  
    fdHasDefault                =   0x8000,  
    fdHasFieldRVA               =   0x0100  
  
} CorFieldAttr;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`fdFieldAccessMask`|Указывает сведения о специальных возможностях.|  
|`fdPrivateScope`|Указывает, что на поле нельзя ссылаться.|  
|`fdPrivate`|Указывает, что поле доступно только для его родительского типа.|  
|`fdFamANDAssem`|Указывает, что поле доступно для производных классов в его сборке.|  
|`fdAssembly`|Указывает, что поле доступно для всех типов в его сборке.|  
|`fdFamily`|Указывает, что поле доступно только для его типа и производных классов.|  
|`fdFamORAssem`|Указывает, что поле доступно для производных классов и всех типов в его сборке.|  
|`fdPublic`|Указывает, что поле доступно для всех типов с видимостью этой области.|  
|`fdStatic`|Указывает, что поле является членом его типа, а не членом экземпляра.|  
|`fdInitOnly`|Указывает, что поле нельзя изменить после его инициализации.|  
|`fdLiteral`|Указывает, что значение поля является константой времени компиляции.|  
|`fdNotSerialized`|Указывает, что поле не сериализуется при удаленном типе.|  
|`fdSpecialName`|Указывает, что поле является специальным, и что его имя описывает, как это делать.|  
|`fdPinvokeImpl`|Указывает, что реализация поля пересылается через PInvoke.|  
|`fdReservedMask`|Зарезервировано для внутреннего использования средой CLR.|  
|`fdRTSpecialName`|Указывает, что внутренние API метаданных среды CLR должны проверять кодировку имени.|  
|`fdHasFieldMarshal`|Указывает, что поле содержит сведения о маршалировании.|  
|`fdHasDefault`|Указывает, что поле имеет значение по умолчанию.|  
|`fdHasFieldRVA`|Указывает, что поле имеет относительный виртуальный адрес.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Корхдр. h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
