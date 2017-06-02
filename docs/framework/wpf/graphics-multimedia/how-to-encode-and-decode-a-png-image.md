---
title: "Практическое руководство. Кодирование и декодирование изображения в формате PNG | Microsoft Docs"
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
  - "декодирование форматов изображения"
  - "декодирование изображений PNG"
  - "кодирование форматов изображения"
  - "кодирование изображений PNG"
  - "декодирование PNG"
  - "кодирование PNG"
ms.assetid: 3d31d186-af73-47f0-b5a7-c26ae46409a6
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Кодирование и декодирование изображения в формате PNG
В следующих примерах показано, как декодировать и кодировать изображение [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)], используя особые объекты <xref:System.Windows.Media.Imaging.PngBitmapDecoder> и <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.  
  
## Пример  
 В этом примере показано, как декодировать изображение [!INCLUDE[TLA2#tla_png](../../../../includes/tla2sharptla-png-md.md)] с помощью <xref:System.Windows.Media.Imaging.PngBitmapDecoder> из <xref:System.IO.FileStream>.  
  
 [!code-cpp[PngBitmapDecoderEncoder#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CPP/PngEncoderDecoder.cpp#1)]
 [!code-csharp[PngBitmapDecoderEncoder#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CSharp/PngEncoderDecoder.cs#1)]
 [!code-vb[PngBitmapDecoderEncoder#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PngBitmapDecoderEncoder/VB/PngEncoderDecoder.vb#1)]  
  
## Пример  
 В этом примере демонстрируется, как кодировать <xref:System.Windows.Media.Imaging.BitmapSource> в изображение в формате [!INCLUDE[TLA2#tla_png](../../../../includes/tla2sharptla-png-md.md)] с помощью <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.  
  
 [!code-cpp[PngBitmapDecoderEncoder#4](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CPP/PngEncoderDecoder.cpp#4)]
 [!code-csharp[PngBitmapDecoderEncoder#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CSharp/PngEncoderDecoder.cs#4)]
 [!code-vb[PngBitmapDecoderEncoder#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PngBitmapDecoderEncoder/VB/PngEncoderDecoder.vb#4)]  
  
## См. также  
 [Общие сведения об обработке изображений](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)