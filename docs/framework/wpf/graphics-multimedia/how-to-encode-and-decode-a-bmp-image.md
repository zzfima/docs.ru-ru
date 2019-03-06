---
title: Практическое руководство. Кодирование и декодирование изображения в формате BMP
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- encoding BMP images [WPF]
- BMP encoding [WPF]
- decoding BMP images [WPF]
- encoding image formats [WPF]
- BMP decoding [WPF]
- decoding image formats [WPF]
ms.assetid: feb5ef27-28ac-40ab-bfc2-e0456990d32c
ms.openlocfilehash: 5aee77ab70c6a24846967b01bbb458ba4cdbe970
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57379631"
---
# <a name="how-to-encode-and-decode-a-bmp-image"></a><span data-ttu-id="01bac-102">Практическое руководство. Кодирование и декодирование изображения в формате BMP</span><span class="sxs-lookup"><span data-stu-id="01bac-102">How to: Encode and Decode a BMP Image</span></span>
<span data-ttu-id="01bac-103">Следующие примеры показывают, как декодировать и кодировать [!INCLUDE[TLA#tla_bmp](../../../../includes/tlasharptla-bmp-md.md)] изображений, используя заданный <xref:System.Windows.Media.Imaging.BmpBitmapDecoder> и <xref:System.Windows.Media.Imaging.BmpBitmapEncoder> объектов.</span><span class="sxs-lookup"><span data-stu-id="01bac-103">The following examples show how to decode and encode a [!INCLUDE[TLA#tla_bmp](../../../../includes/tlasharptla-bmp-md.md)] image using the specific <xref:System.Windows.Media.Imaging.BmpBitmapDecoder> and <xref:System.Windows.Media.Imaging.BmpBitmapEncoder> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="01bac-104">Пример</span><span class="sxs-lookup"><span data-stu-id="01bac-104">Example</span></span>  
 <span data-ttu-id="01bac-105">В этом примере показано, как декодировать [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)] изображений с помощью <xref:System.Windows.Media.Imaging.BmpBitmapDecoder> из <xref:System.Uri>.</span><span class="sxs-lookup"><span data-stu-id="01bac-105">This example demonstrates how to decode a [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)] image using a <xref:System.Windows.Media.Imaging.BmpBitmapDecoder> from a <xref:System.Uri>.</span></span>  
  
 [!code-cpp[BmpBitmapDecoderEncoder#5](~/samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#5)]
 [!code-csharp[BmpBitmapDecoderEncoder#5](~/samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#5)]
 [!code-vb[BmpBitmapDecoderEncoder#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="01bac-106">Пример</span><span class="sxs-lookup"><span data-stu-id="01bac-106">Example</span></span>  
 <span data-ttu-id="01bac-107">В этом примере показаны способы кодирования <xref:System.Windows.Media.Imaging.BitmapSource> в [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)] изображений с помощью <xref:System.Windows.Media.Imaging.BmpBitmapEncoder>.</span><span class="sxs-lookup"><span data-stu-id="01bac-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)] image using a <xref:System.Windows.Media.Imaging.BmpBitmapEncoder>.</span></span>  
  
 [!code-cpp[BmpBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#4)]
 [!code-csharp[BmpBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#4)]
 [!code-vb[BmpBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="01bac-108">См. также</span><span class="sxs-lookup"><span data-stu-id="01bac-108">See also</span></span>
- [<span data-ttu-id="01bac-109">Общие сведения об обработке изображений</span><span class="sxs-lookup"><span data-stu-id="01bac-109">Imaging Overview</span></span>](imaging-overview.md)
