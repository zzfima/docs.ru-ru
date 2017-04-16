---
title: "Как раскрасить область с видео | Microsoft Docs"
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
  - "кисти, рисование с видео"
  - "рисование с видео"
  - "видео, рисование с помощью"
ms.assetid: 04dd6600-4a6e-4b43-a93e-21cce7dfbcb8
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Как раскрасить область с видео
В этом примере демонстрируется рисование области с мультимедиа.  Одним из способов рисования области с мультимедиа является использование <xref:System.Windows.Controls.MediaElement> вместе с <xref:System.Windows.Media.VisualBrush>.  Используйте объект <xref:System.Windows.Controls.MediaElement> для загрузки и воспроизведения файла мультимедиа, а затем используйте его, чтобы задать свойство <xref:System.Windows.Media.VisualBrush.Visual%2A> для <xref:System.Windows.Media.VisualBrush>.  Затем можно использовать <xref:System.Windows.Media.VisualBrush> для закрашивания области с загруженным мультимедиа.  
  
## Пример  
 Следующий пример использует <xref:System.Windows.Controls.MediaElement> и <xref:System.Windows.Media.VisualBrush>, чтобы раскрасить <xref:System.Windows.Controls.TextBlock.Foreground%2A> элемента управления <xref:System.Windows.Controls.TextBlock> с видео.  Этот пример задает для свойства <xref:System.Windows.Controls.MediaElement.IsMuted%2A> объекта <xref:System.Windows.Controls.MediaElement> значение `true`, чтобы отключить звук.  
  
 [!code-csharp[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/PaintWithVideoExample.cs#graphicsmmvideoastextbackgroundinline)]
 [!code-vb[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/paintwithvideoexample.vb#graphicsmmvideoastextbackgroundinline)]
 [!code-xml[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/PaintWithVideoExample.xaml#graphicsmmvideoastextbackgroundinline)]  
  
## Пример  
 Поскольку объект <xref:System.Windows.Media.VisualBrush> наследуется из класса <xref:System.Windows.Media.TileBrush>, он предоставляет несколько режимов заполнения.  Установив для свойства <xref:System.Windows.Media.TileBrush.TileMode%2A> объекта <xref:System.Windows.Media.VisualBrush> значение <xref:System.Windows.Media.TileMode> и задав его свойству <xref:System.Windows.Media.TileBrush.Viewport%2A> значение меньше, чем область закрашивания, можно создать шаблон заполнения.  
  
 Следующий пример идентичен предыдущему, за исключением того, что <xref:System.Windows.Media.VisualBrush> создает шаблон из видео.  
  
 [!code-csharp[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/PaintWithVideoExample.cs#graphicsmmvideoastextbackgroundtiledinline)]
 [!code-vb[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/paintwithvideoexample.vb#graphicsmmvideoastextbackgroundtiledinline)]
 [!code-xml[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/PaintWithVideoExample.xaml#graphicsmmvideoastextbackgroundtiledinline)]  
  
 Сведения о добавлении файла содержимого, например файла мультимедиа, к приложению содержатся в разделе [Ресурсы, Содержимое и Файлы данных WPF\-приложения](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md).  При добавлении файла мультимедиа необходимо добавить его как файл содержимого, а не как файл ресурса.  
  
## См. также  
 <xref:System.Windows.Media.VisualBrush>   
 [Рисование с помощью объектов Image, Drawing и Visual](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)   
 [Общие сведения о TileBrush](../../../../docs/framework/wpf/graphics-multimedia/tilebrush-overview.md)   
 [Общие сведения о мультимедиа](../../../../docs/framework/wpf/graphics-multimedia/multimedia-overview.md)