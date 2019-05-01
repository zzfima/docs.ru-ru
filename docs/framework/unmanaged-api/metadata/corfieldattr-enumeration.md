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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 432e202eb8db105e8d56d3d36cdc8001bac5320c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045946"
---
# <a name="corfieldattr-enumeration"></a>Перечисление CorFieldAttr
Содержит значения, описывающие метаданные поля.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`fdFieldAccessMask`|Указывает сведения о специальных возможностях.|  
|`fdPrivateScope`|Указывает, что это поле нельзя ссылаться.|  
|`fdPrivate`|Указывает, что поле доступно только для родительского типа.|  
|`fdFamANDAssem`|Указывает, что поле доступно для производных классов в его сборке.|  
|`fdAssembly`|Указывает, что поле доступно для всех типов в его сборке.|  
|`fdFamily`|Указывает, что поле доступно только для его типа и производных классов.|  
|`fdFamORAssem`|Указывает, что поле доступно для производных классов и всеми типами в его сборке.|  
|`fdPublic`|Указывает, что поле доступно для всех типов с областью видимости этой области.|  
|`fdStatic`|Указывает, что поле является членом его типа, а не членом экземпляра.|  
|`fdInitOnly`|Указывает, что поле нельзя изменить после инициализации.|  
|`fdLiteral`|Указывает, что значение поля является константой во время компиляции.|  
|`fdNotSerialized`|Указывает, что поле не сериализуется, если его тип является удаленным.|  
|`fdSpecialName`|Указывает, что поле является специальным, и указывает его имя как.|  
|`fdPinvokeImpl`|Указывает, что реализация поля перенаправляется через PInvoke.|  
|`fdReservedMask`|Зарезервировано для внутреннего использования средой CLR.|  
|`fdRTSpecialName`|Указывает, что внутренние API метаданных среды CLR должна проверять кодировку имени.|  
|`fdHasFieldMarshal`|Указывает, что поле содержит сведения о маршалинге.|  
|`fdHasDefault`|Указывает, что поле имеет значение по умолчанию.|  
|`fdHasFieldRVA`|Указывает, что поле имеет относительный виртуальный адрес.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorHdr.h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
