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
ms.openlocfilehash: 2484fa61c03b95e7cbdb452b92a68a2049701374
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429521"
---
# <a name="ireferenceappid-interface"></a>Интерфейс IReferenceAppId
Представляет ссылку на уникальный идентификатор для приложения в текущей области.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|Возвращает указатель на строковое представление идентификатора кода для приложения, упоминаемой в этом `IReferenceAppId`.|  
|`IReferenceAppId::put_CodeBase`|Задает идентификатор кода для приложения, упоминаемой в этом `IReferenceAppId`.|  
|`IReferenceAppId::EnumAppPath`|Возвращает указатель интерфейса `IEnumReferenceIdentity` содержащий экземпляр `IReferenceIdentity` экземпляры, которые представляют элементы этого `IReferenceAppId`.|  
|`IReferenceAppId::get_SubscriptionId`|Получает указатель на строковое представление идентификатора маркера для подписки на это `IReferenceAppId`.|  
|`IReferenceAppId::put_SubscriptionId`|Задает идентификатор маркера для подписки на этот `IReferenceAppId` заданным строковым значением.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Isolation.h  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейсы Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [Интерфейс IEnumReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ienumreferenceidentity-interface.md)  
 [Интерфейс IReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
