---
title: "Инструкция по закрашиванию области с изображением | Microsoft Docs"
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
  - "кисти, рисование с помощью изображений"
  - "изображения, рисование с помощью"
  - "рисование, с помощью изображений"
ms.assetid: 3432c533-1fc7-492d-94ee-0b13d60125ae
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Инструкция по закрашиванию области с изображением
В этом примере показано использование класса <xref:System.Windows.Media.ImageBrush> для закраски области с изображением.  <xref:System.Windows.Media.ImageBrush> отображает одно изображение, которое задается его свойством <xref:System.Windows.Media.ImageBrush.ImageSource%2A>.  
  
## Пример  
 В следующем примере закрашивается <xref:System.Windows.Controls.Control.Background%2A> кнопки с использованием <xref:System.Windows.Media.ImageBrush>.  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/PaintingWithImagesExample.cs#imagebrushexamplewholepage)]  
  
 По умолчанию, <xref:System.Windows.Media.ImageBrush> увеличивает изображение для полного заполнения закрашиваемой области.  В предыдущем примере изображение было растянуто до заполнения кнопки, возможно с искажением изображения.  Такое поведение можно контролировать, установив свойства <xref:System.Windows.Media.TileBrush.Stretch%2A> из <xref:System.Windows.Media.TileBrush> в <xref:System.Windows.Media.Stretch> или <xref:System.Windows.Media.Stretch>, в результате чего кисть сохранит [пропорции](GTMT) изображения.  
  
 При задании свойств <xref:System.Windows.Media.TileBrush.Viewport%2A> и <xref:System.Windows.Media.TileBrush.TileMode%2A> из <xref:System.Windows.Media.ImageBrush>, вы можете создать повторяющийся рисунок.  Следующий пример закрашивает кнопку с помощью рисунка, созданного из изображения.  
  
 [!code-csharp[UsingImageBrush_snip#TiledImageBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TiledImageBrushExample.cs#tiledimagebrushexamplewholepage)]
 [!code-vb[UsingImageBrush_snip#TiledImageBrushExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UsingImageBrush_snip/VisualBasic/TiledImageBrushExample.vb#tiledimagebrushexamplewholepage)]  
  
 Дополнительные сведения о классе <xref:System.Windows.Media.ImageBrush> см. в разделе [Рисование с помощью объектов Image, Drawing и Visual](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
 Этот пример кода является частью более крупного примера для класса <xref:System.Windows.Media.ImageBrush>.  Полный код примера см. в разделе [Пример ImageBrush](http://go.microsoft.com/fwlink/?LinkID=160005).  
  
## См. также  
 [Рисование с помощью объектов Image, Drawing и Visual](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)