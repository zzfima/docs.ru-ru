---
title: "Практическое руководство. Упрощение анимации с помощью дочерних шкал времени"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- simplifying animations by child timelines [WPF]
- animation [WPF], simplifying by child timelines
- child timelines [WPF]
ms.assetid: 8335d770-d13d-42bd-8dfa-63f92c0327e2
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0d3b8f1ca1dbf7ba5452acffc62fdf0b655c9c12
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-simplify-animations-by-using-child-timelines"></a><span data-ttu-id="aff18-102">Практическое руководство. Упрощение анимации с помощью дочерних шкал времени</span><span class="sxs-lookup"><span data-stu-id="aff18-102">How to: Simplify Animations by Using Child Timelines</span></span>
<span data-ttu-id="aff18-103">В этом примере показано, как упростить анимации с помощью дочерних <xref:System.Windows.Media.Animation.ParallelTimeline> объектов.</span><span class="sxs-lookup"><span data-stu-id="aff18-103">This example shows how to simplify animations by using child <xref:System.Windows.Media.Animation.ParallelTimeline> objects.</span></span> <span data-ttu-id="aff18-104">Объект <xref:System.Windows.Media.Animation.Storyboard> — это тип <xref:System.Windows.Media.Animation.Timeline> , предоставляющий сведения о содержащихся в нем шкалах.</span><span class="sxs-lookup"><span data-stu-id="aff18-104">A <xref:System.Windows.Media.Animation.Storyboard> is a type of <xref:System.Windows.Media.Animation.Timeline> that provides targeting information for the timelines it contains.</span></span> <span data-ttu-id="aff18-105">Используйте <xref:System.Windows.Media.Animation.Storyboard> для предоставления данных, включая объект и свойство сведения о шкале времени.</span><span class="sxs-lookup"><span data-stu-id="aff18-105">Use a <xref:System.Windows.Media.Animation.Storyboard> to provide timeline targeting information, including object and property information.</span></span>  
  
 <span data-ttu-id="aff18-106">Чтобы начать анимацию, используйте один или несколько <xref:System.Windows.Media.Animation.ParallelTimeline> объекты, как вложенные дочерние элементы <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="aff18-106">To begin an animation, use one or more <xref:System.Windows.Media.Animation.ParallelTimeline> objects as nested child elements of a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="aff18-107">Эти <xref:System.Windows.Media.Animation.ParallelTimeline> объекты могут содержать другие анимации и таким образом, могут лучше инкапсулировать временные последовательности в сложных анимациях.</span><span class="sxs-lookup"><span data-stu-id="aff18-107">These <xref:System.Windows.Media.Animation.ParallelTimeline> objects can contain other animations and therefore, can better encapsulate the timing sequences in complex animations.</span></span> <span data-ttu-id="aff18-108">Например, при анимации <xref:System.Windows.Controls.TextBlock> и нескольких фигур в одном <xref:System.Windows.Media.Animation.Storyboard>, можно разделить анимацию для <xref:System.Windows.Controls.TextBlock> и фигур, помещая каждую в отдельный <xref:System.Windows.Media.Animation.ParallelTimeline>.</span><span class="sxs-lookup"><span data-stu-id="aff18-108">For example, if you are animating a <xref:System.Windows.Controls.TextBlock> and several shapes in the same <xref:System.Windows.Media.Animation.Storyboard>, you can separate the animations for the <xref:System.Windows.Controls.TextBlock> and the shapes, putting each into a separate <xref:System.Windows.Media.Animation.ParallelTimeline>.</span></span> <span data-ttu-id="aff18-109">Поскольку каждый <xref:System.Windows.Media.Animation.ParallelTimeline> имеет свой собственный <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> и все дочерние элементы элемента <xref:System.Windows.Media.Animation.ParallelTimeline> начинаются относительно этого <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>, время инкапсулируется лучше.</span><span class="sxs-lookup"><span data-stu-id="aff18-109">Because each <xref:System.Windows.Media.Animation.ParallelTimeline> has its own <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> and all child elements of the <xref:System.Windows.Media.Animation.ParallelTimeline> begin relative to this <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>, timing is better encapsulated.</span></span>  
  
 <span data-ttu-id="aff18-110">В следующем примере анимируется двух фрагментов текста (<xref:System.Windows.Controls.TextBlock> объектов) из в одном <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="aff18-110">The following example animates two pieces of text (<xref:System.Windows.Controls.TextBlock> objects) from within the same <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="aff18-111">Объект <xref:System.Windows.Media.Animation.ParallelTimeline> инкапсулирует анимацию одного из <xref:System.Windows.Controls.TextBlock> объектов.</span><span class="sxs-lookup"><span data-stu-id="aff18-111">A <xref:System.Windows.Media.Animation.ParallelTimeline> encapsulates the animations of one of the <xref:System.Windows.Controls.TextBlock> objects.</span></span>  
  
 <span data-ttu-id="aff18-112">**Замечания о производительности:** несмотря на то, что можно вложить <xref:System.Windows.Media.Animation.Storyboard> временных шкал друг в друга, <xref:System.Windows.Media.Animation.ParallelTimeline>больше подходят для вложения, так как они требуют меньше ресурсов.</span><span class="sxs-lookup"><span data-stu-id="aff18-112">**Performance Note:** Although you can nest <xref:System.Windows.Media.Animation.Storyboard> timelines inside each other, <xref:System.Windows.Media.Animation.ParallelTimeline>s are more suitable for nesting because they require less overhead.</span></span> <span data-ttu-id="aff18-113">( <xref:System.Windows.Media.Animation.Storyboard> Класс наследует от <xref:System.Windows.Media.Animation.ParallelTimeline> класса.)</span><span class="sxs-lookup"><span data-stu-id="aff18-113">(The <xref:System.Windows.Media.Animation.Storyboard> class inherits from the <xref:System.Windows.Media.Animation.ParallelTimeline> class.)</span></span>  
  
## <a name="example"></a><span data-ttu-id="aff18-114">Пример</span><span class="sxs-lookup"><span data-stu-id="aff18-114">Example</span></span>  
 [!code-xaml[Timelines_snip#ParallelTimelineWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Timelines_snip/CS/ParallelTimelineExample.xaml#paralleltimelinewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="aff18-115">См. также</span><span class="sxs-lookup"><span data-stu-id="aff18-115">See Also</span></span>  
 [<span data-ttu-id="aff18-116">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="aff18-116">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="aff18-117">Задание значения свойства HandoffBehavior для анимаций раскадровки</span><span class="sxs-lookup"><span data-stu-id="aff18-117">Specify HandoffBehavior Between Storyboard Animations</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-handoffbehavior-between-storyboard-animations.md)
