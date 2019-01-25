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
ms.openlocfilehash: 2289a9a75311c9642a764844ee466adcc5838655
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54744353"
---
# <a name="ireferenceappid-interface"></a>Интерфейс IReferenceAppId
Представляет ссылку на уникальный идентификатор для приложения в текущей области.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание:|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|Возвращает указатель на строковое представление идентификатора кода для приложения, который ссылается этот `IReferenceAppId`.|  
|`IReferenceAppId::put_CodeBase`|Задает идентификатор кода для приложения, который ссылается этот `IReferenceAppId`.|  
|`IReferenceAppId::EnumAppPath`|Получает указатель интерфейса на `IEnumReferenceIdentity` содержащий экземпляр `IReferenceIdentity` экземпляры, представляющие элементов этой `IReferenceAppId`.|  
|`IReferenceAppId::get_SubscriptionId`|Получает указатель на строковое представление идентификатора маркера для подписки на это `IReferenceAppId`.|  
|`IReferenceAppId::put_SubscriptionId`|Задает идентификатор токена для подписки на это `IReferenceAppId` к указанному строковому значению.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Isolation.h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейсы Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [Интерфейс IEnumReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ienumreferenceidentity-interface.md)
- [Интерфейс IReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
