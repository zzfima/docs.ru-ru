---
title: "Практическое руководство. Указание режима FillBehavior для временной шкалы, достигшей конца периода активности | Microsoft Docs"
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
  - "FillBehavior - свойство для неактивных временных шкал Timeline"
  - "Временные шкалы, FillBehavior - свойство"
ms.assetid: db805f59-d513-4dac-af15-47005dae3199
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Указание режима FillBehavior для временной шкалы, достигшей конца периода активности
В этом примере демонстрируется, как указать режим <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> для неактивной шкалы <xref:System.Windows.Media.Animation.Timeline> анимированного свойства.  
  
## Пример  
 Свойство <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> класса <xref:System.Windows.Media.Animation.Timeline> определяет, что происходит со значением анимированного свойства, когда оно не анимируется, то есть, когда временная шкала <xref:System.Windows.Media.Animation.Timeline> неактивна, но ее родительская шкала <xref:System.Windows.Media.Animation.Timeline> находится в периоде активности или хранения.  Например, сохранит ли анимированное свойство свое конечное значение после окончания анимации или будет выполнен возврат к значению, которое было до начала анимации.  
  
 В следующем примере используется анимация <xref:System.Windows.Media.Animation.DoubleAnimation> для анимации ширины <xref:System.Windows.FrameworkElement.Width%2A> двух прямоугольников.  Каждый прямоугольник использует различные объекты <xref:System.Windows.Media.Animation.Timeline>.  
  
 Одна шкала <xref:System.Windows.Media.Animation.Timeline> имеет режим <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>, установленный в значение <xref:System.Windows.Media.Animation.FillBehavior>, в результате чего ширина прямоугольника возвращается к неанимированному значению по окончанию шкалы <xref:System.Windows.Media.Animation.Timeline>.  Другая шкала <xref:System.Windows.Media.Animation.Timeline> имеет режим <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> со значением <xref:System.Windows.Media.Animation.FillBehavior>, в результате чего ширина остается в конечном значении по окончанию шкалы <xref:System.Windows.Media.Animation.Timeline>.  
  
 [!code-xml[timingbehaviors_snip#FillBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/FillBehaviorExample.xaml#fillbehaviorwholepage)]  
  
 Полный пример см. на веб\-странице [Галерея примеров анимации](http://go.microsoft.com/fwlink/?LinkID=159969).  
  
## См. также  
 <xref:System.Windows.Media.Animation.DoubleAnimation>   
 <xref:System.Windows.FrameworkElement.Width%2A>   
 <xref:System.Windows.Media.Animation.Timeline>   
 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>   
 <xref:System.Windows.Media.Animation.FillBehavior>   
 <xref:System.Windows.Media.Animation.FillBehavior>   
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Animation and Timing](http://msdn.microsoft.com/ru-ru/7d83765b-d5ae-41b1-b423-80206e1124aa)   
 [Практические руководства](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)