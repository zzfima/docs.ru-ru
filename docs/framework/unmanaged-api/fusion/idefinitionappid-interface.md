---
title: Интерфейс IDefinitionAppId
ms.date: 03/30/2017
api_name:
- IDefinitionAppId
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDefinitionAppId
helpviewer_keywords:
- IDefinitionAppId interface [.NET Framework fusion]
ms.assetid: e72f2550-bdec-4a20-a2f4-2e14847266c1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4e8bb31967a6ad515761e6cd03657f2c834debe5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54545560"
---
# <a name="idefinitionappid-interface"></a>Интерфейс IDefinitionAppId
Представляет уникальный идентификатор для кода, который определяет приложение в текущей области.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание:|  
|------------|-----------------|  
|`IDefinitionAppId::get_Codebase`|Возвращает форматированную строку, представляющее код в этом `IDefinitionAppId` объекта.|  
|`IDefinitionAppId::put_Codebase`|Задает код это `IDefinitionAppId` строковое значение в объект в указанном формате.|  
|`IDefinitionAppId::EnumAppPath`|Получает указатель интерфейса на [IEnumDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/ienumdefinitionidentity-interface.md) , содержащий сборки в путь текущего приложения.|  
|`IDefinitionAppId::SetAppPath`|Задает путь к приложению для сборки в текущей области к значению, который ссылается заданный [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) объекта.|  
|`IDefinitionAppId::get_SubscriptionId`|Получает указатель на строковое представление идентификатора маркера для подписки на это `IDefinitionAppId` объекта.|  
|`IDefinitionAppId::put_SubscriptionId`|Задает идентификатор токена для подписки на это `IDefinitionAppId` объекта указанному строковому значению.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Isolation.h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейсы Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
