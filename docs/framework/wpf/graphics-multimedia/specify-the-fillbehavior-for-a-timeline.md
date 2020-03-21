---
title: Практическое руководство. Указание режима FillBehavior для временной шкалы, достигшей конца периода активности
ms.date: 03/30/2017
helpviewer_keywords:
- FillBehavior property for inactive timelines [WPF]
- Timelines [WPF], FillBehavior property
ms.assetid: db805f59-d513-4dac-af15-47005dae3199
ms.openlocfilehash: 1f54f2c1bb49bb7a0301f112a109194ab1a8658e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141177"
---
# <a name="how-to-specify-the-fillbehavior-for-a-timeline-that-has-reached-the-end-of-its-active-period"></a><span data-ttu-id="d197c-102">Практическое руководство. Указание режима FillBehavior для временной шкалы, достигшей конца периода активности</span><span class="sxs-lookup"><span data-stu-id="d197c-102">How to: Specify the FillBehavior for a Timeline that has Reached the End of Its Active Period</span></span>
<span data-ttu-id="d197c-103">В этом примере <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> показано, как <xref:System.Windows.Media.Animation.Timeline> указать для неактивного анимированного свойства.</span><span class="sxs-lookup"><span data-stu-id="d197c-103">This example shows how to specify the <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> for the inactive <xref:System.Windows.Media.Animation.Timeline> of an animated property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d197c-104">Пример</span><span class="sxs-lookup"><span data-stu-id="d197c-104">Example</span></span>  
 <span data-ttu-id="d197c-105">Свойство <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> свойства <xref:System.Windows.Media.Animation.Timeline> определяет, что происходит со значением анимированного свойства, когда <xref:System.Windows.Media.Animation.Timeline> оно не анимируется, то есть, когда оно неактивно, но его родитель <xref:System.Windows.Media.Animation.Timeline> находится внутри своего активного или удерживаемого периода.</span><span class="sxs-lookup"><span data-stu-id="d197c-105">The <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> determines what happens to the value of an animated property when it is not being animated, that is, when the <xref:System.Windows.Media.Animation.Timeline> is inactive but its parent <xref:System.Windows.Media.Animation.Timeline> is inside its active or hold period.</span></span> <span data-ttu-id="d197c-106">Например, остается ли анимированное свойство в конечном значении после окончания анимации или возвращается к значению, имевачтому до начала анимации?</span><span class="sxs-lookup"><span data-stu-id="d197c-106">For example, does an animated property remain at its end value after the animation ends or does it revert back to the value it had before the animation started?</span></span>  
  
 <span data-ttu-id="d197c-107">В следующем примере <xref:System.Windows.Media.Animation.DoubleAnimation> используется для <xref:System.Windows.FrameworkElement.Width%2A> анимировать два прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="d197c-107">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the <xref:System.Windows.FrameworkElement.Width%2A> of two rectangles.</span></span> <span data-ttu-id="d197c-108">В каждом прямоугольнике используется другой <xref:System.Windows.Media.Animation.Timeline> объект.</span><span class="sxs-lookup"><span data-stu-id="d197c-108">Each rectangle uses a different <xref:System.Windows.Media.Animation.Timeline> object.</span></span>  
  
 <span data-ttu-id="d197c-109">Один <xref:System.Windows.Media.Animation.Timeline> <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> имеет, что <xref:System.Windows.Media.Animation.FillBehavior.Stop>установлен на , что приводит к ширине прямоугольника, чтобы <xref:System.Windows.Media.Animation.Timeline> вернуться к своей неанимированной значение, когда заканчивается.</span><span class="sxs-lookup"><span data-stu-id="d197c-109">One <xref:System.Windows.Media.Animation.Timeline> has a <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> that is set to <xref:System.Windows.Media.Animation.FillBehavior.Stop>, which causes the width of the rectangle to revert back to its non-animated value when the <xref:System.Windows.Media.Animation.Timeline> ends.</span></span> <span data-ttu-id="d197c-110">Другой <xref:System.Windows.Media.Animation.Timeline> имеет <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>из, что приводит к ширине, чтобы <xref:System.Windows.Media.Animation.Timeline> остаться в его конечное значение, когда заканчивается.</span><span class="sxs-lookup"><span data-stu-id="d197c-110">The other <xref:System.Windows.Media.Animation.Timeline> has a <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> of <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, which causes the width to remain at its end value when the <xref:System.Windows.Media.Animation.Timeline> ends.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#FillBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/FillBehaviorExample.xaml#fillbehaviorwholepage)]  
  
 <span data-ttu-id="d197c-111">Для полного примера, см [Анимация Пример Галерея](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).</span><span class="sxs-lookup"><span data-stu-id="d197c-111">For the complete sample, see [Animation Example Gallery](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d197c-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d197c-112">See also</span></span>

- <xref:System.Windows.Media.Animation.DoubleAnimation>
- <xref:System.Windows.FrameworkElement.Width%2A>
- <xref:System.Windows.Media.Animation.Timeline>
- <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>
- <xref:System.Windows.Media.Animation.FillBehavior.Stop>
- <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>
- [<span data-ttu-id="d197c-113">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="d197c-113">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="d197c-114">Разделы руководства по анимации и таймерам</span><span class="sxs-lookup"><span data-stu-id="d197c-114">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
