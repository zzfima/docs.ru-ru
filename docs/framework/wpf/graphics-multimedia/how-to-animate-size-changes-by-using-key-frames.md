---
title: Практическое руководство. Анимация изменений размера с использованием ключевых кадров
ms.date: 03/30/2017
helpviewer_keywords:
- key frames [WPF], animating size changes with
- animation [WPF], size changes with key frames
- size changes [WPF], animating with key frames
ms.assetid: 86bd2950-d4c9-4ec4-aa8d-7dc3ccadded4
ms.openlocfilehash: 42cecfc9df4304be4033ea39edc0517016de4a92
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344655"
---
# <a name="how-to-animate-size-changes-by-using-key-frames"></a><span data-ttu-id="591e2-102">Практическое руководство. Анимация изменений размера с использованием ключевых кадров</span><span class="sxs-lookup"><span data-stu-id="591e2-102">How to: Animate Size Changes by Using Key Frames</span></span>
<span data-ttu-id="591e2-103">В этом примере показано, как можно анимировать изменения размера с использованием ключевых кадров.</span><span class="sxs-lookup"><span data-stu-id="591e2-103">This example shows how to animate size changes by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="591e2-104">Пример</span><span class="sxs-lookup"><span data-stu-id="591e2-104">Example</span></span>  
 <span data-ttu-id="591e2-105">В следующем примере <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames> используется класс <xref:System.Windows.Media.ArcSegment.Size%2A> для анимировать свойство <xref:System.Windows.Media.ArcSegment>.</span><span class="sxs-lookup"><span data-stu-id="591e2-105">The following example uses the <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.ArcSegment.Size%2A> property of an <xref:System.Windows.Media.ArcSegment>.</span></span> <span data-ttu-id="591e2-106">Эта анимация использует три ключевых кадра следующим образом:</span><span class="sxs-lookup"><span data-stu-id="591e2-106">This animation uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="591e2-107">В первой половине второй анимации, использует <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> экземпляр класса постепенно увеличивать размер дуги. Линейные ключевые <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> кадры, такие как создание плавного линейного перехода между значениями.</span><span class="sxs-lookup"><span data-stu-id="591e2-107">During the first half second of the animation, uses an instance of the <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> class to gradually increase the size of the arc. Linear key frames like <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> create a smooth linear transition between values.</span></span>  
  
2. <span data-ttu-id="591e2-108">В конце следующей половины секунды, <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> использует экземпляр класса, чтобы внезапно увеличить размер дуги. Дискретные ключевые <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> кадры, такие как создают внезапные скачки между значениями, то есть изменения размера происходят внезапно и не являются тонкими.</span><span class="sxs-lookup"><span data-stu-id="591e2-108">At the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> class to suddenly increase the size of the arc. Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> create sudden jumps between values, that is, the size changes occur suddenly and are not subtle.</span></span>  
  
3. <span data-ttu-id="591e2-109">В течение последних двух секунд, <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> использует экземпляр класса, чтобы увеличить размер дуги. Сплайс-ключевые кадры, такие как <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> создание переменного <xref:System.Windows.Media.Animation.SplineSizeKeyFrame.KeySpline%2A> перехода между значениями в зависимости от значений свойства.</span><span class="sxs-lookup"><span data-stu-id="591e2-109">Over the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> class to increase the size of the arc. Spline key frames like <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineSizeKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="591e2-110">В этом примере размер дуги сначала увеличивается медленно, а ближе к концу временного сегмента — экспоненциально.</span><span class="sxs-lookup"><span data-stu-id="591e2-110">In this example, the size of the arc increases slowly at first and then increases exponentially toward the end of the time segment.</span></span>  
  
 [!code-xaml[keyframes_snip#SizeAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/SizeAnimationUsingKeyFramesExample.xaml#sizeanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="591e2-111">Описание полного примера см. в разделе [Пример анимации по ключевым кадрам](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span><span class="sxs-lookup"><span data-stu-id="591e2-111">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="591e2-112">См. также</span><span class="sxs-lookup"><span data-stu-id="591e2-112">See also</span></span>

- <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>
- <xref:System.Windows.Media.ArcSegment.Size%2A>
- <xref:System.Windows.Media.ArcSegment>
- <xref:System.Windows.Media.Animation.LinearSizeKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame>
- <xref:System.Windows.Media.Animation.SplineSizeKeyFrame>
- [<span data-ttu-id="591e2-113">Общие сведения об анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="591e2-113">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="591e2-114">Практические руководства, посвященные анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="591e2-114">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
