---
title: "Интерфейс IReferenceAppId"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IReferenceAppId
api_location: fusion.dll
api_type: COM
f1_keywords: IReferenceAppId
helpviewer_keywords: IReferenceAppId interface [.NET Framework fusion]
ms.assetid: 8eb9e565-f358-43ce-900e-a8f8a5aa6cfb
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 22ac2d75632b3c670d7c185cbbf5081732dcaffc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ireferenceappid-interface"></a>Интерфейс IReferenceAppId
Представляет ссылку на уникальный идентификатор для приложения в текущей области.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание:|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|Возвращает указатель на строковое представление идентификатора кода для приложения, упоминаемой в этом `IReferenceAppId`.|  
|`IReferenceAppId::put_CodeBase`|Задает идентификатор кода для приложения, упоминаемой в этом `IReferenceAppId`.|  
|`IReferenceAppId::EnumAppPath`|Возвращает указатель интерфейса `IEnumReferenceIdentity` содержащий экземпляр `IReferenceIdentity` экземпляры, которые представляют элементы этого `IReferenceAppId`.|  
|`IReferenceAppId::get_SubscriptionId`|Получает указатель на строковое представление идентификатора маркера для подписки на это `IReferenceAppId`.|  
|`IReferenceAppId::put_SubscriptionId`|Задает идентификатор маркера для подписки на этот `IReferenceAppId` заданным строковым значением.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Isolation.h  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейсы Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [Интерфейс IEnumReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ienumreferenceidentity-interface.md)  
 [Интерфейс IReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
