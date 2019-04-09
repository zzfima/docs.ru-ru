---
title: Практическое руководство. Создание объекта GeometryDrawing
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], renderable
- renderable shapes [WPF]
- graphics [WPF], GeometryDrawing class
- classes [WPF], GeometryDrawing
ms.assetid: 11d3c096-91ba-4d41-9bba-aeac0db70f97
ms.openlocfilehash: f5cdcfdb68ad8030bcbd6c689f45a8baddd000e1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59179794"
---
# <a name="how-to-create-a-geometrydrawing"></a><span data-ttu-id="7028f-102">Практическое руководство. Создание объекта GeometryDrawing</span><span class="sxs-lookup"><span data-stu-id="7028f-102">How to: Create a GeometryDrawing</span></span>
<span data-ttu-id="7028f-103">В этом примере показано, как создать и отобразить <xref:System.Windows.Media.GeometryDrawing>.</span><span class="sxs-lookup"><span data-stu-id="7028f-103">This example shows how to create and display a <xref:System.Windows.Media.GeometryDrawing>.</span></span> <span data-ttu-id="7028f-104">Объект <xref:System.Windows.Media.GeometryDrawing> позволяет создавать фигура с заливкой и структуры, связав <xref:System.Windows.Media.Pen> и <xref:System.Windows.Media.Brush> с <xref:System.Windows.Media.Geometry>.</span><span class="sxs-lookup"><span data-stu-id="7028f-104">A <xref:System.Windows.Media.GeometryDrawing> enables you to create shape with a fill and an outline by associating a <xref:System.Windows.Media.Pen> and a <xref:System.Windows.Media.Brush> with a <xref:System.Windows.Media.Geometry>.</span></span> <span data-ttu-id="7028f-105"><xref:System.Windows.Media.GeometryDrawing.Geometry%2A> Описывает структуру фигуры <xref:System.Windows.Media.GeometryDrawing.Brush%2A> описывает заливку фигуры и <xref:System.Windows.Media.GeometryDrawing.Pen%2A> описывает контура фигуры.</span><span class="sxs-lookup"><span data-stu-id="7028f-105">The <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> describes the shape's structure, the <xref:System.Windows.Media.GeometryDrawing.Brush%2A> describes the shape's fill, and the <xref:System.Windows.Media.GeometryDrawing.Pen%2A> describes the shape's outline.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7028f-106">Пример</span><span class="sxs-lookup"><span data-stu-id="7028f-106">Example</span></span>  
 <span data-ttu-id="7028f-107">В следующем примере используется <xref:System.Windows.Media.GeometryDrawing> для отображения фигуры.</span><span class="sxs-lookup"><span data-stu-id="7028f-107">The following example uses a <xref:System.Windows.Media.GeometryDrawing> to render a shape.</span></span> <span data-ttu-id="7028f-108">Фигура описывается <xref:System.Windows.Media.GeometryGroup> и два <xref:System.Windows.Media.EllipseGeometry> объектов.</span><span class="sxs-lookup"><span data-stu-id="7028f-108">The shape is described by a <xref:System.Windows.Media.GeometryGroup> and two <xref:System.Windows.Media.EllipseGeometry> objects.</span></span> <span data-ttu-id="7028f-109">Фигуры закрашивается кистью <xref:System.Windows.Media.LinearGradientBrush> и ее контур рисуется пером <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>.</span><span class="sxs-lookup"><span data-stu-id="7028f-109">The shape's interior is painted with a <xref:System.Windows.Media.LinearGradientBrush> and its outline is drawn with a <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>.</span></span> <span data-ttu-id="7028f-110"><xref:System.Windows.Media.GeometryDrawing> Отображается с использованием <xref:System.Windows.Media.ImageDrawing> и <xref:System.Windows.Controls.Image> элемент.</span><span class="sxs-lookup"><span data-stu-id="7028f-110">The <xref:System.Windows.Media.GeometryDrawing> is displayed using an <xref:System.Windows.Media.ImageDrawing> and an <xref:System.Windows.Controls.Image> element.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexamplewholepage)]  
  
 <span data-ttu-id="7028f-111">На следующем рисунке показан итоговый <xref:System.Windows.Media.GeometryDrawing>.</span><span class="sxs-lookup"><span data-stu-id="7028f-111">The following illustration shows the resulting <xref:System.Windows.Media.GeometryDrawing>.</span></span>  
  
 <span data-ttu-id="7028f-112">![GeometryDrawing двух эллипсов](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")</span><span class="sxs-lookup"><span data-stu-id="7028f-112">![A GeometryDrawing of two ellipses](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")</span></span>  
  
 <span data-ttu-id="7028f-113">Для создания более сложных рисунков, можно объединить несколько графических объектов в один составной рисунок с помощью <xref:System.Windows.Media.DrawingGroup>.</span><span class="sxs-lookup"><span data-stu-id="7028f-113">To create more complex drawings, you can combine multiple drawing objects into a single composite drawing using a <xref:System.Windows.Media.DrawingGroup>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7028f-114">См. также</span><span class="sxs-lookup"><span data-stu-id="7028f-114">See also</span></span>

- <xref:System.Windows.Media.DrawingGroup>
- [<span data-ttu-id="7028f-115">Обзор объектов Drawing</span><span class="sxs-lookup"><span data-stu-id="7028f-115">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="7028f-116">Общие сведения о классе Geometry</span><span class="sxs-lookup"><span data-stu-id="7028f-116">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="7028f-117">Создание составного рисунка</span><span class="sxs-lookup"><span data-stu-id="7028f-117">Create a Composite Drawing</span></span>](how-to-create-a-composite-drawing.md)
