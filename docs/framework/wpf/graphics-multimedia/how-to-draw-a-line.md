---
title: Практическое руководство. Рисование линии
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], lines
- graphics [WPF], lines
- lines [WPF], drawing
ms.assetid: 0513ee01-6b27-4bb3-85f3-3a3e6710d80e
ms.openlocfilehash: a194fad5471cafcb567aa00522a597a4186ef4af
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57374194"
---
# <a name="how-to-draw-a-line"></a>Практическое руководство. Рисование линии
В этом примере показано, как рисование линий с помощью <xref:System.Windows.Shapes.Line> элемент.  
  
 Чтобы нарисовать линию, создайте <xref:System.Windows.Shapes.Line> элемент. Используйте его <xref:System.Windows.Shapes.Line.X1%2A> и <xref:System.Windows.Shapes.Line.Y1%2A> свойства для задания начальной точки; и используйте его <xref:System.Windows.Shapes.Line.X2%2A> и <xref:System.Windows.Shapes.Line.Y2%2A> свойства для задания конечной точки. Наконец, установите его <xref:System.Windows.Shapes.Shape.Stroke%2A> и <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> так, как в строку без штриха остается невидимым.  
  
 Параметр <xref:System.Windows.Shapes.Shape.Fill%2A> элемент строку, не оказывает влияния, так как строки не имеет внутренней части.  
  
 В следующем примере рисуется три строки внутри <xref:System.Windows.Controls.Canvas> элемент.  
  
## <a name="example"></a>Пример  
 [!code-xaml[drawingwithshapeelements#LineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 Этот пример является частью большего примера; Полный пример см. в разделе [пример элементов-фигур](https://go.microsoft.com/fwlink/?LinkID=160037).  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Shapes.Line>
- [Пример элементов-фигур](https://go.microsoft.com/fwlink/?LinkID=160037)
