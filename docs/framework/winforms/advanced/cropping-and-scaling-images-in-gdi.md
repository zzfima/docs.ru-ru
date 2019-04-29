---
title: Обрезка и масштабирование изображений в GDI+
ms.date: 03/30/2017
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
ms.openlocfilehash: c3cdb06e99770808461f9266fb5f07df9074149b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769503"
---
# <a name="cropping-and-scaling-images-in-gdi"></a><span data-ttu-id="49682-102">Обрезка и масштабирование изображений в GDI+</span><span class="sxs-lookup"><span data-stu-id="49682-102">Cropping and Scaling Images in GDI+</span></span>
<span data-ttu-id="49682-103">Можно использовать <xref:System.Drawing.Graphics.DrawImage%2A> метод <xref:System.Drawing.Graphics> позволяет рисовать и размещать векторные и растровые изображения.</span><span class="sxs-lookup"><span data-stu-id="49682-103">You can use the <xref:System.Drawing.Graphics.DrawImage%2A> method of the <xref:System.Drawing.Graphics> class to draw and position vector images and raster images.</span></span> <span data-ttu-id="49682-104"><xref:System.Drawing.Graphics.DrawImage%2A> — Это перегруженный метод, поэтому существует несколько способов передачи аргументов.</span><span class="sxs-lookup"><span data-stu-id="49682-104"><xref:System.Drawing.Graphics.DrawImage%2A> is an overloaded method, so there are several ways you can supply it with arguments.</span></span>  
  
## <a name="drawimage-variations"></a><span data-ttu-id="49682-105">DrawImage вариантов</span><span class="sxs-lookup"><span data-stu-id="49682-105">DrawImage Variations</span></span>  
 <span data-ttu-id="49682-106">Один из вариантов <xref:System.Drawing.Graphics.DrawImage%2A> метод получает <xref:System.Drawing.Bitmap> и <xref:System.Drawing.Rectangle>.</span><span class="sxs-lookup"><span data-stu-id="49682-106">One variation of the <xref:System.Drawing.Graphics.DrawImage%2A> method receives a <xref:System.Drawing.Bitmap> and a <xref:System.Drawing.Rectangle>.</span></span> <span data-ttu-id="49682-107">Прямоугольник определяет место назначения для операции рисования; то есть он задает прямоугольник, в котором должно быть нарисовано изображение.</span><span class="sxs-lookup"><span data-stu-id="49682-107">The rectangle specifies the destination for the drawing operation; that is, it specifies the rectangle in which to draw the image.</span></span> <span data-ttu-id="49682-108">Если размер целевого прямоугольника отличаются от размера исходного изображения, изображение масштабируется по размерам прямоугольника назначения.</span><span class="sxs-lookup"><span data-stu-id="49682-108">If the size of the destination rectangle is different from the size of the original image, the image is scaled to fit the destination rectangle.</span></span> <span data-ttu-id="49682-109">В следующем примере кода показано, как должно быть нарисовано изображение же три раза: один раз без масштабирования, один раз с помощью расширения и один раз с сжатия:</span><span class="sxs-lookup"><span data-stu-id="49682-109">The following code example shows how to draw the same image three times: once with no scaling, once with an expansion, and once with a compression:</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#31)]  
  
 <span data-ttu-id="49682-110">Ниже показаны три изображения.</span><span class="sxs-lookup"><span data-stu-id="49682-110">The following illustration shows the three pictures.</span></span>  
  
 <span data-ttu-id="49682-111">![Масштабирование](./media/aboutgdip03-art06.gif "AboutGdip03_Art06")</span><span class="sxs-lookup"><span data-stu-id="49682-111">![Scaling](./media/aboutgdip03-art06.gif "AboutGdip03_Art06")</span></span>  
  
 <span data-ttu-id="49682-112">Некоторые варианты <xref:System.Drawing.Graphics.DrawImage%2A> метод иметь исходный прямоугольник, а также параметр целевого прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="49682-112">Some variations of the <xref:System.Drawing.Graphics.DrawImage%2A> method have a source-rectangle parameter as well as a destination-rectangle parameter.</span></span> <span data-ttu-id="49682-113">Исходный прямоугольник задает часть исходного изображения для рисования.</span><span class="sxs-lookup"><span data-stu-id="49682-113">The source-rectangle parameter specifies the portion of the original image to draw.</span></span> <span data-ttu-id="49682-114">Прямоугольник назначения задает прямоугольник, в котором для рисования эту часть изображения.</span><span class="sxs-lookup"><span data-stu-id="49682-114">The destination rectangle specifies the rectangle in which to draw that portion of the image.</span></span> <span data-ttu-id="49682-115">Если размер целевого прямоугольника отличаются от размера исходного прямоугольника, изображение масштабируется по размерам прямоугольника назначения.</span><span class="sxs-lookup"><span data-stu-id="49682-115">If the size of the destination rectangle is different from the size of the source rectangle, the picture is scaled to fit the destination rectangle.</span></span>  
  
 <span data-ttu-id="49682-116">В следующем примере кода показано создание <xref:System.Drawing.Bitmap> из файла Runner.jpg.</span><span class="sxs-lookup"><span data-stu-id="49682-116">The following code example shows how to construct a <xref:System.Drawing.Bitmap> from the file Runner.jpg.</span></span> <span data-ttu-id="49682-117">Все изображение рисуется без масштабирования на (0, 0).</span><span class="sxs-lookup"><span data-stu-id="49682-117">The entire image is drawn with no scaling at (0, 0).</span></span> <span data-ttu-id="49682-118">Затем небольшую часть изображения отображается дважды: один раз со сжатием и один раз с помощью расширения.</span><span class="sxs-lookup"><span data-stu-id="49682-118">Then a small portion of the image is drawn twice: once with a compression and once with an expansion.</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#32)]  
  
 <span data-ttu-id="49682-119">Ниже показан немасштабированного рисунка и части, сжатые и Развернутое изображение.</span><span class="sxs-lookup"><span data-stu-id="49682-119">The following illustration shows the unscaled image, and the compressed and expanded image portions.</span></span>  
  
 <span data-ttu-id="49682-120">![Обрезка и масштабирование](./media/aboutgdip03-art07.gif "AboutGdip03_Art07")</span><span class="sxs-lookup"><span data-stu-id="49682-120">![Cropping and Scaling](./media/aboutgdip03-art07.gif "AboutGdip03_Art07")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49682-121">См. также</span><span class="sxs-lookup"><span data-stu-id="49682-121">See also</span></span>

- [<span data-ttu-id="49682-122">Изображения, точечные рисунки и метафайлы</span><span class="sxs-lookup"><span data-stu-id="49682-122">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="49682-123">Работа с растровыми и векторными изображениями, значками и метафайлами</span><span class="sxs-lookup"><span data-stu-id="49682-123">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
