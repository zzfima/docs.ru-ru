---
title: "Практическое руководство. Поворот, отражение и наклон изображений"
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
- images [Windows Forms], reflecting
- images [Windows Forms], rotating
- images [Windows Forms], skewing
ms.assetid: a3bf97eb-63ed-425a-ba07-dcc65efb567c
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: eaa6286731d196dad387e1648644ca3e8103da03
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-rotate-reflect-and-skew-images"></a><span data-ttu-id="50055-102">Практическое руководство. Поворот, отражение и наклон изображений</span><span class="sxs-lookup"><span data-stu-id="50055-102">How to: Rotate, Reflect, and Skew Images</span></span>
<span data-ttu-id="50055-103">Поворот, отражать и наклонять изображения путем указания точек назначения для верхнего левого, правого верхнего и левого нижнего углов исходного изображения.</span><span class="sxs-lookup"><span data-stu-id="50055-103">You can rotate, reflect, and skew an image by specifying destination points for the upper-left, upper-right, and lower-left corners of the original image.</span></span> <span data-ttu-id="50055-104">Эти три точки назначения определяют аффинное преобразование, которое сопоставляет исходное прямоугольное изображение в параллелограмм.</span><span class="sxs-lookup"><span data-stu-id="50055-104">The three destination points determine an affine transformation that maps the original rectangular image to a parallelogram.</span></span>  
  
## <a name="example"></a><span data-ttu-id="50055-105">Пример</span><span class="sxs-lookup"><span data-stu-id="50055-105">Example</span></span>  
 <span data-ttu-id="50055-106">Предположим, что исходное изображение представляет собой прямоугольник с левого верхнего угла в (0, 0), правого верхнего угла в (100, 0) и левого нижнего угла на (0, 50).</span><span class="sxs-lookup"><span data-stu-id="50055-106">For example, suppose the original image is a rectangle with upper-left corner at (0, 0), upper-right corner at (100, 0), and lower-left corner at (0, 50).</span></span> <span data-ttu-id="50055-107">Теперь допустим, эти три точки в конечные точки следующим образом.</span><span class="sxs-lookup"><span data-stu-id="50055-107">Now suppose you map those three points to destination points as follows.</span></span>  
  
|<span data-ttu-id="50055-108">Исходная точка</span><span class="sxs-lookup"><span data-stu-id="50055-108">Original point</span></span>|<span data-ttu-id="50055-109">Конечная точка</span><span class="sxs-lookup"><span data-stu-id="50055-109">Destination point</span></span>|  
|--------------------|-----------------------|  
|<span data-ttu-id="50055-110">Верхний левый угол (0, 0)</span><span class="sxs-lookup"><span data-stu-id="50055-110">Upper-left (0, 0)</span></span>|<span data-ttu-id="50055-111">(200, 20)</span><span class="sxs-lookup"><span data-stu-id="50055-111">(200, 20)</span></span>|  
|<span data-ttu-id="50055-112">Правый верхний угол (100, 0)</span><span class="sxs-lookup"><span data-stu-id="50055-112">Upper-right (100, 0)</span></span>|<span data-ttu-id="50055-113">(110, 100)</span><span class="sxs-lookup"><span data-stu-id="50055-113">(110, 100)</span></span>|  
|<span data-ttu-id="50055-114">Нижний левый угол (0, 50)</span><span class="sxs-lookup"><span data-stu-id="50055-114">Lower-left (0, 50)</span></span>|<span data-ttu-id="50055-115">(250, 30)</span><span class="sxs-lookup"><span data-stu-id="50055-115">(250, 30)</span></span>|  
  
 <span data-ttu-id="50055-116">Ниже показан исходный образ и образ в параллелограмм.</span><span class="sxs-lookup"><span data-stu-id="50055-116">The following illustration shows the original image and the image mapped to the parallelogram.</span></span> <span data-ttu-id="50055-117">Исходный образ была синхронизована, отражаются, поворачивать и преобразовать.</span><span class="sxs-lookup"><span data-stu-id="50055-117">The original image has been skewed, reflected, rotated, and translated.</span></span> <span data-ttu-id="50055-118">На строку, проходящую через сопоставлен горизонтальной оси вдоль верхнего края исходного изображения (200, 20) и (110, 100).</span><span class="sxs-lookup"><span data-stu-id="50055-118">The x-axis along the top edge of the original image is mapped to the line that runs through (200, 20) and (110, 100).</span></span> <span data-ttu-id="50055-119">Ось y — вдоль левого края исходного изображения сопоставляется строку, проходящую через (200, 20) и (250, 30).</span><span class="sxs-lookup"><span data-stu-id="50055-119">The y-axis along the left edge of the original image is mapped to the line that runs through (200, 20) and (250, 30).</span></span>  
  
 <span data-ttu-id="50055-120">![Полосы](../../../../docs/framework/winforms/advanced/media/stripes1.gif "Stripes1")</span><span class="sxs-lookup"><span data-stu-id="50055-120">![Stripes](../../../../docs/framework/winforms/advanced/media/stripes1.gif "Stripes1")</span></span>  
  
 <span data-ttu-id="50055-121">Аналогичные преобразования, примененного к фотографии на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="50055-121">The following illustration shows a similar transformation applied to a photographic image.</span></span>  
  
 <span data-ttu-id="50055-122">![Преобразовать Climber](../../../../docs/framework/winforms/advanced/media/transformedclimber.png "TransformedClimber")</span><span class="sxs-lookup"><span data-stu-id="50055-122">![Transformed Climber](../../../../docs/framework/winforms/advanced/media/transformedclimber.png "TransformedClimber")</span></span>  
  
 <span data-ttu-id="50055-123">На следующем рисунке аналогичные преобразования, примененного в метафайл.</span><span class="sxs-lookup"><span data-stu-id="50055-123">The following illustration shows a similar transformation applied to a metafile.</span></span>  
  
 <span data-ttu-id="50055-124">![Преобразовать метафайл](../../../../docs/framework/winforms/advanced/media/transformedmetafile.png "TransformedMetafile")</span><span class="sxs-lookup"><span data-stu-id="50055-124">![Transformed Metafile](../../../../docs/framework/winforms/advanced/media/transformedmetafile.png "TransformedMetafile")</span></span>  
  
 <span data-ttu-id="50055-125">В следующем примере создается изображения, показанные на первом рисунке.</span><span class="sxs-lookup"><span data-stu-id="50055-125">The following example produces the images shown in the first illustration.</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.WorkingWithImages#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="50055-126">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="50055-126">Compiling the Code</span></span>  
 <span data-ttu-id="50055-127">Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs>`e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="50055-127">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="50055-128">Обязательно замените `Stripes.bmp` с путем к изображение, которое находится в вашей системе.</span><span class="sxs-lookup"><span data-stu-id="50055-128">Make sure to replace `Stripes.bmp` with the path to an image that is valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50055-129">См. также</span><span class="sxs-lookup"><span data-stu-id="50055-129">See Also</span></span>  
 [<span data-ttu-id="50055-130">Работа с растровыми и векторными изображениями, значками и метафайлами</span><span class="sxs-lookup"><span data-stu-id="50055-130">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
