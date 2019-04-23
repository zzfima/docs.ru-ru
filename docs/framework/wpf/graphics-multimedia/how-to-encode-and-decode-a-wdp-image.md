---
title: Практическое руководство. Кодирование и декодирование изображения в формате WDP
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- WDP encoding [WPF]
- WDP decoding [WPF]
- encoding image formats [WPF]
- decoding WDP images [WPF]
- decoding image formats [WPF]
- encoding WDP images [WPF]
ms.assetid: 911777d1-516b-49db-a87b-b54e31b18532
ms.openlocfilehash: b143106092235b42044d264189c135d2cd65426c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59153365"
---
# <a name="how-to-encode-and-decode-a-wdp-image"></a><span data-ttu-id="5eda3-102">Практическое руководство. Кодирование и декодирование изображения в формате WDP</span><span class="sxs-lookup"><span data-stu-id="5eda3-102">How to: Encode and Decode a WDP Image</span></span>
<span data-ttu-id="5eda3-103">Следующие примеры показывают, как декодировать и кодировать [!INCLUDE[TLA#tla_wdp](../../../../includes/tlasharptla-wdp-md.md)] изображений, используя заданный <xref:System.Windows.Media.Imaging.WmpBitmapDecoder> и <xref:System.Windows.Media.Imaging.WmpBitmapEncoder> объектов.</span><span class="sxs-lookup"><span data-stu-id="5eda3-103">The following examples show how to decode and encode a [!INCLUDE[TLA#tla_wdp](../../../../includes/tlasharptla-wdp-md.md)] image using the specific <xref:System.Windows.Media.Imaging.WmpBitmapDecoder> and <xref:System.Windows.Media.Imaging.WmpBitmapEncoder> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5eda3-104">Пример</span><span class="sxs-lookup"><span data-stu-id="5eda3-104">Example</span></span>  
 <span data-ttu-id="5eda3-105">В этом примере показано, как декодировать [!INCLUDE[TLA2#tla_wdp](../../../../includes/tla2sharptla-wdp-md.md)] изображений с помощью <xref:System.Windows.Media.Imaging.WmpBitmapDecoder> из <xref:System.Uri>.</span><span class="sxs-lookup"><span data-stu-id="5eda3-105">This example demonstrates how to decode a [!INCLUDE[TLA2#tla_wdp](../../../../includes/tla2sharptla-wdp-md.md)] image using a <xref:System.Windows.Media.Imaging.WmpBitmapDecoder> from a <xref:System.Uri>.</span></span>  
  
 [!code-cpp[WdpBitmapDecoderEncoder#1](~/samples/snippets/cpp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CPP/WDPEncoderDecoder.cpp#1)]
 [!code-csharp[WdpBitmapDecoderEncoder#1](~/samples/snippets/csharp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CSharp/WDPEncoderDecoder.cs#1)]
 [!code-vb[WdpBitmapDecoderEncoder#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/VB/WDPEncoderDecoder.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="5eda3-106">Пример</span><span class="sxs-lookup"><span data-stu-id="5eda3-106">Example</span></span>  
 <span data-ttu-id="5eda3-107">В этом примере показаны способы кодирования <xref:System.Windows.Media.Imaging.BitmapSource> в [!INCLUDE[TLA2#tla_wdp](../../../../includes/tla2sharptla-wdp-md.md)] изображений с помощью <xref:System.Windows.Media.Imaging.WmpBitmapEncoder>.</span><span class="sxs-lookup"><span data-stu-id="5eda3-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a [!INCLUDE[TLA2#tla_wdp](../../../../includes/tla2sharptla-wdp-md.md)] image using a <xref:System.Windows.Media.Imaging.WmpBitmapEncoder>.</span></span>  
  
 [!code-cpp[WdpBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CPP/WDPEncoderDecoder.cpp#4)]
 [!code-csharp[WdpBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CSharp/WDPEncoderDecoder.cs#4)]
 [!code-vb[WdpBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/VB/WDPEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="5eda3-108">См. также</span><span class="sxs-lookup"><span data-stu-id="5eda3-108">See also</span></span>

- [<span data-ttu-id="5eda3-109">Общие сведения об обработке изображений</span><span class="sxs-lookup"><span data-stu-id="5eda3-109">Imaging Overview</span></span>](imaging-overview.md)
