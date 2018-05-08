---
title: Практическое руководство. Рисование прямоугольника
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], rectangles
- graphics [WPF], rectangles
- rectangles [WPF], drawing
ms.assetid: beeb57ef-fab5-4446-a38a-1588f97b4c2f
ms.openlocfilehash: 100f1a8062628e892e9a71b988bb2a8754ea6bad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-draw-a-rectangle"></a>Практическое руководство. Рисование прямоугольника
В этом примере показано, как рисование прямоугольника с помощью <xref:System.Windows.Shapes.Rectangle> элемента.  
  
 Чтобы нарисовать прямоугольник, создайте <xref:System.Windows.Shapes.Rectangle> элемент и указать его <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A>. Чтобы рисовать внутри прямоугольника, задайте его <xref:System.Windows.Shapes.Shape.Fill%2A>. Чтобы предоставить структуру прямоугольник, используйте его <xref:System.Windows.Shapes.Shape.Stroke%2A> и <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> свойства.  
  
 Чтобы предоставить прямоугольника скругленные углы, укажите необязательное <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> и <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> свойства. <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> И <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> свойства заданы радиусы осей x и y для эллипса, который используется для скругления углов прямоугольника.  
  
 В следующем примере два <xref:System.Windows.Shapes.Rectangle> элементы отображаются в <xref:System.Windows.Controls.Canvas>. Первый прямоугольник имеет <xref:System.Windows.Media.Brushes.Blue%2A> внутренних. Второй прямоугольник имеет <xref:System.Windows.Media.Brushes.Blue%2A> внутренних, <xref:System.Windows.Media.Brushes.Black%2A> структуры и прямоугольника с закругленными углами.  
  
## <a name="example"></a>Пример  
 [!code-xaml[drawingwithshapeelements#Rectangle1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/rectangleexample.xaml#rectangle1)]  
  
 Несмотря на то, что в этом примере используется <xref:System.Windows.Controls.Canvas> содержать прямоугольники, можно использовать элементы прямоугольник (и все остальные элементы фигур) с любым <xref:System.Windows.Controls.Panel> или <xref:System.Windows.Controls.Control> , поддерживающую нетекстовых содержимое. На самом деле это особенно полезно в качестве фона для частей прямоугольники <xref:System.Windows.Controls.Grid> панелей. Пример см. в разделе [Общие сведения о таблицах](../../../../docs/framework/wpf/advanced/table-overview.md).  
  
 Этот пример является частью большего примера; Полный пример см. в разделе [пример элементов фигуры](http://go.microsoft.com/fwlink/?LinkID=160037).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Shapes.Rectangle>  
 [Пример элементов фигуры](http://go.microsoft.com/fwlink/?LinkID=160037)  
 [Обзор фигур и базовых средств рисования в приложении WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)  
 [Общие сведения о таблицах](../../../../docs/framework/wpf/advanced/table-overview.md)
