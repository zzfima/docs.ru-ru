---
title: "Практическое руководство. Управление элементом &quot;MediaElement&quot; с помощью объекта &quot;Storyboard&quot; | Microsoft Docs"
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
  - "управление воспроизведением мультимедиа, с раскадровками"
  - "носители, управление воспроизведением с помощью Storyboard"
  - "мультимедиа, управление воспроизведением мультимедиа с помощью Storyboard"
  - "воспроизведение мультимедиа, управление с помощью Storyboard"
  - "Раскадровки, управление воспроизведением мультимедиа с помощью"
ms.assetid: 6128ca77-b826-4e36-b968-6f237157c543
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Управление элементом &quot;MediaElement&quot; с помощью объекта &quot;Storyboard&quot;
В этом примере демонстрируется управление объектом <xref:System.Windows.Controls.MediaElement> с помощью объекта <xref:System.Windows.Media.MediaTimeline> в объекте <xref:System.Windows.Media.Animation.Storyboard>.  
  
## Пример  
 При использовании объекта <xref:System.Windows.Media.MediaTimeline> в <xref:System.Windows.Media.Animation.Storyboard> для управления синхронизацией <xref:System.Windows.Controls.MediaElement> функциональные возможности идентичны функциям других объектов <xref:System.Windows.Media.Animation.Timeline>, таких как анимация.  Например, объект <xref:System.Windows.Media.MediaTimeline> использует свойства <xref:System.Windows.Media.Animation.Timeline> как свойство <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>, чтобы указать время запуска <xref:System.Windows.Controls.MediaElement> \(начало воспроизведения мультимедиа\).  Он также использует свойство <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, чтобы указать время активности объекта <xref:System.Windows.Controls.MediaElement> \(длительность воспроизведения мультимедиа\).  Дополнительные сведения об использовании объектов <xref:System.Windows.Media.Animation.Timeline> с объектом <xref:System.Windows.Media.Animation.Storyboard> содержатся в разделе [Общие сведения о Storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
 В этом примере демонстрируется создание простой программы воспроизведения мультимедиа, которая использует <xref:System.Windows.Media.MediaTimeline> для управления воспроизведением.  Проигрыватель мультимедиа включает кнопки воспроизведения, паузы, возобновления и остановки.  Проигрыватель также имеет элемент управления <xref:System.Windows.Controls.Slider>, который действует как индикатор хода выполнения.  
  
 В следующем примере для проигрывателя создается [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].  
  
 [!code-xml[MediaGallery_snip#MediaTimelineExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml#mediatimelineexamplewholepage)]  
  
 В следующем примере создается функциональная возможность для индикатора хода выполнения.  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaTimelineExample.xaml.cs#codebehindmediatimelineexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml.vb#codebehindmediatimelineexamplewholepage)]  
  
## См. также  
 <xref:System.Windows.Controls.MediaElement>   
 <xref:System.Windows.Media.MediaTimeline>   
 <xref:System.Windows.Media.Animation.Storyboard>   
 [Управление элементом MediaElement \(воспроизведение, пауза, остановка, громкость и скорость\)](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md)   
 [Общие сведения о Storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)   
 [Общие сведения об анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/graphics-multimedia/audio-and-video-how-to-topics.md)   
 [Графика и мультимедиа](../../../../docs/framework/wpf/graphics-multimedia/index.md)