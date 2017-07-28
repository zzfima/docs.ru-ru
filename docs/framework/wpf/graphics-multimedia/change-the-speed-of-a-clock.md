---
title: "Практическое руководство. Изменение скорости часов без изменения скорости шкалы времени | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "часы, изменение скорости"
  - "Clock - скорость, изменение"
ms.assetid: 72f36dd0-f085-445d-8589-19a83fe74f5e
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# Практическое руководство. Изменение скорости часов без изменения скорости шкалы времени
Свойство <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> объекта <xref:System.Windows.Media.Animation.ClockController> позволяет изменять скорость <xref:System.Windows.Media.Animation.Clock> без изменения свойства <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> для <xref:System.Windows.Media.Animation.Timeline> часов.  В следующем примере <xref:System.Windows.Media.Animation.ClockController> используется для интерактивного изменения <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> часов.  Событие <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeedInvalidated> и свойство <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeed%2A> часов используются для отображения текущей глобальной скорости при каждом изменении его интерактивного <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A>.  
  
## Пример  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerSpeedRatioExample.cs#graphicsmmclockcontrollerspeedratioexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerspeedratioexample.vb#graphicsmmclockcontrollerspeedratioexample)]