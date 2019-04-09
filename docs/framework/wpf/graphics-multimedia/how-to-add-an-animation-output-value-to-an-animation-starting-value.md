---
title: Практическое руководство. Добавление выходного значения анимации к начальному значению анимации
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF]
ms.assetid: b89a82be-b03d-481e-a8d3-cc513d09ca00
ms.openlocfilehash: 945675d03a280e2394fdb0eab27c0978dc7cc320
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59102613"
---
# <a name="how-to-add-an-animation-output-value-to-an-animation-starting-value"></a><span data-ttu-id="dbbbe-102">Практическое руководство. Добавление выходного значения анимации к начальному значению анимации</span><span class="sxs-lookup"><span data-stu-id="dbbbe-102">How to: Add an Animation Output Value to an Animation Starting Value</span></span>
<span data-ttu-id="dbbbe-103">В этом примере показано, как добавление выходного значения анимации к начальному значению анимации.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-103">This example shows how to add an animation output value to an animation starting value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dbbbe-104">Пример</span><span class="sxs-lookup"><span data-stu-id="dbbbe-104">Example</span></span>  
 <span data-ttu-id="dbbbe-105"><xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> Свойство указывает, следует ли выходное значение анимации добавлены начальным значением (базовое значение) анимированного свойства.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-105">The <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> property specifies whether you want the output value of an animation added to the starting value (base value) of an animated property.</span></span> <span data-ttu-id="dbbbe-106">Можно использовать <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> свойство с большинством базовых анимаций и большинство анимации ключевого кадра.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-106">You can use the <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> property with most basic animations and most key frame animations.</span></span> <span data-ttu-id="dbbbe-107">Дополнительные сведения см. в разделе [Общие сведения об анимации](animation-overview.md) и [сведения об анимации по ключевым кадрам](key-frame-animations-overview.md).</span><span class="sxs-lookup"><span data-stu-id="dbbbe-107">For more information, see [Animation Overview](animation-overview.md) and [Key-Frame Animations Overview](key-frame-animations-overview.md).</span></span>  
  
 <span data-ttu-id="dbbbe-108">В следующем примере показано применение <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A?displayProperty=nameWithType> свойство с <xref:System.Windows.Media.Animation.DoubleAnimation> и с помощью <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsAdditive%2A?displayProperty=nameWithType> свойство с <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-108">The following example shows the effect of using the <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A?displayProperty=nameWithType> property with <xref:System.Windows.Media.Animation.DoubleAnimation> and using the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsAdditive%2A?displayProperty=nameWithType> property with <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#IsAdditiveWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsAdditiveExample.xaml#isadditivewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="dbbbe-109">См. также</span><span class="sxs-lookup"><span data-stu-id="dbbbe-109">See also</span></span>

- [<span data-ttu-id="dbbbe-110">Накапливание значений анимации в повторяющихся циклах</span><span class="sxs-lookup"><span data-stu-id="dbbbe-110">Accumulate Animation Values During Repeat Cycles</span></span>](how-to-accumulate-animation-values-during-repeat-cycles.md)
- [<span data-ttu-id="dbbbe-111">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="dbbbe-111">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="dbbbe-112">Общие сведения об анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="dbbbe-112">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="dbbbe-113">Разделы руководства по анимации и таймерам</span><span class="sxs-lookup"><span data-stu-id="dbbbe-113">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
