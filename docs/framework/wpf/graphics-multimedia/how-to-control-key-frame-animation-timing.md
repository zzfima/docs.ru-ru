---
title: Практическое руководство. Распределение времени для анимации с ключевыми кадрами
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], timing
- timing key-frame animation
ms.assetid: b059216f-7d4b-4ca8-a019-bc287ee7bf16
ms.openlocfilehash: 8cfd2be0bbc526ed92a5fb1b558a5a41dc9c3113
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344738"
---
# <a name="how-to-control-key-frame-animation-timing"></a><span data-ttu-id="34b2c-102">Практическое руководство. Распределение времени для анимации с ключевыми кадрами</span><span class="sxs-lookup"><span data-stu-id="34b2c-102">How to: Control Key-Frame Animation Timing</span></span>

<span data-ttu-id="34b2c-103">В этом примере показано, как управлять временем ключевых кадров в анимации с ключевым и образом.</span><span class="sxs-lookup"><span data-stu-id="34b2c-103">This example shows how to control the timing of key frames within a key-frame animation.</span></span> <span data-ttu-id="34b2c-104">Как и другие анимации, анимация ключей-кадров имеет свойство. <xref:System.Windows.Media.Animation.Timeline.Duration%2A></span><span class="sxs-lookup"><span data-stu-id="34b2c-104">Like other animations, key-frame animations have a <xref:System.Windows.Media.Animation.Timeline.Duration%2A> property.</span></span> <span data-ttu-id="34b2c-105">Помимо указания продолжительности анимации, необходимо указать, какая часть этой продолжительности отведена каждому из ключевых кадров.</span><span class="sxs-lookup"><span data-stu-id="34b2c-105">In addition to specifying the duration of an animation, you need to specify what part of that duration is allotted to each of its key frames.</span></span> <span data-ttu-id="34b2c-106">Чтобы выделить время, вы <xref:System.Windows.Media.Animation.KeyTime> указываете для каждого ключевого кадра в анимации.</span><span class="sxs-lookup"><span data-stu-id="34b2c-106">To allot the time, you specify a <xref:System.Windows.Media.Animation.KeyTime> for each key frame in the animation.</span></span>

<span data-ttu-id="34b2c-107">Для <xref:System.Windows.Media.Animation.KeyTime> каждого ключевого кадра указывается, когда заканчивается ключ кадра (в нем не указывается продолжительность времени воспроизведения ключевого кадра).</span><span class="sxs-lookup"><span data-stu-id="34b2c-107">The <xref:System.Windows.Media.Animation.KeyTime> for each key frame specifies when a key frame ends (it does not specify the length of time a key frame plays).</span></span> <span data-ttu-id="34b2c-108">Вы можете <xref:System.Windows.Media.Animation.KeyTime> указать <xref:System.TimeSpan> значение в процентах, <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> или <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> как или специальное значение.</span><span class="sxs-lookup"><span data-stu-id="34b2c-108">You can specify a <xref:System.Windows.Media.Animation.KeyTime> as a <xref:System.TimeSpan> value, as a percentage, or as the <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> or <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> special value.</span></span>

## <a name="example"></a><span data-ttu-id="34b2c-109">Пример</span><span class="sxs-lookup"><span data-stu-id="34b2c-109">Example</span></span>

<span data-ttu-id="34b2c-110">В следующем примере <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> используется для анимировать прямоугольник по экрану.</span><span class="sxs-lookup"><span data-stu-id="34b2c-110">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> to animate a rectangle across the screen.</span></span> <span data-ttu-id="34b2c-111">Ключевые времена ключевых кадров <xref:System.TimeSpan> устанавливаются значениями.</span><span class="sxs-lookup"><span data-stu-id="34b2c-111">The key frames' key times are set with <xref:System.TimeSpan> values.</span></span>

[!code-csharp[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimestimespanexample)]
[!code-vb[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimestimespanexample)]
[!code-xaml[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimestimespanexample)]

<span data-ttu-id="34b2c-112">Следующая иллюстрация показывает, когда значение каждого ключевого кадра достигается.</span><span class="sxs-lookup"><span data-stu-id="34b2c-112">The following illustration shows when the value of each key frame is reached.</span></span>

<span data-ttu-id="34b2c-113">![Ключевые значения достигаются за 3, 4 и 10 секунд](./media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm_keyframe_keytime1_timespan")</span><span class="sxs-lookup"><span data-stu-id="34b2c-113">![Key values are reached at 3, 4, and 10 seconds](./media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm_keyframe_keytime1_timespan")</span></span>

