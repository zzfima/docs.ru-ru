---
title: "Как начертить линию"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- drawing [WPF], lines
- graphics [WPF], lines
- lines [WPF], drawing
ms.assetid: 0513ee01-6b27-4bb3-85f3-3a3e6710d80e
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4911aea91416fb84e9a18d54c145b494737ef9dd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-a-line"></a>Как начертить линию
В этом примере показано, как рисование линий с помощью <xref:System.Windows.Shapes.Line> элемента.  
  
 Чтобы нарисовать линию, создайте <xref:System.Windows.Shapes.Line> элемента. Используйте его <xref:System.Windows.Shapes.Line.X1%2A> и <xref:System.Windows.Shapes.Line.Y1%2A> свойства для задания начальной точки; и использовать его <xref:System.Windows.Shapes.Line.X2%2A> и <xref:System.Windows.Shapes.Line.Y2%2A> свойства для задания конечной точки. Наконец, установите его <xref:System.Windows.Shapes.Shape.Stroke%2A> и <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> так, как выполняется без внешних проявлений линия без штриха.  
  
 Параметр <xref:System.Windows.Shapes.Shape.Fill%2A> элемент для строки не делает ничего, так как строки не имеет внутренней части.  
  
 В следующем примере рисуются три линии внутри <xref:System.Windows.Controls.Canvas> элемента.  
  
## <a name="example"></a>Пример  
 [!code-xaml[drawingwithshapeelements#LineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 Этот пример является частью большего примера; Полный пример см. в разделе [пример элементов фигуры](http://go.microsoft.com/fwlink/?LinkID=160037).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Shapes.Line>  
 [Пример элементов фигуры](http://go.microsoft.com/fwlink/?LinkID=160037)
