---
title: "Практическое руководство. Использование рисунка в качестве источника изображения | Microsoft Docs"
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
  - "объекты рисования, в качестве источников изображений"
  - "графика, объекты рисования, в качестве источников изображений"
  - "источники изображений, объекты рисования"
ms.assetid: dcf71c7b-9e86-4b8e-8e39-0d0ce0389ef4
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Практическое руководство. Использование рисунка в качестве источника изображения
В этом примере показано использование <xref:System.Windows.Media.Drawing> в качестве источника изображения <xref:System.Windows.Controls.Image.Source%2A> для элемента управления <xref:System.Windows.Controls.Image>.  Чтобы отобразить <xref:System.Windows.Media.Drawing> в элементе управления <xref:System.Windows.Controls.Image>, используйте объект <xref:System.Windows.Media.DrawingImage> элемента управления <xref:System.Windows.Controls.Image> в качестве источника <xref:System.Windows.Controls.Image.Source%2A> и установите для объекта <xref:System.Windows.Media.DrawingImage> свойство <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=fullName> для рисунка, который нужно отобразить.  
  
## Пример  
 В следующем примере используется объект <xref:System.Windows.Media.DrawingImage> и элемент управления <xref:System.Windows.Controls.Image> для отображения объекта <xref:System.Windows.Media.GeometryDrawing>.  В этом примере получается следующий результат:  
  
 ![GeometryDrawing двух эллипсов](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.png "graphicsmm\_geodraw")  
DrawingImage  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
## См. также  
 <xref:System.Windows.Freezable.Freeze%2A>   
 [Рисование изображения с помощью ImageDrawing](../../../../docs/framework/wpf/graphics-multimedia/how-to-draw-an-image-using-imagedrawing.md)   
 [Обзор объектов Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)   
 [Общие сведения об объектах класса Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)   
 [Атрибут PresentationOptions:Freeze](../../../../docs/framework/wpf/advanced/presentationoptions-freeze-attribute.md)