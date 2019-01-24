---
title: Как выполнить Загрузка изображения в виде эскиза
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- loading images as thumbnails [WPF]
- images [WPF], loading as thumbnails
- thumbnails [WPF], loading images as
ms.assetid: 02e055a0-54df-499a-b8b6-ab6ff7535cff
ms.openlocfilehash: d92a489f19f8c7160bed5ec83535bdc33cfe561b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54735993"
---
# <a name="how-to-load-an-image-as-a-thumbnail"></a>Как выполнить Загрузка изображения в виде эскиза
Следующие примеры показывают, как загрузить <xref:System.Windows.Controls.Image> виде эскиза для экономии памяти приложения.  
  
## <a name="example"></a>Пример  
 В следующем примере задается <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> свойство <xref:System.Windows.Media.Imaging.BitmapImage> в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] чтобы уменьшить память, необходимую для загрузки изображения.  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
## <a name="example"></a>Пример  
 В следующем примере задается <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> свойство <xref:System.Windows.Media.Imaging.BitmapImage> в коде, чтобы уменьшить память, необходимую для загрузки изображения.  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
## <a name="see-also"></a>См. также
- [Общие сведения об обработке изображений](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
