---
title: "Практическое руководство. Как сделать UIElement прозрачным или полупрозрачным"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UIElements [WPF], transparency
- opacity [WPF], of UIElements
- transparency of UIElements [WPF]
- UIElements [WPF], opacity
ms.assetid: a49fc8d6-7b32-4f28-9122-39b632a19b4b
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 25245319c02ae376410d71afb7a1e56eda259e99
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-make-a-uielement-transparent-or-semi-transparent"></a><span data-ttu-id="7728f-102">Практическое руководство. Как сделать UIElement прозрачным или полупрозрачным</span><span class="sxs-lookup"><span data-stu-id="7728f-102">How to: Make a UIElement Transparent or Semi-Transparent</span></span>
<span data-ttu-id="7728f-103">В этом примере показано, как сделать <xref:System.Windows.UIElement> прозрачным или полупрозрачным.</span><span class="sxs-lookup"><span data-stu-id="7728f-103">This example shows how to make a <xref:System.Windows.UIElement> transparent or semi-transparent.</span></span> <span data-ttu-id="7728f-104">Чтобы сделать элемент прозрачным или полупрозрачным, задайте его <xref:System.Windows.UIElement.Opacity%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="7728f-104">To make an element transparent or semi-transparent, you set its <xref:System.Windows.UIElement.Opacity%2A> property.</span></span> <span data-ttu-id="7728f-105">Значение `0.0` делает элемент полностью прозрачной, а значение `1.0` делает элемент полностью непрозрачным.</span><span class="sxs-lookup"><span data-stu-id="7728f-105">A value of `0.0` makes the element completely transparent, while a value of `1.0` makes the element completely opaque.</span></span> <span data-ttu-id="7728f-106">Значение `0.5` делает элемент 50% непрозрачный и т. д.</span><span class="sxs-lookup"><span data-stu-id="7728f-106">A value of `0.5` makes the element 50% opaque, and so on.</span></span> <span data-ttu-id="7728f-107">Элемент <xref:System.Windows.UIElement.Opacity%2A> равно `1.0` по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7728f-107">An element's <xref:System.Windows.UIElement.Opacity%2A> is set to `1.0` by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7728f-108">Пример</span><span class="sxs-lookup"><span data-stu-id="7728f-108">Example</span></span>  
 <span data-ttu-id="7728f-109">В следующем примере задается <xref:System.Windows.UIElement.Opacity%2A> кнопку, чтобы `0.25`, что делает ее и ее содержимое (в данном случае текст кнопки) на 25% непрозрачной.</span><span class="sxs-lookup"><span data-stu-id="7728f-109">The following example sets the <xref:System.Windows.UIElement.Opacity%2A> of a button to `0.25`, making it and its contents (in this case, the button's text) 25% opaque.</span></span>  
  
 [!code-xaml[brushsamples_snip#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#2)]  
  
 [!code-csharp[brushsamples_procedural_snip#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#2)]  
  
 <span data-ttu-id="7728f-110">Если содержимое элемента имеют свой собственный <xref:System.Windows.UIElement.Opacity%2A> параметры, эти значения умножаются от содержащего элементы <xref:System.Windows.UIElement.Opacity%2A>.</span><span class="sxs-lookup"><span data-stu-id="7728f-110">If an element's contents have their own <xref:System.Windows.UIElement.Opacity%2A> settings, those values are multiplied against the containing elements <xref:System.Windows.UIElement.Opacity%2A>.</span></span>  
  
 <span data-ttu-id="7728f-111">В следующем примере задается кнопки <xref:System.Windows.UIElement.Opacity%2A> для `0.25`и <xref:System.Windows.UIElement.Opacity%2A> из <xref:System.Windows.Controls.Image> содержащегося в кнопку, чтобы `0.5`.</span><span class="sxs-lookup"><span data-stu-id="7728f-111">The following example sets a button's <xref:System.Windows.UIElement.Opacity%2A> to `0.25`, and the <xref:System.Windows.UIElement.Opacity%2A> of an <xref:System.Windows.Controls.Image> control contained with in the button to `0.5`.</span></span> <span data-ttu-id="7728f-112">В результате изображение отображается 12,5% непрозрачным: 0,25 * 0,5 = 0,125.</span><span class="sxs-lookup"><span data-stu-id="7728f-112">As a result, the image appears 12.5% opaque: 0.25 * 0.5 = 0.125.</span></span>  
  
 [!code-xaml[brushsamples_snip#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#3)]  
  
 [!code-csharp[brushsamples_procedural_snip#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#3)]  
  
 <span data-ttu-id="7728f-113">Другой способ управления прозрачностью элемента является установка степени непрозрачности <xref:System.Windows.Media.Brush> которая рисует элемент.</span><span class="sxs-lookup"><span data-stu-id="7728f-113">Another way to control the opacity of an element is to set the opacity of the <xref:System.Windows.Media.Brush> that paints the element.</span></span> <span data-ttu-id="7728f-114">Такой подход позволяет выборочно изменения непрозрачности отдельных частей элемента и дает выигрыш в производительности по сравнению с использованием элемента <xref:System.Windows.UIElement.Opacity%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="7728f-114">This approach enables you to selectively alter the opacity of portions of an element, and provides performance benefits over using the element's <xref:System.Windows.UIElement.Opacity%2A> property.</span></span> <span data-ttu-id="7728f-115">В следующем примере задается <xref:System.Windows.Media.Brush.Opacity%2A> из <xref:System.Windows.Media.SolidColorBrush> используется для рисования кнопки <xref:System.Windows.Controls.Control.Background%2A> равно `0.25`.</span><span class="sxs-lookup"><span data-stu-id="7728f-115">The following example sets the <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.SolidColorBrush> used to paint the button's <xref:System.Windows.Controls.Control.Background%2A> is set to `0.25`.</span></span> <span data-ttu-id="7728f-116">В результате кисти фона — непрозрачный 25%, но его содержимое (текст кнопки) остаются 100% непрозрачным.</span><span class="sxs-lookup"><span data-stu-id="7728f-116">As a result, the brush's background is 25% opaque, but its contents (the button's text) remain 100% opaque.</span></span>  
  
 [!code-xaml[brushsamples_snip#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/OpacityExample.xaml#4)]  
  
 [!code-csharp[brushsamples_procedural_snip#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/OpacityExample.cs#4)]  
  
 <span data-ttu-id="7728f-117">Можно также управлять прозрачностью отдельных цветов в кисти.</span><span class="sxs-lookup"><span data-stu-id="7728f-117">You may also control the opacity of individual colors within a brush.</span></span> <span data-ttu-id="7728f-118">Дополнительные сведения о цветах и кистях см. в разделе [Рисование с сплошные цвета и градиенты Обзор](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7728f-118">For more information about colors and brushes, see [Painting with Solid Colors and Gradients Overview](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).</span></span> <span data-ttu-id="7728f-119">Пример, в котором показана анимация непрозрачности элемента см. в разделе [Анимация прозрачности элемента или кисти](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-the-opacity-of-an-element-or-brush.md).</span><span class="sxs-lookup"><span data-stu-id="7728f-119">For an example showing how to animate an element's opacity, see [Animate the Opacity of an Element or Brush](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-the-opacity-of-an-element-or-brush.md).</span></span>
