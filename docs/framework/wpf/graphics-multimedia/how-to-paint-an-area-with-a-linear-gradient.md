---
title: Как закрасить область с линейным градиентом
ms.date: 03/30/2017
helpviewer_keywords:
- linear gradients [WPF], painting with
- brushes [WPF], painting with linear gradients
- painting [WPF], with linear gradients
ms.assetid: 00e0cd04-48c0-4ec5-850e-d321beb37a34
ms.openlocfilehash: ec07a0c33468681f67d086ec3d1d58b378412ff9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560881"
---
# <a name="how-to-paint-an-area-with-a-linear-gradient"></a><span data-ttu-id="36004-102">Как закрасить область с линейным градиентом</span><span class="sxs-lookup"><span data-stu-id="36004-102">How to: Paint an Area with a Linear Gradient</span></span>
<span data-ttu-id="36004-103">В этом примере показано, как использовать <xref:System.Windows.Media.LinearGradientBrush> класса Закраска области с линейным градиентом.</span><span class="sxs-lookup"><span data-stu-id="36004-103">This example shows how to use the <xref:System.Windows.Media.LinearGradientBrush> class to paint an area with a linear gradient.</span></span> <span data-ttu-id="36004-104">В следующем примере <xref:System.Windows.Shapes.Shape.Fill%2A> из <xref:System.Windows.Shapes.Rectangle> отрисовывается с диагонального линейного градиента, которая переходит с желтого на красный цвет на синий и зеленого.</span><span class="sxs-lookup"><span data-stu-id="36004-104">In the following example, the <xref:System.Windows.Shapes.Shape.Fill%2A> of a <xref:System.Windows.Shapes.Rectangle> is painted with a diagonal linear gradient that transitions from yellow to red to blue to lime green.</span></span>  
  
## <a name="example"></a><span data-ttu-id="36004-105">Пример</span><span class="sxs-lookup"><span data-stu-id="36004-105">Example</span></span>  
 [!code-xaml[GradientBrushExamples_snip#DiagonalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#diagonalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#DiagonalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#diagonalgradient1csharp)]  
  
 <span data-ttu-id="36004-106">Ниже показан градиент, созданный в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="36004-106">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="36004-107">![Диагональный линейный градиент](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-diagonallgb.jpg "graphicsmm_DiagonalLGB")</span><span class="sxs-lookup"><span data-stu-id="36004-107">![Diagonal linear gradient](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-diagonallgb.jpg "graphicsmm_DiagonalLGB")</span></span>  
  
 <span data-ttu-id="36004-108">Чтобы создать горизонтальный линейный градиент, измените <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> и <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> из <xref:System.Windows.Media.LinearGradientBrush> для (0,0.5) и (1,0.5).</span><span class="sxs-lookup"><span data-stu-id="36004-108">To create a horizontal linear gradient, change the <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> and <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> of the <xref:System.Windows.Media.LinearGradientBrush> to (0,0.5) and (1,0.5).</span></span> <span data-ttu-id="36004-109">В следующем примере <xref:System.Windows.Shapes.Rectangle> отрисовывается с горизонтального линейного градиента.</span><span class="sxs-lookup"><span data-stu-id="36004-109">In the following example, a <xref:System.Windows.Shapes.Rectangle> is painted with a horizontal linear gradient.</span></span>  
  
 [!code-xaml[GradientBrushExamples_snip#HorizontalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#horizontalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#HorizontalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#horizontalgradient1csharp)]  
  
 <span data-ttu-id="36004-110">Ниже показан градиент, созданный в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="36004-110">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="36004-111">![Горизонтальный линейный градиент](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-horizontallgb.jpg "graphicsmm_HorizontalLGB")</span><span class="sxs-lookup"><span data-stu-id="36004-111">![A horizontal linear gradient](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-horizontallgb.jpg "graphicsmm_HorizontalLGB")</span></span>  
  
 <span data-ttu-id="36004-112">Чтобы создать Вертикальный линейный градиент, измените <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> и <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> из <xref:System.Windows.Media.LinearGradientBrush> на (0.5,0) и (0.5,1).</span><span class="sxs-lookup"><span data-stu-id="36004-112">To create a vertical linear gradient, change the <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> and <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> of the <xref:System.Windows.Media.LinearGradientBrush> to (0.5,0) and (0.5,1).</span></span> <span data-ttu-id="36004-113">В следующем примере <xref:System.Windows.Shapes.Rectangle> отрисовывается с помощью вертикального линейного градиента.</span><span class="sxs-lookup"><span data-stu-id="36004-113">In the following example, a <xref:System.Windows.Shapes.Rectangle> is painted with a vertical linear gradient.</span></span>  
  
 [!code-xaml[GradientBrushExamples_snip#VerticalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#verticalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#VerticalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#verticalgradient1csharp)]  
  
 <span data-ttu-id="36004-114">Ниже показан градиент, созданный в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="36004-114">The following illustration shows the gradient created by the previous example.</span></span>  
  
 <span data-ttu-id="36004-115">![Вертикальный линейный градиент](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-verticallgb.jpg "graphicsmm_VerticalLGB")</span><span class="sxs-lookup"><span data-stu-id="36004-115">![Vertical linear gradient](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-verticallgb.jpg "graphicsmm_VerticalLGB")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="36004-116">В примерах в этом разделе используется система координат по умолчанию для установки начальной и конечной точек.</span><span class="sxs-lookup"><span data-stu-id="36004-116">The examples in this topic use the default coordinate system for setting start points and end points.</span></span> <span data-ttu-id="36004-117">Система координат по умолчанию задается относительно ограничивающего прямоугольника: 0 указывает 0 процентов ограничивающего прямоугольника, а 1 — 100 процентов ограничивающего прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="36004-117">The default coordinate system is relative to a bounding box: 0 indicates 0 percent of the bounding box, and 1 indicates 100 percent of the bounding box.</span></span> <span data-ttu-id="36004-118">Можно изменить эту систему координат, задав <xref:System.Windows.Media.GradientBrush.MappingMode%2A> значение <xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="36004-118">You can change this coordinate system by setting the <xref:System.Windows.Media.GradientBrush.MappingMode%2A> property to the value <xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType>.</span></span> <span data-ttu-id="36004-119">Абсолютная система координат не привязана к ограничивающему прямоугольнику.</span><span class="sxs-lookup"><span data-stu-id="36004-119">An absolute coordinate system is not relative to a bounding box.</span></span> <span data-ttu-id="36004-120">Значения интерпретируются непосредственно в локальной области.</span><span class="sxs-lookup"><span data-stu-id="36004-120">Values are interpreted directly in local space.</span></span>  
  
 <span data-ttu-id="36004-121">Дополнительные примеры см. в разделе [образец кисти](http://go.microsoft.com/fwlink/?LinkID=159973).</span><span class="sxs-lookup"><span data-stu-id="36004-121">For additional examples, see [Brushes Sample](http://go.microsoft.com/fwlink/?LinkID=159973).</span></span> <span data-ttu-id="36004-122">Дополнительные сведения о градиенте и других типах кистей см. в разделе [Рисование с сплошные цвета и градиенты Обзор](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="36004-122">For more information about gradients and other types of brushes, see [Painting with Solid Colors and Gradients Overview](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).</span></span>
