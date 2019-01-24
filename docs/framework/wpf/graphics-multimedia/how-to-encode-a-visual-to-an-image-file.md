---
title: Как выполнить Кодирование визуального объекта в файл изображения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image files [WPF], encoding from visuals
- encoding image formats [WPF]
- visuals [WPF], encoding to an image file
ms.assetid: 2036385b-ea47-4d54-8027-5797f52c8149
ms.openlocfilehash: e8988256d4b7181c5e1af12252ca26e0248d016f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54645227"
---
# <a name="how-to-encode-a-visual-to-an-image-file"></a>Как выполнить Кодирование визуального объекта в файл изображения
В этом примере показаны способы кодирования <xref:System.Windows.Media.Visual> объекта в файл изображения с помощью <xref:System.Windows.Media.Imaging.RenderTargetBitmap> и <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.  
  
## <a name="example"></a>Пример  
 <xref:System.Windows.Media.DrawingVisual> Создается с помощью <xref:System.Windows.Media.Imaging.BitmapImage> и <xref:System.Windows.Media.FormattedText> который отображается <xref:System.Windows.Media.Imaging.RenderTargetBitmap>. Визуализированный точечный рисунок затем используется для создания <xref:System.Windows.Media.Imaging.BitmapFrame> добавляемым к <xref:System.Windows.Media.Imaging.PngBitmapEncoder> для создания нового [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)] файл.  
  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample_Encode.cs#rtbencodeinline1)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample_Encode.vb#rtbencodeinline1)]  
  
 Объект <xref:System.Windows.Media.Imaging.PngBitmapEncoder> использовался в этом примере, но содержит производного <xref:System.Windows.Media.Imaging.BitmapEncoder> объекты можно было бы для создания файла образа.  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Media.DrawingContext>
- [Общие сведения об обработке изображений](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
- [Обзор объектов Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
- [Использование объектов DrawingVisual](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md)
