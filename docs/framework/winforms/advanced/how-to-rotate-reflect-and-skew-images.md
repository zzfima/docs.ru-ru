---
title: Как выполнить Поворот, отражение и наклон изображений
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], reflecting
- images [Windows Forms], rotating
- images [Windows Forms], skewing
ms.assetid: a3bf97eb-63ed-425a-ba07-dcc65efb567c
ms.openlocfilehash: 2150e7797095b88227b499ec5481a3ce521270e9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54667915"
---
# <a name="how-to-rotate-reflect-and-skew-images"></a><span data-ttu-id="0027a-102">Как выполнить Поворот, отражение и наклон изображений</span><span class="sxs-lookup"><span data-stu-id="0027a-102">How to: Rotate, Reflect, and Skew Images</span></span>
<span data-ttu-id="0027a-103">Поворот, отражение и наклон образ, указав конечные точки для верхнего левого, правого верхнего и левого нижнего углов исходного изображения.</span><span class="sxs-lookup"><span data-stu-id="0027a-103">You can rotate, reflect, and skew an image by specifying destination points for the upper-left, upper-right, and lower-left corners of the original image.</span></span> <span data-ttu-id="0027a-104">Три конечные точки определяют аффинное преобразование, которое сопоставляет исходное прямоугольное изображение в параллелограмм.</span><span class="sxs-lookup"><span data-stu-id="0027a-104">The three destination points determine an affine transformation that maps the original rectangular image to a parallelogram.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0027a-105">Пример</span><span class="sxs-lookup"><span data-stu-id="0027a-105">Example</span></span>  
 <span data-ttu-id="0027a-106">Предположим, например, исходный образ представляет собой прямоугольник с верхнего левого угла в (0, 0), правом верхнем углу на (100, 0) и в левом нижнем углу в (0, 50).</span><span class="sxs-lookup"><span data-stu-id="0027a-106">For example, suppose the original image is a rectangle with upper-left corner at (0, 0), upper-right corner at (100, 0), and lower-left corner at (0, 50).</span></span> <span data-ttu-id="0027a-107">Теперь допустим, эти три точки в конечные точки следующим образом.</span><span class="sxs-lookup"><span data-stu-id="0027a-107">Now suppose you map those three points to destination points as follows.</span></span>  
  
|<span data-ttu-id="0027a-108">Исходная точка</span><span class="sxs-lookup"><span data-stu-id="0027a-108">Original point</span></span>|<span data-ttu-id="0027a-109">Конечная точка</span><span class="sxs-lookup"><span data-stu-id="0027a-109">Destination point</span></span>|  
|--------------------|-----------------------|  
|<span data-ttu-id="0027a-110">Верхний левый угол (0, 0)</span><span class="sxs-lookup"><span data-stu-id="0027a-110">Upper-left (0, 0)</span></span>|<span data-ttu-id="0027a-111">(200, 20)</span><span class="sxs-lookup"><span data-stu-id="0027a-111">(200, 20)</span></span>|  
|<span data-ttu-id="0027a-112">Верхний правый угол (100, 0)</span><span class="sxs-lookup"><span data-stu-id="0027a-112">Upper-right (100, 0)</span></span>|<span data-ttu-id="0027a-113">(110, 100)</span><span class="sxs-lookup"><span data-stu-id="0027a-113">(110, 100)</span></span>|  
|<span data-ttu-id="0027a-114">Нижний левый угол (0, 50)</span><span class="sxs-lookup"><span data-stu-id="0027a-114">Lower-left (0, 50)</span></span>|<span data-ttu-id="0027a-115">(250, 30)</span><span class="sxs-lookup"><span data-stu-id="0027a-115">(250, 30)</span></span>|  
  
 <span data-ttu-id="0027a-116">Ниже показан исходный образ и образ в параллелограмм.</span><span class="sxs-lookup"><span data-stu-id="0027a-116">The following illustration shows the original image and the image mapped to the parallelogram.</span></span> <span data-ttu-id="0027a-117">Исходное изображение были неравномерным, отражаются, (повернутый) и перевода.</span><span class="sxs-lookup"><span data-stu-id="0027a-117">The original image has been skewed, reflected, rotated, and translated.</span></span> <span data-ttu-id="0027a-118">Ось x вдоль верхней границы исходного изображения сопоставляется строку, которая выполняется через (200, 20) и (110, 100).</span><span class="sxs-lookup"><span data-stu-id="0027a-118">The x-axis along the top edge of the original image is mapped to the line that runs through (200, 20) and (110, 100).</span></span> <span data-ttu-id="0027a-119">Ось y — вдоль левого края исходного изображения сопоставляется строку, которая выполняется через (200, 20) и (250, 30).</span><span class="sxs-lookup"><span data-stu-id="0027a-119">The y-axis along the left edge of the original image is mapped to the line that runs through (200, 20) and (250, 30).</span></span>  
  
 <span data-ttu-id="0027a-120">![Полосы](../../../../docs/framework/winforms/advanced/media/stripes1.gif "Stripes1")</span><span class="sxs-lookup"><span data-stu-id="0027a-120">![Stripes](../../../../docs/framework/winforms/advanced/media/stripes1.gif "Stripes1")</span></span>  
  
 <span data-ttu-id="0027a-121">Ниже показано, как преобразование, примененное к фотографии.</span><span class="sxs-lookup"><span data-stu-id="0027a-121">The following illustration shows a similar transformation applied to a photographic image.</span></span>  
  
 <span data-ttu-id="0027a-122">![Преобразовать Climber](../../../../docs/framework/winforms/advanced/media/transformedclimber.png "TransformedClimber")</span><span class="sxs-lookup"><span data-stu-id="0027a-122">![Transformed Climber](../../../../docs/framework/winforms/advanced/media/transformedclimber.png "TransformedClimber")</span></span>  
  
 <span data-ttu-id="0027a-123">Ниже показано, как преобразование, примененное к метафайл.</span><span class="sxs-lookup"><span data-stu-id="0027a-123">The following illustration shows a similar transformation applied to a metafile.</span></span>  
  
 <span data-ttu-id="0027a-124">![Преобразовать метафайла](../../../../docs/framework/winforms/advanced/media/transformedmetafile.png "TransformedMetafile")</span><span class="sxs-lookup"><span data-stu-id="0027a-124">![Transformed Metafile](../../../../docs/framework/winforms/advanced/media/transformedmetafile.png "TransformedMetafile")</span></span>  
  
 <span data-ttu-id="0027a-125">В следующем примере создается изображения, показанные на первом рисунке.</span><span class="sxs-lookup"><span data-stu-id="0027a-125">The following example produces the images shown in the first illustration.</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.WorkingWithImages#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0027a-126">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="0027a-126">Compiling the Code</span></span>  
 <span data-ttu-id="0027a-127">Предыдущий пример предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.Control.Paint> обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="0027a-127">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="0027a-128">Не забудьте заменить `Stripes.bmp` с путем к изображению, который действителен в вашей системе.</span><span class="sxs-lookup"><span data-stu-id="0027a-128">Make sure to replace `Stripes.bmp` with the path to an image that is valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0027a-129">См. также</span><span class="sxs-lookup"><span data-stu-id="0027a-129">See also</span></span>
- [<span data-ttu-id="0027a-130">Работа с растровыми и векторными изображениями, значками и метафайлами</span><span class="sxs-lookup"><span data-stu-id="0027a-130">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
