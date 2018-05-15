---
title: Практическое руководство. Инициирование воспроизведение мультимедиа с помощью пользовательского события
ms.date: 03/30/2017
helpviewer_keywords:
- synchronizing media playback with events [WPF]
- playback of media [WPF], synchronizing with events
- media [WPF], synchronizing playback with events
- multimedia [WPF], synchronizing media playback with events
ms.assetid: c4dbe632-6e7f-4d7f-9df5-98737a758bc3
ms.openlocfilehash: faa82ee29e3501f484f150100f9069a5fe011312
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-trigger-media-playback-with-a-user-event"></a><span data-ttu-id="5f7b7-102">Практическое руководство. Инициирование воспроизведение мультимедиа с помощью пользовательского события</span><span class="sxs-lookup"><span data-stu-id="5f7b7-102">How to: Trigger Media Playback with a User Event</span></span>
<span data-ttu-id="5f7b7-103">В этом примере показано, как синхронизировать воспроизведение мультимедиа с событием.</span><span class="sxs-lookup"><span data-stu-id="5f7b7-103">This example shows how to synchronize media playback with an event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f7b7-104">Пример</span><span class="sxs-lookup"><span data-stu-id="5f7b7-104">Example</span></span>  
 <span data-ttu-id="5f7b7-105">В следующем примере используется <xref:System.Windows.Controls.MediaElement> управления и <xref:System.Windows.Media.MediaTimeline> класса для воспроизведения звука, которая возникает, когда пользователь нажимает кнопку <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="5f7b7-105">The following example uses the <xref:System.Windows.Controls.MediaElement> control and the <xref:System.Windows.Media.MediaTimeline> class to play a sound that occurs when the user clicks a <xref:System.Windows.Controls.Button>.</span></span>  
  
 [!code-xaml[MediaGallery_snippet#SoundFromUserEventExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snippet/CSharp/SoundFromUserEventExample.xaml#soundfromusereventexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="5f7b7-106">См. также</span><span class="sxs-lookup"><span data-stu-id="5f7b7-106">See Also</span></span>  
 <xref:System.Windows.Controls.MediaElement>  
 <xref:System.Windows.Media.MediaTimeline>  
 <xref:System.Windows.EventTrigger.RoutedEvent%2A>  
 <xref:System.Windows.Media.Animation.Storyboard>  
 [<span data-ttu-id="5f7b7-107">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="5f7b7-107">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/audio-and-video-how-to-topics.md)  
 [<span data-ttu-id="5f7b7-108">Графика и мультимедиа</span><span class="sxs-lookup"><span data-stu-id="5f7b7-108">Graphics and Multimedia</span></span>](../../../../docs/framework/wpf/graphics-multimedia/index.md)
