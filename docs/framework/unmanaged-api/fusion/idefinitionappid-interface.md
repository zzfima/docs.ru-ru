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
ms.openlocfilehash: 2735355097a1f3f581b3a4bc74f08d8f2ebf3bd8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="idefinitionappid-interface"></a>Интерфейс IDefinitionAppId
Представляет уникальный идентификатор для кода, определяющего приложение в текущей области.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|`IDefinitionAppId::get_Codebase`|Возвращает строку форматирования, которая представляет код, в этом `IDefinitionAppId` объекта.|  
|`IDefinitionAppId::put_Codebase`|Задает код это `IDefinitionAppId` объекта на указанное значение форматированной строки.|  
|`IDefinitionAppId::EnumAppPath`|Возвращает указатель интерфейса [IEnumDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/ienumdefinitionidentity-interface.md) , содержащий сборки в путь текущего приложения.|  
|`IDefinitionAppId::SetAppPath`|Задает путь приложения для сборки в текущей области, на которое ссылается указанный [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) объекта.|  
|`IDefinitionAppId::get_SubscriptionId`|Получает указатель на строковое представление идентификатора маркера для подписки на это `IDefinitionAppId` объекта.|  
|`IDefinitionAppId::put_SubscriptionId`|Задает идентификатор маркера для подписки на этот `IDefinitionAppId` объекта указанному строковому значению.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Isolation.h  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейсы Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
