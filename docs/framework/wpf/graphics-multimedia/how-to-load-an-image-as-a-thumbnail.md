---
title: "Как загрузить изображение в виде эскиза | Microsoft Docs"
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
  - "изображения, загрузка в виде эскизов"
  - "загрузка изображений в виде эскизов"
  - "Эскизы, загрузка изображений как"
ms.assetid: 02e055a0-54df-499a-b8b6-ab6ff7535cff
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Как загрузить изображение в виде эскиза
В следующих примерах показана загрузка объекта <xref:System.Windows.Controls.Image> в виде эскиза для экономии памяти приложения.  
  
## Пример  
 В следующем примере устанавливается свойство <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> объекта <xref:System.Windows.Media.Imaging.BitmapImage> [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], чтобы уменьшить память, необходимую для загрузки изображения.  
  
 [!code-xml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
## Пример  
 В следующем примере устанавливается свойство <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> объекта <xref:System.Windows.Media.Imaging.BitmapImage> в коде, чтобы уменьшить память, необходимую для загрузки изображения.  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
## См. также  
 [Общие сведения об обработке изображений](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)