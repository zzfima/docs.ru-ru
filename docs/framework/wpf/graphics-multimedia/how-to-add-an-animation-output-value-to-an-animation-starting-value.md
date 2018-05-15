---
title: Практическое руководство. Добавление выходного значения анимации к начальному значению анимации
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF]
ms.assetid: b89a82be-b03d-481e-a8d3-cc513d09ca00
ms.openlocfilehash: 7f60a3cd3fc88c5bb2460864be6cee008dc672fd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-an-animation-output-value-to-an-animation-starting-value"></a><span data-ttu-id="d9230-102">Практическое руководство. Добавление выходного значения анимации к начальному значению анимации</span><span class="sxs-lookup"><span data-stu-id="d9230-102">How to: Add an Animation Output Value to an Animation Starting Value</span></span>
<span data-ttu-id="d9230-103">В этом примере показано, как добавить выходное значение анимации к начальному значению анимации.</span><span class="sxs-lookup"><span data-stu-id="d9230-103">This example shows how to add an animation output value to an animation starting value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9230-104">Пример</span><span class="sxs-lookup"><span data-stu-id="d9230-104">Example</span></span>  
 <span data-ttu-id="d9230-105"><xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> Свойство указывает, следует ли выходное значение анимации добавлен к начальному значению (базовое значение) анимированного свойства.</span><span class="sxs-lookup"><span data-stu-id="d9230-105">The <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> property specifies whether you want the output value of an animation added to the starting value (base value) of an animated property.</span></span> <span data-ttu-id="d9230-106">Можно использовать <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> свойство с большинством базовых анимаций и большинство анимации ключевого кадра.</span><span class="sxs-lookup"><span data-stu-id="d9230-106">You can use the <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> property with most basic animations and most key frame animations.</span></span> <span data-ttu-id="d9230-107">Дополнительные сведения см. в разделе [Обзор анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) и [кадрами ключ](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d9230-107">For more information, see [Animation Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) and [Key-Frame Animations Overview](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).</span></span>  
  
 <span data-ttu-id="d9230-108">В следующем примере показано применение <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A?displayProperty=nameWithType> свойство с <xref:System.Windows.Media.Animation.DoubleAnimation> и с помощью <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsAdditive%2A?displayProperty=nameWithType> свойство с <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>.</span><span class="sxs-lookup"><span data-stu-id="d9230-108">The following example shows the effect of using the <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A?displayProperty=nameWithType> property with <xref:System.Windows.Media.Animation.DoubleAnimation> and using the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsAdditive%2A?displayProperty=nameWithType> property with <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#IsAdditiveWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsAdditiveExample.xaml#isadditivewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="d9230-109">См. также</span><span class="sxs-lookup"><span data-stu-id="d9230-109">See Also</span></span>  
 [<span data-ttu-id="d9230-110">Накапливание значений анимации в повторяющихся циклах</span><span class="sxs-lookup"><span data-stu-id="d9230-110">Accumulate Animation Values During Repeat Cycles</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-accumulate-animation-values-during-repeat-cycles.md)  
 [<span data-ttu-id="d9230-111">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="d9230-111">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="d9230-112">Общие сведения об анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="d9230-112">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="d9230-113">Анимация и расчет времени</span><span class="sxs-lookup"><span data-stu-id="d9230-113">Animation and Timing</span></span>](http://msdn.microsoft.com/library/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [<span data-ttu-id="d9230-114">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="d9230-114">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
