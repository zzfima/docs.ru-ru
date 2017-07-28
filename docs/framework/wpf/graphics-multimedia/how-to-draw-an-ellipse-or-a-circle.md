---
title: "Практическое руководство. Рисование эллипса или круга | Microsoft Docs"
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
  - "круги, рисование"
  - "рисование кругов"
  - "рисование эллипсов"
  - "эллипсы, рисование"
  - "графика, рисование кругов"
  - "графика, рисование эллипсов"
ms.assetid: 99763b8c-bfc8-44be-8231-8a70daf5481a
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Практическое руководство. Рисование эллипса или круга
В данном примере демонстрируется рисование эллипсов и кругов с помощью элемента <xref:System.Windows.Shapes.Ellipse>.  Чтобы нарисовать эллипс, необходимо создать элемент <xref:System.Windows.Shapes.Ellipse> и задать значения его свойств <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A>.  Для указания объекта <xref:System.Windows.Media.Brush>, используемого для рисования внутренней части эллипса, необходимо использовать свойство <xref:System.Windows.Shapes.Shape.Fill%2A>.  Для указания объекта <xref:System.Windows.Media.Brush>, используемого для рисования контура эллипса, необходимо использовать свойство <xref:System.Windows.Shapes.Shape.Stroke%2A>.  Свойство <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> задает толщину контура эллипса.  
  
 Чтобы нарисовать круг, значения свойств <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> элемента <xref:System.Windows.Shapes.Ellipse> должны быть одинаковыми.  
  
 В следующем примере рисуется четыре элемента <xref:System.Windows.Shapes.Ellipse> внутри объекта <xref:System.Windows.Controls.Canvas>.  
  
## Пример  
 [!code-xml[drawingwithshapeelements#EllipseExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/ellipseexample.xaml#ellipseexample1)]  
  
 Хотя данный пример для хранения эллипсов использует элемент управления <xref:System.Windows.Controls.Canvas>, можно использовать элементы эллипсов \(и все остальные элементы фигур\) с любым из элементов управления <xref:System.Windows.Controls.Panel> или <xref:System.Windows.Controls.Control>, поддерживающих нетекстовое содержимое.  
  
 Этот пример является фрагментом большего примера; полный пример см. на веб\-странице [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).  
  
## См. также  
 <xref:System.Windows.Shapes.Ellipse>   
 <xref:System.Windows.Shapes.Shape>   
 [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037)