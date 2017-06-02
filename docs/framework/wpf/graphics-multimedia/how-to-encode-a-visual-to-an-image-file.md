---
title: "Инструкция по Кодированию Visual в Файл Изображения | Microsoft Docs"
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
  - "кодирование форматов изображения"
  - "файлы изображений, кодирование из визуальных элементов"
  - "визуальные элементы, кодирование в файл изображения"
ms.assetid: 2036385b-ea47-4d54-8027-5797f52c8149
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# Инструкция по Кодированию Visual в Файл Изображения
Этот пример показывает, как кодировать объект <xref:System.Windows.Media.Visual> в файл изображения с помощью <xref:System.Windows.Media.Imaging.RenderTargetBitmap> и <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.  
  
## Пример  
 <xref:System.Windows.Media.DrawingVisual> создается с использованием <xref:System.Windows.Media.Imaging.BitmapImage> и <xref:System.Windows.Media.FormattedText>, который отображается в <xref:System.Windows.Media.Imaging.RenderTargetBitmap>.  Отображенный точеный рисунок затем используется для создания <xref:System.Windows.Media.Imaging.BitmapFrame>, который добавляется к <xref:System.Windows.Media.Imaging.PngBitmapEncoder> для создания нового [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)] файла.  
  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample_Encode.cs#rtbencodeinline1)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample_Encode.vb#rtbencodeinline1)]  
  
 Хотя <xref:System.Windows.Media.Imaging.PngBitmapEncoder> было использовано в этом примере, любой из производных объектов <xref:System.Windows.Media.Imaging.BitmapEncoder> мог использоваться для создания файла изображения.  
  
## См. также  
 <xref:System.Windows.Media.DrawingContext>   
 [Общие сведения об обработке изображений](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)   
 [Обзор объектов Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)   
 [Использование объектов DrawingVisual](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md)