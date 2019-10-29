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
ms.openlocfilehash: 8c5c312c7e58d48a865e493c38c3defd3f5f3d1d
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040780"
---
# <a name="how-to-encode-and-decode-a-wdp-image"></a>Практическое руководство. Кодирование и декодирование изображения в формате WDP
В следующих примерах показано, как декодировать и кодировать фото-изображение Microsoft Windows Media с помощью конкретных <xref:System.Windows.Media.Imaging.WmpBitmapDecoder> и <xref:System.Windows.Media.Imaging.WmpBitmapEncoder> объектов.  
  
## <a name="example"></a>Пример  
 В этом примере показано, как декодировать изображение фотографии Windows Media с помощью <xref:System.Windows.Media.Imaging.WmpBitmapDecoder> из <xref:System.Uri>.  
  
 [!code-cpp[WdpBitmapDecoderEncoder#1](~/samples/snippets/cpp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CPP/WDPEncoderDecoder.cpp#1)]
 [!code-csharp[WdpBitmapDecoderEncoder#1](~/samples/snippets/csharp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CSharp/WDPEncoderDecoder.cs#1)]
 [!code-vb[WdpBitmapDecoderEncoder#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/VB/WDPEncoderDecoder.vb#1)]  
  
## <a name="example"></a>Пример  
 В этом примере показано, как кодировать <xref:System.Windows.Media.Imaging.BitmapSource> в фото-образ Windows Media с помощью <xref:System.Windows.Media.Imaging.WmpBitmapEncoder>.  
  
 [!code-cpp[WdpBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CPP/WDPEncoderDecoder.cpp#4)]
 [!code-csharp[WdpBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CSharp/WDPEncoderDecoder.cs#4)]
 [!code-vb[WdpBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/VB/WDPEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a>См. также

- [Общие сведения об обработке изображений](imaging-overview.md)
