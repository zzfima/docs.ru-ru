---
title: Практическое руководство. Анимация свойства без раскадровки
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- non-Storyboard animation
- local animation [WPF]
- animation [WPF], non-Storyboard (local)
ms.assetid: d411db70-4df7-487d-82bc-95a7c1b2e7f8
ms.openlocfilehash: 18f8fb4edf5f71904335180e43dd65bd9910bdef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-animate-a-property-without-using-a-storyboard"></a><span data-ttu-id="aab22-102">Практическое руководство. Анимация свойства без раскадровки</span><span class="sxs-lookup"><span data-stu-id="aab22-102">How to: Animate a Property Without Using a Storyboard</span></span>
<span data-ttu-id="aab22-103">В этом примере показан один из способов применения анимации свойства без использования <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="aab22-103">This example shows one way to apply an animation to a property without using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aab22-104">Эта функциональность недоступна в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aab22-104">This functionality is not available in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="aab22-105">Дополнительные сведения об анимации свойств в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] см. в разделе [Анимация свойства с помощью раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="aab22-105">For information about animating a property in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], see [Animate a Property by Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md).</span></span>  
  
 <span data-ttu-id="aab22-106">Чтобы применить локальную анимацию к свойству, используйте <xref:System.Windows.UIElement.BeginAnimation%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="aab22-106">To apply a local animation to a property, use the <xref:System.Windows.UIElement.BeginAnimation%2A> method.</span></span> <span data-ttu-id="aab22-107">Этот метод принимает два параметра: <xref:System.Windows.DependencyProperty> , указывающий анимируемое свойство и анимации, применяемую к этому свойству.</span><span class="sxs-lookup"><span data-stu-id="aab22-107">This method takes two parameters: a <xref:System.Windows.DependencyProperty> that specifies the property to animate, and the animation to apply to that property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aab22-108">Пример</span><span class="sxs-lookup"><span data-stu-id="aab22-108">Example</span></span>  
 <span data-ttu-id="aab22-109">В следующем примере показано, как анимация ширины и цвета фона <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="aab22-109">The following example shows how to animate the width and background color of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 [!code-cpp[animateproperty#11](../../../../samples/snippets/cpp/VS_Snippets_Wpf/animateproperty/CPP/LocalAnimationExample.cpp#11)]
 [!code-csharp[animateproperty#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animateproperty/CSharp/LocalAnimationExample.cs#11)]
 [!code-vb[animateproperty#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animateproperty/VisualBasic/LocalAnimationExample.vb#11)]  
  
 <span data-ttu-id="aab22-110">Различные классы анимации в <xref:System.Windows.Media.Animation> существует пространство имен для анимации различных типов свойств.</span><span class="sxs-lookup"><span data-stu-id="aab22-110">A variety of animation classes in the <xref:System.Windows.Media.Animation> namespace exist for animating different types of properties.</span></span> <span data-ttu-id="aab22-111">Дополнительные сведения об анимации свойств см. в разделе [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="aab22-111">For more information about animating properties, see [Animation Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span></span> <span data-ttu-id="aab22-112">Дополнительные сведения о свойствах зависимостей (тип свойств, приведенных в этих примерах) и их функциях см. в разделе [Общие сведения о свойствах зависимостей](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="aab22-112">For more information about dependency properties (the type of properties that are shown in these examples) and their features, see [Dependency Properties Overview](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).</span></span>  
  
 <span data-ttu-id="aab22-113">Существуют другие способы анимации без использования <xref:System.Windows.Media.Animation.Storyboard> объектов; Дополнительные сведения см. в разделе [Общие сведения о методах анимации свойства](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).</span><span class="sxs-lookup"><span data-stu-id="aab22-113">There are other ways to animate without using <xref:System.Windows.Media.Animation.Storyboard> objects; for more information, see [Property Animation Techniques Overview](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aab22-114">См. также</span><span class="sxs-lookup"><span data-stu-id="aab22-114">See Also</span></span>  
 <xref:System.Windows.Media.Animation.AnimationTimeline>  
 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>  
 <xref:System.Windows.Media.Animation>  
 <xref:System.Windows.Media.Animation.Storyboard>  
 [<span data-ttu-id="aab22-115">Общие сведения о методах анимации свойств</span><span class="sxs-lookup"><span data-stu-id="aab22-115">Property Animation Techniques Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)  
 [<span data-ttu-id="aab22-116">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="aab22-116">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
