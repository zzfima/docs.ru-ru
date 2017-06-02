---
title: "Практическое руководство. Кодирование и декодирование изображения в формате GIF | Microsoft Docs"
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
  - "декодирование изображений GIF"
  - "декодирование форматов изображения"
  - "кодирование изображений GIF"
  - "кодирование форматов изображения"
  - "декодирование GIF"
  - "кодирование GIF"
ms.assetid: 9cdd9ec7-71eb-444b-b9e3-991958461163
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Практическое руководство. Кодирование и декодирование изображения в формате GIF
В следующих примерах показано, как декодировать и кодировать изображение [!INCLUDE[TLA#tla_gif](../../../../includes/tlasharptla-gif-md.md)], используя особые объекты <xref:System.Windows.Media.Imaging.GifBitmapDecoder> и <xref:System.Windows.Media.Imaging.GifBitmapEncoder>.  
  
## Пример  
 В этом примере показано, как декодировать изображение [!INCLUDE[TLA2#tla_gif](../../../../includes/tla2sharptla-gif-md.md)] с помощью объекта <xref:System.Windows.Media.Imaging.GifBitmapDecoder> из объекта <xref:System.IO.FileStream>.  
  
 [!code-cpp[GifBitmapDecoderEncoder#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CPP/GifEncoderDecoder.cpp#1)]
 [!code-csharp[GifBitmapDecoderEncoder#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CSharp/GifEncoderDecoder.cs#1)]
 [!code-vb[GifBitmapDecoderEncoder#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GifBitmapDecoderEncoder/VB/GifEncoderDecoder.vb#1)]  
  
## Пример  
 В данном примере демонстрируется, как кодировать объект <xref:System.Windows.Media.Imaging.BitmapSource> в изображение формата [!INCLUDE[TLA2#tla_gif](../../../../includes/tla2sharptla-gif-md.md)] с помощью объекта <xref:System.Windows.Media.Imaging.GifBitmapEncoder>.  
  
 [!code-cpp[GifBitmapDecoderEncoder#4](../../../../samples/snippets/cpp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CPP/GifEncoderDecoder.cpp#4)]
 [!code-csharp[GifBitmapDecoderEncoder#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CSharp/GifEncoderDecoder.cs#4)]
 [!code-vb[GifBitmapDecoderEncoder#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GifBitmapDecoderEncoder/VB/GifEncoderDecoder.vb#4)]  
  
## См. также  
 [Общие сведения об обработке изображений](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)