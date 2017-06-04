---
title: "Практическое руководство. Кодирование и декодирование изображения в формате TIFF | Microsoft Docs"
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
  - "декодирование изображений TIFF"
  - "кодирование форматов изображения"
  - "кодирование изображений TIFF"
  - "декодирование TIFF"
  - "кодирование TIFF"
ms.assetid: 1dfe3209-fc73-40e6-ad1c-71c1c58b3364
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Практическое руководство. Кодирование и декодирование изображения в формате TIFF
В следующих примерах показано, как декодировать и кодировать изображение [!INCLUDE[TLA#tla_tiff](../../../../includes/tlasharptla-tiff-md.md)], используя особые объекты <xref:System.Windows.Media.Imaging.TiffBitmapDecoder> и <xref:System.Windows.Media.Imaging.TiffBitmapEncoder>.  
  
## Пример  
 В этом примере показано, как декодировать изображение [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)] с помощью <xref:System.Windows.Media.Imaging.TiffBitmapDecoder> из <xref:System.Uri>.  
  
 [!code-cpp[TiffBitmapDecoderEncoder#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CPP/TiffEncoderDecoder.cpp#1)]
 [!code-csharp[TiffBitmapDecoderEncoder#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CSharp/TiffEncoderDecoder.cs#1)]
 [!code-vb[TiffBitmapDecoderEncoder#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/VB/TiffEncoderDecoder.vb#1)]  
  
## Пример  
 В этом примере демонстрируется, как кодировать <xref:System.Windows.Media.Imaging.BitmapSource> в изображение в формате [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)] с помощью <xref:System.Windows.Media.Imaging.TiffBitmapEncoder>.  
  
 [!code-cpp[TiffBitmapDecoderEncoder#4](../../../../samples/snippets/cpp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CPP/TiffEncoderDecoder.cpp#4)]
 [!code-csharp[TiffBitmapDecoderEncoder#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CSharp/TiffEncoderDecoder.cs#4)]
 [!code-vb[TiffBitmapDecoderEncoder#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/VB/TiffEncoderDecoder.vb#4)]  
  
## См. также  
 [Общие сведения об обработке изображений](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)