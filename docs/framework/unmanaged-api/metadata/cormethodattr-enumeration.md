---
title: Перечисление CorMethodAttr
ms.date: 03/30/2017
api_name:
- CorMethodAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodAttr
helpviewer_keywords:
- CorMethodAttr enumeration [.NET Framework metadata]
ms.assetid: 4e0c3521-e54d-43c1-9857-cc76b49b8ffc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8f144426996583d5058f70daed99d8a37cfb6bfb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444670"
---
# <a name="cormethodattr-enumeration"></a>Перечисление CorMethodAttr
Содержит значения, описывающие функции метода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum CorMethodAttr {  
  
    mdMemberAccessMask          =   0x0007,  
    mdPrivateScope              =   0x0000,  
    mdPrivate                   =   0x0001,  
    mdFamANDAssem               =   0x0002,  
    mdAssem                     =   0x0003,  
    mdFamily                    =   0x0004,  
    mdFamORAssem                =   0x0005,  
    mdPublic                    =   0x0006,  
  
    mdStatic                    =   0x0010,  
    mdFinal                     =   0x0020,  
    mdVirtual                   =   0x0040,  
    mdHideBySig                 =   0x0080,  
  
    mdVtableLayoutMask          =   0x0100,  
    mdReuseSlot                 =   0x0000,  
    mdNewSlot                   =   0x0100,  
  
    mdCheckAccessOnOverride     =   0x0200,  
    mdAbstract                  =   0x0400,  
    mdSpecialName               =   0x0800,  
  
    mdPinvokeImpl               =   0x2000,  
    mdUnmanagedExport           =   0x0008,  
  
    mdReservedMask              =   0xd000,  
    mdRTSpecialName             =   0x1000,  
    mdHasSecurity               =   0x4000,  
    mdRequireSecObject          =   0x8000,  
  
} CorMethodAttr;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`mdMemberAccessMask`|Указывает доступ к членам.|  
|`mdPrivateScope`|Указывает, что элемент невозможно ссылаться.|  
|`mdPrivate`|Указывает, что член доступен только для родительского типа.|  
|`mdFamANDAssem`|Указывает, что член доступен подтипов только в этой сборке.|  
|`mdAssem`|Указывает, что член доступен любой пользователь в сборке.|  
|`mdFamily`|Указывает, что член доступен только для типа и подтипов.|  
|`mdFamORAssem`|Указывает, что член доступен для производных классов и других типов в его сборке.|  
|`mdPublic`|Указывает, элемент доступен для всех типов с доступом к области.|  
|`mdStatic`|Указывает, что член определен как часть типа, а не является членом экземпляра.|  
|`mdFinal`|Указывает, что метод не может быть переопределен.|  
|`mdVirtual`|Указывает, что метод может быть переопределен.|  
|`mdHideBySig`|Указывает, что метод скрывает по имени и подписи, а не только по имени.|  
|`mdVtableLayoutMask`|Задает макет виртуальной таблицы.|  
|`mdReuseSlot`|Указывает, использовать повторно ячейка, используемая для этого метода в виртуальной таблице. Это значение по умолчанию.|  
|`mdNewSlot`|Указывает, что метод всегда получает новую ячейку в виртуальной таблице.|  
|`mdCheckAccessOnOverride`|Указывает, что метод может быть переопределено те же типы, к которым она была видна.|  
|`mdAbstract`|Указывает, что метод не реализован.|  
|`mdSpecialName`|Указывает, что метод является специальным и указывает его имя как.|  
|`mdPinvokeImpl`|Указывает, что реализация метода пересылается с помощью PInvoke.|  
|`mdUnmanagedExport`|Указывает, что метод является управляемый метод экспорте в неуправляемый код.|  
|`mdReservedMask`|Зарезервировано для внутреннего использования средой CLR.|  
|`mdRTSpecialName`|Указывает, что общеязыковая среда выполнения должна проверять кодировку имени метода.|  
|`mdHasSecurity`|Указывает, что метод имеет безопасности, связанные с ним.|  
|`mdRequireSecObject`|Указывает, что метод вызывает другой метод, содержащий код безопасности.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorHdr.h  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
