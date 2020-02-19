---
title: Как начертить линию
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], lines
- graphics [WPF], lines
- lines [WPF], drawing
ms.assetid: 0513ee01-6b27-4bb3-85f3-3a3e6710d80e
ms.openlocfilehash: a803c1be01086ca8911ef4cc33bd67697239e2c0
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452952"
---
# <a name="how-to-draw-a-line"></a>Как начертить линию
В этом примере показано, как нарисовать линии с помощью элемента <xref:System.Windows.Shapes.Line>.  
  
 Чтобы нарисовать линию, создайте элемент <xref:System.Windows.Shapes.Line>. Чтобы задать начальную точку, используйте его свойства <xref:System.Windows.Shapes.Line.X1%2A> и <xref:System.Windows.Shapes.Line.Y1%2A>. чтобы задать конечную точку, используйте его свойства <xref:System.Windows.Shapes.Line.X2%2A> и <xref:System.Windows.Shapes.Line.Y2%2A>. Наконец, задайте его <xref:System.Windows.Shapes.Shape.Stroke%2A> и <xref:System.Windows.Shapes.Shape.StrokeThickness%2A>, так как линия без штриха невидима.  
  
 Установка элемента <xref:System.Windows.Shapes.Shape.Fill%2A> для линии не оказывает никакого воздействия, так как линия не имеет внутренней части.  
  
 В следующем примере в элемент <xref:System.Windows.Controls.Canvas> выводится три строки.  
  
## <a name="example"></a>Пример  
 [!code-xaml[drawingwithshapeelements#LineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 Этот пример является частью более крупного примера; Полный пример см. в разделе [Пример элементов Shape](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Shapes.Line>
- [Пример элементов Shape](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
