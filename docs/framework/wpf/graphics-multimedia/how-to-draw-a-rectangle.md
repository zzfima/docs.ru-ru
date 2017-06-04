---
title: "Практическое руководство. Рисование прямоугольника | Microsoft Docs"
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
  - "рисование, прямоугольники"
  - "графика [WPF], прямоугольники"
  - "прямоугольники, рисование"
ms.assetid: beeb57ef-fab5-4446-a38a-1588f97b4c2f
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Рисование прямоугольника
В этом примере демонстрируется рисование прямоугольника с помощью элемента <xref:System.Windows.Shapes.Rectangle>.  
  
 Чтобы нарисовать прямоугольник, создайте элемент <xref:System.Windows.Shapes.Rectangle> и установите его свойства <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A>.  Для закраски области внутри прямоугольника установите свойство <xref:System.Windows.Shapes.Shape.Fill%2A>.  Для рисования контура прямоугольника используйте его свойства <xref:System.Windows.Shapes.Shape.Stroke%2A> и <xref:System.Windows.Shapes.Shape.StrokeThickness%2A>.  
  
 Для рисования округленных углов прямоугольника установите необязательные свойства <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> и <xref:System.Windows.Shapes.Rectangle.RadiusY%2A>.  Свойства <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> и <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> устанавливают радиусы эллипса, который используется для округления углов прямоугольника, по осям x и y.  
  
 В следующем примере выполняется рисование двух элементов <xref:System.Windows.Shapes.Rectangle> на объекте <xref:System.Windows.Controls.Canvas>.  Для первого прямоугольника выполняется внутренняя заливка с использованием цвета <xref:System.Windows.Media.Brushes.Blue%2A>.  Для второго прямоугольника применяется внутренняя заливка с использованием цвета <xref:System.Windows.Media.Brushes.Blue%2A>, а также контур цвета <xref:System.Windows.Media.Brushes.Black%2A> и округленные углы.  
  
## Пример  
 [!code-xml[drawingwithshapeelements#Rectangle1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/rectangleexample.xaml#rectangle1)]  
  
 В этом примере прямоугольники содержатся на объекте <xref:System.Windows.Controls.Canvas>. Также можно использовать прямоугольники \(и любые другие элементы фигур\) с любыми объектами <xref:System.Windows.Controls.Panel> или <xref:System.Windows.Controls.Control>, поддерживающими нетекстовое содержимое.  Прямоугольники часто используются в качестве фона для частей панелей <xref:System.Windows.Controls.Grid>.  Пример см. в разделе [Общие сведения о таблицах](../../../../docs/framework/wpf/advanced/table-overview.md).  
  
 Этот пример является фрагментом большего примера; полный пример см. на веб\-странице [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).  
  
## См. также  
 <xref:System.Windows.Shapes.Rectangle>   
 [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037)   
 [Обзор фигур и базовых средств рисования в приложении WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)   
 [Общие сведения о таблицах](../../../../docs/framework/wpf/advanced/table-overview.md)