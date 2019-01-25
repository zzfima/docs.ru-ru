---
title: Как выполнить Кодирование и декодирование изображения в формате PNG
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- PNG encoding [WPF]
- decoding PNG images [WPF]
- PNG decoding [WPF]
- encoding image formats [WPF]
- decoding image formats [WPF]
- encoding PNG images [WPF]
ms.assetid: 3d31d186-af73-47f0-b5a7-c26ae46409a6
ms.openlocfilehash: 3e3f4d498b18901538b1d6df0ade3b8017407346
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54740129"
---
# <a name="how-to-encode-and-decode-a-png-image"></a><span data-ttu-id="16da6-102">Как выполнить Кодирование и декодирование изображения в формате PNG</span><span class="sxs-lookup"><span data-stu-id="16da6-102">How to: Encode and Decode a PNG Image</span></span>
<span data-ttu-id="16da6-103">Следующие примеры показывают, как декодировать и кодировать [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)] изображений, используя заданный <xref:System.Windows.Media.Imaging.PngBitmapDecoder> и <xref:System.Windows.Media.Imaging.PngBitmapEncoder> объектов.</span><span class="sxs-lookup"><span data-stu-id="16da6-103">The following examples show how to decode and encode a [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)] image using the specific <xref:System.Windows.Media.Imaging.PngBitmapDecoder> and <xref:System.Windows.Media.Imaging.PngBitmapEncoder> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="16da6-104">Пример</span><span class="sxs-lookup"><span data-stu-id="16da6-104">Example</span></span>  
 <span data-ttu-id="16da6-105">В этом примере показано, как декодировать [!INCLUDE[TLA2#tla_png](../../../../includes/tla2sharptla-png-md.md)] изображений с помощью <xref:System.Windows.Media.Imaging.PngBitmapDecoder> из <xref:System.IO.FileStream>.</span><span class="sxs-lookup"><span data-stu-id="16da6-105">This example demonstrates how to decode a [!INCLUDE[TLA2#tla_png](../../../../includes/tla2sharptla-png-md.md)] image using a <xref:System.Windows.Media.Imaging.PngBitmapDecoder> from a <xref:System.IO.FileStream>.</span></span>  
  
 [!code-cpp[PngBitmapDecoderEncoder#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CPP/PngEncoderDecoder.cpp#1)]
 [!code-csharp[PngBitmapDecoderEncoder#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CSharp/PngEncoderDecoder.cs#1)]
 [!code-vb[PngBitmapDecoderEncoder#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PngBitmapDecoderEncoder/VB/PngEncoderDecoder.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="16da6-106">Пример</span><span class="sxs-lookup"><span data-stu-id="16da6-106">Example</span></span>  
 <span data-ttu-id="16da6-107">В этом примере показаны способы кодирования <xref:System.Windows.Media.Imaging.BitmapSource> в [!INCLUDE[TLA2#tla_png](../../../../includes/tla2sharptla-png-md.md)] изображений с помощью <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.</span><span class="sxs-lookup"><span data-stu-id="16da6-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a [!INCLUDE[TLA2#tla_png](../../../../includes/tla2sharptla-png-md.md)] image using a <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.</span></span>  
  
 [!code-cpp[PngBitmapDecoderEncoder#4](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CPP/PngEncoderDecoder.cpp#4)]
 [!code-csharp[PngBitmapDecoderEncoder#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CSharp/PngEncoderDecoder.cs#4)]
 [!code-vb[PngBitmapDecoderEncoder#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PngBitmapDecoderEncoder/VB/PngEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="16da6-108">См. также</span><span class="sxs-lookup"><span data-stu-id="16da6-108">See also</span></span>
- [<span data-ttu-id="16da6-109">Общие сведения об обработке изображений</span><span class="sxs-lookup"><span data-stu-id="16da6-109">Imaging Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
