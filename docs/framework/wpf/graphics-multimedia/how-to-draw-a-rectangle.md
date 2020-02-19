---
title: Практическое руководство. Рисование прямоугольника
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], rectangles
- graphics [WPF], rectangles
- rectangles [WPF], drawing
ms.assetid: beeb57ef-fab5-4446-a38a-1588f97b4c2f
ms.openlocfilehash: 95191e9d90bc2ac32902399125d9a51192e897bf
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452939"
---
# <a name="how-to-draw-a-rectangle"></a>Практическое руководство. Рисование прямоугольника
В этом примере показано, как нарисовать прямоугольник с помощью элемента <xref:System.Windows.Shapes.Rectangle>.  
  
 Чтобы нарисовать прямоугольник, создайте элемент <xref:System.Windows.Shapes.Rectangle> и укажите его <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A>. Чтобы закрасить внутри прямоугольника, задайте его <xref:System.Windows.Shapes.Shape.Fill%2A>. Чтобы присвоить прямоугольнику структуру, используйте его свойства <xref:System.Windows.Shapes.Shape.Stroke%2A> и <xref:System.Windows.Shapes.Shape.StrokeThickness%2A>.  
  
 Чтобы задать скругленные углы прямоугольника, укажите необязательные свойства <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> и <xref:System.Windows.Shapes.Rectangle.RadiusY%2A>. Свойства <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> и <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> устанавливают радиус эллипса по оси x и оси y, который используется для закругления углов прямоугольника.  
  
 В следующем примере в <xref:System.Windows.Controls.Canvas>рисуются два элемента <xref:System.Windows.Shapes.Rectangle>. Первый прямоугольник имеет <xref:System.Windows.Media.Brushes.Blue%2A> внутренней. Второй прямоугольник имеет <xref:System.Windows.Media.Brushes.Blue%2A> внутреннюю, <xref:System.Windows.Media.Brushes.Black%2A>ную структуру и скругленные углы.  
  
## <a name="example"></a>Пример  
 [!code-xaml[drawingwithshapeelements#Rectangle1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/rectangleexample.xaml#rectangle1)]  
  
 Несмотря на то, что в этом примере используется <xref:System.Windows.Controls.Canvas> для хранения прямоугольников, можно использовать элементы Rectangle (и все остальные элементы Shape) с любыми <xref:System.Windows.Controls.Panel> или <xref:System.Windows.Controls.Control>, поддерживающими нетекстовое содержимое. Фактически, прямоугольники особенно полезны для предоставления фона для частей <xref:System.Windows.Controls.Grid> панелей. Пример см. в разделе [Общие сведения о таблице](../advanced/table-overview.md).  
  
 Этот пример является частью более крупного примера; Полный пример см. в разделе [Пример элементов Shape](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Shapes.Rectangle>
- [Пример элементов Shape](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
- [Обзор фигур и базовых средств рисования в приложении WPF](shapes-and-basic-drawing-in-wpf-overview.md)
- [Table Overview](../advanced/table-overview.md)
