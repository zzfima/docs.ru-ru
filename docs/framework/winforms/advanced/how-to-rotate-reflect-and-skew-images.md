---
title: Практическое руководство. Поворот, отражение и наклон изображений
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], reflecting
- images [Windows Forms], rotating
- images [Windows Forms], skewing
ms.assetid: a3bf97eb-63ed-425a-ba07-dcc65efb567c
ms.openlocfilehash: dda03c9c1e1390ca6a5250471f047d3747e989e2
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58839916"
---
# <a name="how-to-rotate-reflect-and-skew-images"></a><span data-ttu-id="2e8fe-102">Практическое руководство. Поворот, отражение и наклон изображений</span><span class="sxs-lookup"><span data-stu-id="2e8fe-102">How to: Rotate, Reflect, and Skew Images</span></span>
<span data-ttu-id="2e8fe-103">Поворот, отражение и наклон образ, указав конечные точки для верхнего левого, правого верхнего и левого нижнего углов исходного изображения.</span><span class="sxs-lookup"><span data-stu-id="2e8fe-103">You can rotate, reflect, and skew an image by specifying destination points for the upper-left, upper-right, and lower-left corners of the original image.</span></span> <span data-ttu-id="2e8fe-104">Три конечные точки определяют аффинное преобразование, которое сопоставляет исходное прямоугольное изображение в параллелограмм.</span><span class="sxs-lookup"><span data-stu-id="2e8fe-104">The three destination points determine an affine transformation that maps the original rectangular image to a parallelogram.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e8fe-105">Пример</span><span class="sxs-lookup"><span data-stu-id="2e8fe-105">Example</span></span>  
 <span data-ttu-id="2e8fe-106">Предположим, например, исходный образ представляет собой прямоугольник с верхнего левого угла в (0, 0), правом верхнем углу на (100, 0) и в левом нижнем углу в (0, 50).</span><span class="sxs-lookup"><span data-stu-id="2e8fe-106">For example, suppose the original image is a rectangle with upper-left corner at (0, 0), upper-right corner at (100, 0), and lower-left corner at (0, 50).</span></span> <span data-ttu-id="2e8fe-107">Теперь допустим, эти три точки в конечные точки следующим образом.</span><span class="sxs-lookup"><span data-stu-id="2e8fe-107">Now suppose you map those three points to destination points as follows.</span></span>  
  
|<span data-ttu-id="2e8fe-108">Исходная точка</span><span class="sxs-lookup"><span data-stu-id="2e8fe-108">Original point</span></span>|<span data-ttu-id="2e8fe-109">Конечная точка</span><span class="sxs-lookup"><span data-stu-id="2e8fe-109">Destination point</span></span>|  
|--------------------|-----------------------|  
|<span data-ttu-id="2e8fe-110">Верхний левый угол (0, 0)</span><span class="sxs-lookup"><span data-stu-id="2e8fe-110">Upper-left (0, 0)</span></span>|<span data-ttu-id="2e8fe-111">(200, 20)</span><span class="sxs-lookup"><span data-stu-id="2e8fe-111">(200, 20)</span></span>|  
|<span data-ttu-id="2e8fe-112">Верхний правый угол (100, 0)</span><span class="sxs-lookup"><span data-stu-id="2e8fe-112">Upper-right (100, 0)</span></span>|<span data-ttu-id="2e8fe-113">(110, 100)</span><span class="sxs-lookup"><span data-stu-id="2e8fe-113">(110, 100)</span></span>|  
|<span data-ttu-id="2e8fe-114">Нижний левый угол (0, 50)</span><span class="sxs-lookup"><span data-stu-id="2e8fe-114">Lower-left (0, 50)</span></span>|<span data-ttu-id="2e8fe-115">(250, 30)</span><span class="sxs-lookup"><span data-stu-id="2e8fe-115">(250, 30)</span></span>|  
  
 <span data-ttu-id="2e8fe-116">Ниже показан исходный образ и образ в параллелограмм.</span><span class="sxs-lookup"><span data-stu-id="2e8fe-116">The following illustration shows the original image and the image mapped to the parallelogram.</span></span> <span data-ttu-id="2e8fe-117">Исходное изображение были неравномерным, отражаются, (повернутый) и перевода.</span><span class="sxs-lookup"><span data-stu-id="2e8fe-117">The original image has been skewed, reflected, rotated, and translated.</span></span> <span data-ttu-id="2e8fe-118">Ось x вдоль верхней границы исходного изображения сопоставляется строку, которая выполняется через (200, 20) и (110, 100).</span><span class="sxs-lookup"><span data-stu-id="2e8fe-118">The x-axis along the top edge of the original image is mapped to the line that runs through (200, 20) and (110, 100).</span></span> <span data-ttu-id="2e8fe-119">Ось y — вдоль левого края исходного изображения сопоставляется строку, которая выполняется через (200, 20) и (250, 30).</span><span class="sxs-lookup"><span data-stu-id="2e8fe-119">The y-axis along the left edge of the original image is mapped to the line that runs through (200, 20) and (250, 30).</span></span>  
  
 ![Исходный образ и образ в параллелограмм.](./media/how-to-rotate-reflect-and-skew-images/reflected-skewed-rotated-illustration.gif)  
  
 <span data-ttu-id="2e8fe-121">На следующем рисунке показано, как преобразование, примененное к фотографии:</span><span class="sxs-lookup"><span data-stu-id="2e8fe-121">The following illustration shows a similar transformation applied to a photographic image:</span></span>  
  
 ![Рисунок climber и изображения в параллелограмм.](./media/how-to-rotate-reflect-and-skew-images/reflected-skewed-rotated-photo.png)  
  
 <span data-ttu-id="2e8fe-123">На следующем рисунке показано такое же преобразование, примененное к метафайлу:</span><span class="sxs-lookup"><span data-stu-id="2e8fe-123">The following illustration shows a similar transformation applied to a metafile:</span></span>  
  
 ![Иллюстрация фигур и текста и, в параллелограмм.](./media/how-to-rotate-reflect-and-skew-images/reflected-skewed-rotated-metafile.png)  
  
 <span data-ttu-id="2e8fe-125">В следующем примере создается изображения, показанные на первом рисунке.</span><span class="sxs-lookup"><span data-stu-id="2e8fe-125">The following example produces the images shown in the first illustration.</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.WorkingWithImages#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2e8fe-126">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="2e8fe-126">Compiling the Code</span></span>  
 <span data-ttu-id="2e8fe-127">Предыдущий пример предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром обработчика события <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="2e8fe-127">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="2e8fe-128">Не забудьте заменить `Stripes.bmp` с путем к изображению, который действителен в вашей системе.</span><span class="sxs-lookup"><span data-stu-id="2e8fe-128">Make sure to replace `Stripes.bmp` with the path to an image that is valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e8fe-129">См. также</span><span class="sxs-lookup"><span data-stu-id="2e8fe-129">See also</span></span>
- [<span data-ttu-id="2e8fe-130">Работа с растровыми и векторными изображениями, значками и метафайлами</span><span class="sxs-lookup"><span data-stu-id="2e8fe-130">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
