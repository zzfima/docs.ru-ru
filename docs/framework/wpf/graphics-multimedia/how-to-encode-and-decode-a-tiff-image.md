---
title: Как выполнить Кодирование и декодирование изображения в формате TIFF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TIFF encoding [WPF]
- encoding TIFF images [WPF]
- encoding image formats [WPF]
- decoding TIFF images [WPF]
- decoding image formats [WPF]
- TIFF decoding [WPF]
ms.assetid: 1dfe3209-fc73-40e6-ad1c-71c1c58b3364
ms.openlocfilehash: 0b1d5f19583e0a0014903ef6ace01bc164b70d0b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54696169"
---
# <a name="how-to-encode-and-decode-a-tiff-image"></a><span data-ttu-id="ff736-102">Как выполнить Кодирование и декодирование изображения в формате TIFF</span><span class="sxs-lookup"><span data-stu-id="ff736-102">How to: Encode and Decode a TIFF Image</span></span>
<span data-ttu-id="ff736-103">Следующие примеры показывают, как декодировать и кодировать [!INCLUDE[TLA#tla_tiff](../../../../includes/tlasharptla-tiff-md.md)] изображений, используя заданный <xref:System.Windows.Media.Imaging.TiffBitmapDecoder> и <xref:System.Windows.Media.Imaging.TiffBitmapEncoder> объектов.</span><span class="sxs-lookup"><span data-stu-id="ff736-103">The following examples show how to decode and encode a [!INCLUDE[TLA#tla_tiff](../../../../includes/tlasharptla-tiff-md.md)] image using the specific <xref:System.Windows.Media.Imaging.TiffBitmapDecoder> and <xref:System.Windows.Media.Imaging.TiffBitmapEncoder> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff736-104">Пример</span><span class="sxs-lookup"><span data-stu-id="ff736-104">Example</span></span>  
 <span data-ttu-id="ff736-105">В этом примере показано, как декодировать [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)] изображений с помощью <xref:System.Windows.Media.Imaging.TiffBitmapDecoder> из <xref:System.Uri>.</span><span class="sxs-lookup"><span data-stu-id="ff736-105">This example demonstrates how to decode a [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)] image using a <xref:System.Windows.Media.Imaging.TiffBitmapDecoder> from a <xref:System.Uri>.</span></span>  
  
 [!code-cpp[TiffBitmapDecoderEncoder#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CPP/TiffEncoderDecoder.cpp#1)]
 [!code-csharp[TiffBitmapDecoderEncoder#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CSharp/TiffEncoderDecoder.cs#1)]
 [!code-vb[TiffBitmapDecoderEncoder#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/VB/TiffEncoderDecoder.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="ff736-106">Пример</span><span class="sxs-lookup"><span data-stu-id="ff736-106">Example</span></span>  
 <span data-ttu-id="ff736-107">В этом примере показаны способы кодирования <xref:System.Windows.Media.Imaging.BitmapSource> в [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)] изображений с помощью <xref:System.Windows.Media.Imaging.TiffBitmapEncoder>.</span><span class="sxs-lookup"><span data-stu-id="ff736-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)] image using a <xref:System.Windows.Media.Imaging.TiffBitmapEncoder>.</span></span>  
  
 [!code-cpp[TiffBitmapDecoderEncoder#4](../../../../samples/snippets/cpp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CPP/TiffEncoderDecoder.cpp#4)]
 [!code-csharp[TiffBitmapDecoderEncoder#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CSharp/TiffEncoderDecoder.cs#4)]
 [!code-vb[TiffBitmapDecoderEncoder#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/VB/TiffEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="ff736-108">См. также</span><span class="sxs-lookup"><span data-stu-id="ff736-108">See also</span></span>
- [<span data-ttu-id="ff736-109">Общие сведения об обработке изображений</span><span class="sxs-lookup"><span data-stu-id="ff736-109">Imaging Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
