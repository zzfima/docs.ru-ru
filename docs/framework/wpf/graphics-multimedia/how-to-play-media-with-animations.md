---
title: "Практическое руководство. Воспроизведение мультимедиа с анимацией | Microsoft Docs"
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
  - "воспроизведение мультимедиа с анимацией"
  - "воспроизведение мультимедиа с анимацией"
  - "анимация, воспроизведение мультимедиа"
  - "носитель, воспроизведение в анимации"
ms.assetid: 8982b7b7-1c6c-4b24-8801-b328862975f5
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Воспроизведение мультимедиа с анимацией
В этом примере показано, как воспроизвести мультимедиа и анимацию в то же время с помощью <xref:System.Windows.Media.MediaTimeline> и <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> классы в одном <xref:System.Windows.Media.Animation.Storyboard>.  
  
## <a name="example"></a>Пример  
 Можно использовать один или несколько <xref:System.Windows.Media.MediaTimeline> объектов в <xref:System.Windows.Media.Animation.Storyboard> с другими <xref:System.Windows.Media.Animation.Timeline> объекты, такие как анимации.  
  
 В следующем примере задается <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A> свойство <xref:System.Windows.Media.Animation.Storyboard> значение `Slip`, которое указывает, что анимацию не доходит до выполнения мультимедиа (видео в этом примере). Эта функция может потребоваться, если воспроизведение мультимедиа задерживается из-за времени загрузки.  
  
 [!code-xml[MediaGallery_snippet#MediaTimelinePlusAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snippet/CSharp/MediaTimelinePlusAnimationExample.xaml#mediatimelineplusanimationexamplewholepage)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.MediaTimeline>   
 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>   
 <xref:System.Windows.Media.Animation.Storyboard>   
 <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A>   
 [Разделы практического руководства](../../../../docs/framework/wpf/graphics-multimedia/audio-and-video-how-to-topics.md)   
 [Общие сведения о раскадровках](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)   
 [Общие сведения об анимации по полным кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Обзор анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Графика и мультимедиа](../../../../docs/framework/wpf/graphics-multimedia/index.md)