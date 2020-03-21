---
title: Практическое руководство. Повторение анимации
ms.date: 03/30/2017
helpviewer_keywords:
- RepeatBehavior property of timelines [WPF]
- repeating animating [WPF]
- Timelines RepeatBehavior property [WPF]
- animation [WPF], repeating
ms.assetid: e6f3b068-eeeb-47fd-8d40-8848c31f1e1e
ms.openlocfilehash: 1512c49a658c80f3ab6af652839c3562af3dd205
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141553"
---
# <a name="how-to-repeat-an-animation"></a><span data-ttu-id="48dbe-102">Практическое руководство. Повторение анимации</span><span class="sxs-lookup"><span data-stu-id="48dbe-102">How to: Repeat an Animation</span></span>
<span data-ttu-id="48dbe-103">В этом примере <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> показано, <xref:System.Windows.Media.Animation.Timeline> как использовать свойство объекта для управления повторным поведением анимации.</span><span class="sxs-lookup"><span data-stu-id="48dbe-103">This example shows how to use the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> in order to control the repeat behavior of an animation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="48dbe-104">Пример</span><span class="sxs-lookup"><span data-stu-id="48dbe-104">Example</span></span>  
 <span data-ttu-id="48dbe-105">Свойство <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> элемента <xref:System.Windows.Media.Animation.Timeline> управления, сколько раз анимация повторяет свою простую продолжительность.</span><span class="sxs-lookup"><span data-stu-id="48dbe-105">The <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> controls how many times an animation repeats its simple duration.</span></span> <span data-ttu-id="48dbe-106">С <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>помощью этого можно <xref:System.Windows.Media.Animation.Timeline> указать, что повторяется определенное количество раз (количество итерации) или за определенный период времени.</span><span class="sxs-lookup"><span data-stu-id="48dbe-106">By using <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, you can specify that a <xref:System.Windows.Media.Animation.Timeline> repeats for a certain number of times (an iteration count) or for a specified time period.</span></span> <span data-ttu-id="48dbe-107">В любом случае анимация проходит столько от начала до конца, что ему нужно для заполнения запрошенного подсчета или продолжительности.</span><span class="sxs-lookup"><span data-stu-id="48dbe-107">In either case, the animation goes through as many beginning-to-end runs that it needs in order to fill the requested count or duration.</span></span>  
  
 <span data-ttu-id="48dbe-108">По умолчанию, сроки имеют повторный подсчет 1,0, что означает, что они играют один раз и не повторяются.</span><span class="sxs-lookup"><span data-stu-id="48dbe-108">By default, timelines have a repeat count of 1.0, which means they play one time and do not repeat.</span></span> <span data-ttu-id="48dbe-109">Однако, если <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> вы установите свойство <xref:System.Windows.Media.Animation.Timeline> к, <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>сроки повторяется на неопределенный срок.</span><span class="sxs-lookup"><span data-stu-id="48dbe-109">However, if you set the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> to <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, the timeline repeats indefinitely.</span></span>  
  
 <span data-ttu-id="48dbe-110">В следующем примере показано, как использовать свойство <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> для управления повторным поведением анимации.</span><span class="sxs-lookup"><span data-stu-id="48dbe-110">The following example shows how to use the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property to control the repeat behavior of an animation.</span></span> <span data-ttu-id="48dbe-111">Пример оживляет <xref:System.Windows.FrameworkElement.Width%2A> свойство пяти прямоугольников с каждым прямоугольником, используя другой тип повторного поведения.</span><span class="sxs-lookup"><span data-stu-id="48dbe-111">The example animates the <xref:System.Windows.FrameworkElement.Width%2A> property of five rectangles with each rectangle using a different type of repeat behavior.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#RepeatBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/RepeatBehaviorExample.xaml#repeatbehaviorwholepage)]  
  
 <span data-ttu-id="48dbe-112">Для полного примера [см.](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationTiming)</span><span class="sxs-lookup"><span data-stu-id="48dbe-112">For the complete sample, see [Animation Timing Behavior Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationTiming).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48dbe-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="48dbe-113">See also</span></span>

- [<span data-ttu-id="48dbe-114">Накапливание значений анимации в повторяющихся циклах</span><span class="sxs-lookup"><span data-stu-id="48dbe-114">Accumulate Animation Values During Repeat Cycles</span></span>](how-to-accumulate-animation-values-during-repeat-cycles.md)
- [<span data-ttu-id="48dbe-115">Определение автоматического реверса для шкалы времени</span><span class="sxs-lookup"><span data-stu-id="48dbe-115">Specify Whether a Timeline Automatically Reverses</span></span>](how-to-specify-whether-a-timeline-automatically-reverses.md)
- [<span data-ttu-id="48dbe-116">Разделы руководства по анимации и таймерам</span><span class="sxs-lookup"><span data-stu-id="48dbe-116">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
- [<span data-ttu-id="48dbe-117">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="48dbe-117">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="48dbe-118">Пример поведения анимации с учетом времени</span><span class="sxs-lookup"><span data-stu-id="48dbe-118">Animation Timing Behavior Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationTiming)
