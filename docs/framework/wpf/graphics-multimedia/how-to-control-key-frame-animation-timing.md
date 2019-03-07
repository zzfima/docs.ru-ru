---
title: Практическое руководство. Распределение времени для анимации с полными кадрами
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], timing
- timing key-frame animation
ms.assetid: b059216f-7d4b-4ca8-a019-bc287ee7bf16
ms.openlocfilehash: d0ea56b24f8fffeb688d297a675681bce3fdc4e0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489882"
---
# <a name="how-to-control-key-frame-animation-timing"></a><span data-ttu-id="f81db-102">Практическое руководство. Распределение времени для анимации с полными кадрами</span><span class="sxs-lookup"><span data-stu-id="f81db-102">How to: Control Key-Frame Animation Timing</span></span>

<span data-ttu-id="f81db-103">В этом примере показано, как управлять временем ключевые кадры в анимации по полным кадрам.</span><span class="sxs-lookup"><span data-stu-id="f81db-103">This example shows how to control the timing of key frames within a key-frame animation.</span></span> <span data-ttu-id="f81db-104">Как и другие виды анимации, имеют покадровой анимации <xref:System.Windows.Media.Animation.Timeline.Duration%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="f81db-104">Like other animations, key-frame animations have a <xref:System.Windows.Media.Animation.Timeline.Duration%2A> property.</span></span> <span data-ttu-id="f81db-105">Помимо задания длительности анимации, необходимо указать, какая часть, в течение выделенного для каждого из его ключевых кадров.</span><span class="sxs-lookup"><span data-stu-id="f81db-105">In addition to specifying the duration of an animation, you need to specify what part of that duration is allotted to each of its key frames.</span></span> <span data-ttu-id="f81db-106">Чтобы выделить время, необходимо указать <xref:System.Windows.Media.Animation.KeyTime> для каждого ключевого кадра анимации.</span><span class="sxs-lookup"><span data-stu-id="f81db-106">To allot the time, you specify a <xref:System.Windows.Media.Animation.KeyTime> for each key frame in the animation.</span></span>

<span data-ttu-id="f81db-107"><xref:System.Windows.Media.Animation.KeyTime> Для каждого ключевого кадра определяет, когда полного кадра (не указывает продолжительность времени ключевого кадра).</span><span class="sxs-lookup"><span data-stu-id="f81db-107">The <xref:System.Windows.Media.Animation.KeyTime> for each key frame specifies when a key frame ends (it does not specify the length of time a key frame plays).</span></span> <span data-ttu-id="f81db-108">Можно указать <xref:System.Windows.Media.Animation.KeyTime> как <xref:System.TimeSpan> значение, в процентах, а также <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> или <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> специальное значение.</span><span class="sxs-lookup"><span data-stu-id="f81db-108">You can specify a <xref:System.Windows.Media.Animation.KeyTime> as a <xref:System.TimeSpan> value, as a percentage, or as the <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> or <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> special value.</span></span>

## <a name="example"></a><span data-ttu-id="f81db-109">Пример</span><span class="sxs-lookup"><span data-stu-id="f81db-109">Example</span></span>

<span data-ttu-id="f81db-110">В следующем примере используется <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> для анимации прямоугольника по экрану.</span><span class="sxs-lookup"><span data-stu-id="f81db-110">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> to animate a rectangle across the screen.</span></span> <span data-ttu-id="f81db-111">Ключевые кадры время задаются с помощью <xref:System.TimeSpan> значения.</span><span class="sxs-lookup"><span data-stu-id="f81db-111">The key frames' key times are set with <xref:System.TimeSpan> values.</span></span>

[!code-csharp[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimestimespanexample)]
[!code-vb[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimestimespanexample)]
[!code-xaml[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimestimespanexample)]

<span data-ttu-id="f81db-112">На следующем рисунке показано, когда будет достигнуто значение каждого ключевого кадра.</span><span class="sxs-lookup"><span data-stu-id="f81db-112">The following illustration shows when the value of each key frame is reached.</span></span>

<span data-ttu-id="f81db-113">![Ключевые значения достигаются за 3, 4 и 10 секунд](./media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm_keyframe_keytime1_timespan")</span><span class="sxs-lookup"><span data-stu-id="f81db-113">![Key values are reached at 3, 4, and 10 seconds](./media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm_keyframe_keytime1_timespan")</span></span>

