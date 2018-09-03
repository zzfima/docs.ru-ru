---
title: Практическое руководство. Рисование замкнутой фигуры с помощью элемента "Многоугольник"
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], Polygon elements
- closed shapes [WPF], drawing with Polygon elements
- Polygon elements [WPF]
- drawing [WPF], closed shapes with Polygon elements
ms.assetid: 4b0ca008-29ce-48dd-8bc3-f3a20ffca6a6
ms.openlocfilehash: 89c78877e196e803f6b4139ffcfa2b4def1a07d7
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2018
ms.locfileid: "43468096"
---
# <a name="how-to-draw-a-closed-shape-by-using-the-polygon-element"></a><span data-ttu-id="7da57-102">Практическое руководство. Рисование замкнутой фигуры с помощью элемента "Многоугольник"</span><span class="sxs-lookup"><span data-stu-id="7da57-102">How to: Draw a Closed Shape by Using the Polygon Element</span></span>
<span data-ttu-id="7da57-103">В этом примере показано, как Рисование замкнутой фигуры с помощью <xref:System.Windows.Shapes.Polygon> элемент.</span><span class="sxs-lookup"><span data-stu-id="7da57-103">This example shows how to draw a closed shape by using the <xref:System.Windows.Shapes.Polygon> element.</span></span> <span data-ttu-id="7da57-104">Чтобы Рисование замкнутой фигуры, создайте <xref:System.Windows.Shapes.Polygon> элемента и использование его <xref:System.Windows.Shapes.Polygon.Points%2A> свойство, чтобы указать вершины фигуры.</span><span class="sxs-lookup"><span data-stu-id="7da57-104">To draw a closed shape, create a <xref:System.Windows.Shapes.Polygon> element and use its <xref:System.Windows.Shapes.Polygon.Points%2A> property to specify the vertices of a shape.</span></span> <span data-ttu-id="7da57-105">Автоматически отображается линия, соединяющая точки первого и последнего.</span><span class="sxs-lookup"><span data-stu-id="7da57-105">A line is automatically drawn that connects the first and last points.</span></span> <span data-ttu-id="7da57-106">Наконец, укажите <xref:System.Windows.Shapes.Shape.Fill%2A>, <xref:System.Windows.Shapes.Shape.Stroke%2A>, или оба.</span><span class="sxs-lookup"><span data-stu-id="7da57-106">Finally, specify a <xref:System.Windows.Shapes.Shape.Fill%2A>, a <xref:System.Windows.Shapes.Shape.Stroke%2A>, or both.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7da57-107">Пример</span><span class="sxs-lookup"><span data-stu-id="7da57-107">Example</span></span>  
 <span data-ttu-id="7da57-108">В [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], допустимым синтаксисом для точек является список с разделителями запятыми координат x и y пар.</span><span class="sxs-lookup"><span data-stu-id="7da57-108">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], valid syntax for points is a space-delimited list of comma-separated x- and y-coordinate pairs.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#PolygonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polygonexample.xaml#polygonexample1)]  
  
 <span data-ttu-id="7da57-109">Несмотря на то, что в примере используется <xref:System.Windows.Controls.Canvas> для хранения многоугольников, можно использовать элементы многоугольника (и все остальные элементы фигуры) с любым <xref:System.Windows.Controls.Panel> или <xref:System.Windows.Controls.Control> , поддерживающий нетекстовое содержимое.</span><span class="sxs-lookup"><span data-stu-id="7da57-109">Although the example uses a <xref:System.Windows.Controls.Canvas> to contain the polygons, you can use polygon elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="7da57-110">Этот пример является частью большего примера; Полный пример см. в разделе [пример элементов-фигур](https://go.microsoft.com/fwlink/?LinkID=160037).</span><span class="sxs-lookup"><span data-stu-id="7da57-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).</span></span>
