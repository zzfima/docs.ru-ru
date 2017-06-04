---
title: "Практическое руководство. Рисование замкнутой фигуры с помощью элемента &quot;Многоугольник&quot; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "замкнутые фигуры, рисование с помощью элементов Polygon"
  - "рисование, закрытых фигур с помощью элементов Polygon"
  - "графика, элементы Polygon"
  - "элементы Polygon"
ms.assetid: 4b0ca008-29ce-48dd-8bc3-f3a20ffca6a6
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Практическое руководство. Рисование замкнутой фигуры с помощью элемента &quot;Многоугольник&quot;
В этом примере демонстрируется рисование замкнутой фигуры с помощью элемента <xref:System.Windows.Shapes.Polygon>.  Чтобы нарисовать замкнутую фигуру, создайте элемент <xref:System.Windows.Shapes.Polygon> и используйте его свойство <xref:System.Windows.Shapes.Polygon.Points%2A> для указания вершин фигуры.  Автоматически рисуется линия, соединяющая первую и последнюю точки.  Затем укажите <xref:System.Windows.Shapes.Shape.Fill%2A>, <xref:System.Windows.Shapes.Shape.Stroke%2A> или оба свойства.  
  
## Пример  
 В [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] допустимым синтаксисом для точек является список, содержащий пары разделенных пробелом координат x и y.  
  
 [!code-xml[drawingwithshapeelements#PolygonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polygonexample.xaml#polygonexample1)]  
  
 Хотя в примере для хранения многоугольников используется <xref:System.Windows.Controls.Canvas>, элементы многоугольника \(и все остальные элементы фигур\) можно использовать с любым <xref:System.Windows.Controls.Panel> или <xref:System.Windows.Controls.Control>, поддерживающим нетекстовое содержимое.  
  
 Этот пример является фрагментом большего примера; полный пример см. на веб\-странице [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).