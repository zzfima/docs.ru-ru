---
title: "Практическое руководство. Анимация свойства \"Цвет\" или \"Непрозрачность\" элемента SolidColorBrush"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SolidColorBrush [WPF], animating color of
- colors [WPF], animating
- opacity [WPF], animating
- animation [WPF], color of SolidColorBrush
- animation [WPF], opacity of SolidColorBrush
- SolidColorBrush [WPF], animating opacity of
ms.assetid: d9154354-843f-4713-bad1-35bb0ba6eaeb
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 03052cdf68a5a8564d5a24c91521749c10afa6cc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-the-color-or-opacity-of-a-solidcolorbrush"></a><span data-ttu-id="c1c45-102">Практическое руководство. Анимация свойства "Цвет" или "Непрозрачность" элемента SolidColorBrush</span><span class="sxs-lookup"><span data-stu-id="c1c45-102">How to: Animate the Color or Opacity of a SolidColorBrush</span></span>
<span data-ttu-id="c1c45-103">В этом примере демонстрируется анимация <xref:System.Windows.Media.SolidColorBrush.Color%2A> и <xref:System.Windows.Media.Brush.Opacity%2A> из <xref:System.Windows.Media.SolidColorBrush>.</span><span class="sxs-lookup"><span data-stu-id="c1c45-103">This example shows how to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> and <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.SolidColorBrush>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c1c45-104">Пример</span><span class="sxs-lookup"><span data-stu-id="c1c45-104">Example</span></span>  
 <span data-ttu-id="c1c45-105">В следующем примере используется три анимации для анимации <xref:System.Windows.Media.SolidColorBrush.Color%2A> и <xref:System.Windows.Media.Brush.Opacity%2A> из <xref:System.Windows.Media.SolidColorBrush>.</span><span class="sxs-lookup"><span data-stu-id="c1c45-105">The following example uses three animations to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> and <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.SolidColorBrush>.</span></span>  
  
-   <span data-ttu-id="c1c45-106">Первая анимация <xref:System.Windows.Media.Animation.ColorAnimation>, изменяет цвет кисти на <xref:System.Windows.Media.Colors.Gray%2A> когда указатель мыши попадает на прямоугольник.</span><span class="sxs-lookup"><span data-stu-id="c1c45-106">The first animation, a <xref:System.Windows.Media.Animation.ColorAnimation>, changes the brush's color to <xref:System.Windows.Media.Colors.Gray%2A> when the mouse enters the rectangle.</span></span>  
  
-   <span data-ttu-id="c1c45-107">Далее анимации другой <xref:System.Windows.Media.Animation.ColorAnimation>, изменяет цвет кисти на <xref:System.Windows.Media.Colors.Orange%2A> когда указатель мыши выходит за пределы прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="c1c45-107">The next animation, another <xref:System.Windows.Media.Animation.ColorAnimation>, changes the brush's color to <xref:System.Windows.Media.Colors.Orange%2A> when the mouse leaves the rectangle.</span></span>  
  
-   <span data-ttu-id="c1c45-108">Последняя анимация <xref:System.Windows.Media.Animation.DoubleAnimation>, изменяет непрозрачность кисти 0,0 при нажатии левой кнопки мыши.</span><span class="sxs-lookup"><span data-stu-id="c1c45-108">The final animation, a <xref:System.Windows.Media.Animation.DoubleAnimation>, changes the brush's opacity to 0.0 when the left mouse button is pressed.</span></span>  
  
 [!code-csharp[brushanimations_snip#SolidColorBrushAnimationExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushanimations_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushanimationexample)]  
  
 <span data-ttu-id="c1c45-109">Более полный пример, в котором показано, как анимировать различные типы кистей, в разделе [образец кисти](http://go.microsoft.com/fwlink/?LinkID=159973).</span><span class="sxs-lookup"><span data-stu-id="c1c45-109">For a more complete sample, which shows how to animate different types of brushes, see the [Brushes Sample](http://go.microsoft.com/fwlink/?LinkID=159973).</span></span> <span data-ttu-id="c1c45-110">Дополнительные сведения об анимации см. в разделе [Обзор анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c1c45-110">For more information about animation, see the [Animation Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span></span>  
  
 <span data-ttu-id="c1c45-111">Для совместимости с другими примерами анимации версии кода этого примера используют <xref:System.Windows.Media.Animation.Storyboard> объекта для применения соответствующих анимаций.</span><span class="sxs-lookup"><span data-stu-id="c1c45-111">For consistency with other animation examples, the code versions of this example use a <xref:System.Windows.Media.Animation.Storyboard> object to apply their animations.</span></span> <span data-ttu-id="c1c45-112">Однако при применении одной анимации в коде, проще использовать <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> метод вместо <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="c1c45-112">However, when applying a single animation in code, it's simpler to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method instead of using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="c1c45-113">Пример см. в разделе [Анимация свойства без использования раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="c1c45-113">For an example, see [Animate a Property Without Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1c45-114">См. также</span><span class="sxs-lookup"><span data-stu-id="c1c45-114">See Also</span></span>  
 [<span data-ttu-id="c1c45-115">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="c1c45-115">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="c1c45-116">Общие сведения о раскадровке</span><span class="sxs-lookup"><span data-stu-id="c1c45-116">Storyboards Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)  
 [<span data-ttu-id="c1c45-117">Пример использования кистей</span><span class="sxs-lookup"><span data-stu-id="c1c45-117">Brushes Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=159973)
