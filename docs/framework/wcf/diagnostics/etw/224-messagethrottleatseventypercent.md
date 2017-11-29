---
title: 224 - MessageThrottleAtSeventyPercent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 82bbbfd7-10d2-41fd-805d-2443b0c1b96b
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 0dd985e3986548938f06e86c1f49d23c43307d17
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="224---messagethrottleatseventypercent"></a>224 - MessageThrottleAtSeventyPercent
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|Идентификатор|224|  
|Ключевые слова|EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel|  
|Уровень|Предупреждение|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  
 При превышении одного из основных ограничителей службы создается событие `MessageThrottleExceeded`. Если всплеск активности уменьшился и текущее значение ограничителя составляет 70 процентов от текущего предела, то создается это событие. Обратите внимание, что это событие создается только один раз при замедлении активности. Если текущее значение находится вблизи отметки 70 процентов (например, 70, 69, 70, 71, 69), то только первое значение 70 процентов приводит к созданию события. После возникновения события все последующие превышения предела регулирования приводят к возникновению события `MessageThrottleExceeded`.  
  
## <a name="message"></a>Сообщение  
 Предел ограничителя %1 из %2 находится на отметке 70%%.  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|Throttle Name|`xs:string`|Имя превышенного ограничителя. `MaxConcurrentCalls`, `MaxConcurrentInstances` либо `MaxConcurrentSessions`,|  
|Limit|`xs:long`|Заданный в данный момент предел ограничителя.|  
|HostReference|`xs:string`|Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии. Ее формат определяется как "веб-сайт имя виртуальный путь приложения &#124; Виртуальный путь службы &#124; ServiceName ". Пример: "по умолчанию веб-сайта или CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService ".|  
|AppDomain|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
