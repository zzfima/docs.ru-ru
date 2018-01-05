---
title: "Практическое руководство. Анимирование свойства с помощью AnimationClock"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], properties [WPF], with AnimationClocks
- AnimationClocks [WPF]
ms.assetid: e6542021-714c-4675-9567-04f1c7380834
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 145ff1be88f1af6692a8cf374e871479ed38d7bf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-a-property-by-using-an-animationclock"></a><span data-ttu-id="70c76-102">Практическое руководство. Анимирование свойства с помощью AnimationClock</span><span class="sxs-lookup"><span data-stu-id="70c76-102">How to: Animate a Property by Using an AnimationClock</span></span>
<span data-ttu-id="70c76-103">В этом примере показано, как использовать <xref:System.Windows.Media.Animation.Clock> объекты для анимации свойства.</span><span class="sxs-lookup"><span data-stu-id="70c76-103">This example shows how to use <xref:System.Windows.Media.Animation.Clock> objects to animate a property.</span></span>  
  
 <span data-ttu-id="70c76-104">Есть три способа анимации свойства зависимостей:</span><span class="sxs-lookup"><span data-stu-id="70c76-104">There are three ways to animate a dependency property:</span></span>  
  
-   <span data-ttu-id="70c76-105">Создание <xref:System.Windows.Media.Animation.AnimationTimeline> и связать его с этим свойством, с помощью <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="70c76-105">Create an <xref:System.Windows.Media.Animation.AnimationTimeline> and associate it with that property by using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
-   <span data-ttu-id="70c76-106">Используйте метод объекта <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> применить один метод <xref:System.Windows.Media.Animation.AnimationTimeline> к целевому свойству.</span><span class="sxs-lookup"><span data-stu-id="70c76-106">Use the object's <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method to apply a single <xref:System.Windows.Media.Animation.AnimationTimeline> to a target property.</span></span>  
  
-   <span data-ttu-id="70c76-107">Создание <xref:System.Windows.Media.Animation.AnimationClock> из <xref:System.Windows.Media.Animation.AnimationTimeline> и применить его к свойству.</span><span class="sxs-lookup"><span data-stu-id="70c76-107">Create an <xref:System.Windows.Media.Animation.AnimationClock> from an <xref:System.Windows.Media.Animation.AnimationTimeline> and apply it to a property.</span></span>  
  
 <span data-ttu-id="70c76-108"><xref:System.Windows.Media.Animation.Storyboard>объекты и <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> метод позволяют анимировать свойства без непосредственного создания и распространения часов (примеры см. в разделе [анимации свойства с помощью раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md) и [анимировать свойство без С помощью раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)); часы создаются и распространяются автоматически.</span><span class="sxs-lookup"><span data-stu-id="70c76-108"><xref:System.Windows.Media.Animation.Storyboard> objects and the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method enable you to animate properties without directly creating and distributing clocks (for examples, see [Animate a Property by Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md) and [Animate a Property Without Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)); clocks are created and distributed for you automatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70c76-109">Пример</span><span class="sxs-lookup"><span data-stu-id="70c76-109">Example</span></span>  
 <span data-ttu-id="70c76-110">В следующем примере показано, как создать <xref:System.Windows.Media.Animation.AnimationClock> и применить его к двум аналогичным свойствам.</span><span class="sxs-lookup"><span data-stu-id="70c76-110">The following example shows how to create an <xref:System.Windows.Media.Animation.AnimationClock> and apply it to two similar properties.</span></span>  
  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/AnimationClockExample.cs#graphicsmmcreateanimationclockwholeclass)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/animationclockexample.vb#graphicsmmcreateanimationclockwholeclass)]  
  
 <span data-ttu-id="70c76-111">Пример, показывающий, как управлять в интерактивном режиме <xref:System.Windows.Media.Animation.Clock> после ее запуска в разделе [управление часами в интерактивном режиме](../../../../docs/framework/wpf/graphics-multimedia/how-to-interactively-control-a-clock.md).</span><span class="sxs-lookup"><span data-stu-id="70c76-111">For an example showing how to interactively control a <xref:System.Windows.Media.Animation.Clock> after it starts, see [Interactively Control a Clock](../../../../docs/framework/wpf/graphics-multimedia/how-to-interactively-control-a-clock.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70c76-112">См. также</span><span class="sxs-lookup"><span data-stu-id="70c76-112">See Also</span></span>  
 [<span data-ttu-id="70c76-113">Анимация свойства с помощью раскадровки</span><span class="sxs-lookup"><span data-stu-id="70c76-113">Animate a Property by Using a Storyboard</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)  
 [<span data-ttu-id="70c76-114">Анимация свойства без использования раскадровки</span><span class="sxs-lookup"><span data-stu-id="70c76-114">Animate a Property Without Using a Storyboard</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)  
 [<span data-ttu-id="70c76-115">Общие сведения о методах анимации свойств</span><span class="sxs-lookup"><span data-stu-id="70c76-115">Property Animation Techniques Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)
