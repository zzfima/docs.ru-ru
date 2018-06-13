---
title: Практическое руководство. Изменение завершения отрезка в конце линии или сегмента
ms.date: 03/30/2017
helpviewer_keywords:
- Shape elements [WPF], ends
- Shape elements [WPF], caps
- graphics [WPF], Shape caps
ms.assetid: f4bf3416-b3d8-4568-b98e-3eda8f6dbf7a
ms.openlocfilehash: e69f461d426fc6a587263cea7a18478da53b5b09
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559841"
---
# <a name="how-to-modify-the-cap-at-the-end-of-a-line-or-segment"></a>Практическое руководство. Изменение завершения отрезка в конце линии или сегмента
В этом примере показано, как изменить форму в начале или конце открытой <xref:System.Windows.Shapes.Shape> элемента. Чтобы изменить ограничение начала открытого <xref:System.Windows.Shapes.Shape>, использовать его <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A> свойство. Чтобы изменить ограничение в конце открытого <xref:System.Windows.Shapes.Shape>, использовать его <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> свойство. Для просмотра доступных отрезков см <xref:System.Windows.Media.PenLineCap> перечисления.  
  
> [!NOTE]
>  Это свойство влияет только на открытые фигуры, такие как <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Polyline>, или открытый <xref:System.Windows.Shapes.Path> элемента.  
  
 В следующем примере рисуется четыре <xref:System.Windows.Shapes.Polyline> элементы и использует разный набор фигур в конце каждого.  
  
## <a name="example"></a>Пример  
 [!code-xaml[drawingwithshapeelements#ShapeLineCaps1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/linecapsandjoinsexample.xaml#shapelinecaps1)]  
  
 Этот пример является частью большего примера; Полный пример см. в разделе [пример элементов фигуры](http://go.microsoft.com/fwlink/?LinkID=160037).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Shapes.Polyline>  
 <xref:System.Windows.Media.PenLineCap>
