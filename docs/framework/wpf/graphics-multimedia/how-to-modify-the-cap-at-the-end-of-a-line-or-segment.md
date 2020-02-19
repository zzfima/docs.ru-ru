---
title: Практическое руководство. Изменение завершения отрезка в конце линии или сегмента
ms.date: 03/30/2017
helpviewer_keywords:
- Shape elements [WPF], ends
- Shape elements [WPF], caps
- graphics [WPF], Shape caps
ms.assetid: f4bf3416-b3d8-4568-b98e-3eda8f6dbf7a
ms.openlocfilehash: 5f755d7b4d1682755ea461121f91c0666d450ad1
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452783"
---
# <a name="how-to-modify-the-cap-at-the-end-of-a-line-or-segment"></a>Практическое руководство. Изменение завершения отрезка в конце линии или сегмента
В этом примере показано, как изменить фигуру в начале или в конце открытого элемента <xref:System.Windows.Shapes.Shape>. Чтобы изменить ограничение в начале открытого <xref:System.Windows.Shapes.Shape>, используйте его свойство <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A>. Чтобы изменить ограничение в конце открытого <xref:System.Windows.Shapes.Shape>, используйте его свойство <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A>. Чтобы просмотреть доступные концы строк, см. раздел перечисление <xref:System.Windows.Media.PenLineCap>.  
  
> [!NOTE]
> Это свойство влияет только на открытую фигуру, например <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Polyline>или открытый элемент <xref:System.Windows.Shapes.Path>.  
  
 В следующем примере рисуется четыре элемента <xref:System.Windows.Shapes.Polyline> и в конце каждого из них используется другой набор фигур.  
  
## <a name="example"></a>Пример  
 [!code-xaml[drawingwithshapeelements#ShapeLineCaps1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/linecapsandjoinsexample.xaml#shapelinecaps1)]  
  
 Этот пример является частью более крупного примера; Полный пример см. в разделе [Пример элементов Shape](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Media.PenLineCap>
