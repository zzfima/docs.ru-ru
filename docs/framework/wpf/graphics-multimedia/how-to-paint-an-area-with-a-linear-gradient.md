---
title: Практическое руководство. Заливка области с помощью линейного градиента
ms.date: 03/30/2017
helpviewer_keywords:
- linear gradients [WPF], painting with
- brushes [WPF], painting with linear gradients
- painting [WPF], with linear gradients
ms.assetid: 00e0cd04-48c0-4ec5-850e-d321beb37a34
ms.openlocfilehash: 92c9ccd846dbbce043d13e6ba82b9fa8e72fa8b5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916165"
---
# <a name="how-to-paint-an-area-with-a-linear-gradient"></a><span data-ttu-id="8855f-102">Практическое руководство. Заливка области с помощью линейного градиента</span><span class="sxs-lookup"><span data-stu-id="8855f-102">How to: Paint an Area with a Linear Gradient</span></span>
<span data-ttu-id="8855f-103">В этом примере показано, как использовать <xref:System.Windows.Media.LinearGradientBrush> класс для закрашивания области с линейным градиентом.</span><span class="sxs-lookup"><span data-stu-id="8855f-103">This example shows how to use the <xref:System.Windows.Media.LinearGradientBrush> class to paint an area with a linear gradient.</span></span> <span data-ttu-id="8855f-104">В следующем примере объект <xref:System.Windows.Shapes.Shape.Fill%2A> <xref:System.Windows.Shapes.Rectangle> для закрашивается с помощью диагонального линейного градиента, который переходит от желтого к красному к темному зеленому.</span><span class="sxs-lookup"><span data-stu-id="8855f-104">In the following example, the <xref:System.Windows.Shapes.Shape.Fill%2A> of a <xref:System.Windows.Shapes.Rectangle> is painted with a diagonal linear gradient that transitions from yellow to red to blue to lime green.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8855f-105">Пример</span><span class="sxs-lookup"><span data-stu-id="8855f-105">Example</span></span>  
 [!code-xaml[GradientBrushExamples_snip#DiagonalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#diagonalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#DiagonalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#diagonalgradient1csharp)]  
  
 <span data-ttu-id="8855f-106">На следующем рисунке показан градиент, созданный в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="8855f-106">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="8855f-107">![Диагональный линейный градиент](./media/graphicsmm-diagonallgb.jpg "graphicsmm_DiagonalLGB")</span><span class="sxs-lookup"><span data-stu-id="8855f-107">![Diagonal linear gradient](./media/graphicsmm-diagonallgb.jpg "graphicsmm_DiagonalLGB")</span></span>  
  
 <span data-ttu-id="8855f-108">Чтобы создать горизонтальный линейный градиент, измените <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> и <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> <xref:System.Windows.Media.LinearGradientBrush> в (0, 0,5) и (1, 0,5).</span><span class="sxs-lookup"><span data-stu-id="8855f-108">To create a horizontal linear gradient, change the <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> and <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> of the <xref:System.Windows.Media.LinearGradientBrush> to (0,0.5) and (1,0.5).</span></span> <span data-ttu-id="8855f-109">В следующем примере объект <xref:System.Windows.Shapes.Rectangle> рисуется с горизонтальным линейным градиентом.</span><span class="sxs-lookup"><span data-stu-id="8855f-109">In the following example, a <xref:System.Windows.Shapes.Rectangle> is painted with a horizontal linear gradient.</span></span>  
  
 [!code-xaml[GradientBrushExamples_snip#HorizontalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#horizontalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#HorizontalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#horizontalgradient1csharp)]  
  
 <span data-ttu-id="8855f-110">На следующем рисунке показан градиент, созданный в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="8855f-110">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="8855f-111">![Горизонтальный линейный градиент](./media/graphicsmm-horizontallgb.jpg "graphicsmm_HorizontalLGB")</span><span class="sxs-lookup"><span data-stu-id="8855f-111">![A horizontal linear gradient](./media/graphicsmm-horizontallgb.jpg "graphicsmm_HorizontalLGB")</span></span>  
  
 <span data-ttu-id="8855f-112">Чтобы создать Вертикальный линейный градиент, измените <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> значение <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> и <xref:System.Windows.Media.LinearGradientBrush> для на (0,5, 0) и (0,5, 1).</span><span class="sxs-lookup"><span data-stu-id="8855f-112">To create a vertical linear gradient, change the <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> and <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> of the <xref:System.Windows.Media.LinearGradientBrush> to (0.5,0) and (0.5,1).</span></span> <span data-ttu-id="8855f-113">В следующем примере объект <xref:System.Windows.Shapes.Rectangle> рисуется с помощью вертикального линейного градиента.</span><span class="sxs-lookup"><span data-stu-id="8855f-113">In the following example, a <xref:System.Windows.Shapes.Rectangle> is painted with a vertical linear gradient.</span></span>  
  
 [!code-xaml[GradientBrushExamples_snip#VerticalGradient1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#verticalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#VerticalGradient1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#verticalgradient1csharp)]  
  
 <span data-ttu-id="8855f-114">На следующем рисунке показан градиент, созданный в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="8855f-114">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="8855f-115">![Вертикальный линейный градиент](./media/graphicsmm-verticallgb.jpg "graphicsmm_VerticalLGB")</span><span class="sxs-lookup"><span data-stu-id="8855f-115">![Vertical linear gradient](./media/graphicsmm-verticallgb.jpg "graphicsmm_VerticalLGB")</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8855f-116">В примерах этого раздела используется система координат по умолчанию для установки начальных и конечных точек.</span><span class="sxs-lookup"><span data-stu-id="8855f-116">The examples in this topic use the default coordinate system for setting start points and end points.</span></span> <span data-ttu-id="8855f-117">Система координат по умолчанию относится к ограничивающему прямоугольнику: 0 указывает 0 процентов ограничивающего прямоугольника, а 1 указывает 100 процентов ограничивающего прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="8855f-117">The default coordinate system is relative to a bounding box: 0 indicates 0 percent of the bounding box, and 1 indicates 100 percent of the bounding box.</span></span> <span data-ttu-id="8855f-118">Вы можете изменить эту систему координат, задав <xref:System.Windows.Media.GradientBrush.MappingMode%2A> для свойства значение. <xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="8855f-118">You can change this coordinate system by setting the <xref:System.Windows.Media.GradientBrush.MappingMode%2A> property to the value <xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType>.</span></span> <span data-ttu-id="8855f-119">Абсолютная система координат не привязана к ограничивающему прямоугольнику.</span><span class="sxs-lookup"><span data-stu-id="8855f-119">An absolute coordinate system is not relative to a bounding box.</span></span> <span data-ttu-id="8855f-120">Значения интерпретируются непосредственно в локальной области.</span><span class="sxs-lookup"><span data-stu-id="8855f-120">Values are interpreted directly in local space.</span></span>  
  
 <span data-ttu-id="8855f-121">Дополнительные примеры см. в разделе [образец кистей](https://go.microsoft.com/fwlink/?LinkID=159973).</span><span class="sxs-lookup"><span data-stu-id="8855f-121">For additional examples, see [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span></span> <span data-ttu-id="8855f-122">Дополнительные сведения о градиентах и других типах кистей см. [в статье Общие сведения о рисовании с помощью сплошных цветов и градиентов](painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8855f-122">For more information about gradients and other types of brushes, see [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>
