---
title: "Практическое руководство. Кодирование и декодирование изображения в формате JPEG | Microsoft Docs"
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
  - "декодирование изображений JPEG"
  - "кодирование форматов изображения"
  - "кодирование изображений JPEG"
  - "декодирование JPEG"
  - "кодирование JPEG"
ms.assetid: b8cfde37-9f68-4911-a05e-51d8d7bdec7b
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Кодирование и декодирование изображения в формате JPEG
В следующих примерах показано, как декодировать и кодировать изображение [!INCLUDE[TLA#tla_jpeg](../../../../includes/tlasharptla-jpeg-md.md)], используя особые объекты <xref:System.Windows.Media.Imaging.JpegBitmapDecoder> и <xref:System.Windows.Media.Imaging.JpegBitmapEncoder>.  
  
## Пример  
 В этом примере показано, как декодировать изображение [!INCLUDE[TLA2#tla_jpeg](../../../../includes/tla2sharptla-jpeg-md.md)] с помощью объекта <xref:System.Windows.Media.Imaging.JpegBitmapDecoder> из объекта <xref:System.IO.FileStream>.  
  
 [!code-cpp[JpegBitmapDecoderEncoder#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CPP/jpegencoderdecoder.cpp#1)]
 [!code-csharp[JpegBitmapDecoderEncoder#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CSharp/JpegEncoderDecoder.cs#1)]
 [!code-vb[JpegBitmapDecoderEncoder#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/VB/JpegEncoderDecoder.vb#1)]  
  
## Пример  
 В этом примере описывается порядок кодирования объекта <xref:System.Windows.Media.Imaging.BitmapSource> в изображение в формате [!INCLUDE[TLA2#tla_jpeg](../../../../includes/tla2sharptla-jpeg-md.md)] с помощью объекта <xref:System.Windows.Media.Imaging.JpegBitmapEncoder>.  
  
 [!code-cpp[JpegBitmapDecoderEncoder#4](../../../../samples/snippets/cpp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CPP/jpegencoderdecoder.cpp#4)]
 [!code-csharp[JpegBitmapDecoderEncoder#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CSharp/JpegEncoderDecoder.cs#4)]
 [!code-vb[JpegBitmapDecoderEncoder#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/VB/JpegEncoderDecoder.vb#4)]  
  
## Безопасность платформы .NET Framework  
  
## См. также  
 [Общие сведения об обработке изображений](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)