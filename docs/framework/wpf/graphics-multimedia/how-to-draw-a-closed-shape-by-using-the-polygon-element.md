---
title: "Практическое руководство. Рисование замкнутой фигуры с помощью элемента \"Многоугольник\""
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [WPF], Polygon elements
- closed shapes [WPF], drawing with Polygon elements
- Polygon elements [WPF]
- drawing [WPF], closed shapes with Polygon elements
ms.assetid: 4b0ca008-29ce-48dd-8bc3-f3a20ffca6a6
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0cf842c22238105510b13407d55c8c9773f84a70
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-a-closed-shape-by-using-the-polygon-element"></a>Практическое руководство. Рисование замкнутой фигуры с помощью элемента "Многоугольник"
В этом примере показано, как Рисование замкнутой фигуры с помощью <xref:System.Windows.Shapes.Polygon> элемента. Чтобы нарисовать замкнутую фигуру, создайте <xref:System.Windows.Shapes.Polygon> элемента и использовать его <xref:System.Windows.Shapes.Polygon.Points%2A> свойство, чтобы указать вершинах фигуры. Автоматически отображается линия, соединяющая точки первым и последним. Наконец, укажите <xref:System.Windows.Shapes.Shape.Fill%2A>, <xref:System.Windows.Shapes.Shape.Stroke%2A>, или оба.  
  
## <a name="example"></a>Пример  
 В [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], допустимым синтаксисом для точек — перечень запятыми координат x и y пары.  
  
 [!code-xaml[drawingwithshapeelements#PolygonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polygonexample.xaml#polygonexample1)]  
  
 Несмотря на то, что в этом примере <xref:System.Windows.Controls.Canvas> для хранения многоугольников, можно использовать элементы многоугольника (и все остальные элементы фигур) с любым <xref:System.Windows.Controls.Panel> или <xref:System.Windows.Controls.Control> , поддерживающую нетекстовых содержимое.  
  
 Этот пример является частью большего примера; Полный пример см. в разделе [пример элементов фигуры](http://go.microsoft.com/fwlink/?LinkID=160037).
