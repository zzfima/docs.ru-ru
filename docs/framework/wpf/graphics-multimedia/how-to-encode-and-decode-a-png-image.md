---
title: Практическое руководство. Кодирование и декодирование изображения в формате PNG
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
ms.openlocfilehash: 46d4a7ffbfe7a6a620c26447cce30f3a0bd35adc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59090858"
---
# <a name="how-to-encode-and-decode-a-png-image"></a><span data-ttu-id="ada98-102">Практическое руководство. Кодирование и декодирование изображения в формате PNG</span><span class="sxs-lookup"><span data-stu-id="ada98-102">How to: Encode and Decode a PNG Image</span></span>
<span data-ttu-id="ada98-103">Следующие примеры показывают, как декодировать и кодировать [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)] изображений, используя заданный <xref:System.Windows.Media.Imaging.PngBitmapDecoder> и <xref:System.Windows.Media.Imaging.PngBitmapEncoder> объектов.</span><span class="sxs-lookup"><span data-stu-id="ada98-103">The following examples show how to decode and encode a [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)] image using the specific <xref:System.Windows.Media.Imaging.PngBitmapDecoder> and <xref:System.Windows.Media.Imaging.PngBitmapEncoder> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ada98-104">Пример</span><span class="sxs-lookup"><span data-stu-id="ada98-104">Example</span></span>  
 <span data-ttu-id="ada98-105">В этом примере показано, как декодировать [!INCLUDE[TLA2#tla_png](../../../../includes/tla2sharptla-png-md.md)] изображений с помощью <xref:System.Windows.Media.Imaging.PngBitmapDecoder> из <xref:System.IO.FileStream>.</span><span class="sxs-lookup"><span data-stu-id="ada98-105">This example demonstrates how to decode a [!INCLUDE[TLA2#tla_png](../../../../includes/tla2sharptla-png-md.md)] image using a <xref:System.Windows.Media.Imaging.PngBitmapDecoder> from a <xref:System.IO.FileStream>.</span></span>  
  
 [!code-cpp[PngBitmapDecoderEncoder#1](~/samples/snippets/cpp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CPP/PngEncoderDecoder.cpp#1)]
 [!code-csharp[PngBitmapDecoderEncoder#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CSharp/PngEncoderDecoder.cs#1)]
 [!code-vb[PngBitmapDecoderEncoder#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PngBitmapDecoderEncoder/VB/PngEncoderDecoder.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="ada98-106">Пример</span><span class="sxs-lookup"><span data-stu-id="ada98-106">Example</span></span>  
 <span data-ttu-id="ada98-107">В этом примере показаны способы кодирования <xref:System.Windows.Media.Imaging.BitmapSource> в [!INCLUDE[TLA2#tla_png](../../../../includes/tla2sharptla-png-md.md)] изображений с помощью <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.</span><span class="sxs-lookup"><span data-stu-id="ada98-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a [!INCLUDE[TLA2#tla_png](../../../../includes/tla2sharptla-png-md.md)] image using a <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.</span></span>  
  
 [!code-cpp[PngBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CPP/PngEncoderDecoder.cpp#4)]
 [!code-csharp[PngBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CSharp/PngEncoderDecoder.cs#4)]
 [!code-vb[PngBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PngBitmapDecoderEncoder/VB/PngEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="ada98-108">См. также</span><span class="sxs-lookup"><span data-stu-id="ada98-108">See also</span></span>

- [<span data-ttu-id="ada98-109">Общие сведения об обработке изображений</span><span class="sxs-lookup"><span data-stu-id="ada98-109">Imaging Overview</span></span>](imaging-overview.md)
