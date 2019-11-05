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
ms.openlocfilehash: 5114f74e80da925c7a153b9e481c54067152eaec
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108203"
---
# <a name="idefinitionappid-interface"></a>Интерфейс IDefinitionAppId
Представляет уникальный идентификатор для кода, определяющего приложение в текущей области.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|`IDefinitionAppId::get_Codebase`|Возвращает отформатированную строку, которая представляет код в этом `IDefinitionAppId`ном объекте.|  
|`IDefinitionAppId::put_Codebase`|Задает код этого `IDefinitionAppId` объекта в указанном форматированном строковом значении.|  
|`IDefinitionAppId::EnumAppPath`|Возвращает указатель интерфейса на объект [иенумдефинитионидентити](ienumdefinitionidentity-interface.md) , содержащий сборки в текущем пути приложения.|  
|`IDefinitionAppId::SetAppPath`|Задает путь приложения для сборки в текущей области к значению, на которое ссылается указанный объект [идефинитионидентити](idefinitionidentity-interface.md) .|  
|`IDefinitionAppId::get_SubscriptionId`|Возвращает указатель на строковое представление идентификатора маркера для подписки на этот объект `IDefinitionAppId`.|  
|`IDefinitionAppId::put_SubscriptionId`|Задает идентификатор маркера для подписки на этот объект `IDefinitionAppId` в указанное строковое значение.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Изоляция. h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы Fusion](fusion-interfaces.md)
