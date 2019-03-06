---
title: Практическое руководство. Создание прозрачного или полупрозрачного элемента UIElement
ms.date: 03/30/2017
helpviewer_keywords:
- UIElements [WPF], transparency
- opacity [WPF], of UIElements
- transparency of UIElements [WPF]
- UIElements [WPF], opacity
ms.assetid: a49fc8d6-7b32-4f28-9122-39b632a19b4b
ms.openlocfilehash: 1de9a7e11fee241ecb71242e9808e77b7e5e63b0
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57370531"
---
# <a name="how-to-make-a-uielement-transparent-or-semi-transparent"></a><span data-ttu-id="4efc7-102">Практическое руководство. Создание прозрачного или полупрозрачного элемента UIElement</span><span class="sxs-lookup"><span data-stu-id="4efc7-102">How to: Make a UIElement Transparent or Semi-Transparent</span></span>
<span data-ttu-id="4efc7-103">В этом примере показано, как сделать <xref:System.Windows.UIElement> прозрачным или полупрозрачным.</span><span class="sxs-lookup"><span data-stu-id="4efc7-103">This example shows how to make a <xref:System.Windows.UIElement> transparent or semi-transparent.</span></span> <span data-ttu-id="4efc7-104">Чтобы сделать элемент прозрачным или полупрозрачным, задайте его <xref:System.Windows.UIElement.Opacity%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="4efc7-104">To make an element transparent or semi-transparent, you set its <xref:System.Windows.UIElement.Opacity%2A> property.</span></span> <span data-ttu-id="4efc7-105">Значение `0.0` делает элемент полностью прозрачной, а значение `1.0` делает элемент полностью непрозрачным.</span><span class="sxs-lookup"><span data-stu-id="4efc7-105">A value of `0.0` makes the element completely transparent, while a value of `1.0` makes the element completely opaque.</span></span> <span data-ttu-id="4efc7-106">Значение `0.5` делает элемент 50% непрозрачный и т. д.</span><span class="sxs-lookup"><span data-stu-id="4efc7-106">A value of `0.5` makes the element 50% opaque, and so on.</span></span> <span data-ttu-id="4efc7-107">Элемента <xref:System.Windows.UIElement.Opacity%2A> присваивается `1.0` по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4efc7-107">An element's <xref:System.Windows.UIElement.Opacity%2A> is set to `1.0` by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4efc7-108">Пример</span><span class="sxs-lookup"><span data-stu-id="4efc7-108">Example</span></span>  
 <span data-ttu-id="4efc7-109">В следующем примере задается <xref:System.Windows.UIElement.Opacity%2A> кнопки `0.25`, что делает ее и ее содержимое (в данном случае текст кнопки) на 25% непрозрачной.</span><span class="sxs-lookup"><span data-stu-id="4efc7-109">The following example sets the <xref:System.Windows.UIElement.Opacity%2A> of a button to `0.25`, making it and its contents (in this case, the button's text) 25% opaque.</span></span>  
  
 [!code-xaml[brushsamples_snip#2](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#2)]  
  
 [!code-csharp[brushsamples_procedural_snip#2](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#2)]  
  
 <span data-ttu-id="4efc7-110">Если содержимое элемента имеют свой собственный <xref:System.Windows.UIElement.Opacity%2A> параметры, эти значения при умножении на содержащего элементы массива <xref:System.Windows.UIElement.Opacity%2A>.</span><span class="sxs-lookup"><span data-stu-id="4efc7-110">If an element's contents have their own <xref:System.Windows.UIElement.Opacity%2A> settings, those values are multiplied against the containing elements <xref:System.Windows.UIElement.Opacity%2A>.</span></span>  
  
 <span data-ttu-id="4efc7-111">В следующем примере задается кнопки <xref:System.Windows.UIElement.Opacity%2A> для `0.25`и <xref:System.Windows.UIElement.Opacity%2A> из <xref:System.Windows.Controls.Image> содержащегося в кнопку, чтобы `0.5`.</span><span class="sxs-lookup"><span data-stu-id="4efc7-111">The following example sets a button's <xref:System.Windows.UIElement.Opacity%2A> to `0.25`, and the <xref:System.Windows.UIElement.Opacity%2A> of an <xref:System.Windows.Controls.Image> control contained with in the button to `0.5`.</span></span> <span data-ttu-id="4efc7-112">В результате изображение отображается 12,5% непрозрачным: 0.25 \* 0.5 = 0.125.</span><span class="sxs-lookup"><span data-stu-id="4efc7-112">As a result, the image appears 12.5% opaque: 0.25 \* 0.5 = 0.125.</span></span>  
  
 [!code-xaml[brushsamples_snip#3](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#3)]  
  
 [!code-csharp[brushsamples_procedural_snip#3](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#3)]  
  
 <span data-ttu-id="4efc7-113">Другой способ управления прозрачностью элемента является установка прозрачности <xref:System.Windows.Media.Brush> , рисует элемент.</span><span class="sxs-lookup"><span data-stu-id="4efc7-113">Another way to control the opacity of an element is to set the opacity of the <xref:System.Windows.Media.Brush> that paints the element.</span></span> <span data-ttu-id="4efc7-114">Такой подход позволяет выборочно изменять непрозрачность частей элемента и дает выигрыш в производительности по сравнению с использованием этого элемента <xref:System.Windows.UIElement.Opacity%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="4efc7-114">This approach enables you to selectively alter the opacity of portions of an element, and provides performance benefits over using the element's <xref:System.Windows.UIElement.Opacity%2A> property.</span></span> <span data-ttu-id="4efc7-115">В следующем примере задается <xref:System.Windows.Media.Brush.Opacity%2A> из <xref:System.Windows.Media.SolidColorBrush> используется для закрашивания кнопки <xref:System.Windows.Controls.Control.Background%2A> присваивается `0.25`.</span><span class="sxs-lookup"><span data-stu-id="4efc7-115">The following example sets the <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.SolidColorBrush> used to paint the button's <xref:System.Windows.Controls.Control.Background%2A> is set to `0.25`.</span></span> <span data-ttu-id="4efc7-116">В результате кисти фона является непрозрачным на 25%, но его содержимое (текст кнопки) остаются 100% непрозрачный.</span><span class="sxs-lookup"><span data-stu-id="4efc7-116">As a result, the brush's background is 25% opaque, but its contents (the button's text) remain 100% opaque.</span></span>  
  
 [!code-xaml[brushsamples_snip#4](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#4)]  
  
 [!code-csharp[brushsamples_procedural_snip#4](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#4)]  
  
 <span data-ttu-id="4efc7-117">Вы также можете управлять непрозрачности отдельных цветов в кисти.</span><span class="sxs-lookup"><span data-stu-id="4efc7-117">You may also control the opacity of individual colors within a brush.</span></span> <span data-ttu-id="4efc7-118">Дополнительные сведения о цвета и кисти, см. в разделе [закраске сплошным цветом и градиентом Обзор](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4efc7-118">For more information about colors and brushes, see [Painting with Solid Colors and Gradients Overview](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).</span></span> <span data-ttu-id="4efc7-119">Пример, показывающий, как анимировать непрозрачности элемента, см. в разделе [Анимация прозрачности элемента или кисти](../graphics-multimedia/how-to-animate-the-opacity-of-an-element-or-brush.md).</span><span class="sxs-lookup"><span data-stu-id="4efc7-119">For an example showing how to animate an element's opacity, see [Animate the Opacity of an Element or Brush](../graphics-multimedia/how-to-animate-the-opacity-of-an-element-or-brush.md).</span></span>
