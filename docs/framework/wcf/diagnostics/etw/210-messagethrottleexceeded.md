---
title: 210 - MessageThrottleExceeded
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24ca08ea-c11c-4753-946e-98aa820f8711
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2d027f549e86095c732d0e60df3faded44a39fd2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="210---messagethrottleexceeded"></a>210 - MessageThrottleExceeded
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|Идентификатор|210|  
|Ключевые слова|EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel|  
|Уровень|Предупреждение|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  
 Это событие создается при превышении одного из трех основных пределов регулирования службы. Обратите внимание, что это событие создается только в том случае, если предел регулирования превышен уже в исходной конфигурации. Например, если предел регулирования на число одновременных вызовов составляет 10, то при выполнении одиннадцатого вызова будет вызвано событие `MessageThrottleExceeded`. Выполнение двенадцатого вызова не приведет к созданию еще одного события. Если в рамках действия контролируемое значение незначительно изменилось в области предела регулирования, то новые сообщения не вызываются, что позволяет избежать формирования потока ложных сообщений. В этом примере завершение нескольких вызовов указывает на наличие 9 одновременных вызовов. Если последовательно получено еще два входящих вызова, то текущее значение снова будет равно 11. При этом еще одно событие вызвано не будет. Если текущее значение составляет 70 процентов от предела регулирования, то вызывается другое событие, указывающее на замедление выполнения действия. При выполнении последующих действий, которые приводят к превышению ограничения, вызывается другое событие `MessageThrottleExceeded`. В этом примере, если количество одновременных вызовов в определенный момент времени составляло 7, а затем достигло 11, вызывается еще одно событие `MessageThrottleExceeded`.  
  
## <a name="message"></a>Сообщение  
 Был достигнут предел ограничителя «%1» из «%2».  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|Throttle Name|`xs:string`|Имя превышенного ограничителя. `MaxConcurrentCalls`, `MaxConcurrentInstances` либо `MaxConcurrentSessions`,|  
|Limit|`xs:long`|Заданный в данный момент предел ограничителя.|  
|HostReference|`xs:string`|Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии. Ее формат определяется как "веб-сайт имя виртуальный путь приложения &#124; Виртуальный путь службы &#124; ServiceName ". Пример: "по умолчанию веб-сайта или CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService ".|  
|AppDomain|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
