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
# <a name="how-to-control-a-mediaelement-by-using-a-storyboard"></a><span data-ttu-id="2c007-102">Практическое руководство. Управление элементом "MediaElement" с помощью объекта "Storyboard"</span><span class="sxs-lookup"><span data-stu-id="2c007-102">How to: Control a MediaElement by Using a Storyboard</span></span>
<span data-ttu-id="2c007-103">В этом примере показано, как управлять <xref:System.Windows.Controls.MediaElement> с помощью <xref:System.Windows.Media.MediaTimeline> в <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="2c007-103">This example shows how to control a <xref:System.Windows.Controls.MediaElement> by using a <xref:System.Windows.Media.MediaTimeline> in a <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c007-104">Пример</span><span class="sxs-lookup"><span data-stu-id="2c007-104">Example</span></span>  
 <span data-ttu-id="2c007-105">При использовании <xref:System.Windows.Media.MediaTimeline> в <xref:System.Windows.Media.Animation.Storyboard> для управления временем <xref:System.Windows.Controls.MediaElement>, функциональные возможности идентичны функциям других <xref:System.Windows.Media.Animation.Timeline> объектов, таких как анимации.</span><span class="sxs-lookup"><span data-stu-id="2c007-105">When you use a <xref:System.Windows.Media.MediaTimeline> in a <xref:System.Windows.Media.Animation.Storyboard> to control the timing of a <xref:System.Windows.Controls.MediaElement>, the functionality is identical to the functionality of other <xref:System.Windows.Media.Animation.Timeline> objects, such as animations.</span></span> <span data-ttu-id="2c007-106">Например <xref:System.Windows.Media.MediaTimeline> использует <xref:System.Windows.Media.Animation.Timeline> такие свойства, как <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> свойство, чтобы указать время запуска <xref:System.Windows.Controls.MediaElement> (Начало воспроизведения мультимедиа).</span><span class="sxs-lookup"><span data-stu-id="2c007-106">For example, a <xref:System.Windows.Media.MediaTimeline> uses <xref:System.Windows.Media.Animation.Timeline> properties like the <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> property to specify when to start a <xref:System.Windows.Controls.MediaElement> (start media playback).</span></span> <span data-ttu-id="2c007-107">Она также использует <xref:System.Windows.Media.Animation.Timeline.Duration%2A> свойство, чтобы указать длительность <xref:System.Windows.Controls.MediaElement> активна (длительность воспроизведения мультимедиа).</span><span class="sxs-lookup"><span data-stu-id="2c007-107">It also uses the <xref:System.Windows.Media.Animation.Timeline.Duration%2A> property to specify how long the <xref:System.Windows.Controls.MediaElement> is active (duration of media playback).</span></span> <span data-ttu-id="2c007-108">Дополнительные сведения об использовании <xref:System.Windows.Media.Animation.Timeline> объекты с <xref:System.Windows.Media.Animation.Storyboard>, в разделе [Общие](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2c007-108">For more information about using <xref:System.Windows.Media.Animation.Timeline> objects with a <xref:System.Windows.Media.Animation.Storyboard>, see [Storyboards Overview](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).</span></span>  
  
 <span data-ttu-id="2c007-109">В этом примере показано, как создать простой проигрыватель, который использует <xref:System.Windows.Media.MediaTimeline> для управления воспроизведением.</span><span class="sxs-lookup"><span data-stu-id="2c007-109">This example shows how to create a simple media player that uses a <xref:System.Windows.Media.MediaTimeline> to control playback.</span></span> <span data-ttu-id="2c007-110">Проигрыватель мультимедиа включает воспроизведения, приостановки, возобновления и остановки кнопок.</span><span class="sxs-lookup"><span data-stu-id="2c007-110">The media player includes play, pause, resume, and stop buttons.</span></span> <span data-ttu-id="2c007-111">Проигрыватель также имеет <xref:System.Windows.Controls.Slider> элемента управления, который выступает в качестве индикатора хода выполнения.</span><span class="sxs-lookup"><span data-stu-id="2c007-111">The player also has a <xref:System.Windows.Controls.Slider> control that acts as a progress bar.</span></span>  
  
 <span data-ttu-id="2c007-112">В следующем примере создается [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] для проигрывателя.</span><span class="sxs-lookup"><span data-stu-id="2c007-112">The following example creates the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] for the media player.</span></span>  
  
 [!code-xaml[MediaGallery_snip#MediaTimelineExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml#mediatimelineexamplewholepage)]  
  
 <span data-ttu-id="2c007-113">В следующем примере создается Данная функциональная возможность для индикатора хода выполнения.</span><span class="sxs-lookup"><span data-stu-id="2c007-113">The following example creates the functionality for the progress bar.</span></span>  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaTimelineExample.xaml.cs#codebehindmediatimelineexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml.vb#codebehindmediatimelineexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="2c007-114">См. также</span><span class="sxs-lookup"><span data-stu-id="2c007-114">See Also</span></span>  
 <xref:System.Windows.Controls.MediaElement>  
 <xref:System.Windows.Media.MediaTimeline>  
 <xref:System.Windows.Media.Animation.Storyboard>  
 [<span data-ttu-id="2c007-115">Управление элементом MediaElement (воспроизведение, пауза, остановка, громкость и скорость)</span><span class="sxs-lookup"><span data-stu-id="2c007-115">Control a MediaElement (Play, Pause, Stop, Volume, and Speed)</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md)  
 [<span data-ttu-id="2c007-116">Общие сведения о раскадровке</span><span class="sxs-lookup"><span data-stu-id="2c007-116">Storyboards Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)  
 [<span data-ttu-id="2c007-117">Общие сведения об анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="2c007-117">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="2c007-118">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="2c007-118">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="2c007-119">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="2c007-119">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/audio-and-video-how-to-topics.md)  
 [<span data-ttu-id="2c007-120">Графика и мультимедиа</span><span class="sxs-lookup"><span data-stu-id="2c007-120">Graphics and Multimedia</span></span>](../../../../docs/framework/wpf/graphics-multimedia/index.md)
