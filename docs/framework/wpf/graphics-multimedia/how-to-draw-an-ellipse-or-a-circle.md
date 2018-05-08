---
title: Практическое руководство. Рисование эллипса или круга
ms.date: 03/30/2017
helpviewer_keywords:
- ellipses [WPF], drawing
- circles [WPF], drawing
- drawing circles [WPF]
- drawing ellipses [WPF]
- graphics [WPF], drawing circles
- graphics [WPF], drawing ellipses
ms.assetid: 99763b8c-bfc8-44be-8231-8a70daf5481a
ms.openlocfilehash: 69620d81eb77eb76f21f099b30017b142d818457
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-draw-an-ellipse-or-a-circle"></a>Практическое руководство. Рисование эллипса или круга
В этом примере показано, как рисование эллипсов и кругов с помощью <xref:System.Windows.Shapes.Ellipse> элемента. Чтобы нарисовать эллипс, создайте <xref:System.Windows.Shapes.Ellipse> элемент и указать его <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A>. Используйте его <xref:System.Windows.Shapes.Shape.Fill%2A> свойство, чтобы указать <xref:System.Windows.Media.Brush> , используемый для рисования внутренней части эллипса. Используйте его <xref:System.Windows.Shapes.Shape.Stroke%2A> свойство, чтобы указать <xref:System.Windows.Media.Brush> , используемый для рисования контура эллипса. <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> Свойство задает толщину контура эллипса.  
  
 Рисование окружности, сделать <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> из <xref:System.Windows.Shapes.Ellipse> элементов, равных друг с другом.  
  
 В следующем примере рисуется четыре <xref:System.Windows.Shapes.Ellipse> элементы внутри <xref:System.Windows.Controls.Canvas>.  
  
## <a name="example"></a>Пример  
 [!code-xaml[drawingwithshapeelements#EllipseExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/ellipseexample.xaml#ellipseexample1)]  
  
 Несмотря на то, что в этом примере используется <xref:System.Windows.Controls.Canvas> для хранения эллипсов, можно использовать элементы эллипса (и все остальные элементы фигур) с любым <xref:System.Windows.Controls.Panel> или <xref:System.Windows.Controls.Control> , поддерживающую нетекстовых содержимое.  
  
 Этот пример является частью большего примера; Полный пример см. в разделе [пример элементов фигуры](http://go.microsoft.com/fwlink/?LinkID=160037).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Shapes.Ellipse>  
 <xref:System.Windows.Shapes.Shape>  
 [Пример элементов фигуры](http://go.microsoft.com/fwlink/?LinkID=160037)
