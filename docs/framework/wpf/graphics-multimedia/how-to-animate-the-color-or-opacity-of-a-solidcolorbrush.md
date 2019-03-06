---
title: Практическое руководство. Анимация цвета или прозрачности SolidColorBrush
ms.date: 03/30/2017
helpviewer_keywords:
- SolidColorBrush [WPF], animating color of
- colors [WPF], animating
- opacity [WPF], animating
- animation [WPF], color of SolidColorBrush
- animation [WPF], opacity of SolidColorBrush
- SolidColorBrush [WPF], animating opacity of
ms.assetid: d9154354-843f-4713-bad1-35bb0ba6eaeb
ms.openlocfilehash: 541835a7827467aeceb1ed72e54b69e62dc4f916
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57354444"
---
# <a name="how-to-animate-the-color-or-opacity-of-a-solidcolorbrush"></a><span data-ttu-id="6d187-102">Практическое руководство. Анимация цвета или прозрачности SolidColorBrush</span><span class="sxs-lookup"><span data-stu-id="6d187-102">How to: Animate the Color or Opacity of a SolidColorBrush</span></span>
<span data-ttu-id="6d187-103">В этом примере демонстрируется анимация <xref:System.Windows.Media.SolidColorBrush.Color%2A> и <xref:System.Windows.Media.Brush.Opacity%2A> из <xref:System.Windows.Media.SolidColorBrush>.</span><span class="sxs-lookup"><span data-stu-id="6d187-103">This example shows how to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> and <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.SolidColorBrush>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d187-104">Пример</span><span class="sxs-lookup"><span data-stu-id="6d187-104">Example</span></span>  
 <span data-ttu-id="6d187-105">В следующем примере используется три анимации для анимирования <xref:System.Windows.Media.SolidColorBrush.Color%2A> и <xref:System.Windows.Media.Brush.Opacity%2A> из <xref:System.Windows.Media.SolidColorBrush>.</span><span class="sxs-lookup"><span data-stu-id="6d187-105">The following example uses three animations to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> and <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.SolidColorBrush>.</span></span>  
  
-   <span data-ttu-id="6d187-106">Первая анимация, <xref:System.Windows.Media.Animation.ColorAnimation>, изменяет цвет кисти на <xref:System.Windows.Media.Colors.Gray%2A> когда указатель мыши перемещается прямоугольник.</span><span class="sxs-lookup"><span data-stu-id="6d187-106">The first animation, a <xref:System.Windows.Media.Animation.ColorAnimation>, changes the brush's color to <xref:System.Windows.Media.Colors.Gray%2A> when the mouse enters the rectangle.</span></span>  
  
-   <span data-ttu-id="6d187-107">Следующая анимация, другой <xref:System.Windows.Media.Animation.ColorAnimation>, изменяет цвет кисти на <xref:System.Windows.Media.Colors.Orange%2A> когда указатель мыши покидает прямоугольник.</span><span class="sxs-lookup"><span data-stu-id="6d187-107">The next animation, another <xref:System.Windows.Media.Animation.ColorAnimation>, changes the brush's color to <xref:System.Windows.Media.Colors.Orange%2A> when the mouse leaves the rectangle.</span></span>  
  
-   <span data-ttu-id="6d187-108">Последняя анимация, <xref:System.Windows.Media.Animation.DoubleAnimation>, изменяет непрозрачность кисти на 0.0 при нажатии левой кнопки мыши.</span><span class="sxs-lookup"><span data-stu-id="6d187-108">The final animation, a <xref:System.Windows.Media.Animation.DoubleAnimation>, changes the brush's opacity to 0.0 when the left mouse button is pressed.</span></span>  
  
 [!code-csharp[brushanimations_snip#SolidColorBrushAnimationExample](~/samples/snippets/csharp/VS_Snippets_Wpf/brushanimations_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushanimationexample)]  
  
 <span data-ttu-id="6d187-109">Более полный пример, в котором показано, как анимировать различные типы кисти, см. в разделе [пример использования кистей](https://go.microsoft.com/fwlink/?LinkID=159973).</span><span class="sxs-lookup"><span data-stu-id="6d187-109">For a more complete sample, which shows how to animate different types of brushes, see the [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span></span> <span data-ttu-id="6d187-110">Дополнительные сведения об анимации см. в разделе [Общие сведения об анимации](animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="6d187-110">For more information about animation, see the [Animation Overview](animation-overview.md).</span></span>  
  
 <span data-ttu-id="6d187-111">Для обеспечения согласованности с другими примерами анимации версии кода этого примера используют <xref:System.Windows.Media.Animation.Storyboard> объекта для применения соответствующих анимаций.</span><span class="sxs-lookup"><span data-stu-id="6d187-111">For consistency with other animation examples, the code versions of this example use a <xref:System.Windows.Media.Animation.Storyboard> object to apply their animations.</span></span> <span data-ttu-id="6d187-112">Тем не менее, при применении в коде одной анимации, проще использовать <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> метода вместо использования <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="6d187-112">However, when applying a single animation in code, it's simpler to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method instead of using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="6d187-113">Пример см. в разделе [Анимация свойства без использования раскадровки](how-to-animate-a-property-without-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="6d187-113">For an example, see [Animate a Property Without Using a Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d187-114">См. также</span><span class="sxs-lookup"><span data-stu-id="6d187-114">See also</span></span>
- [<span data-ttu-id="6d187-115">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="6d187-115">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="6d187-116">Общие сведения о раскадровке</span><span class="sxs-lookup"><span data-stu-id="6d187-116">Storyboards Overview</span></span>](storyboards-overview.md)
- [<span data-ttu-id="6d187-117">Пример использования кистей</span><span class="sxs-lookup"><span data-stu-id="6d187-117">Brushes Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159973)
