---
title: Практическое руководство. Определение режима FillBehavior для временной шкалы, достигшей конца периода активности
ms.date: 03/30/2017
helpviewer_keywords:
- FillBehavior property for inactive timelines [WPF]
- Timelines [WPF], FillBehavior property
ms.assetid: db805f59-d513-4dac-af15-47005dae3199
ms.openlocfilehash: 9f03c5b8d4585c32e0a9f119649dd15a23523033
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61973671"
---
# <a name="how-to-specify-the-fillbehavior-for-a-timeline-that-has-reached-the-end-of-its-active-period"></a><span data-ttu-id="67d04-102">Практическое руководство. Определение режима FillBehavior для временной шкалы, достигшей конца периода активности</span><span class="sxs-lookup"><span data-stu-id="67d04-102">How to: Specify the FillBehavior for a Timeline that has Reached the End of Its Active Period</span></span>
<span data-ttu-id="67d04-103">В этом примере показано, как указать <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> для неактивного <xref:System.Windows.Media.Animation.Timeline> анимированного свойства.</span><span class="sxs-lookup"><span data-stu-id="67d04-103">This example shows how to specify the <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> for the inactive <xref:System.Windows.Media.Animation.Timeline> of an animated property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67d04-104">Пример</span><span class="sxs-lookup"><span data-stu-id="67d04-104">Example</span></span>  
 <span data-ttu-id="67d04-105"><xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> Свойство <xref:System.Windows.Media.Animation.Timeline> определяет, что происходит с значение анимированного свойства, если оно не анимировано, то есть когда <xref:System.Windows.Media.Animation.Timeline> неактивна, но его родительский <xref:System.Windows.Media.Animation.Timeline> находится в своем активном периоде или периоде удержания.</span><span class="sxs-lookup"><span data-stu-id="67d04-105">The <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> determines what happens to the value of an animated property when it is not being animated, that is, when the <xref:System.Windows.Media.Animation.Timeline> is inactive but its parent <xref:System.Windows.Media.Animation.Timeline> is inside its active or hold period.</span></span> <span data-ttu-id="67d04-106">Например, она анимированного свойства по-прежнему со своей стороны значение после окончания анимации или делает это вернуться к значению, которое было до начала анимации?</span><span class="sxs-lookup"><span data-stu-id="67d04-106">For example, does an animated property remain at its end value after the animation ends or does it revert back to the value it had before the animation started?</span></span>  
  
 <span data-ttu-id="67d04-107">В следующем примере используется <xref:System.Windows.Media.Animation.DoubleAnimation> для анимации <xref:System.Windows.FrameworkElement.Width%2A> двух прямоугольников.</span><span class="sxs-lookup"><span data-stu-id="67d04-107">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the <xref:System.Windows.FrameworkElement.Width%2A> of two rectangles.</span></span> <span data-ttu-id="67d04-108">Каждый прямоугольник использует другое <xref:System.Windows.Media.Animation.Timeline> объекта.</span><span class="sxs-lookup"><span data-stu-id="67d04-108">Each rectangle uses a different <xref:System.Windows.Media.Animation.Timeline> object.</span></span>  
  
 <span data-ttu-id="67d04-109">Один <xref:System.Windows.Media.Animation.Timeline> имеет <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> , имеет значение <xref:System.Windows.Media.Animation.FillBehavior.Stop>, чего ширина прямоугольника, вернуться к его не анимированное значение, если <xref:System.Windows.Media.Animation.Timeline> заканчивается.</span><span class="sxs-lookup"><span data-stu-id="67d04-109">One <xref:System.Windows.Media.Animation.Timeline> has a <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> that is set to <xref:System.Windows.Media.Animation.FillBehavior.Stop>, which causes the width of the rectangle to revert back to its non-animated value when the <xref:System.Windows.Media.Animation.Timeline> ends.</span></span> <span data-ttu-id="67d04-110">Другой <xref:System.Windows.Media.Animation.Timeline> имеет <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> из <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, чего ширина оставаться в конце значения при <xref:System.Windows.Media.Animation.Timeline> заканчивается.</span><span class="sxs-lookup"><span data-stu-id="67d04-110">The other <xref:System.Windows.Media.Animation.Timeline> has a <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> of <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, which causes the width to remain at its end value when the <xref:System.Windows.Media.Animation.Timeline> ends.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#FillBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/FillBehaviorExample.xaml#fillbehaviorwholepage)]  
  
 <span data-ttu-id="67d04-111">Полный пример см. в разделе [Коллекция примеров анимации](https://go.microsoft.com/fwlink/?LinkID=159969).</span><span class="sxs-lookup"><span data-stu-id="67d04-111">For the complete sample, see [Animation Example Gallery](https://go.microsoft.com/fwlink/?LinkID=159969).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67d04-112">См. также</span><span class="sxs-lookup"><span data-stu-id="67d04-112">See also</span></span>

- <xref:System.Windows.Media.Animation.DoubleAnimation>
- <xref:System.Windows.FrameworkElement.Width%2A>
- <xref:System.Windows.Media.Animation.Timeline>
- <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>
- <xref:System.Windows.Media.Animation.FillBehavior.Stop>
- <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>
- [<span data-ttu-id="67d04-113">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="67d04-113">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="67d04-114">Анимации и практические руководства</span><span class="sxs-lookup"><span data-stu-id="67d04-114">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
