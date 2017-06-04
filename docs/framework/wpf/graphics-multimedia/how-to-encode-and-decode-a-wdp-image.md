---
title: "Практическое руководство. Кодирование и декодирование изображения в формате WDP | Microsoft Docs"
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
  - "декодирование изображений WDP"
  - "кодирование форматов изображения"
  - "кодирование изображений WDP"
  - "декодирование WDP"
  - "кодирование WDP"
ms.assetid: 911777d1-516b-49db-a87b-b54e31b18532
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Практическое руководство. Кодирование и декодирование изображения в формате WDP
В следующих примерах показано, как декодировать и кодировать изображение [!INCLUDE[TLA#tla_wdp](../../../../includes/tlasharptla-wdp-md.md)], используя особые объекты <xref:System.Windows.Media.Imaging.WmpBitmapDecoder> и <xref:System.Windows.Media.Imaging.WmpBitmapEncoder>.  
  
## Пример  
 В этом примере показано, как декодировать изображение [!INCLUDE[TLA2#tla_wdp](../../../../includes/tla2sharptla-wdp-md.md)] с помощью объекта <xref:System.Windows.Media.Imaging.WmpBitmapDecoder> из объекта <xref:System.Uri>.  
  
 [!code-cpp[WdpBitmapDecoderEncoder#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CPP/WDPEncoderDecoder.cpp#1)]
 [!code-csharp[WdpBitmapDecoderEncoder#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CSharp/WDPEncoderDecoder.cs#1)]
 [!code-vb[WdpBitmapDecoderEncoder#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/VB/WDPEncoderDecoder.vb#1)]  
  
## Пример  
 В данном примере показано, как кодировать <xref:System.Windows.Media.Imaging.BitmapSource> в изображение в формате [!INCLUDE[TLA2#tla_wdp](../../../../includes/tla2sharptla-wdp-md.md)] с помощью объекта <xref:System.Windows.Media.Imaging.WmpBitmapEncoder>.  
  
 [!code-cpp[WdpBitmapDecoderEncoder#4](../../../../samples/snippets/cpp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CPP/WDPEncoderDecoder.cpp#4)]
 [!code-csharp[WdpBitmapDecoderEncoder#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CSharp/WDPEncoderDecoder.cs#4)]
 [!code-vb[WdpBitmapDecoderEncoder#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/VB/WDPEncoderDecoder.vb#4)]  
  
## См. также  
 [Общие сведения об обработке изображений](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)