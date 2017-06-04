---
title: "Как управлять раскадровкой после ее запуска | Microsoft Docs"
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
  - "Раскадровки, управление после запуска"
ms.assetid: 040f13f0-69f9-4ab5-be2b-079f4f80c7c0
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Как управлять раскадровкой после ее запуска
В этом примере показано использование кода для управления объектом <xref:System.Windows.Media.Animation.Storyboard> после его запуска.  Чтобы управлять раскадровкой в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], используйте объекты <xref:System.Windows.Trigger> и <xref:System.Windows.TriggerAction>; примеры содержатся в разделе [Использование триггеров событий для управления раскадровкой после ее запуска](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).  
  
 Для запуска раскадровки используйте метод <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>, который распределяет анимации раскадровки на свойства и запускает ее.  
  
 Чтобы сделать раскадровку управляемой, используйте метод <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> и укажите **true** в качестве второго параметра.  Затем можно использовать интерактивные методы раскадровки для паузы, возобновления, поиска, остановки, ускорения или замедления раскадровки, или перемещения ее до периода заполнения.  Ниже приведен список интерактивных методов раскадровки:  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Pause%2A>: приостанавливает раскадровку.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Resume%2A>: возобновляет приостановленную раскадровку.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SetSpeedRatio%2A>: задает интерактивную скорость раскадровки.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Seek%2A>: ищет указанное место раскадровки.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A>: ищет раскадровку в указанном месте.  В отличие от метода <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> эта операция обрабатывается до следующего такта.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>: перемещает раскадровку до периода заполнения, если он имеется.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Stop%2A>: останавливает раскадровку.  
  
 В следующем примере несколько методов используются для интерактивного управления раскадровкой.  
  
 **Примечание.** Для просмотра примера управления раскадровкой с помощью триггеров с [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] см. [Использование триггеров событий для управления раскадровкой после ее запуска](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).  
  
## Пример  
 [!code-csharp[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ControlStoryboardExample.cs#controlstoryboardexampleusingwholepage)]
 [!code-vb[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/controlstoryboardexample.vb#controlstoryboardexampleusingwholepage)]  
  
## См. также  
 [Использование триггеров событий для управления раскадровкой после ее запуска](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)