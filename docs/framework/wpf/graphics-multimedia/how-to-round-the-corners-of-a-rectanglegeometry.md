---
title: "Практическое руководство. Скругление углов объекта RectangleGeometry | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "углы, округление"
  - "графика, скругление углов объектов RectangleGeometry"
  - "RectangleGeometry - класс, скругление углов"
  - "скругление углов объектов RectangleGeometry"
ms.assetid: 926644bc-1357-4c0b-ac81-694bd090ae87
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# Практическое руководство. Скругление углов объекта RectangleGeometry
Чтобы скруглить углы объекта <xref:System.Windows.Media.RectangleGeometry>, необходимо задать для свойств <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> и <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> значение больше нуля.  Чем больше значения, тем больше радиус скругления углов прямоугольника.  
  
## Пример  
 В следующем примере показано несколько объектов <xref:System.Windows.Media.RectangleGeometry> с различными значениями радиусов <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> и <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A>.  Объекты <xref:System.Windows.Media.RectangleGeometry> отображаются с использованием элементов <xref:System.Windows.Shapes.Path>.  
  
 [!code-xml[GeometryOverviewSamples_snip#GraphicsMMRoundedRectangleGeometryExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/RectangleGeometryRoundedCornerExample.xaml#graphicsmmroundedrectanglegeometryexamplewholepage)]  
  
 ![Прямоугольники с различными параметрами RadiusX&#47;RadiusY](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rounded.png "graphicsmm\_rounded")  
Прямоугольники со скругленными углами  
  
## См. также  
 [Общие сведения о классе Geometry](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)   
 [Создание составной фигуры](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)   
 [Создание фигуры с помощью PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)