---
title: "Как загрузить изображение в виде эскиза"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- loading images as thumbnails [WPF]
- images [WPF], loading as thumbnails
- thumbnails [WPF], loading images as
ms.assetid: 02e055a0-54df-499a-b8b6-ab6ff7535cff
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: adcbd5fb82ce9ae89ac59db5aeb7f384f8cc1fc7
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-load-an-image-as-a-thumbnail"></a>Как загрузить изображение в виде эскиза
Следующие примеры показывают, как загрузить <xref:System.Windows.Controls.Image> виде эскиза для экономии памяти приложения.  
  
## <a name="example"></a>Пример  
 В следующем примере задается <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> свойство <xref:System.Windows.Media.Imaging.BitmapImage> в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] чтобы уменьшить память, необходимую для загрузки изображения.  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
## <a name="example"></a>Пример  
 В следующем примере задается <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> свойство <xref:System.Windows.Media.Imaging.BitmapImage> в коде, чтобы уменьшить память, необходимую для загрузки изображения.  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об обработке изображений](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
