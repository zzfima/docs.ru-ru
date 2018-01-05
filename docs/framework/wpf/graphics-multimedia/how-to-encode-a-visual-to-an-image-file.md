---
title: "Инструкция по Кодированию Visual в Файл Изображения"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image files [WPF], encoding from visuals
- encoding image formats [WPF]
- visuals [WPF], encoding to an image file
ms.assetid: 2036385b-ea47-4d54-8027-5797f52c8149
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 88a5d93c9c4726d1f6493df28d0a2a559394ef74
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-encode-a-visual-to-an-image-file"></a><span data-ttu-id="22f61-102">Инструкция по Кодированию Visual в Файл Изображения</span><span class="sxs-lookup"><span data-stu-id="22f61-102">How to: Encode a Visual to an Image File</span></span>
<span data-ttu-id="22f61-103">В этом примере показано, как кодировать <xref:System.Windows.Media.Visual> объект в файл изображения с помощью <xref:System.Windows.Media.Imaging.RenderTargetBitmap> и <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.</span><span class="sxs-lookup"><span data-stu-id="22f61-103">This example demonstrates how to encode a <xref:System.Windows.Media.Visual> object into an image file using a <xref:System.Windows.Media.Imaging.RenderTargetBitmap> and a <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22f61-104">Пример</span><span class="sxs-lookup"><span data-stu-id="22f61-104">Example</span></span>  
 <span data-ttu-id="22f61-105"><xref:System.Windows.Media.DrawingVisual> Создается с помощью <xref:System.Windows.Media.Imaging.BitmapImage> и <xref:System.Windows.Media.FormattedText> которой при подготовке к просмотру <xref:System.Windows.Media.Imaging.RenderTargetBitmap>.</span><span class="sxs-lookup"><span data-stu-id="22f61-105">The <xref:System.Windows.Media.DrawingVisual> is created using a <xref:System.Windows.Media.Imaging.BitmapImage> and <xref:System.Windows.Media.FormattedText> which is rendered to a <xref:System.Windows.Media.Imaging.RenderTargetBitmap>.</span></span> <span data-ttu-id="22f61-106">Визуализированный точечный рисунок затем используется для создания <xref:System.Windows.Media.Imaging.BitmapFrame> которого добавляется <xref:System.Windows.Media.Imaging.PngBitmapEncoder> для создания нового [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)] файла.</span><span class="sxs-lookup"><span data-stu-id="22f61-106">The rendered bitmap is then used to create a <xref:System.Windows.Media.Imaging.BitmapFrame> which is added to the <xref:System.Windows.Media.Imaging.PngBitmapEncoder> to create a new [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)] file.</span></span>  
  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample_Encode.cs#rtbencodeinline1)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample_Encode.vb#rtbencodeinline1)]  
  
 <span data-ttu-id="22f61-107">Объект <xref:System.Windows.Media.Imaging.PngBitmapEncoder> использовался в этом примере, любой из производных <xref:System.Windows.Media.Imaging.BitmapEncoder> объектов может использовались для создания файла образа.</span><span class="sxs-lookup"><span data-stu-id="22f61-107">A <xref:System.Windows.Media.Imaging.PngBitmapEncoder> was used in this example but any of the derived <xref:System.Windows.Media.Imaging.BitmapEncoder> objects could have been used to create the image file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22f61-108">См. также</span><span class="sxs-lookup"><span data-stu-id="22f61-108">See Also</span></span>  
 <xref:System.Windows.Media.DrawingContext>  
 [<span data-ttu-id="22f61-109">Общие сведения об обработке изображений</span><span class="sxs-lookup"><span data-stu-id="22f61-109">Imaging Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)  
 [<span data-ttu-id="22f61-110">Обзор объектов Drawing</span><span class="sxs-lookup"><span data-stu-id="22f61-110">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [<span data-ttu-id="22f61-111">Использование объектов DrawingVisual</span><span class="sxs-lookup"><span data-stu-id="22f61-111">Using DrawingVisual Objects</span></span>](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md)
