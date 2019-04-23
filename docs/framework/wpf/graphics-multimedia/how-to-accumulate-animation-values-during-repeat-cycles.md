---
title: Практическое руководство. Накапливание значений анимации в повторяющихся циклах
ms.date: 03/30/2017
helpviewer_keywords:
- accumulating animation values across repeating cycles [WPF]
- animation [WPF], accumulating values across repeating cycles
ms.assetid: 548df369-c7cc-4dab-b569-08b95ced2e7e
ms.openlocfilehash: 4b739883322751e2df86e13bfd07249abdb10a08
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59146020"
---
# <a name="how-to-accumulate-animation-values-during-repeat-cycles"></a><span data-ttu-id="c28e0-102">Практическое руководство. Накапливание значений анимации в повторяющихся циклах</span><span class="sxs-lookup"><span data-stu-id="c28e0-102">How to: Accumulate Animation Values During Repeat Cycles</span></span>
<span data-ttu-id="c28e0-103">В этом примере показано, как использовать <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> свойство к накоплению значений анимации в повторяющихся циклах.</span><span class="sxs-lookup"><span data-stu-id="c28e0-103">This example shows how to use the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to accumulate animation values across repeating cycles.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c28e0-104">Пример</span><span class="sxs-lookup"><span data-stu-id="c28e0-104">Example</span></span>  
 <span data-ttu-id="c28e0-105">Используйте <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> свойство к накоплению значений анимации в повторяющихся циклах.</span><span class="sxs-lookup"><span data-stu-id="c28e0-105">Use the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to accumulate base values of an animation across repeating cycles.</span></span> <span data-ttu-id="c28e0-106">Например, если выбрать Повтор 9 раз анимации (<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> = «9 x») и задать свойство для анимации в диапазоне от 10 до 15 (From = 10 = 15), свойство анимируется от 10 до 15 во время первого цикла, от 15 до 20 во время второго цикла , от 20 до 25 во время третьего цикла и т. д.</span><span class="sxs-lookup"><span data-stu-id="c28e0-106">For example, if you set an animation to repeat 9 times (<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> = "9x") and you set the property to animate between 10 and 15 (From = 10 To = 15), the property animates from 10 to 15 during the first cycle, from 15 to 20 during the second cycle, from 20 to 25 during the third cycle, and so on.</span></span> <span data-ttu-id="c28e0-107">Таким образом каждый цикл анимации использует конечное значение анимации из предыдущего цикла анимации в качестве базового.</span><span class="sxs-lookup"><span data-stu-id="c28e0-107">Hence, each animation cycle uses the ending animation value from the previous animation cycle as its base value.</span></span>  
  
 <span data-ttu-id="c28e0-108">Можно использовать `IsCumulative` свойство с большинством базовых анимаций и большинство анимации ключевого кадра.</span><span class="sxs-lookup"><span data-stu-id="c28e0-108">You can use the `IsCumulative` property with most basic animations and most key frame animations.</span></span> <span data-ttu-id="c28e0-109">Дополнительные сведения см. в разделе [Общие сведения об анимации](animation-overview.md) и [сведения об анимации по ключевым кадрам](key-frame-animations-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c28e0-109">For more information, see [Animation Overview](animation-overview.md) and [Key-Frame Animations Overview](key-frame-animations-overview.md).</span></span>  
  
 <span data-ttu-id="c28e0-110">В следующем примере показано такое поведение при анимации ширины четыре прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="c28e0-110">The following example shows this behavior by animating the width of four rectangles.</span></span> <span data-ttu-id="c28e0-111">Пример:</span><span class="sxs-lookup"><span data-stu-id="c28e0-111">The example:</span></span>  
  
-   <span data-ttu-id="c28e0-112">Анимирует первый прямоугольник с <xref:System.Windows.Media.Animation.DoubleAnimation> и задает <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="c28e0-112">Animates the first rectangle with <xref:System.Windows.Media.Animation.DoubleAnimation> and sets the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to `true`.</span></span>  
  
-   <span data-ttu-id="c28e0-113">Анимирует второй прямоугольник с <xref:System.Windows.Media.Animation.DoubleAnimation> и задает <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> присваивается значение по умолчанию `false`.</span><span class="sxs-lookup"><span data-stu-id="c28e0-113">Animates the second rectangle with <xref:System.Windows.Media.Animation.DoubleAnimation> and sets the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to the default value of `false`.</span></span>  
  
-   <span data-ttu-id="c28e0-114">Анимирует третий прямоугольник с <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> и задает <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="c28e0-114">Animates the third rectangle with <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> and sets the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> property to `true`.</span></span>  
  
-   <span data-ttu-id="c28e0-115">Анимирует последний прямоугольник с <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> и задает <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> свойства `false`.</span><span class="sxs-lookup"><span data-stu-id="c28e0-115">Animates the last rectangle with <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> and sets the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> property to `false`.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#IsCumulativeWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsCumulativeExample.xaml#iscumulativewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="c28e0-116">См. также</span><span class="sxs-lookup"><span data-stu-id="c28e0-116">See also</span></span>

- [<span data-ttu-id="c28e0-117">Добавление выходного значения анимации к начальному значению анимации</span><span class="sxs-lookup"><span data-stu-id="c28e0-117">Add an Animation Output Value to an Animation Starting Value</span></span>](how-to-add-an-animation-output-value-to-an-animation-starting-value.md)
- [<span data-ttu-id="c28e0-118">Повторение анимации</span><span class="sxs-lookup"><span data-stu-id="c28e0-118">Repeat an Animation</span></span>](how-to-repeat-an-animation.md)
- [<span data-ttu-id="c28e0-119">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="c28e0-119">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="c28e0-120">Общие сведения об анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="c28e0-120">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="c28e0-121">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="c28e0-121">How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
