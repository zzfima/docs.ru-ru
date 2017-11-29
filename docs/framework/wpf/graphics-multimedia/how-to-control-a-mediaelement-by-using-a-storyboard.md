---
title: "Практическое руководство. Управление элементом \"MediaElement\" с помощью объекта \"Storyboard\""
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- multimedia [WPF], controlling playback of media with Storyboards
- controlling playback of media [WPF], with Storyboards
- Storyboards [WPF], controlling playback of media with
- media [WPF], controlling playback with Storyboards
- playback of media [WPF], controlling with Storyboards
ms.assetid: 6128ca77-b826-4e36-b968-6f237157c543
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2341d2814e5bd42c652865c76d115defcc5b15b2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-control-a-mediaelement-by-using-a-storyboard"></a>Практическое руководство. Управление элементом "MediaElement" с помощью объекта "Storyboard"
В этом примере показано, как управлять <xref:System.Windows.Controls.MediaElement> с помощью <xref:System.Windows.Media.MediaTimeline> в <xref:System.Windows.Media.Animation.Storyboard>.  
  
## <a name="example"></a>Пример  
 При использовании <xref:System.Windows.Media.MediaTimeline> в <xref:System.Windows.Media.Animation.Storyboard> для управления временем <xref:System.Windows.Controls.MediaElement>, функциональные возможности идентичны функциям других <xref:System.Windows.Media.Animation.Timeline> объектов, таких как анимации. Например <xref:System.Windows.Media.MediaTimeline> использует <xref:System.Windows.Media.Animation.Timeline> такие свойства, как <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> свойство, чтобы указать время запуска <xref:System.Windows.Controls.MediaElement> (Начало воспроизведения мультимедиа). Она также использует <xref:System.Windows.Media.Animation.Timeline.Duration%2A> свойство, чтобы указать длительность <xref:System.Windows.Controls.MediaElement> активна (длительность воспроизведения мультимедиа). Дополнительные сведения об использовании <xref:System.Windows.Media.Animation.Timeline> объекты с <xref:System.Windows.Media.Animation.Storyboard>, в разделе [Общие](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
 В этом примере показано, как создать простой проигрыватель, который использует <xref:System.Windows.Media.MediaTimeline> для управления воспроизведением. Проигрыватель мультимедиа включает воспроизведения, приостановки, возобновления и остановки кнопок. Проигрыватель также имеет <xref:System.Windows.Controls.Slider> элемента управления, который выступает в качестве индикатора хода выполнения.  
  
 В следующем примере создается [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] для проигрывателя.  
  
 [!code-xaml[MediaGallery_snip#MediaTimelineExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml#mediatimelineexamplewholepage)]  
  
 В следующем примере создается Данная функциональная возможность для индикатора хода выполнения.  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaTimelineExample.xaml.cs#codebehindmediatimelineexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml.vb#codebehindmediatimelineexamplewholepage)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Controls.MediaElement>  
 <xref:System.Windows.Media.MediaTimeline>  
 <xref:System.Windows.Media.Animation.Storyboard>  
 [Управление элементом MediaElement (воспроизведение, пауза, остановка, громкость и скорость)](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md)  
 [Общие сведения о раскадровке](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)  
 [Общие сведения об анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Разделы практического руководства](../../../../docs/framework/wpf/graphics-multimedia/audio-and-video-how-to-topics.md)  
 [Графика и мультимедиа](../../../../docs/framework/wpf/graphics-multimedia/index.md)
