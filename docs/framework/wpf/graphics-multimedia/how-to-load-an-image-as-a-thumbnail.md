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
# <a name="how-to-load-an-image-as-a-thumbnail"></a><span data-ttu-id="2a540-102">Как загрузить изображение в виде эскиза</span><span class="sxs-lookup"><span data-stu-id="2a540-102">How to: Load an Image as a Thumbnail</span></span>
<span data-ttu-id="2a540-103">Следующие примеры показывают, как загрузить <xref:System.Windows.Controls.Image> виде эскиза для экономии памяти приложения.</span><span class="sxs-lookup"><span data-stu-id="2a540-103">The following examples show how to load an <xref:System.Windows.Controls.Image> as a thumbnail to conserve application memory.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a540-104">Пример</span><span class="sxs-lookup"><span data-stu-id="2a540-104">Example</span></span>  
 <span data-ttu-id="2a540-105">В следующем примере задается <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> свойство <xref:System.Windows.Media.Imaging.BitmapImage> в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] чтобы уменьшить память, необходимую для загрузки изображения.</span><span class="sxs-lookup"><span data-stu-id="2a540-105">The following example sets the <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> property of a <xref:System.Windows.Media.Imaging.BitmapImage> in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to reduce the memory required to load the image.</span></span>  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
## <a name="example"></a><span data-ttu-id="2a540-106">Пример</span><span class="sxs-lookup"><span data-stu-id="2a540-106">Example</span></span>  
 <span data-ttu-id="2a540-107">В следующем примере задается <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> свойство <xref:System.Windows.Media.Imaging.BitmapImage> в коде, чтобы уменьшить память, необходимую для загрузки изображения.</span><span class="sxs-lookup"><span data-stu-id="2a540-107">The following example sets the <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> property of a <xref:System.Windows.Media.Imaging.BitmapImage> in code to reduce the memory required to load the image.</span></span>  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
## <a name="see-also"></a><span data-ttu-id="2a540-108">См. также</span><span class="sxs-lookup"><span data-stu-id="2a540-108">See Also</span></span>  
 [<span data-ttu-id="2a540-109">Общие сведения об обработке изображений</span><span class="sxs-lookup"><span data-stu-id="2a540-109">Imaging Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
