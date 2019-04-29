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
ms.openlocfilehash: 872c19af0cfcf4fc980643c37e9a6028457c03b3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947580"
---
# <a name="how-to-encode-a-visual-to-an-image-file"></a><span data-ttu-id="feb0c-102">Практическое руководство. Кодирование визуального элемента в файл изображения</span><span class="sxs-lookup"><span data-stu-id="feb0c-102">How to: Encode a Visual to an Image File</span></span>
<span data-ttu-id="feb0c-103">В этом примере показаны способы кодирования <xref:System.Windows.Media.Visual> объекта в файл изображения с помощью <xref:System.Windows.Media.Imaging.RenderTargetBitmap> и <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.</span><span class="sxs-lookup"><span data-stu-id="feb0c-103">This example demonstrates how to encode a <xref:System.Windows.Media.Visual> object into an image file using a <xref:System.Windows.Media.Imaging.RenderTargetBitmap> and a <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="feb0c-104">Пример</span><span class="sxs-lookup"><span data-stu-id="feb0c-104">Example</span></span>  
 <span data-ttu-id="feb0c-105"><xref:System.Windows.Media.DrawingVisual> Создается с помощью <xref:System.Windows.Media.Imaging.BitmapImage> и <xref:System.Windows.Media.FormattedText> который отображается <xref:System.Windows.Media.Imaging.RenderTargetBitmap>.</span><span class="sxs-lookup"><span data-stu-id="feb0c-105">The <xref:System.Windows.Media.DrawingVisual> is created using a <xref:System.Windows.Media.Imaging.BitmapImage> and <xref:System.Windows.Media.FormattedText> which is rendered to a <xref:System.Windows.Media.Imaging.RenderTargetBitmap>.</span></span> <span data-ttu-id="feb0c-106">Визуализированный точечный рисунок затем используется для создания <xref:System.Windows.Media.Imaging.BitmapFrame> добавляемым к <xref:System.Windows.Media.Imaging.PngBitmapEncoder> для создания нового [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)] файл.</span><span class="sxs-lookup"><span data-stu-id="feb0c-106">The rendered bitmap is then used to create a <xref:System.Windows.Media.Imaging.BitmapFrame> which is added to the <xref:System.Windows.Media.Imaging.PngBitmapEncoder> to create a new [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)] file.</span></span>  
  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample_Encode.cs#rtbencodeinline1)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample_Encode.vb#rtbencodeinline1)]  
  
 <span data-ttu-id="feb0c-107">Объект <xref:System.Windows.Media.Imaging.PngBitmapEncoder> использовался в этом примере, но содержит производного <xref:System.Windows.Media.Imaging.BitmapEncoder> объекты можно было бы для создания файла образа.</span><span class="sxs-lookup"><span data-stu-id="feb0c-107">A <xref:System.Windows.Media.Imaging.PngBitmapEncoder> was used in this example but any of the derived <xref:System.Windows.Media.Imaging.BitmapEncoder> objects could have been used to create the image file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="feb0c-108">См. также</span><span class="sxs-lookup"><span data-stu-id="feb0c-108">See also</span></span>

- <xref:System.Windows.Media.DrawingContext>
- [<span data-ttu-id="feb0c-109">Общие сведения об обработке изображений</span><span class="sxs-lookup"><span data-stu-id="feb0c-109">Imaging Overview</span></span>](imaging-overview.md)
- [<span data-ttu-id="feb0c-110">Обзор объектов Drawing</span><span class="sxs-lookup"><span data-stu-id="feb0c-110">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="feb0c-111">Использование объектов DrawingVisual</span><span class="sxs-lookup"><span data-stu-id="feb0c-111">Using DrawingVisual Objects</span></span>](using-drawingvisual-objects.md)
