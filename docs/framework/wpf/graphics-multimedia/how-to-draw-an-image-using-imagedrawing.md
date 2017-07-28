---
title: "Практическое руководство. Рисование изображения с помощью ImageDrawing | Microsoft Docs"
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
  - "классы, ImageDrawing"
  - "рисование, изображения"
  - "графика, создание изображений"
  - "ImageDrawing - класс"
  - "изображения, рисование"
ms.assetid: df28ab41-25fb-4ab3-b51d-7f695b24f55e
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Практическое руководство. Рисование изображения с помощью ImageDrawing
В этом примере показано использование класса <xref:System.Windows.Media.ImageDrawing> для рисования изображения.  Класс <xref:System.Windows.Media.ImageDrawing> позволяет отображать источник <xref:System.Windows.Media.ImageSource>, используя объекты <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.DrawingImage> или <xref:System.Windows.Media.Visual>.  Для создания изображения необходимо создать класс <xref:System.Windows.Media.ImageDrawing> и установить значения его свойств <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=fullName> и <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=fullName>.  Свойство <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=fullName> задает изображение для рисования, а свойство <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=fullName> задает положение и размер каждого изображения.  
  
## Пример  
 В следующем примере создается составной рисунок с помощью четырех объектов класса <xref:System.Windows.Media.ImageDrawing>.  В этом примере получается следующее изображение:  
  
 ![Несколько объектов DrawingImage](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagedrawingexample.png "graphicsmm\_ImageDrawingExample")  
Четыре объекта ImageDrawing  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawingExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawingexample)]
 [!code-xml[DrawingMiscSnippets_snip#ImageDrawingExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawingexample)]  
  
 Пример, демонстрирующий простой способ отображения изображения без использования класса <xref:System.Windows.Media.ImageDrawing>, см. в разделе [Использование элемента изображения](../../../../docs/framework/wpf/controls/how-to-use-the-image-element.md).  
  
## См. также  
 <xref:System.Windows.Freezable.Freeze%2A>   
 <xref:System.Windows.Controls.Image>   
 [Обзор объектов Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)   
 [Общие сведения об объектах класса Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)   
 [Атрибут PresentationOptions:Freeze](../../../../docs/framework/wpf/advanced/presentationoptions-freeze-attribute.md)