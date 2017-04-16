---
title: "Как начертить линию | Microsoft Docs"
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
  - "рисование, линии"
  - "графика [WPF], линии"
  - "линии, рисование"
ms.assetid: 0513ee01-6b27-4bb3-85f3-3a3e6710d80e
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Как начертить линию
Этот пример показывает, как начертить линию с помощью элемента <xref:System.Windows.Shapes.Line>.  
  
 Чтобы начертить линию, создайте элемент <xref:System.Windows.Shapes.Line>.  Используйте его свойства <xref:System.Windows.Shapes.Line.X1%2A> и <xref:System.Windows.Shapes.Line.Y1%2A> для задания начальной точки; и его свойства <xref:System.Windows.Shapes.Line.X2%2A> и <xref:System.Windows.Shapes.Line.Y2%2A> для задания конечной точки.  В заключение, установите свойства<xref:System.Windows.Shapes.Shape.Stroke%2A> и <xref:System.Windows.Shapes.Shape.StrokeThickness%2A>, поскольку линия без штрихов не видна.  
  
 Задание элемента <xref:System.Windows.Shapes.Shape.Fill%2A> для линии ни к чему не приводит, поскольку линия не имеет внутренней части.  
  
 В следующем примере чертятся три линии внутри элемента <xref:System.Windows.Controls.Canvas>.  
  
## Пример  
 [!code-xml[drawingwithshapeelements#LineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 Этот пример является фрагментом большего примера; полный пример см. на веб\-странице [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).  
  
## См. также  
 <xref:System.Windows.Shapes.Line>   
 [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037)