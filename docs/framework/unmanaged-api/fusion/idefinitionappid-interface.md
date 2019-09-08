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
ms.openlocfilehash: 929909a7f2c4fa1799c8fed94787b8f853c7eac2
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796519"
---
# <a name="idefinitionappid-interface"></a>Интерфейс IDefinitionAppId
Представляет уникальный идентификатор для кода, определяющего приложение в текущей области.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|`IDefinitionAppId::get_Codebase`|Возвращает отформатированную строку, которая представляет код в `IDefinitionAppId` этом объекте.|  
|`IDefinitionAppId::put_Codebase`|Задает код этого `IDefinitionAppId` объекта в указанном форматированном строковом значении.|  
|`IDefinitionAppId::EnumAppPath`|Возвращает указатель интерфейса на объект [иенумдефинитионидентити](ienumdefinitionidentity-interface.md) , содержащий сборки в текущем пути приложения.|  
|`IDefinitionAppId::SetAppPath`|Задает путь приложения для сборки в текущей области к значению, на которое ссылается указанный объект [идефинитионидентити](idefinitionidentity-interface.md) .|  
|`IDefinitionAppId::get_SubscriptionId`|Возвращает указатель на строковое представление идентификатора маркера для подписки на этот `IDefinitionAppId` объект.|  
|`IDefinitionAppId::put_SubscriptionId`|Устанавливает идентификатор маркера для подписки на этот `IDefinitionAppId` объект в указанном строковом значении.|  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок.** Изоляция. h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы Fusion](fusion-interfaces.md)
