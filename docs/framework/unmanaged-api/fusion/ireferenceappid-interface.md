---
title: Интерфейс IReferenceAppId
ms.date: 03/30/2017
api_name:
- IReferenceAppId
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IReferenceAppId
helpviewer_keywords:
- IReferenceAppId interface [.NET Framework fusion]
ms.assetid: 8eb9e565-f358-43ce-900e-a8f8a5aa6cfb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 522ed80f161f114af25e1fa7ad041c8238073d6f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796368"
---
# <a name="ireferenceappid-interface"></a>Интерфейс IReferenceAppId
Представляет ссылку на уникальный идентификатор приложения в текущей области.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|Возвращает указатель на строковое представление идентификатора кода для приложения, на которое ссылается this `IReferenceAppId`.|  
|`IReferenceAppId::put_CodeBase`|Задает идентификатор кода для приложения, на которое ссылается this `IReferenceAppId`.|  
|`IReferenceAppId::EnumAppPath`|Возвращает указатель интерфейса на `IEnumReferenceIdentity` экземпляр, `IReferenceIdentity` содержащий экземпляры, представляющие члены этого `IReferenceAppId`объекта.|  
|`IReferenceAppId::get_SubscriptionId`|Возвращает указатель на строковое представление идентификатора маркера для подписки на этот `IReferenceAppId`объект.|  
|`IReferenceAppId::put_SubscriptionId`|Задает для идентификатора маркера подписки это `IReferenceAppId` значение в указанном строковом значении.|  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок.** Изоляция. h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы Fusion](fusion-interfaces.md)
- [Интерфейс IEnumReferenceIdentity](ienumreferenceidentity-interface.md)
- [Интерфейс IReferenceIdentity](ireferenceidentity-interface.md)
