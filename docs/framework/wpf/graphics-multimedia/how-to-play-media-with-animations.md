---
title: "Практическое руководство. Воспроизведение мультимедиа с анимацией"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- multimedia [WPF], playback with animations
- playback of media [WPF], with animations
- animation [WPF], media playback with
- media [WPF], playback with animations
ms.assetid: 8982b7b7-1c6c-4b24-8801-b328862975f5
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 44ebb89c25fc37292f82533c929aae44854db5c9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-play-media-with-animations"></a>Практическое руководство. Воспроизведение мультимедиа с анимацией
В этом примере показано, как воспроизведение мультимедиа и анимации в то же время с помощью <xref:System.Windows.Media.MediaTimeline> и <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> классы в одном <xref:System.Windows.Media.Animation.Storyboard>.  
  
## <a name="example"></a>Пример  
 Можно использовать один или несколько <xref:System.Windows.Media.MediaTimeline> объекты в <xref:System.Windows.Media.Animation.Storyboard> вместе с другими <xref:System.Windows.Media.Animation.Timeline> объектов, таких как анимации.  
  
 В следующем примере задается <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A> свойство <xref:System.Windows.Media.Animation.Storyboard> значение `Slip`, которое указывает, что анимация не доходит до проведения мультимедиа (видео в этом примере). Эта возможность может потребоваться, если воспроизведение мультимедиа задерживается из-за времени загрузки.  
  
 [!code-xaml[MediaGallery_snippet#MediaTimelinePlusAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snippet/CSharp/MediaTimelinePlusAnimationExample.xaml#mediatimelineplusanimationexamplewholepage)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.MediaTimeline>  
 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>  
 <xref:System.Windows.Media.Animation.Storyboard>  
 <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A>  
 [Разделы практического руководства](../../../../docs/framework/wpf/graphics-multimedia/audio-and-video-how-to-topics.md)  
 [Общие сведения о раскадровке](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)  
 [Общие сведения об анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Графика и мультимедиа](../../../../docs/framework/wpf/graphics-multimedia/index.md)
