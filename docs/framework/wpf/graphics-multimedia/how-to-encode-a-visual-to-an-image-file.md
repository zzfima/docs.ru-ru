---
title: Практическое руководство. Кодирование визуального объекта в файл изображения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image files [WPF], encoding from visuals
- encoding image formats [WPF]
- visuals [WPF], encoding to an image file
ms.assetid: 2036385b-ea47-4d54-8027-5797f52c8149
ms.openlocfilehash: 2d5da0bde243128bc0d7aa29bf865ca9bfbd1d9a
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356002"
---
# <a name="how-to-encode-a-visual-to-an-image-file"></a><span data-ttu-id="d9cd0-102">Практическое руководство. Кодирование визуального объекта в файл изображения</span><span class="sxs-lookup"><span data-stu-id="d9cd0-102">How to: Encode a Visual to an Image File</span></span>
<span data-ttu-id="d9cd0-103">В этом примере показаны способы кодирования <xref:System.Windows.Media.Visual> объекта в файл изображения с помощью <xref:System.Windows.Media.Imaging.RenderTargetBitmap> и <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.</span><span class="sxs-lookup"><span data-stu-id="d9cd0-103">This example demonstrates how to encode a <xref:System.Windows.Media.Visual> object into an image file using a <xref:System.Windows.Media.Imaging.RenderTargetBitmap> and a <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9cd0-104">Пример</span><span class="sxs-lookup"><span data-stu-id="d9cd0-104">Example</span></span>  
 <span data-ttu-id="d9cd0-105"><xref:System.Windows.Media.DrawingVisual> Создается с помощью <xref:System.Windows.Media.Imaging.BitmapImage> и <xref:System.Windows.Media.FormattedText> который отображается <xref:System.Windows.Media.Imaging.RenderTargetBitmap>.</span><span class="sxs-lookup"><span data-stu-id="d9cd0-105">The <xref:System.Windows.Media.DrawingVisual> is created using a <xref:System.Windows.Media.Imaging.BitmapImage> and <xref:System.Windows.Media.FormattedText> which is rendered to a <xref:System.Windows.Media.Imaging.RenderTargetBitmap>.</span></span> <span data-ttu-id="d9cd0-106">Визуализированный точечный рисунок затем используется для создания <xref:System.Windows.Media.Imaging.BitmapFrame> добавляемым к <xref:System.Windows.Media.Imaging.PngBitmapEncoder> для создания нового [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)] файл.</span><span class="sxs-lookup"><span data-stu-id="d9cd0-106">The rendered bitmap is then used to create a <xref:System.Windows.Media.Imaging.BitmapFrame> which is added to the <xref:System.Windows.Media.Imaging.PngBitmapEncoder> to create a new [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)] file.</span></span>  
  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample_Encode.cs#rtbencodeinline1)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample_Encode.vb#rtbencodeinline1)]  
  
 <span data-ttu-id="d9cd0-107">Объект <xref:System.Windows.Media.Imaging.PngBitmapEncoder> использовался в этом примере, но содержит производного <xref:System.Windows.Media.Imaging.BitmapEncoder> объекты можно было бы для создания файла образа.</span><span class="sxs-lookup"><span data-stu-id="d9cd0-107">A <xref:System.Windows.Media.Imaging.PngBitmapEncoder> was used in this example but any of the derived <xref:System.Windows.Media.Imaging.BitmapEncoder> objects could have been used to create the image file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9cd0-108">См. также</span><span class="sxs-lookup"><span data-stu-id="d9cd0-108">See also</span></span>
- <xref:System.Windows.Media.DrawingContext>
- [<span data-ttu-id="d9cd0-109">Общие сведения об обработке изображений</span><span class="sxs-lookup"><span data-stu-id="d9cd0-109">Imaging Overview</span></span>](imaging-overview.md)
- [<span data-ttu-id="d9cd0-110">Обзор объектов Drawing</span><span class="sxs-lookup"><span data-stu-id="d9cd0-110">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="d9cd0-111">Использование объектов DrawingVisual</span><span class="sxs-lookup"><span data-stu-id="d9cd0-111">Using DrawingVisual Objects</span></span>](using-drawingvisual-objects.md)
