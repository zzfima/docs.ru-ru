---
title: "Практическое руководство. Создание GeometryDrawing | Microsoft Docs"
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
  - "классы, GeometryDrawing"
  - "GeometryDrawing - класс"
  - "графика, GeometryDrawing - класс"
  - "отрисовываемые фигуры"
  - "фигуры, отрисовываемые"
ms.assetid: 11d3c096-91ba-4d41-9bba-aeac0db70f97
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Создание GeometryDrawing
В этом примере демонстрируется создание и отображение <xref:System.Windows.Media.GeometryDrawing>.  <xref:System.Windows.Media.GeometryDrawing> позволяет создать фигуру с заливкой и контуром путем совместного использования <xref:System.Windows.Media.Pen>, <xref:System.Windows.Media.Brush> и <xref:System.Windows.Media.Geometry>.  <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> описывает структуру фигуры, <xref:System.Windows.Media.GeometryDrawing.Brush%2A> описывает заливку фигуры, а <xref:System.Windows.Media.GeometryDrawing.Pen%2A> описывает контур фигуры.  
  
## Пример  
 В следующем примере <xref:System.Windows.Media.GeometryDrawing> используется для отображения фигуры.  Фигура описывается <xref:System.Windows.Media.GeometryGroup> и двумя объектами <xref:System.Windows.Media.EllipseGeometry>.  Внутренняя часть фигуры рисуется с помощью <xref:System.Windows.Media.LinearGradientBrush>, а ее контур — с помощью <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>.  <xref:System.Windows.Media.GeometryDrawing> отображается с использованием элемента <xref:System.Windows.Media.ImageDrawing> и <xref:System.Windows.Controls.Image>.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexamplewholepage)]
 [!code-xml[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexamplewholepage)]  
  
 На следующем рисунке показан получившийся <xref:System.Windows.Media.GeometryDrawing>.  
  
 ![GeometryDrawing двух эллипсов](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.png "graphicsmm\_geodraw")  
  
 Для создания более сложных рисунков можно объединить несколько графических объектов в один составной рисунок с помощью <xref:System.Windows.Media.DrawingGroup>.  
  
## См. также  
 <xref:System.Windows.Media.DrawingGroup>   
 [Обзор объектов Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)   
 [Общие сведения о классе Geometry](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)   
 [Создание составного рисунка](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-drawing.md)