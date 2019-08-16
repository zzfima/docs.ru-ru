---
title: Практическое руководство. Кодирование визуального элемента в файл изображения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image files [WPF], encoding from visuals
- encoding image formats [WPF]
- visuals [WPF], encoding to an image file
ms.assetid: 2036385b-ea47-4d54-8027-5797f52c8149
ms.openlocfilehash: 193b6a14e404d32bb49d6e0ef3cbd513166bcce2
ms.sourcegitcommit: 43761fcee10aeefcf851ea81cea3f3c691420856
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/16/2019
ms.locfileid: "69545291"
---
# <a name="how-to-encode-a-visual-to-an-image-file"></a>Практическое руководство. Кодирование визуального элемента в файл изображения
В этом примере показано, как кодировать <xref:System.Windows.Media.Visual> объект в файл изображения <xref:System.Windows.Media.Imaging.RenderTargetBitmap> с помощью и <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.  
  
## <a name="example"></a>Пример  
 Объект <xref:System.Windows.Media.DrawingVisual> создается <xref:System.Windows.Media.FormattedText> <xref:System.Windows.Media.Imaging.RenderTargetBitmap>с помощью и, который подготавливается к просмотру в. <xref:System.Windows.Media.Imaging.BitmapImage> Затем отображаемый точечный рисунок используется для создания <xref:System.Windows.Media.Imaging.BitmapFrame> элемента, который добавляется <xref:System.Windows.Media.Imaging.PngBitmapEncoder> в, чтобы создать новый PNG-файл.  
  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample_Encode.cs#rtbencodeinline1)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample_Encode.vb#rtbencodeinline1)]  
  
 В этом примере использовался любой из производных <xref:System.Windows.Media.Imaging.BitmapEncoder> объектов, который мог бы быть использован для создания файла изображения. <xref:System.Windows.Media.Imaging.PngBitmapEncoder>  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Media.DrawingContext>
- [Общие сведения об обработке изображений](imaging-overview.md)
- [Обзор объектов Drawing](drawing-objects-overview.md)
- [Использование объектов DrawingVisual](using-drawingvisual-objects.md)
