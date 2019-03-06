---
title: Практическое руководство. Создание растрового изображения из Visual
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [WPF], rendering from visuals
- visuals [WPF], rendering to bitmaps
ms.assetid: 103fc7f5-7306-4026-9d61-2005e79959f3
ms.openlocfilehash: 429aacc99d8ead5a18e9be7602b19a74773b419a
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57362868"
---
# <a name="how-to-create-a-bitmap-from-a-visual"></a>Практическое руководство. Создание растрового изображения из Visual
В этом примере показано, как можно создать точечный рисунок из <xref:System.Windows.Media.Visual>. Объект <xref:System.Windows.Media.DrawingVisual> визуализируется с <xref:System.Windows.Media.FormattedText>. <xref:System.Windows.Media.Visual> Присваивается <xref:System.Windows.Media.Imaging.RenderTargetBitmap> создании точечного рисунка для заданного текста.  
  
## <a name="example"></a>Пример  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#CreateRTBImage](~/samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample.cs#creatertbimage)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#CreateRTBImage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample.vb#creatertbimage)]  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Media.DrawingContext>
- [Общие сведения об обработке изображений](imaging-overview.md)
- [Обзор объектов Drawing](drawing-objects-overview.md)
- [Использование объектов DrawingVisual](using-drawingvisual-objects.md)
