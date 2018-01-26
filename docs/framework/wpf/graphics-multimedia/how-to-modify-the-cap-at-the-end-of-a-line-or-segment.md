---
title: "Практическое руководство. Изменение завершения отрезка в конце линии или сегмента"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Shape elements [WPF], ends
- Shape elements [WPF], caps
- graphics [WPF], Shape caps
ms.assetid: f4bf3416-b3d8-4568-b98e-3eda8f6dbf7a
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0d2cd55de403b766344749259068ccd313558f89
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
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
