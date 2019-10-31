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
ms.openlocfilehash: 6f20fb2e9e026253fb02b47dfcd63cf655acc4ee
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131649"
---
# <a name="ireferenceappid-interface"></a>Интерфейс IReferenceAppId
Представляет ссылку на уникальный идентификатор приложения в текущей области.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|Возвращает указатель на строковое представление идентификатора кода для приложения, на которое ссылается эта `IReferenceAppId`.|  
|`IReferenceAppId::put_CodeBase`|Задает идентификатор кода для приложения, на которое ссылается эта `IReferenceAppId`.|  
|`IReferenceAppId::EnumAppPath`|Возвращает указатель интерфейса на экземпляр `IEnumReferenceIdentity`, содержащий экземпляры `IReferenceIdentity`, представляющие члены этого `IReferenceAppId`.|  
|`IReferenceAppId::get_SubscriptionId`|Возвращает указатель на строковое представление идентификатора маркера для подписки на этот `IReferenceAppId`.|  
|`IReferenceAppId::put_SubscriptionId`|Устанавливает идентификатор маркера для подписки на этот `IReferenceAppId` указанное строковое значение.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Изоляция. h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы Fusion](fusion-interfaces.md)
- [Интерфейс IEnumReferenceIdentity](ienumreferenceidentity-interface.md)
- [Интерфейс IReferenceIdentity](ireferenceidentity-interface.md)
