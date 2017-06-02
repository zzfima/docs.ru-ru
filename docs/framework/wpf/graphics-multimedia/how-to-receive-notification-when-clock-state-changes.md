---
title: "Практическое руководство. Получение уведомлений при изменениях состояния часов | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "часы, уведомления об изменениях состояния"
  - "уведомления, изменения состояния часов"
ms.assetid: ecb10fc9-d0c2-45c3-b0a1-7b11baa733da
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Практическое руководство. Получение уведомлений при изменениях состояния часов
Событие часов <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> возникает, когда <xref:System.Windows.Media.Animation.Clock.CurrentState%2A> становится недействительным, например при запуске или остановке часов.  Это событие можно зарегистрировать непосредственно с помощью <xref:System.Windows.Media.Animation.Clock> или с помощью <xref:System.Windows.Media.Animation.Timeline>.  
  
 В следующем примере <xref:System.Windows.Media.Animation.Storyboard> и два объекта <xref:System.Windows.Media.Animation.DoubleAnimation> используются для анимации ширины двух прямоугольников.  Событие <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> используется для отслеживания изменений состояния часов.  
  
## Пример  
 [!code-xml[timingbehaviors_snip#_graphicsmm_StateExampleMarkupWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StateExample.xaml#_graphicsmm_stateexamplemarkupwholepage)]  
  
 [!code-csharp[timingbehaviors_snip#_graphicsmm_StateEventHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StateExample.xaml.cs#_graphicsmm_stateeventhandlers)]
 [!code-vb[timingbehaviors_snip#_graphicsmm_StateEventHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/stateexample.xaml.vb#_graphicsmm_stateeventhandlers)]  
  
 Ниже показаны различные состояния анимаций по мере продвижения родительской временной шкалы \(*раскадровки*\).  
  
 ![Состояния таймера для раскадровки с двумя анимациями](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-3timelines.png "graphicsmm\_3timelines")  
  
 В следующей таблице показаны случаи, в которых активируется событие <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> *Animation1*:  
  
||||||||  
|-|-|-|-|-|-|-|  
|Время \(секунды\)|1|10|19|21|30|39|  
|Состояние|Активно|Активно|Остановлен|Активно|Активно|Остановлен|  
  
 В следующей таблице показаны случаи, в которых активируется событие <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> *Animation2*:  
  
||||||||||  
|-|-|-|-|-|-|-|-|-|  
|Время \(секунды\)|1|9|11|19|21|29|31|39|  
|Состояние|Активно|Заполнение|Активно|Остановлен|Активно|Заполнение|Активно|Остановлен|  
  
 Обратите внимание на то, что событие <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated>*Animation1* активируется на 10\-ой секунде, хотя его состояние остается <xref:System.Windows.Media.Animation.ClockState>.  Это происходит от того, что ее состояние изменилось на 10\-ой секунде, но изменилось из <xref:System.Windows.Media.Animation.ClockState> в <xref:System.Windows.Media.Animation.ClockState>, а затем обратно в <xref:System.Windows.Media.Animation.ClockState> в тот же тик времени.