---
title: Практическое руководство. Изменение завершения отрезка в конце линии или сегмента
ms.date: 03/30/2017
helpviewer_keywords:
- Shape elements [WPF], ends
- Shape elements [WPF], caps
- graphics [WPF], Shape caps
ms.assetid: f4bf3416-b3d8-4568-b98e-3eda8f6dbf7a
ms.openlocfilehash: 53487417636dae8d855fe70b7b9255351a2dfb1e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916138"
---
# <a name="how-to-modify-the-cap-at-the-end-of-a-line-or-segment"></a>Практическое руководство. Изменение завершения отрезка в конце линии или сегмента
В этом примере показано, как изменить фигуру в начале или в конце открытого <xref:System.Windows.Shapes.Shape> элемента. Чтобы изменить ограничение в начале открытого <xref:System.Windows.Shapes.Shape>объекта, используйте его <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A> свойство. Чтобы изменить ограничение в конце открытого <xref:System.Windows.Shapes.Shape>объекта, используйте его <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> свойство. Чтобы просмотреть доступные концы строк, см <xref:System.Windows.Media.PenLineCap> . перечисление.  
  
> [!NOTE]
> Это свойство влияет только на открытую фигуру, например <xref:System.Windows.Shapes.Line>, на <xref:System.Windows.Shapes.Polyline>, или на открытый <xref:System.Windows.Shapes.Path> элемент.  
  
 В следующем примере рисуются <xref:System.Windows.Shapes.Polyline> четыре элемента и используется другой набор фигур на концах каждого из них.  
  
## <a name="example"></a>Пример  
 [!code-xaml[drawingwithshapeelements#ShapeLineCaps1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/linecapsandjoinsexample.xaml#shapelinecaps1)]  
  
 Этот пример является частью более крупного примера; Полный пример см. в разделе [Пример элементов Shape](https://go.microsoft.com/fwlink/?LinkID=160037).  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Media.PenLineCap>
