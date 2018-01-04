---
title: "Практическое руководство. Рисование ломаной, используя элемент Polyline"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- connected lines [WPF]
- polylines [WPF], drawing
- graphics [WPF], polylines
- lines [WPF], connected (see polylines)
- drawing [WPF], polylines
ms.assetid: 65db8935-d047-4295-87c4-b427ff3ad293
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9b0b027aa34b310413fa02e81149292fabb40f79
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-a-polyline-by-using-the-polyline-element"></a>Практическое руководство. Рисование ломаной, используя элемент Polyline
В этом примере показано, как рисование ломаной, которая представляет собой последовательность соединенных линий, с помощью <xref:System.Windows.Shapes.Polyline> элемента.  
  
 Чтобы нарисовать ломаной линии, создайте <xref:System.Windows.Shapes.Polyline> элемента и использовать его <xref:System.Windows.Shapes.Polyline.Points%2A> свойство, чтобы указать вершинах фигуры. Наконец, используйте <xref:System.Windows.Shapes.Shape.Stroke%2A> и <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> свойства для описания ломаной линии структуры, так как выполняется без внешних проявлений линия без штриха.  
  
> [!NOTE]
>  Поскольку <xref:System.Windows.Shapes.Polyline> элемент не является замкнутой фигуры <xref:System.Windows.Shapes.Shape.Fill%2A> свойство не имеет значения, даже если закрыть намеренно контура фигуры. Для создания замкнутой фигуры с <xref:System.Windows.Shapes.Shape.Fill%2A>, используйте <xref:System.Windows.Shapes.Polygon> элемента.  
  
 В следующем примере рисуется два <xref:System.Windows.Shapes.Polyline> элементов внутри <xref:System.Windows.Controls.Canvas>.  
  
## <a name="example"></a>Пример  
 В [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], допустимым синтаксисом для точек — перечень запятыми координат x и y пары.  
  
 [!code-xaml[drawingwithshapeelements#PolylineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polylineexample.xaml#polylineexample1)]  
  
 Несмотря на то, что в этом примере используется <xref:System.Windows.Controls.Canvas> для хранения ломаных, можно использовать элементы ломаной линии (и все остальные элементы фигур) с любым <xref:System.Windows.Controls.Panel> или <xref:System.Windows.Controls.Control> , поддерживающую нетекстовых содержимое.  
  
 Этот пример является частью большего примера; Полный пример см. в разделе [пример элементов фигуры](http://go.microsoft.com/fwlink/?LinkID=160037).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Shapes.Polyline>  
 <xref:System.Windows.Shapes.Polygon>  
 <xref:System.Windows.Shapes.Shape>  
 [Пример элементов фигуры](http://go.microsoft.com/fwlink/?LinkID=160037)  
 [Обзор фигур и базовых средств рисования в приложении WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)