<span data-ttu-id="f81db-114">В следующем примере показано анимацию, которая идентична, за исключением того, что время ключевые кадры задаются с помощью значения в процентах.</span><span class="sxs-lookup"><span data-stu-id="f81db-114">The next example shows an animation that is identical, except that the key frames' key times are set with percentage values.</span></span>

[!code-csharp[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespercentageexample)]
[!code-vb[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespercentageexample)]
[!code-xaml[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespercentageexample)]

<span data-ttu-id="f81db-115">На следующем рисунке показано, когда будет достигнуто значение каждого ключевого кадра.</span><span class="sxs-lookup"><span data-stu-id="f81db-115">The following illustration shows when the value of each key frame is reached.</span></span>

<span data-ttu-id="f81db-116">![Ключевые значения достигаются за 3, 4 и 10 секунд](./media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm_keyframe_keytime2_percentage")</span><span class="sxs-lookup"><span data-stu-id="f81db-116">![Key values are reached at 3, 4, and 10 seconds](./media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm_keyframe_keytime2_percentage")</span></span>

<span data-ttu-id="f81db-117">В следующем примере используется <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> ключевых значений времени.</span><span class="sxs-lookup"><span data-stu-id="f81db-117">The next example uses <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> key time values.</span></span>

[!code-csharp[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimesuniformexample)]
[!code-vb[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimesuniformexample)]
[!code-xaml[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimesuniformexample)]

<span data-ttu-id="f81db-118">На следующем рисунке показано, когда будет достигнуто значение каждого ключевого кадра.</span><span class="sxs-lookup"><span data-stu-id="f81db-118">The following illustration shows when the value of each key frame is reached.</span></span>

<span data-ttu-id="f81db-119">![Ключевые значения достигаются за 3,3; 6,6 и 9,9 секунды](./media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm_keyframe_keytime3_uniform")</span><span class="sxs-lookup"><span data-stu-id="f81db-119">![Key values are reached at 3.3,6.6, and 9.9 seconds](./media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm_keyframe_keytime3_uniform")</span></span>

<span data-ttu-id="f81db-120">В последнем примере используются <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> ключевых значений времени.</span><span class="sxs-lookup"><span data-stu-id="f81db-120">The final example uses <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> key time values.</span></span>

[!code-csharp[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespacedexample)]
[!code-vb[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespacedexample)]
[!code-xaml[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespacedexample)]

<span data-ttu-id="f81db-121">На следующем рисунке показано, когда будет достигнуто значение каждого ключевого кадра.</span><span class="sxs-lookup"><span data-stu-id="f81db-121">The following illustration shows when the value of each key frame is reached.</span></span>

<span data-ttu-id="f81db-122">![Ключевые значения достигаются за 0, 5 и 10 секунд](./media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm_keyframe_keytime4_paced")</span><span class="sxs-lookup"><span data-stu-id="f81db-122">![Key values are reached at 0, 5, and 10 seconds](./media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm_keyframe_keytime4_paced")</span></span>

<span data-ttu-id="f81db-123">Для простоты версии кода этого примера используются локальные анимации, не раскадровки, поскольку только одна анимация применяется к одному свойству, но примеры, которые могут быть изменены а.</span><span class="sxs-lookup"><span data-stu-id="f81db-123">For simplicity, the code versions of this example use local animations, not storyboards, because only a single animation is being applied to a single property, but the examples may be modified to use storyboards instead.</span></span> <span data-ttu-id="f81db-124">Пример, показывающий, как объявить раскадровки в коде, см. в разделе [анимация свойства с помощью раскадровки](how-to-animate-a-property-by-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="f81db-124">For an example showing how to declare a storyboard in code, see [Animate a Property by Using a Storyboard](how-to-animate-a-property-by-using-a-storyboard.md).</span></span>

<span data-ttu-id="f81db-125">Описание полного примера см. в разделе [Пример анимации по ключевым кадрам](https://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="f81db-125">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span> <span data-ttu-id="f81db-126">Дополнительные сведения об анимации см. в разделе [сведения об анимации по ключевым кадрам](key-frame-animations-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f81db-126">For more information about key frame animations, see the [Key-Frame Animations Overview](key-frame-animations-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f81db-127">См. также</span><span class="sxs-lookup"><span data-stu-id="f81db-127">See also</span></span>

- [<span data-ttu-id="f81db-128">Общие сведения об анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="f81db-128">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="f81db-129">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="f81db-129">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="f81db-130">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="f81db-130">How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
