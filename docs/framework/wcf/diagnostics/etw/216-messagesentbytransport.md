---
title: 216 - MessageSentByTransport
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 150c3167-4154-4225-8d94-57cc94341233
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7b35f46ae7a214ab45e4062928de82c4da6541a1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="216---messagesentbytransport"></a>216 - MessageSentByTransport
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|Идентификатор|216|  
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
|HostReference|xs:string|Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии. Ее формат определяется как "веб-сайт имя виртуальный путь приложения &#124; Виртуальный путь службы &#124; ServiceName ". Пример: "по умолчанию веб-сайта или CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService ".|  
|AppDomain|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
