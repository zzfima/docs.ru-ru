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
ms.openlocfilehash: 5f17615da4907cba6e25b68f2f934602c2f8a390
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452926"
---
# <a name="how-to-draw-an-ellipse-or-a-circle"></a>Практическое руководство. Рисование эллипса или круга
В этом примере показано, как рисовать эллипсы и окружности с помощью элемента <xref:System.Windows.Shapes.Ellipse>. Чтобы нарисовать эллипс, создайте элемент <xref:System.Windows.Shapes.Ellipse> и укажите его <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A>. Используйте его свойство <xref:System.Windows.Shapes.Shape.Fill%2A>, чтобы указать <xref:System.Windows.Media.Brush>, используемый для заполнения внутренней части эллипса. Используйте его свойство <xref:System.Windows.Shapes.Shape.Stroke%2A>, чтобы указать <xref:System.Windows.Media.Brush>, используемый для рисования контура эллипса. Свойство <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> задает толщину контура эллипса.  
  
 Чтобы нарисовать круг, сделайте <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> элемента <xref:System.Windows.Shapes.Ellipse> равными друг другу.  
  
 В следующем примере в <xref:System.Windows.Controls.Canvas>рисуется четыре элемента <xref:System.Windows.Shapes.Ellipse>.  
  
## <a name="example"></a>Пример  
 [!code-xaml[drawingwithshapeelements#EllipseExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/ellipseexample.xaml#ellipseexample1)]  
  
 Хотя в этом примере используется <xref:System.Windows.Controls.Canvas> для хранения эллипсов, можно использовать элементы Ellipse (и все остальные элементы Shape) с любыми <xref:System.Windows.Controls.Panel> или <xref:System.Windows.Controls.Control>, поддерживающими нетекстовое содержимое.  
  
 Этот пример является частью более крупного примера; Полный пример см. в разделе [Пример элементов Shape](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Shapes.Ellipse>
- <xref:System.Windows.Shapes.Shape>
- [Пример элементов Shape](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
