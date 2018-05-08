---
title: Практическое руководство. Создание точечного рисунка из Visual
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [WPF], rendering from visuals
- visuals [WPF], rendering to bitmaps
ms.assetid: 103fc7f5-7306-4026-9d61-2005e79959f3
ms.openlocfilehash: 4735474d00712598cb5e41fad289e8f568d83a48
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-bitmap-from-a-visual"></a>Практическое руководство. Создание точечного рисунка из Visual
В этом примере показано, как можно создать точечный рисунок из <xref:System.Windows.Media.Visual>. Объект <xref:System.Windows.Media.DrawingVisual> визуализируется с <xref:System.Windows.Media.FormattedText>. <xref:System.Windows.Media.Visual> Присваивается <xref:System.Windows.Media.Imaging.RenderTargetBitmap> создания растрового рисунка заданного текста.  
  
## <a name="example"></a>Пример  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#CreateRTBImage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample.cs#creatertbimage)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#CreateRTBImage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample.vb#creatertbimage)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.DrawingContext>  
 [Общие сведения об обработке изображений](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)  
 [Обзор объектов Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [Использование объектов DrawingVisual](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md)
