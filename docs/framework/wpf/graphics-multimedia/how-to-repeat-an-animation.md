---
title: "Практическое руководство. Повторение анимации | Microsoft Docs"
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
  - "анимация, повтор"
  - "RepeatBehavior - свойство временных шкал Timeline"
  - "повторяющаяся анимация"
  - "RepeatBehavior - свойство Timeline"
ms.assetid: e6f3b068-eeeb-47fd-8d40-8848c31f1e1e
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Повторение анимации
В этом примере показано использование свойства <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> <xref:System.Windows.Media.Animation.Timeline> для управления повторением анимации.  
  
## Пример  
 Свойство <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> <xref:System.Windows.Media.Animation.Timeline> определяет, сколько раз будет повторяться анимация.  С помощью <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> можно указать, что <xref:System.Windows.Media.Animation.Timeline> будет повторяться определенное число раз \(итераций\) или в течение указанного периода времени.  В любом случае анимация осуществляет столько проходов от начала до конца, сколько требуется для выполнения запрошенного числа повторений или длительности.  
  
 По умолчанию временные шкалы имеют число повторений, равное 1.0. Это означает, что они воспроизводятся один раз и не повторяются.  Тем не менее, если установить свойство <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> элемента <xref:System.Windows.Media.Animation.Timeline> в значение <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, временная последовательность повторяется бесконечное число раз.  
  
 В следующем примере показано использование свойства <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> для управления повторением анимации.  В примере анимируется свойство <xref:System.Windows.FrameworkElement.Width%2A> пяти прямоугольников, каждый из которых использует разный тип повторения.  
  
 [!code-xml[timingbehaviors_snip#RepeatBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/RepeatBehaviorExample.xaml#repeatbehaviorwholepage)]  
  
 Полный код примера см. на веб\-странице [Пример поведения анимации во времени](http://go.microsoft.com/fwlink/?LinkID=159970).  
  
## См. также  
 [Накапливание значений анимации в повторяющихся циклах](../../../../docs/framework/wpf/graphics-multimedia/how-to-accumulate-animation-values-during-repeat-cycles.md)   
 [Определение автоматического реверса для шкалы времени](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-whether-a-timeline-automatically-reverses.md)   
 [Практические руководства](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)   
 [Animation and Timing](http://msdn.microsoft.com/ru-ru/7d83765b-d5ae-41b1-b423-80206e1124aa)   
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Animation Timing Behavior Sample](http://go.microsoft.com/fwlink/?LinkID=159970)