---
title: Практическое руководство. Повторение анимации
ms.date: 03/30/2017
helpviewer_keywords:
- RepeatBehavior property of timelines [WPF]
- repeating animating [WPF]
- Timelines RepeatBehavior property [WPF]
- animation [WPF], repeating
ms.assetid: e6f3b068-eeeb-47fd-8d40-8848c31f1e1e
ms.openlocfilehash: 176fc9c31f85361a243cd9357d79608e0ff6a4cd
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43855300"
---
# <a name="how-to-repeat-an-animation"></a><span data-ttu-id="f388b-102">Практическое руководство. Повторение анимации</span><span class="sxs-lookup"><span data-stu-id="f388b-102">How to: Repeat an Animation</span></span>
<span data-ttu-id="f388b-103">В этом примере показано, как использовать <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> свойство <xref:System.Windows.Media.Animation.Timeline> чтобы контролировать поведение при повторе анимации.</span><span class="sxs-lookup"><span data-stu-id="f388b-103">This example shows how to use the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> in order to control the repeat behavior of an animation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f388b-104">Пример</span><span class="sxs-lookup"><span data-stu-id="f388b-104">Example</span></span>  
 <span data-ttu-id="f388b-105"><xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> Свойство <xref:System.Windows.Media.Animation.Timeline> определяет, сколько раз анимации повторе его простой длительности.</span><span class="sxs-lookup"><span data-stu-id="f388b-105">The <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> controls how many times an animation repeats its simple duration.</span></span> <span data-ttu-id="f388b-106">С помощью <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, можно указать, что <xref:System.Windows.Media.Animation.Timeline> повторяется для определенное число раз (итераций) или в течение указанного времени.</span><span class="sxs-lookup"><span data-stu-id="f388b-106">By using <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, you can specify that a <xref:System.Windows.Media.Animation.Timeline> repeats for a certain number of times (an iteration count) or for a specified time period.</span></span> <span data-ttu-id="f388b-107">В любом случае анимация пройдет такое столько запусков начала до конца, сколько необходимо для заполнения запрошенное количество или длительность.</span><span class="sxs-lookup"><span data-stu-id="f388b-107">In either case, the animation goes through as many beginning-to-end runs that it needs in order to fill the requested count or duration.</span></span>  
  
 <span data-ttu-id="f388b-108">По умолчанию временных шкал установлено число повторов, равным 1,0, это означает, воспроизведение происходит один раз и не повторяется.</span><span class="sxs-lookup"><span data-stu-id="f388b-108">By default, timelines have a repeat count of 1.0, which means they play one time and do not repeat.</span></span> <span data-ttu-id="f388b-109">Тем не менее если задать <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> свойство <xref:System.Windows.Media.Animation.Timeline> для <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, временная шкала повторяется бесконечно.</span><span class="sxs-lookup"><span data-stu-id="f388b-109">However, if you set the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> to <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, the timeline repeats indefinitely.</span></span>  
  
 <span data-ttu-id="f388b-110">В следующем примере показано, как использовать <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> свойства для управления повторением анимации.</span><span class="sxs-lookup"><span data-stu-id="f388b-110">The following example shows how to use the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property to control the repeat behavior of an animation.</span></span> <span data-ttu-id="f388b-111">В примере выполняется анимация <xref:System.Windows.FrameworkElement.Width%2A> свойство пяти прямоугольников, каждый с помощью другой тип поведения повтора.</span><span class="sxs-lookup"><span data-stu-id="f388b-111">The example animates the <xref:System.Windows.FrameworkElement.Width%2A> property of five rectangles with each rectangle using a different type of repeat behavior.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#RepeatBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/RepeatBehaviorExample.xaml#repeatbehaviorwholepage)]  
  
 <span data-ttu-id="f388b-112">Полный пример см. в разделе [пример поведения анимации времени](https://go.microsoft.com/fwlink/?LinkID=159970).</span><span class="sxs-lookup"><span data-stu-id="f388b-112">For the complete sample, see [Animation Timing Behavior Sample](https://go.microsoft.com/fwlink/?LinkID=159970).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f388b-113">См. также</span><span class="sxs-lookup"><span data-stu-id="f388b-113">See Also</span></span>  
 [<span data-ttu-id="f388b-114">Накапливание значений анимации в повторяющихся циклах</span><span class="sxs-lookup"><span data-stu-id="f388b-114">Accumulate Animation Values During Repeat Cycles</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-accumulate-animation-values-during-repeat-cycles.md)  
 [<span data-ttu-id="f388b-115">Определение автоматического реверса для шкалы времени</span><span class="sxs-lookup"><span data-stu-id="f388b-115">Specify Whether a Timeline Automatically Reverses</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-whether-a-timeline-automatically-reverses.md)  
 [<span data-ttu-id="f388b-116">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="f388b-116">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)  
 [<span data-ttu-id="f388b-117">Анимация и расчет времени</span><span class="sxs-lookup"><span data-stu-id="f388b-117">Animation and Timing</span></span>](https://msdn.microsoft.com/library/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [<span data-ttu-id="f388b-118">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="f388b-118">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="f388b-119">Пример поведения анимации с учетом времени</span><span class="sxs-lookup"><span data-stu-id="f388b-119">Animation Timing Behavior Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159970)
