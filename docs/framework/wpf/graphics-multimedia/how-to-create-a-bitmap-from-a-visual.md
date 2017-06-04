---
title: "Практическое руководство. Создание точечного рисунка из Visual | Microsoft Docs"
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
  - "растровые изображения, отрисовка из графических параметров"
  - "визуальные элементы, отрисовка в растровые изображения"
ms.assetid: 103fc7f5-7306-4026-9d61-2005e79959f3
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Практическое руководство. Создание точечного рисунка из Visual
В этом примере показано, как создать точечный рисунок из <xref:System.Windows.Media.Visual>.  <xref:System.Windows.Media.DrawingVisual> отображается с <xref:System.Windows.Media.FormattedText>.  <xref:System.Windows.Media.Visual> затем преобразуется в <xref:System.Windows.Media.Imaging.RenderTargetBitmap>. При этом создается точечный рисунок заданного текста.  
  
## Пример  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#CreateRTBImage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample.cs#creatertbimage)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#CreateRTBImage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample.vb#creatertbimage)]  
  
## См. также  
 <xref:System.Windows.Media.DrawingContext>   
 [Общие сведения об обработке изображений](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)   
 [Обзор объектов Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)   
 [Использование объектов DrawingVisual](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md)