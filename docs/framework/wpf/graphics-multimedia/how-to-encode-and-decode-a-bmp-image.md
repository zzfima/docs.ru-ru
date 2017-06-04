---
title: "Практическое руководство. Кодирование и декодирование изображения в формате BMP | Microsoft Docs"
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
  - "декодирование BMP"
  - "кодирование BMP"
  - "декодирование изображений BMP"
  - "декодирование форматов изображения"
  - "кодирование изображений BMP"
  - "кодирование форматов изображения"
ms.assetid: feb5ef27-28ac-40ab-bfc2-e0456990d32c
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Кодирование и декодирование изображения в формате BMP
В следующих примерах показано, как декодировать и кодировать изображение [!INCLUDE[TLA#tla_bmp](../../../../includes/tlasharptla-bmp-md.md)], используя особые объекты <xref:System.Windows.Media.Imaging.BmpBitmapDecoder> и <xref:System.Windows.Media.Imaging.BmpBitmapEncoder>.  
  
## Пример  
 В этом примере показано, как декодировать изображение в формате [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)] с помощью объекта <xref:System.Windows.Media.Imaging.BmpBitmapDecoder> из объекта <xref:System.Uri>.  
  
 [!code-cpp[BmpBitmapDecoderEncoder#5](../../../../samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#5)]
 [!code-csharp[BmpBitmapDecoderEncoder#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#5)]
 [!code-vb[BmpBitmapDecoderEncoder#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#5)]  
  
## Пример  
 В этом примере описывается порядок кодирования объекта <xref:System.Windows.Media.Imaging.BitmapSource> в изображение в формате [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)] с помощью объекта <xref:System.Windows.Media.Imaging.BmpBitmapEncoder>.  
  
 [!code-cpp[BmpBitmapDecoderEncoder#4](../../../../samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#4)]
 [!code-csharp[BmpBitmapDecoderEncoder#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#4)]
 [!code-vb[BmpBitmapDecoderEncoder#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#4)]  
  
## См. также  
 [Общие сведения об обработке изображений](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)