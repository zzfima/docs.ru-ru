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
ms.openlocfilehash: 74088d1cd018bb07406fc7d00ff83d783a98b663
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450226"
---
# <a name="cormethodattr-enumeration"></a>Перечисление CorMethodAttr
Содержит значения, описывающие возможности метода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
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
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`mdMemberAccessMask`|Указывает доступ к члену.|  
|`mdPrivateScope`|Указывает, что элемент не может быть указан.|  
|`mdPrivate`|Указывает, что элемент доступен только для родительского типа.|  
|`mdFamANDAssem`|Указывает, что элемент доступен только для подтипов в этой сборке.|  
|`mdAssem`|Указывает, что элемент акцессиблися любым пользователем в сборке.|  
|`mdFamily`|Указывает, что элемент доступен только по типу и подтипам.|  
|`mdFamORAssem`|Указывает, что член доступен для производных классов и других типов в его сборке.|  
|`mdPublic`|Указывает, что элемент доступен для всех типов с доступом к области.|  
|`mdStatic`|Указывает, что член определен как часть типа, а не как член экземпляра.|  
|`mdFinal`|Указывает, что метод не может быть переопределен.|  
|`mdVirtual`|Указывает, что метод может быть переопределен.|  
|`mdHideBySig`|Указывает, что метод скрывается по имени и сигнатуре, а не просто по имени.|  
|`mdVtableLayoutMask`|Указывает макет виртуальной таблицы.|  
|`mdReuseSlot`|Указывает, что необходимо повторно использовать слот, используемый для этого метода в виртуальной таблице. Это значение по умолчанию.|  
|`mdNewSlot`|Указывает, что метод всегда получает новый слот в виртуальной таблице.|  
|`mdCheckAccessOnOverride`|Указывает, что метод может быть переопределен теми же типами, для которых он является видимым.|  
|`mdAbstract`|Указывает, что метод не реализован.|  
|`mdSpecialName`|Указывает, что метод является специальным и что его имя описывает, как это делать.|  
|`mdPinvokeImpl`|Указывает, что реализация метода пересылается с помощью PInvoke.|  
|`mdUnmanagedExport`|Указывает, что метод является управляемым методом, экспортированным в неуправляемый код.|  
|`mdReservedMask`|Зарезервировано для внутреннего использования средой CLR.|  
|`mdRTSpecialName`|Указывает, что среда CLR должна проверять кодировку имени метода.|  
|`mdHasSecurity`|Указывает, что метод имеет связанную с ним безопасность.|  
|`mdRequireSecObject`|Указывает, что метод вызывает другой метод, содержащий код безопасности.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Корхдр. h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
