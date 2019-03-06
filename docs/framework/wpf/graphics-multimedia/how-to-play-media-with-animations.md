---
title: Практическое руководство. Воспроизведение мультимедиа с анимацией
ms.date: 03/30/2017
helpviewer_keywords:
- multimedia [WPF], playback with animations
- playback of media [WPF], with animations
- animation [WPF], media playback with
- media [WPF], playback with animations
ms.assetid: 8982b7b7-1c6c-4b24-8801-b328862975f5
ms.openlocfilehash: 0dc39d08ef17a628675018c17602623f2efd0173
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57372910"
---
# <a name="how-to-play-media-with-animations"></a><span data-ttu-id="614a7-102">Практическое руководство. Воспроизведение мультимедиа с анимацией</span><span class="sxs-lookup"><span data-stu-id="614a7-102">How to: Play Media with Animations</span></span>
<span data-ttu-id="614a7-103">В этом примере показано, как воспроизвести мультимедиа и анимацию одновременно с помощью <xref:System.Windows.Media.MediaTimeline> и <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> классы в одном <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="614a7-103">This example shows how to play media and animations at the same time by using the <xref:System.Windows.Media.MediaTimeline> and <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> classes in the same <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="614a7-104">Пример</span><span class="sxs-lookup"><span data-stu-id="614a7-104">Example</span></span>  
 <span data-ttu-id="614a7-105">Можно использовать один или несколько <xref:System.Windows.Media.MediaTimeline> объекты в <xref:System.Windows.Media.Animation.Storyboard> другим <xref:System.Windows.Media.Animation.Timeline> объекты, такие как анимации.</span><span class="sxs-lookup"><span data-stu-id="614a7-105">You can use one or more <xref:System.Windows.Media.MediaTimeline> objects in a <xref:System.Windows.Media.Animation.Storyboard> together with other <xref:System.Windows.Media.Animation.Timeline> objects, such as animations.</span></span>  
  
 <span data-ttu-id="614a7-106">В следующем примере задается <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A> свойство <xref:System.Windows.Media.Animation.Storyboard> значение `Slip`, которое указывает, что анимация не выполняется до выполнения мультимедиа (видео в этом примере).</span><span class="sxs-lookup"><span data-stu-id="614a7-106">The following example sets the <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A> property of the <xref:System.Windows.Media.Animation.Storyboard> to a value of `Slip`, which specifies that the animation does not progress until the media (video in this example) progresses.</span></span> <span data-ttu-id="614a7-107">Эта возможность может потребоваться, если воспроизведение мультимедиа задерживается из-за времени загрузки.</span><span class="sxs-lookup"><span data-stu-id="614a7-107">This functionality might be needed if media playback is delayed because of loading time.</span></span>  
  
 [!code-xaml[MediaGallery_snippet#MediaTimelinePlusAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snippet/CSharp/MediaTimelinePlusAnimationExample.xaml#mediatimelineplusanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="614a7-108">См. также</span><span class="sxs-lookup"><span data-stu-id="614a7-108">See also</span></span>
- <xref:System.Windows.Media.MediaTimeline>
- <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>
- <xref:System.Windows.Media.Animation.Storyboard>
- <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A>
- [<span data-ttu-id="614a7-109">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="614a7-109">How-to Topics</span></span>](audio-and-video-how-to-topics.md)
- [<span data-ttu-id="614a7-110">Общие сведения о раскадровке</span><span class="sxs-lookup"><span data-stu-id="614a7-110">Storyboards Overview</span></span>](storyboards-overview.md)
- [<span data-ttu-id="614a7-111">Общие сведения об анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="614a7-111">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="614a7-112">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="614a7-112">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="614a7-113">Графика и мультимедиа</span><span class="sxs-lookup"><span data-stu-id="614a7-113">Graphics and Multimedia</span></span>](index.md)
