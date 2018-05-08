---
title: 216 - MessageSentByTransport
ms.date: 03/30/2017
ms.assetid: 150c3167-4154-4225-8d94-57cc94341233
ms.openlocfilehash: fa21568e4c8c38eefe359c417d47ec0a9d30a7c4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="216---messagesentbytransport"></a>216 - MessageSentByTransport
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|216|  
|Ключевые слова|Troubleshooting, ServiceModel|  
|Уровень|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  
 Это событие возникает при отправке сообщения транспортом на основе TCP. Обратите внимание, что в рамках одной операции между клиентом и службой может быть передано несколько сообщений уровня транспорта. Это может быть вызвано особенностями инфраструктуры (и требования безопасности - хороший пример). Таким образом, число **MessageSentByTransport** создаваемых событий зависит от привязки службы и его конфигурации.  
  
## <a name="message"></a>Сообщение  
 Транспорт отправил сообщение «%1».  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|DestinationAddress|`xs:string`|Адрес, на который было отправлено сообщение запроса.|  
|HostReference|xs:string|Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии. Ее формат определяется как "веб-сайт имя виртуальный путь приложения&#124;виртуальный путь службы&#124;имя_службы". Пример: "по умолчанию веб-сайта или CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService".|  
|AppDomain|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
