---
title: Практическое руководство. Анимация изменений размера с использованием ключевых кадров
ms.date: 03/30/2017
helpviewer_keywords:
- key frames [WPF], animating size changes with
- animation [WPF], size changes with key frames
- size changes [WPF], animating with key frames
ms.assetid: 86bd2950-d4c9-4ec4-aa8d-7dc3ccadded4
ms.openlocfilehash: 69845d1d75f81042bbeb20ee6b1015f5c2f53b81
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2018
ms.locfileid: "43479936"
---
# <a name="how-to-animate-size-changes-by-using-key-frames"></a><span data-ttu-id="99362-102">Практическое руководство. Анимация изменений размера с использованием ключевых кадров</span><span class="sxs-lookup"><span data-stu-id="99362-102">How to: Animate Size Changes by Using Key Frames</span></span>
<span data-ttu-id="99362-103">В этом примере показано, как можно анимировать изменения размера с использованием ключевых кадров.</span><span class="sxs-lookup"><span data-stu-id="99362-103">This example shows how to animate size changes by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="99362-104">Пример</span><span class="sxs-lookup"><span data-stu-id="99362-104">Example</span></span>  
 <span data-ttu-id="99362-105">В следующем примере используется <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames> класс для анимации <xref:System.Windows.Media.ArcSegment.Size%2A> свойство <xref:System.Windows.Media.ArcSegment>.</span><span class="sxs-lookup"><span data-stu-id="99362-105">The following example uses the <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.ArcSegment.Size%2A> property of an <xref:System.Windows.Media.ArcSegment>.</span></span> <span data-ttu-id="99362-106">Эта анимация использует три ключевых кадра следующим образом:</span><span class="sxs-lookup"><span data-stu-id="99362-106">This animation uses three key frames in the following manner:</span></span>  
  
1.  <span data-ttu-id="99362-107">В течение первой половины секунды анимации используется экземпляр <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> класс для постепенного увеличения размера дуги. Линейные ключевые кадры, например <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> создать плавный линейный переход между значениями.</span><span class="sxs-lookup"><span data-stu-id="99362-107">During the first half second of the animation, uses an instance of the <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> class to gradually increase the size of the arc. Linear key frames like <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> create a smooth linear transition between values.</span></span>  
  
2.  <span data-ttu-id="99362-108">В конце следующей половины секунды используется экземпляр <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> класс для резкого увеличения размера дуги. Дискретные ключевые кадры, например <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> , создают скачкообразные переходы между значениями, то есть, изменения размера происходят внезапно и не плавно.</span><span class="sxs-lookup"><span data-stu-id="99362-108">At the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> class to suddenly increase the size of the arc. Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> create sudden jumps between values, that is, the size changes occur suddenly and are not subtle.</span></span>  
  
3.  <span data-ttu-id="99362-109">За последних двух секунд используется экземпляр <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> класс для увеличения размера дуги. Ключевые кадры сплайна, например <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> , создают переменный переход между значениями в соответствии со значениями из <xref:System.Windows.Media.Animation.SplineSizeKeyFrame.KeySpline%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="99362-109">Over the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> class to increase the size of the arc. Spline key frames like <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineSizeKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="99362-110">В этом примере размер дуги сначала увеличивается медленно, а ближе к концу временного сегмента — экспоненциально.</span><span class="sxs-lookup"><span data-stu-id="99362-110">In this example, the size of the arc increases slowly at first and then increases exponentially toward the end of the time segment.</span></span>  
  
 [!code-xaml[keyframes_snip#SizeAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/SizeAnimationUsingKeyFramesExample.xaml#sizeanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="99362-111">Описание полного примера см. в разделе [Пример анимации по ключевым кадрам](https://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="99362-111">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99362-112">См. также</span><span class="sxs-lookup"><span data-stu-id="99362-112">See Also</span></span>  
 <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>  
 <xref:System.Windows.Media.ArcSegment.Size%2A>  
 <xref:System.Windows.Media.ArcSegment>  
 <xref:System.Windows.Media.Animation.LinearSizeKeyFrame>  
 <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame>  
 <xref:System.Windows.Media.Animation.SplineSizeKeyFrame>  
 [<span data-ttu-id="99362-113">Общие сведения об анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="99362-113">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="99362-114">Практические руководства, посвященные анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="99362-114">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
