---
title: Практическое руководство. Использование режима интерполяции для управления качеством изображений при масштабировании
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- interpolation mode [Windows Forms], controlling image quality
- images [Windows Forms], scaling
- images [Windows Forms], controlling quality
ms.assetid: fde9bccf-8aa5-4b0d-ba4b-788740627b02
ms.openlocfilehash: 93430f521904d9d38ba98f4055480583fd650114
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2019
ms.locfileid: "58410372"
---
# <a name="how-to-use-interpolation-mode-to-control-image-quality-during-scaling"></a><span data-ttu-id="c8459-102">Практическое руководство. Использование режима интерполяции для управления качеством изображений при масштабировании</span><span class="sxs-lookup"><span data-stu-id="c8459-102">How to: Use Interpolation Mode to Control Image Quality During Scaling</span></span>
<span data-ttu-id="c8459-103">Режим интерполяции <xref:System.Drawing.Graphics> влияет на способ [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] масштабирует (растягивает и сжимает) изображения.</span><span class="sxs-lookup"><span data-stu-id="c8459-103">The interpolation mode of a <xref:System.Drawing.Graphics> object influences the way [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] scales (stretches and shrinks) images.</span></span> <span data-ttu-id="c8459-104"><xref:System.Drawing.Drawing2D.InterpolationMode> Перечисление определяет различные режимы интерполяции, некоторые из которых приведены в следующем списке:</span><span class="sxs-lookup"><span data-stu-id="c8459-104">The <xref:System.Drawing.Drawing2D.InterpolationMode> enumeration defines several interpolation modes, some of which are shown in the following list:</span></span>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.Bilinear>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBilinear>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.Bicubic>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic>  
  
 <span data-ttu-id="c8459-105">Чтобы растянуть изображение, каждый пиксель исходного изображения должен быть сопоставлен группе точек увеличенного изображения.</span><span class="sxs-lookup"><span data-stu-id="c8459-105">To stretch an image, each pixel in the original image must be mapped to a group of pixels in the larger image.</span></span> <span data-ttu-id="c8459-106">Чтобы сжать изображение, группы точек исходного изображения должны сопоставляться отдельным точкам уменьшенного изображения.</span><span class="sxs-lookup"><span data-stu-id="c8459-106">To shrink an image, groups of pixels in the original image must be mapped to single pixels in the smaller image.</span></span> <span data-ttu-id="c8459-107">Эффективность алгоритмов, которые выполняют эти сопоставления определяет качество масштабированное изображение.</span><span class="sxs-lookup"><span data-stu-id="c8459-107">The effectiveness of the algorithms that perform these mappings determines the quality of a scaled image.</span></span> <span data-ttu-id="c8459-108">Алгоритмы, создающие масштабированные изображения более высокого качества, как правило, требуют большего времени обработки.</span><span class="sxs-lookup"><span data-stu-id="c8459-108">Algorithms that produce higher-quality scaled images tend to require more processing time.</span></span> <span data-ttu-id="c8459-109">В приведенном выше списке <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor> режим низкое качество и <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic> режим высочайшего качества.</span><span class="sxs-lookup"><span data-stu-id="c8459-109">In the preceding list, <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor> is the lowest-quality mode and <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic> is the highest-quality mode.</span></span>  
  
 <span data-ttu-id="c8459-110">Чтобы задать режим интерполяции, назначить один из членов <xref:System.Drawing.Drawing2D.InterpolationMode> перечисления <xref:System.Drawing.Graphics.InterpolationMode%2A> свойство <xref:System.Drawing.Graphics> объекта.</span><span class="sxs-lookup"><span data-stu-id="c8459-110">To set the interpolation mode, assign one of the members of the <xref:System.Drawing.Drawing2D.InterpolationMode> enumeration to the <xref:System.Drawing.Graphics.InterpolationMode%2A> property of a <xref:System.Drawing.Graphics> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8459-111">Пример</span><span class="sxs-lookup"><span data-stu-id="c8459-111">Example</span></span>  
 <span data-ttu-id="c8459-112">В следующем примере изображение рисуется и затем сжимается с использованием трех различных способов интерполяции.</span><span class="sxs-lookup"><span data-stu-id="c8459-112">The following example draws an image and then shrinks the image with three different interpolation modes.</span></span>  
  
 <span data-ttu-id="c8459-113">Ниже показан исходный образ и три меньшего размера изображения.</span><span class="sxs-lookup"><span data-stu-id="c8459-113">The following illustration shows the original image and the three smaller images.</span></span>  
  
 ![Снимок экрана, показывающий изображение с отличными параметрами вставки.](./media/how-to-use-interpolation-mode-to-control-image-quality-during-scaling/varied-interpolation-settings.png)  
  
 [!code-csharp[System.Drawing.WorkingWithImages#81](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#81)]
 [!code-vb[System.Drawing.WorkingWithImages#81](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#81)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c8459-115">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="c8459-115">Compiling the Code</span></span>  
 <span data-ttu-id="c8459-116">Предыдущий пример предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.Control.Paint> обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="c8459-116">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8459-117">См. также</span><span class="sxs-lookup"><span data-stu-id="c8459-117">See also</span></span>
- [<span data-ttu-id="c8459-118">Изображения, точечные рисунки и метафайлы</span><span class="sxs-lookup"><span data-stu-id="c8459-118">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="c8459-119">Работа с растровыми и векторными изображениями, значками и метафайлами</span><span class="sxs-lookup"><span data-stu-id="c8459-119">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
