---
title: Перечисление CorDeclSecurity
ms.date: 03/30/2017
api_name:
- CorDeclSecurity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorDeclSecurity
helpviewer_keywords:
- CorDeclSecurity enumeration [.NET Framework metadata]
ms.assetid: 864f1267-d267-4696-8df7-1f83f8444d6f
topic_type:
- apiref
ms.openlocfilehash: 98183ed02f8821b7c40852de2d040775d30f2518
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443743"
---
# <a name="cordeclsecurity-enumeration"></a>Перечисление CorDeclSecurity
Указывает действия безопасности, которые можно выполнить с помощью декларативной безопасности.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CorDeclSecurity {  
  
    dclActionMask               =   0x001f,  
    dclActionNil                =   0x0000,  
    dclRequest                  =   0x0001,  
    dclDemand                   =   0x0002,  
    dclAssert                   =   0x0003,  
    dclDeny                     =   0x0004,  
    dclPermitOnly               =   0x0005,  
    dclLinktimeCheck            =   0x0006,  
    dclInheritanceCheck         =   0x0007,  
    dclRequestMinimum           =   0x0008,  
    dclRequestOptional          =   0x0009,  
    dclRequestRefuse            =   0x000a,  
    dclPrejitGrant              =   0x000b,  
    dclPrejitDenied             =   0x000c,  
    dclNonCasDemand             =   0x000d,  
    dclNonCasLinkDemand         =   0x000e,  
    dclNonCasInheritance        =   0x000f,  
    dclLinkDemandChoice         =   0x0010,  
    dclInheritanceDemandChoice  =   0x0011,  
    dclDemandChoice             =   0x0012,  
    dclMaximumValue             =   0x0012  
  
} CorDeclSecurity;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`dclActionMask`|Зарезервировано.|  
|`dclActionNil`|Зарезервировано.|  
|`dclRequest`|Зарезервировано.|  
|`dclDemand`|Всем вызывающим объектам выше в стеке вызовов должно быть предоставлено разрешение, заданное текущим объектом разрешений.|  
|`dclAssert`|Вызывающий код может получить доступ к ресурсу, определяемому текущим объектом разрешения, даже если вызывающим объектам выше в стеке не предоставлено разрешение на доступ к ресурсу.|  
|`dclDeny`|Доступ к ресурсу, указанному текущим объектом разрешения, запрещен для вызывающих объектов, даже если им предоставлено разрешение на доступ к нему.|  
|`dclPermitOnly`|Доступ можно получить только к ресурсам, указанным данным объектом разрешения, даже если коду предоставлено разрешение на доступ к другим ресурсам.|  
|`dclLinktimeCheck`|Непосредственный вызывающий объект должен предоставить указанное разрешение в течение заданного периода времени.|  
|`dclInheritanceCheck`|Производный класс, наследующий от другого класса или переопределяющий метод, должен предоставить указанное разрешение.|  
|`dclRequestMinimum`|Вызывающий объект может запросить минимальные разрешения, необходимые для выполнения кода. Это действие может использоваться только в пределах сборки.|  
|`dclRequestOptional`|Вызывающий объект может запросить дополнительные разрешения, которые являются необязательными (не требуются для запуска). Этот запрос неявно отклоняет все прочие разрешения, не запрошенные специально. Это действие может использоваться только в пределах сборки.|  
|`dclRequestRefuse`|Запрос вызывающего объекта для разрешений, которые могут быть неправильно использованы, не будет предоставлен. Это действие может использоваться только в пределах сборки.|  
|`dclPrejitGrant`|Зарезервировано.|  
|`dclPrejitDenied`|Зарезервировано.|  
|`dclNonCasDemand`|Зарезервировано.|  
|`dclNonCasLinkDemand`|Указанное разрешение необходимо предоставить непосредственно вызывающему объекту.|  
|`dclNonCasInheritance`|Зарезервировано.|  
|`dclLinkDemandChoice`|Зарезервировано.|  
|`dclInheritanceDemandChoice`|Зарезервировано.|  
|`dclDemandChoice`|Зарезервировано.|  
|`dclMaximumValue`|Зарезервировано.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Корхдр. h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
