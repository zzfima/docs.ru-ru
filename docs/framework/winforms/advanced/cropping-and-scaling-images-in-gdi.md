---
title: "Обрезка и масштабирование изображений в GDI+"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, scaling images
- GDI+, cropping images
- images [Windows Forms], cropping
- compressing data [Windows Forms], images
- images [Windows Forms], expansion
- images [Windows Forms], scaling
- rectangles [Windows Forms], source
- rectangles [Windows Forms], destination
- images [Windows Forms], compression
ms.assetid: ad5daf26-005f-45bc-a2af-e0e97777a21a
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0bbe7ac4b8c541ea76392f94f538e41816cf5c3f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="cropping-and-scaling-images-in-gdi"></a><span data-ttu-id="e5373-102">Обрезка и масштабирование изображений в GDI+</span><span class="sxs-lookup"><span data-stu-id="e5373-102">Cropping and Scaling Images in GDI+</span></span>
<span data-ttu-id="e5373-103">Можно использовать <xref:System.Drawing.Graphics.DrawImage%2A> метод <xref:System.Drawing.Graphics> класса для рисования и размещения векторных и растровых изображений.</span><span class="sxs-lookup"><span data-stu-id="e5373-103">You can use the <xref:System.Drawing.Graphics.DrawImage%2A> method of the <xref:System.Drawing.Graphics> class to draw and position vector images and raster images.</span></span> <span data-ttu-id="e5373-104"><xref:System.Drawing.Graphics.DrawImage%2A>— перегружаемый метод, поэтому существует несколько способов передачи аргументов.</span><span class="sxs-lookup"><span data-stu-id="e5373-104"><xref:System.Drawing.Graphics.DrawImage%2A> is an overloaded method, so there are several ways you can supply it with arguments.</span></span>  
  
## <a name="drawimage-variations"></a><span data-ttu-id="e5373-105">DrawImage вариантов</span><span class="sxs-lookup"><span data-stu-id="e5373-105">DrawImage Variations</span></span>  
 <span data-ttu-id="e5373-106">Один из вариантов <xref:System.Drawing.Graphics.DrawImage%2A> метод получает <xref:System.Drawing.Bitmap> и <xref:System.Drawing.Rectangle>.</span><span class="sxs-lookup"><span data-stu-id="e5373-106">One variation of the <xref:System.Drawing.Graphics.DrawImage%2A> method receives a <xref:System.Drawing.Bitmap> and a <xref:System.Drawing.Rectangle>.</span></span> <span data-ttu-id="e5373-107">Прямоугольник определяет место назначения для операции рисования; то есть он указывает прямоугольник, в котором будет рисоваться изображение.</span><span class="sxs-lookup"><span data-stu-id="e5373-107">The rectangle specifies the destination for the drawing operation; that is, it specifies the rectangle in which to draw the image.</span></span> <span data-ttu-id="e5373-108">Если размер прямоугольника назначения отличается от размера исходного изображения, изображение масштабируется по размерам прямоугольника назначения.</span><span class="sxs-lookup"><span data-stu-id="e5373-108">If the size of the destination rectangle is different from the size of the original image, the image is scaled to fit the destination rectangle.</span></span> <span data-ttu-id="e5373-109">В следующем примере кода показано, как рисовать тот же образ три раза: один раз без масштабирования, рисование с увеличением и рисование со сжатием:</span><span class="sxs-lookup"><span data-stu-id="e5373-109">The following code example shows how to draw the same image three times: once with no scaling, once with an expansion, and once with a compression:</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#31)]  
  
 <span data-ttu-id="e5373-110">На следующем рисунке три изображения.</span><span class="sxs-lookup"><span data-stu-id="e5373-110">The following illustration shows the three pictures.</span></span>  
  
 <span data-ttu-id="e5373-111">![Масштабирование](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art06.gif "AboutGdip03_Art06")</span><span class="sxs-lookup"><span data-stu-id="e5373-111">![Scaling](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art06.gif "AboutGdip03_Art06")</span></span>  
  
 <span data-ttu-id="e5373-112">Некоторые варианты <xref:System.Drawing.Graphics.DrawImage%2A> метод иметь исходный прямоугольник, а также параметр прямоугольника назначения.</span><span class="sxs-lookup"><span data-stu-id="e5373-112">Some variations of the <xref:System.Drawing.Graphics.DrawImage%2A> method have a source-rectangle parameter as well as a destination-rectangle parameter.</span></span> <span data-ttu-id="e5373-113">Исходный прямоугольник задает часть исходного изображения для рисования.</span><span class="sxs-lookup"><span data-stu-id="e5373-113">The source-rectangle parameter specifies the portion of the original image to draw.</span></span> <span data-ttu-id="e5373-114">Прямоугольник назначения задает прямоугольник, в которой выводится часть изображения.</span><span class="sxs-lookup"><span data-stu-id="e5373-114">The destination rectangle specifies the rectangle in which to draw that portion of the image.</span></span> <span data-ttu-id="e5373-115">Если размер прямоугольника назначения отличается от размера исходного прямоугольника, изображение масштабируется по размерам прямоугольника назначения.</span><span class="sxs-lookup"><span data-stu-id="e5373-115">If the size of the destination rectangle is different from the size of the source rectangle, the picture is scaled to fit the destination rectangle.</span></span>  
  
 <span data-ttu-id="e5373-116">В следующем примере кода показано создание <xref:System.Drawing.Bitmap> из файла Runner.jpg.</span><span class="sxs-lookup"><span data-stu-id="e5373-116">The following code example shows how to construct a <xref:System.Drawing.Bitmap> from the file Runner.jpg.</span></span> <span data-ttu-id="e5373-117">Все изображение рисуется без масштабирования на (0, 0).</span><span class="sxs-lookup"><span data-stu-id="e5373-117">The entire image is drawn with no scaling at (0, 0).</span></span> <span data-ttu-id="e5373-118">Затем небольшую часть изображения отображается дважды: один раз со сжатием и один раз с помощью расширения.</span><span class="sxs-lookup"><span data-stu-id="e5373-118">Then a small portion of the image is drawn twice: once with a compression and once with an expansion.</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#32)]  
  
 <span data-ttu-id="e5373-119">На следующем рисунке зависимым изображения и сжатые и увеличенная части рисунка.</span><span class="sxs-lookup"><span data-stu-id="e5373-119">The following illustration shows the unscaled image, and the compressed and expanded image portions.</span></span>  
  
 <span data-ttu-id="e5373-120">![Обрезка и масштабирование](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art07.gif "AboutGdip03_Art07")</span><span class="sxs-lookup"><span data-stu-id="e5373-120">![Cropping and Scaling](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art07.gif "AboutGdip03_Art07")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5373-121">См. также</span><span class="sxs-lookup"><span data-stu-id="e5373-121">See Also</span></span>  
 [<span data-ttu-id="e5373-122">Изображения, точечные рисунки и метафайлы</span><span class="sxs-lookup"><span data-stu-id="e5373-122">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [<span data-ttu-id="e5373-123">Работа с растровыми и векторными изображениями, значками и метафайлами</span><span class="sxs-lookup"><span data-stu-id="e5373-123">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
