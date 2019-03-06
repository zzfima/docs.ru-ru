---
title: Практическое руководство. Загрузка изображения в виде эскиза
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- loading images as thumbnails [WPF]
- images [WPF], loading as thumbnails
- thumbnails [WPF], loading images as
ms.assetid: 02e055a0-54df-499a-b8b6-ab6ff7535cff
ms.openlocfilehash: 0b5435e9b06f37dae7dc762e9035b1eca8156ca6
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57353392"
---
# <a name="how-to-load-an-image-as-a-thumbnail"></a>Практическое руководство. Загрузка изображения в виде эскиза
Следующие примеры показывают, как загрузить <xref:System.Windows.Controls.Image> виде эскиза для экономии памяти приложения.  
  
## <a name="example"></a>Пример  
 В следующем примере задается <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> свойство <xref:System.Windows.Media.Imaging.BitmapImage> в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] чтобы уменьшить память, необходимую для загрузки изображения.  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
## <a name="example"></a>Пример  
 В следующем примере задается <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> свойство <xref:System.Windows.Media.Imaging.BitmapImage> в коде, чтобы уменьшить память, необходимую для загрузки изображения.  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
## <a name="see-also"></a>См. также
- [Общие сведения об обработке изображений](imaging-overview.md)
