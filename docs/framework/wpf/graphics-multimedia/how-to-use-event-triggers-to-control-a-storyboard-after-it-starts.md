---
title: "Инструкция по Использованию Триггеров Событий для Управления Раскадровкой после ее Запуска | Microsoft Docs"
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
  - "триггеры событий, управление Storyboard"
  - "Раскадровки, управление после запуска"
  - "триггеры, управление Storyboard"
ms.assetid: 3b115594-6a93-4972-b24d-61aa16f1c15f
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Инструкция по Использованию Триггеров Событий для Управления Раскадровкой после ее Запуска
Этот пример демонстрирует управление <xref:System.Windows.Media.Animation.Storyboard> после его запуска.  Для запуска <xref:System.Windows.Media.Animation.Storyboard> с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], используйте <xref:System.Windows.Media.Animation.BeginStoryboard>, которая распределяет анимацию по анимированным им объектам и свойствам, и затем запускает раскадровку.  Если вы дадите имя <xref:System.Windows.Media.Animation.BeginStoryboard>, присвоив его свойству <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A>, вы сделаете управляемую раскадровку.  Вы можете затем интерактивно управлять раскадровкой после ее запуска.  
  
 Используйте следующие действия раскадровки вместе с объектами <xref:System.Windows.EventTrigger> для управления раскадровкой.  
  
-   <xref:System.Windows.Media.Animation.PauseStoryboard>: приостанавливает раскадровку.  
  
-   <xref:System.Windows.Media.Animation.ResumeStoryboard>: возобновляет приостановленную раскадровку.  
  
-   <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: изменяет скорость раскадровки.  
  
-   <xref:System.Windows.Media.Animation.SkipStoryboardToFill>: перемещает раскадровку к концу ее периода заполнения, если он есть.  
  
-   <xref:System.Windows.Media.Animation.StopStoryboard>: останавливает раскадровку.  
  
-   <xref:System.Windows.Media.Animation.RemoveStoryboard>: удаляет раскадровку, освобождает ресурсы.  
  
## Пример  
 Следующий пример использует управляемые действия раскадровки для интерактивного управления раскадровки.  
  
 **Примечание.** Чтобы увидеть пример управления раскадровки с помощью кода, см. [Управление раскадровкой после ее запуска](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-storyboard-after-it-starts.md).  
  
 [!code-xml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]  
  
 Дополнительные примеры см. в разделе [Галерея примеров анимации](http://go.microsoft.com/fwlink/?LinkID=159969).  
  
## См. также  
 <xref:System.Windows.Media.Animation.ResumeStoryboard>   
 <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>   
 <xref:System.Windows.Media.Animation.SkipStoryboardToFill>   
 <xref:System.Windows.Media.Animation.PauseStoryboard>   
 <xref:System.Windows.Media.Animation.StopStoryboard>   
 <xref:System.Windows.Media.Animation.SeekStoryboard>   
 [Управление раскадровкой после ее запуска](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-storyboard-after-it-starts.md)   
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Общие сведения о Storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)