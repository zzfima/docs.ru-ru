---
title: Практическое руководство. Создание растрового изображения из визуального элемента
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [WPF], rendering from visuals
- visuals [WPF], rendering to bitmaps
ms.assetid: 103fc7f5-7306-4026-9d61-2005e79959f3
ms.openlocfilehash: a622d99f7c477f8654526ed399f1eb37288682fe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61910264"
---
# <a name="how-to-create-a-bitmap-from-a-visual"></a><span data-ttu-id="6c228-102">Практическое руководство. Создание растрового изображения из визуального элемента</span><span class="sxs-lookup"><span data-stu-id="6c228-102">How to: Create a Bitmap from a Visual</span></span>
<span data-ttu-id="6c228-103">В этом примере показано, как можно создать точечный рисунок из <xref:System.Windows.Media.Visual>.</span><span class="sxs-lookup"><span data-stu-id="6c228-103">This example shows how you can create a bitmap from a <xref:System.Windows.Media.Visual>.</span></span> <span data-ttu-id="6c228-104">Объект <xref:System.Windows.Media.DrawingVisual> визуализируется с <xref:System.Windows.Media.FormattedText>.</span><span class="sxs-lookup"><span data-stu-id="6c228-104">A <xref:System.Windows.Media.DrawingVisual> is rendered with <xref:System.Windows.Media.FormattedText>.</span></span> <span data-ttu-id="6c228-105"><xref:System.Windows.Media.Visual> Присваивается <xref:System.Windows.Media.Imaging.RenderTargetBitmap> создании точечного рисунка для заданного текста.</span><span class="sxs-lookup"><span data-stu-id="6c228-105">The <xref:System.Windows.Media.Visual> is then rendered to the <xref:System.Windows.Media.Imaging.RenderTargetBitmap> creating a bitmap of the given text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c228-106">Пример</span><span class="sxs-lookup"><span data-stu-id="6c228-106">Example</span></span>  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#CreateRTBImage](~/samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample.cs#creatertbimage)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#CreateRTBImage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample.vb#creatertbimage)]  
  
## <a name="see-also"></a><span data-ttu-id="6c228-107">См. также</span><span class="sxs-lookup"><span data-stu-id="6c228-107">See also</span></span>

- <xref:System.Windows.Media.DrawingContext>
- [<span data-ttu-id="6c228-108">Общие сведения об обработке изображений</span><span class="sxs-lookup"><span data-stu-id="6c228-108">Imaging Overview</span></span>](imaging-overview.md)
- [<span data-ttu-id="6c228-109">Обзор объектов Drawing</span><span class="sxs-lookup"><span data-stu-id="6c228-109">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="6c228-110">Использование объектов DrawingVisual</span><span class="sxs-lookup"><span data-stu-id="6c228-110">Using DrawingVisual Objects</span></span>](using-drawingvisual-objects.md)
