---
title: Практическое руководство. Указание режима FillBehavior для временной шкалы, достигшей конца периода активности
ms.date: 03/30/2017
helpviewer_keywords:
- FillBehavior property for inactive timelines [WPF]
- Timelines [WPF], FillBehavior property
ms.assetid: db805f59-d513-4dac-af15-47005dae3199
ms.openlocfilehash: 947be09140dc2d1d5e130ccb74472d8dce3408cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-specify-the-fillbehavior-for-a-timeline-that-has-reached-the-end-of-its-active-period"></a><span data-ttu-id="0d87d-102">Практическое руководство. Указание режима FillBehavior для временной шкалы, достигшей конца периода активности</span><span class="sxs-lookup"><span data-stu-id="0d87d-102">How to: Specify the FillBehavior for a Timeline that has Reached the End of Its Active Period</span></span>
<span data-ttu-id="0d87d-103">В этом примере показано, как указать <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> для неактивных <xref:System.Windows.Media.Animation.Timeline> анимированного свойства.</span><span class="sxs-lookup"><span data-stu-id="0d87d-103">This example shows how to specify the <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> for the inactive <xref:System.Windows.Media.Animation.Timeline> of an animated property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d87d-104">Пример</span><span class="sxs-lookup"><span data-stu-id="0d87d-104">Example</span></span>  
 <span data-ttu-id="0d87d-105"><xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> Свойство <xref:System.Windows.Media.Animation.Timeline> определяет, что происходит значение анимируемого свойства, если оно не анимируется, то есть, когда <xref:System.Windows.Media.Animation.Timeline> неактивна, но его родительский <xref:System.Windows.Media.Animation.Timeline> находится в своем активном периоде или периоде удержания.</span><span class="sxs-lookup"><span data-stu-id="0d87d-105">The <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> determines what happens to the value of an animated property when it is not being animated, that is, when the <xref:System.Windows.Media.Animation.Timeline> is inactive but its parent <xref:System.Windows.Media.Animation.Timeline> is inside its active or hold period.</span></span> <span data-ttu-id="0d87d-106">Например, анимированного свойства, остается в конечном значение после окончания анимации или он будет вернуться к значению, которое было до начала анимации?</span><span class="sxs-lookup"><span data-stu-id="0d87d-106">For example, does an animated property remain at its end value after the animation ends or does it revert back to the value it had before the animation started?</span></span>  
  
 <span data-ttu-id="0d87d-107">В следующем примере используется <xref:System.Windows.Media.Animation.DoubleAnimation> для анимации <xref:System.Windows.FrameworkElement.Width%2A> двух прямоугольников.</span><span class="sxs-lookup"><span data-stu-id="0d87d-107">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the <xref:System.Windows.FrameworkElement.Width%2A> of two rectangles.</span></span> <span data-ttu-id="0d87d-108">Каждый прямоугольник использует различные <xref:System.Windows.Media.Animation.Timeline> объекта.</span><span class="sxs-lookup"><span data-stu-id="0d87d-108">Each rectangle uses a different <xref:System.Windows.Media.Animation.Timeline> object.</span></span>  
  
 <span data-ttu-id="0d87d-109">Один <xref:System.Windows.Media.Animation.Timeline> имеет <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> , имеющим значение <xref:System.Windows.Media.Animation.FillBehavior.Stop>, чего ширина прямоугольника для возврата к его без анимации значения при <xref:System.Windows.Media.Animation.Timeline> заканчивается.</span><span class="sxs-lookup"><span data-stu-id="0d87d-109">One <xref:System.Windows.Media.Animation.Timeline> has a <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> that is set to <xref:System.Windows.Media.Animation.FillBehavior.Stop>, which causes the width of the rectangle to revert back to its non-animated value when the <xref:System.Windows.Media.Animation.Timeline> ends.</span></span> <span data-ttu-id="0d87d-110">Другой <xref:System.Windows.Media.Animation.Timeline> имеет <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> из <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, вследствие чего ширина остается в конце значения при <xref:System.Windows.Media.Animation.Timeline> заканчивается.</span><span class="sxs-lookup"><span data-stu-id="0d87d-110">The other <xref:System.Windows.Media.Animation.Timeline> has a <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> of <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, which causes the width to remain at its end value when the <xref:System.Windows.Media.Animation.Timeline> ends.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#FillBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/FillBehaviorExample.xaml#fillbehaviorwholepage)]  
  
 <span data-ttu-id="0d87d-111">Полный пример см. в разделе [Коллекция примеров анимации](http://go.microsoft.com/fwlink/?LinkID=159969).</span><span class="sxs-lookup"><span data-stu-id="0d87d-111">For the complete sample, see [Animation Example Gallery](http://go.microsoft.com/fwlink/?LinkID=159969).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d87d-112">См. также</span><span class="sxs-lookup"><span data-stu-id="0d87d-112">See Also</span></span>  
 <xref:System.Windows.Media.Animation.DoubleAnimation>  
 <xref:System.Windows.FrameworkElement.Width%2A>  
 <xref:System.Windows.Media.Animation.Timeline>  
 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>  
 <xref:System.Windows.Media.Animation.FillBehavior.Stop>  
 <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>  
 [<span data-ttu-id="0d87d-113">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="0d87d-113">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="0d87d-114">Анимация и расчет времени</span><span class="sxs-lookup"><span data-stu-id="0d87d-114">Animation and Timing</span></span>](http://msdn.microsoft.com/library/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [<span data-ttu-id="0d87d-115">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="0d87d-115">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
