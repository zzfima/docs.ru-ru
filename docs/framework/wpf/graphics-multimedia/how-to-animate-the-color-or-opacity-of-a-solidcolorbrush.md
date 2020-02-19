---
title: Практическое руководство. Анимация свойства "Цвет" или "Непрозрачность" элемента SolidColorBrush
ms.date: 03/30/2017
helpviewer_keywords:
- SolidColorBrush [WPF], animating color of
- colors [WPF], animating
- opacity [WPF], animating
- animation [WPF], color of SolidColorBrush
- animation [WPF], opacity of SolidColorBrush
- SolidColorBrush [WPF], animating opacity of
ms.assetid: d9154354-843f-4713-bad1-35bb0ba6eaeb
ms.openlocfilehash: 08b85935e0cb1ababd1fb63b9d02518ea3fcfa17
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452887"
---
# <a name="how-to-animate-the-color-or-opacity-of-a-solidcolorbrush"></a><span data-ttu-id="b96ec-102">Практическое руководство. Анимация свойства "Цвет" или "Непрозрачность" элемента SolidColorBrush</span><span class="sxs-lookup"><span data-stu-id="b96ec-102">How to: Animate the Color or Opacity of a SolidColorBrush</span></span>
<span data-ttu-id="b96ec-103">В этом примере показано, как анимировать <xref:System.Windows.Media.SolidColorBrush.Color%2A> и <xref:System.Windows.Media.Brush.Opacity%2A> <xref:System.Windows.Media.SolidColorBrush>.</span><span class="sxs-lookup"><span data-stu-id="b96ec-103">This example shows how to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> and <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.SolidColorBrush>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b96ec-104">Пример</span><span class="sxs-lookup"><span data-stu-id="b96ec-104">Example</span></span>  
 <span data-ttu-id="b96ec-105">В следующем примере три анимации используются для анимации <xref:System.Windows.Media.SolidColorBrush.Color%2A> и <xref:System.Windows.Media.Brush.Opacity%2A> <xref:System.Windows.Media.SolidColorBrush>.</span><span class="sxs-lookup"><span data-stu-id="b96ec-105">The following example uses three animations to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> and <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.SolidColorBrush>.</span></span>  
  
- <span data-ttu-id="b96ec-106">Первая анимация, <xref:System.Windows.Media.Animation.ColorAnimation>, изменяет цвет кисти на <xref:System.Windows.Media.Colors.Gray%2A>, когда указатель мыши попадает в прямоугольник.</span><span class="sxs-lookup"><span data-stu-id="b96ec-106">The first animation, a <xref:System.Windows.Media.Animation.ColorAnimation>, changes the brush's color to <xref:System.Windows.Media.Colors.Gray%2A> when the mouse enters the rectangle.</span></span>  
  
- <span data-ttu-id="b96ec-107">Следующая анимация, другая <xref:System.Windows.Media.Animation.ColorAnimation>, изменяет цвет кисти на <xref:System.Windows.Media.Colors.Orange%2A>, когда указатель мыши покидает прямоугольник.</span><span class="sxs-lookup"><span data-stu-id="b96ec-107">The next animation, another <xref:System.Windows.Media.Animation.ColorAnimation>, changes the brush's color to <xref:System.Windows.Media.Colors.Orange%2A> when the mouse leaves the rectangle.</span></span>  
  
- <span data-ttu-id="b96ec-108">Последняя анимация, <xref:System.Windows.Media.Animation.DoubleAnimation>, изменяет непрозрачность кисти на 0,0 при нажатии левой кнопки мыши.</span><span class="sxs-lookup"><span data-stu-id="b96ec-108">The final animation, a <xref:System.Windows.Media.Animation.DoubleAnimation>, changes the brush's opacity to 0.0 when the left mouse button is pressed.</span></span>  
  
 [!code-csharp[brushanimations_snip#SolidColorBrushAnimationExample](~/samples/snippets/csharp/VS_Snippets_Wpf/brushanimations_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushanimationexample)]  
  
 <span data-ttu-id="b96ec-109">Более полный пример, демонстрирующий анимацию различных типов кистей, см. в [примере кисти](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span><span class="sxs-lookup"><span data-stu-id="b96ec-109">For a more complete sample, which shows how to animate different types of brushes, see the [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span> <span data-ttu-id="b96ec-110">Дополнительные сведения о анимации см. в разделе [Общие сведения об анимации](animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b96ec-110">For more information about animation, see the [Animation Overview](animation-overview.md).</span></span>  
  
 <span data-ttu-id="b96ec-111">Для обеспечения согласованности с другими примерами анимации в версиях кода этого примера для применения анимации используется объект <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="b96ec-111">For consistency with other animation examples, the code versions of this example use a <xref:System.Windows.Media.Animation.Storyboard> object to apply their animations.</span></span> <span data-ttu-id="b96ec-112">Однако при применении одной анимации в коде проще использовать <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> метод вместо использования <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="b96ec-112">However, when applying a single animation in code, it's simpler to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method instead of using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="b96ec-113">Пример см. в разделе [Анимация свойства без использования раскадровки](how-to-animate-a-property-without-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="b96ec-113">For an example, see [Animate a Property Without Using a Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b96ec-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b96ec-114">See also</span></span>

- [<span data-ttu-id="b96ec-115">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="b96ec-115">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="b96ec-116">Общие сведения о раскадровке</span><span class="sxs-lookup"><span data-stu-id="b96ec-116">Storyboards Overview</span></span>](storyboards-overview.md)
- [<span data-ttu-id="b96ec-117">Пример использования кистей</span><span class="sxs-lookup"><span data-stu-id="b96ec-117">Brushes Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)
