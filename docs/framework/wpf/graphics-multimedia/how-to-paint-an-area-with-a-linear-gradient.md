---
title: Как закрасить область с линейным градиентом
ms.date: 03/30/2017
helpviewer_keywords:
- linear gradients [WPF], painting with
- brushes [WPF], painting with linear gradients
- painting [WPF], with linear gradients
ms.assetid: 00e0cd04-48c0-4ec5-850e-d321beb37a34
ms.openlocfilehash: 76c491632911c48db34d932ba3895278591378a5
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452770"
---
# <a name="how-to-paint-an-area-with-a-linear-gradient"></a><span data-ttu-id="dc46e-102">Как закрасить область с линейным градиентом</span><span class="sxs-lookup"><span data-stu-id="dc46e-102">How to: Paint an Area with a Linear Gradient</span></span>
<span data-ttu-id="dc46e-103">В этом примере показано, как использовать класс <xref:System.Windows.Media.LinearGradientBrush> для заливки области с линейным градиентом.</span><span class="sxs-lookup"><span data-stu-id="dc46e-103">This example shows how to use the <xref:System.Windows.Media.LinearGradientBrush> class to paint an area with a linear gradient.</span></span> <span data-ttu-id="dc46e-104">В следующем примере <xref:System.Windows.Shapes.Shape.Fill%2A> <xref:System.Windows.Shapes.Rectangle> закрашивается диагональным линейным градиентом, который переходит от желтого к красному к темному зеленому.</span><span class="sxs-lookup"><span data-stu-id="dc46e-104">In the following example, the <xref:System.Windows.Shapes.Shape.Fill%2A> of a <xref:System.Windows.Shapes.Rectangle> is painted with a diagonal linear gradient that transitions from yellow to red to blue to lime green.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc46e-105">Пример</span><span class="sxs-lookup"><span data-stu-id="dc46e-105">Example</span></span>  
 [!code-xaml[GradientBrushExamples_snip#DiagonalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#diagonalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#DiagonalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#diagonalgradient1csharp)]  
  
 <span data-ttu-id="dc46e-106">На следующем рисунке показан градиент, созданный в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="dc46e-106">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="dc46e-107">![Диагональный линейный градиент](./media/graphicsmm-diagonallgb.jpg "graphicsmm_DiagonalLGB")</span><span class="sxs-lookup"><span data-stu-id="dc46e-107">![Diagonal linear gradient](./media/graphicsmm-diagonallgb.jpg "graphicsmm_DiagonalLGB")</span></span>  
  
 <span data-ttu-id="dc46e-108">Чтобы создать горизонтальный линейный градиент, измените <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> и <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> <xref:System.Windows.Media.LinearGradientBrush> на (0, 0,5) и (1, 0,5).</span><span class="sxs-lookup"><span data-stu-id="dc46e-108">To create a horizontal linear gradient, change the <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> and <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> of the <xref:System.Windows.Media.LinearGradientBrush> to (0,0.5) and (1,0.5).</span></span> <span data-ttu-id="dc46e-109">В следующем примере <xref:System.Windows.Shapes.Rectangle> закрашивается горизонтальным линейным градиентом.</span><span class="sxs-lookup"><span data-stu-id="dc46e-109">In the following example, a <xref:System.Windows.Shapes.Rectangle> is painted with a horizontal linear gradient.</span></span>  
  
 [!code-xaml[GradientBrushExamples_snip#HorizontalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#horizontalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#HorizontalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#horizontalgradient1csharp)]  
  
 <span data-ttu-id="dc46e-110">На следующем рисунке показан градиент, созданный в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="dc46e-110">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="dc46e-111">![Горизонтальный линейный градиент](./media/graphicsmm-horizontallgb.jpg "graphicsmm_HorizontalLGB")</span><span class="sxs-lookup"><span data-stu-id="dc46e-111">![A horizontal linear gradient](./media/graphicsmm-horizontallgb.jpg "graphicsmm_HorizontalLGB")</span></span>  
  
 <span data-ttu-id="dc46e-112">Чтобы создать Вертикальный линейный градиент, измените <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> и <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> <xref:System.Windows.Media.LinearGradientBrush> на (0,5, 0) и (0,5, 1).</span><span class="sxs-lookup"><span data-stu-id="dc46e-112">To create a vertical linear gradient, change the <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> and <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> of the <xref:System.Windows.Media.LinearGradientBrush> to (0.5,0) and (0.5,1).</span></span> <span data-ttu-id="dc46e-113">В следующем примере <xref:System.Windows.Shapes.Rectangle> закрашивается вертикальным линейным градиентом.</span><span class="sxs-lookup"><span data-stu-id="dc46e-113">In the following example, a <xref:System.Windows.Shapes.Rectangle> is painted with a vertical linear gradient.</span></span>  
  
 [!code-xaml[GradientBrushExamples_snip#VerticalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#verticalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#VerticalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#verticalgradient1csharp)]  
  
 <span data-ttu-id="dc46e-114">На следующем рисунке показан градиент, созданный в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="dc46e-114">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="dc46e-115">![Вертикальный линейный градиент](./media/graphicsmm-verticallgb.jpg "graphicsmm_VerticalLGB")</span><span class="sxs-lookup"><span data-stu-id="dc46e-115">![Vertical linear gradient](./media/graphicsmm-verticallgb.jpg "graphicsmm_VerticalLGB")</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dc46e-116">В примерах этого раздела используется система координат по умолчанию для установки начальных и конечных точек.</span><span class="sxs-lookup"><span data-stu-id="dc46e-116">The examples in this topic use the default coordinate system for setting start points and end points.</span></span> <span data-ttu-id="dc46e-117">Система координат по умолчанию задается относительно ограничивающего прямоугольника: 0 указывает 0 процентов ограничивающего прямоугольника, а 1 — 100 процентов ограничивающего прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="dc46e-117">The default coordinate system is relative to a bounding box: 0 indicates 0 percent of the bounding box, and 1 indicates 100 percent of the bounding box.</span></span> <span data-ttu-id="dc46e-118">Вы можете изменить эту систему координат, задав для свойства <xref:System.Windows.Media.GradientBrush.MappingMode%2A> значение <xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="dc46e-118">You can change this coordinate system by setting the <xref:System.Windows.Media.GradientBrush.MappingMode%2A> property to the value <xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType>.</span></span> <span data-ttu-id="dc46e-119">Абсолютная система координат не привязана к ограничивающему прямоугольнику.</span><span class="sxs-lookup"><span data-stu-id="dc46e-119">An absolute coordinate system is not relative to a bounding box.</span></span> <span data-ttu-id="dc46e-120">Значения интерпретируются непосредственно в локальной области.</span><span class="sxs-lookup"><span data-stu-id="dc46e-120">Values are interpreted directly in local space.</span></span>  
  
 <span data-ttu-id="dc46e-121">Дополнительные примеры см. в разделе [образец кистей](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span><span class="sxs-lookup"><span data-stu-id="dc46e-121">For additional examples, see [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span> <span data-ttu-id="dc46e-122">Дополнительные сведения о градиентах и других типах кистей см. [в статье Общие сведения о рисовании с помощью сплошных цветов и градиентов](painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="dc46e-122">For more information about gradients and other types of brushes, see [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>
