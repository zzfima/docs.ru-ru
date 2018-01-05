---
title: "Практическое руководство. Создание GeometryDrawing"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- shapes [WPF], renderable
- renderable shapes [WPF]
- graphics [WPF], GeometryDrawing class
- classes [WPF], GeometryDrawing
ms.assetid: 11d3c096-91ba-4d41-9bba-aeac0db70f97
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 31417a3eeee2c1e61674c43558c2799705797c35
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-geometrydrawing"></a><span data-ttu-id="7f7a9-102">Практическое руководство. Создание GeometryDrawing</span><span class="sxs-lookup"><span data-stu-id="7f7a9-102">How to: Create a GeometryDrawing</span></span>
<span data-ttu-id="7f7a9-103">В этом примере показано, как создать и отобразить <xref:System.Windows.Media.GeometryDrawing>.</span><span class="sxs-lookup"><span data-stu-id="7f7a9-103">This example shows how to create and display a <xref:System.Windows.Media.GeometryDrawing>.</span></span> <span data-ttu-id="7f7a9-104">Объект <xref:System.Windows.Media.GeometryDrawing> позволяет создавать фигура с заливкой и контуром, связав <xref:System.Windows.Media.Pen> и <xref:System.Windows.Media.Brush> с <xref:System.Windows.Media.Geometry>.</span><span class="sxs-lookup"><span data-stu-id="7f7a9-104">A <xref:System.Windows.Media.GeometryDrawing> enables you to create shape with a fill and an outline by associating a <xref:System.Windows.Media.Pen> and a <xref:System.Windows.Media.Brush> with a <xref:System.Windows.Media.Geometry>.</span></span> <span data-ttu-id="7f7a9-105"><xref:System.Windows.Media.GeometryDrawing.Geometry%2A> Описывает структуру фигуры <xref:System.Windows.Media.GeometryDrawing.Brush%2A> описывает заливку фигуры и <xref:System.Windows.Media.GeometryDrawing.Pen%2A> описывает контура фигуры.</span><span class="sxs-lookup"><span data-stu-id="7f7a9-105">The <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> describes the shape's structure, the <xref:System.Windows.Media.GeometryDrawing.Brush%2A> describes the shape's fill, and the <xref:System.Windows.Media.GeometryDrawing.Pen%2A> describes the shape's outline.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f7a9-106">Пример</span><span class="sxs-lookup"><span data-stu-id="7f7a9-106">Example</span></span>  
 <span data-ttu-id="7f7a9-107">В следующем примере используется <xref:System.Windows.Media.GeometryDrawing> для отображения фигуры.</span><span class="sxs-lookup"><span data-stu-id="7f7a9-107">The following example uses a <xref:System.Windows.Media.GeometryDrawing> to render a shape.</span></span> <span data-ttu-id="7f7a9-108">Описывается фигуры <xref:System.Windows.Media.GeometryGroup> и два <xref:System.Windows.Media.EllipseGeometry> объектов.</span><span class="sxs-lookup"><span data-stu-id="7f7a9-108">The shape is described by a <xref:System.Windows.Media.GeometryGroup> and two <xref:System.Windows.Media.EllipseGeometry> objects.</span></span> <span data-ttu-id="7f7a9-109">Рисования внутренней области фигуры с <xref:System.Windows.Media.LinearGradientBrush> и его контур рисуется с <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>.</span><span class="sxs-lookup"><span data-stu-id="7f7a9-109">The shape's interior is painted with a <xref:System.Windows.Media.LinearGradientBrush> and its outline is drawn with a <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>.</span></span> <span data-ttu-id="7f7a9-110"><xref:System.Windows.Media.GeometryDrawing> Отображается с использованием <xref:System.Windows.Media.ImageDrawing> и <xref:System.Windows.Controls.Image> элемента.</span><span class="sxs-lookup"><span data-stu-id="7f7a9-110">The <xref:System.Windows.Media.GeometryDrawing> is displayed using an <xref:System.Windows.Media.ImageDrawing> and an <xref:System.Windows.Controls.Image> element.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexamplewholepage)]  
  
 <span data-ttu-id="7f7a9-111">На следующем рисунке показан итоговый <xref:System.Windows.Media.GeometryDrawing>.</span><span class="sxs-lookup"><span data-stu-id="7f7a9-111">The following illustration shows the resulting <xref:System.Windows.Media.GeometryDrawing>.</span></span>  
  
 <span data-ttu-id="7f7a9-112">![GeometryDrawing двух эллипсов](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")</span><span class="sxs-lookup"><span data-stu-id="7f7a9-112">![A GeometryDrawing of two ellipses](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")</span></span>  
  
 <span data-ttu-id="7f7a9-113">Для создания более сложных рисунков можно объединить несколько графических объектов в один составной рисунок с помощью <xref:System.Windows.Media.DrawingGroup>.</span><span class="sxs-lookup"><span data-stu-id="7f7a9-113">To create more complex drawings, you can combine multiple drawing objects into a single composite drawing using a <xref:System.Windows.Media.DrawingGroup>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f7a9-114">См. также</span><span class="sxs-lookup"><span data-stu-id="7f7a9-114">See Also</span></span>  
 <xref:System.Windows.Media.DrawingGroup>  
 [<span data-ttu-id="7f7a9-115">Обзор объектов Drawing</span><span class="sxs-lookup"><span data-stu-id="7f7a9-115">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [<span data-ttu-id="7f7a9-116">Общие сведения о классе Geometry</span><span class="sxs-lookup"><span data-stu-id="7f7a9-116">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [<span data-ttu-id="7f7a9-117">Создание составного рисунка</span><span class="sxs-lookup"><span data-stu-id="7f7a9-117">Create a Composite Drawing</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-drawing.md)