<span data-ttu-id="34b2c-114">Следующий пример показывает идентичную анимацию, за исключением того, что ключевые времена ключевых кадров установлены с значениями в процентах.</span><span class="sxs-lookup"><span data-stu-id="34b2c-114">The next example shows an animation that is identical, except that the key frames' key times are set with percentage values.</span></span>

[!code-csharp[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespercentageexample)]
[!code-vb[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespercentageexample)]
[!code-xaml[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespercentageexample)]

<span data-ttu-id="34b2c-115">Следующая иллюстрация показывает, когда значение каждого ключевого кадра достигается.</span><span class="sxs-lookup"><span data-stu-id="34b2c-115">The following illustration shows when the value of each key frame is reached.</span></span>

<span data-ttu-id="34b2c-116">![Ключевые значения достигаются за 3, 4 и 10 секунд](./media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm_keyframe_keytime2_percentage")</span><span class="sxs-lookup"><span data-stu-id="34b2c-116">![Key values are reached at 3, 4, and 10 seconds](./media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm_keyframe_keytime2_percentage")</span></span>

<span data-ttu-id="34b2c-117">В следующем <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> примере используются ключевые значения времени.</span><span class="sxs-lookup"><span data-stu-id="34b2c-117">The next example uses <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> key time values.</span></span>

[!code-csharp[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimesuniformexample)]
[!code-vb[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimesuniformexample)]
[!code-xaml[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimesuniformexample)]

<span data-ttu-id="34b2c-118">Следующая иллюстрация показывает, когда значение каждого ключевого кадра достигается.</span><span class="sxs-lookup"><span data-stu-id="34b2c-118">The following illustration shows when the value of each key frame is reached.</span></span>

<span data-ttu-id="34b2c-119">![Ключевые значение достигаются за 3,3; 6,6, и 9,9 секунды](./media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm_keyframe_keytime3_uniform")</span><span class="sxs-lookup"><span data-stu-id="34b2c-119">![Key values are reached at 3.3,6.6, and 9.9 seconds](./media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm_keyframe_keytime3_uniform")</span></span>

<span data-ttu-id="34b2c-120">В заключительном <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> примере используются ключевые значения времени.</span><span class="sxs-lookup"><span data-stu-id="34b2c-120">The final example uses <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> key time values.</span></span>

[!code-csharp[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespacedexample)]
[!code-vb[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespacedexample)]
[!code-xaml[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespacedexample)]

<span data-ttu-id="34b2c-121">Следующая иллюстрация показывает, когда значение каждого ключевого кадра достигается.</span><span class="sxs-lookup"><span data-stu-id="34b2c-121">The following illustration shows when the value of each key frame is reached.</span></span>

<span data-ttu-id="34b2c-122">![Ключевые значения достигаются за 0, 5 и 10 секунд](./media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm_keyframe_keytime4_paced")</span><span class="sxs-lookup"><span data-stu-id="34b2c-122">![Key values are reached at 0, 5, and 10 seconds](./media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm_keyframe_keytime4_paced")</span></span>

<span data-ttu-id="34b2c-123">Для простоты в кодовых версиях этого примера используются локальные анимации, а не раскадровки, поскольку к одному свойству применяется только одна анимация, но вместо этого примеры могут быть изменены для использования раскадровок.</span><span class="sxs-lookup"><span data-stu-id="34b2c-123">For simplicity, the code versions of this example use local animations, not storyboards, because only a single animation is being applied to a single property, but the examples may be modified to use storyboards instead.</span></span> <span data-ttu-id="34b2c-124">Например, с указанием того, как [Animate a Property by Using a Storyboard](how-to-animate-a-property-by-using-a-storyboard.md)объявить раскадровку в коде, см.</span><span class="sxs-lookup"><span data-stu-id="34b2c-124">For an example showing how to declare a storyboard in code, see [Animate a Property by Using a Storyboard](how-to-animate-a-property-by-using-a-storyboard.md).</span></span>

<span data-ttu-id="34b2c-125">Описание полного примера см. в разделе [Пример анимации по ключевым кадрам](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span><span class="sxs-lookup"><span data-stu-id="34b2c-125">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span> <span data-ttu-id="34b2c-126">Для получения дополнительной информации о ключевых анимациях кадра [см.](key-frame-animations-overview.md)</span><span class="sxs-lookup"><span data-stu-id="34b2c-126">For more information about key frame animations, see the [Key-Frame Animations Overview](key-frame-animations-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="34b2c-127">См. также</span><span class="sxs-lookup"><span data-stu-id="34b2c-127">See also</span></span>

- [<span data-ttu-id="34b2c-128">Общие сведения об анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="34b2c-128">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="34b2c-129">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="34b2c-129">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="34b2c-130">Практические руководства</span><span class="sxs-lookup"><span data-stu-id="34b2c-130">How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
