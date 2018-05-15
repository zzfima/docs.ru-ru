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
# <a name="how-to-create-a-bitmap-from-a-visual"></a><span data-ttu-id="0b666-102">Практическое руководство. Создание точечного рисунка из Visual</span><span class="sxs-lookup"><span data-stu-id="0b666-102">How to: Create a Bitmap from a Visual</span></span>
<span data-ttu-id="0b666-103">В этом примере показано, как можно создать точечный рисунок из <xref:System.Windows.Media.Visual>.</span><span class="sxs-lookup"><span data-stu-id="0b666-103">This example shows how you can create a bitmap from a <xref:System.Windows.Media.Visual>.</span></span> <span data-ttu-id="0b666-104">Объект <xref:System.Windows.Media.DrawingVisual> визуализируется с <xref:System.Windows.Media.FormattedText>.</span><span class="sxs-lookup"><span data-stu-id="0b666-104">A <xref:System.Windows.Media.DrawingVisual> is rendered with <xref:System.Windows.Media.FormattedText>.</span></span> <span data-ttu-id="0b666-105"><xref:System.Windows.Media.Visual> Присваивается <xref:System.Windows.Media.Imaging.RenderTargetBitmap> создания растрового рисунка заданного текста.</span><span class="sxs-lookup"><span data-stu-id="0b666-105">The <xref:System.Windows.Media.Visual> is then rendered to the <xref:System.Windows.Media.Imaging.RenderTargetBitmap> creating a bitmap of the given text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b666-106">Пример</span><span class="sxs-lookup"><span data-stu-id="0b666-106">Example</span></span>  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#CreateRTBImage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample.cs#creatertbimage)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#CreateRTBImage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample.vb#creatertbimage)]  
  
## <a name="see-also"></a><span data-ttu-id="0b666-107">См. также</span><span class="sxs-lookup"><span data-stu-id="0b666-107">See Also</span></span>  
 <xref:System.Windows.Media.DrawingContext>  
 [<span data-ttu-id="0b666-108">Общие сведения об обработке изображений</span><span class="sxs-lookup"><span data-stu-id="0b666-108">Imaging Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)  
 [<span data-ttu-id="0b666-109">Обзор объектов Drawing</span><span class="sxs-lookup"><span data-stu-id="0b666-109">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [<span data-ttu-id="0b666-110">Использование объектов DrawingVisual</span><span class="sxs-lookup"><span data-stu-id="0b666-110">Using DrawingVisual Objects</span></span>](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md)
