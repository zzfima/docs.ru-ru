---
title: Практическое руководство. Сдвиг цветов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], transforming with color matrices
- colors [Windows Forms], shearing
ms.assetid: 0a424171-5b8b-45c4-afef-e9720a6c3e22
ms.openlocfilehash: bf645cf88c4905cd5cf47c2a6c7af088fa428c8a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59076254"
---
# <a name="how-to-shear-colors"></a><span data-ttu-id="a7689-102">Практическое руководство. Сдвиг цветов</span><span class="sxs-lookup"><span data-stu-id="a7689-102">How to: Shear Colors</span></span>
<span data-ttu-id="a7689-103">Пропорциональное изменение увеличивает или уменьшает компонент цвета, обратно пропорционально значению другого компонента цвета.</span><span class="sxs-lookup"><span data-stu-id="a7689-103">Shearing increases or decreases a color component by an amount proportional to another color component.</span></span> <span data-ttu-id="a7689-104">Например рассмотрим преобразования, где красный компонент увеличивается на половину значения синего компонента.</span><span class="sxs-lookup"><span data-stu-id="a7689-104">For example, consider the transformation where the red component is increased by one half the value of the blue component.</span></span> <span data-ttu-id="a7689-105">При таком преобразовании цвет (0,2, 0,5, 1) станет (0,7, 0,5, 1).</span><span class="sxs-lookup"><span data-stu-id="a7689-105">Under such a transformation, the color (0.2, 0.5, 1) would become (0.7, 0.5, 1).</span></span> <span data-ttu-id="a7689-106">Новое значение красного компонента — 0,2 + (1/2)(1) = 0,7.</span><span class="sxs-lookup"><span data-stu-id="a7689-106">The new red component is 0.2 + (1/2)(1) = 0.7.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7689-107">Пример</span><span class="sxs-lookup"><span data-stu-id="a7689-107">Example</span></span>  
 <span data-ttu-id="a7689-108">В следующем примере создается <xref:System.Drawing.Image> объекта из файла ColorBars4.bmp.</span><span class="sxs-lookup"><span data-stu-id="a7689-108">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars4.bmp.</span></span> <span data-ttu-id="a7689-109">Затем код применяет наклон преобразование, описанное в предыдущем абзаце для каждого пикселя в изображении.</span><span class="sxs-lookup"><span data-stu-id="a7689-109">Then the code applies the shearing transformation described in the preceding paragraph to each pixel in the image.</span></span>  
  
 <span data-ttu-id="a7689-110">Ниже показан исходное изображение в левой части и преобразованное изображение справа:</span><span class="sxs-lookup"><span data-stu-id="a7689-110">The following illustration shows the original image on the left and the sheared image on the right:</span></span> 
  
 ![Две клетки с цветной полосы side-by-side иллюстрирующая исходного изображения, а преобразованное изображение.](./media/how-to-shear-colors/original-image-sheared-image.png)  
  
 <span data-ttu-id="a7689-112">Ниже перечислены эти векторы четырех полос до и после преобразования.</span><span class="sxs-lookup"><span data-stu-id="a7689-112">The following table lists the color vectors for the four bars before and after the shearing transformation.</span></span>  
  
|<span data-ttu-id="a7689-113">До преобразования</span><span class="sxs-lookup"><span data-stu-id="a7689-113">Original</span></span>|<span data-ttu-id="a7689-114">Обрезается</span><span class="sxs-lookup"><span data-stu-id="a7689-114">Sheared</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="a7689-115">(0, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="a7689-115">(0, 0, 1, 1)</span></span>|<span data-ttu-id="a7689-116">(0.5, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="a7689-116">(0.5, 0, 1, 1)</span></span>|  
|<span data-ttu-id="a7689-117">(0.5, 1, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="a7689-117">(0.5, 1, 0.5, 1)</span></span>|<span data-ttu-id="a7689-118">(0.75, 1, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="a7689-118">(0.75, 1, 0.5, 1)</span></span>|  
|<span data-ttu-id="a7689-119">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="a7689-119">(1, 1, 0, 1)</span></span>|<span data-ttu-id="a7689-120">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="a7689-120">(1, 1, 0, 1)</span></span>|  
|<span data-ttu-id="a7689-121">(0.4, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="a7689-121">(0.4, 0.4, 0.4, 1)</span></span>|<span data-ttu-id="a7689-122">(0.6, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="a7689-122">(0.6, 0.4, 0.4, 1)</span></span>|  
  
 [!code-csharp[System.Drawing.Misc3#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Misc3/CS/Form1.cs#9)]
 [!code-vb[System.Drawing.Misc3#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Misc3/VB/Form1.vb#9)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a7689-123">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="a7689-123">Compiling the Code</span></span>  
 <span data-ttu-id="a7689-124">Предыдущий пример предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs>`e`, который является параметром <xref:System.Windows.Forms.Control.Paint> обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="a7689-124">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="a7689-125">Замените `ColorBars.bmp` в вашей системе путь и имя образа.</span><span class="sxs-lookup"><span data-stu-id="a7689-125">Replace `ColorBars.bmp` with an image name and path valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7689-126">См. также</span><span class="sxs-lookup"><span data-stu-id="a7689-126">See also</span></span>

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="a7689-127">Объекты Graphics и Drawing в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a7689-127">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="a7689-128">Перекрашивание изображений</span><span class="sxs-lookup"><span data-stu-id="a7689-128">Recoloring Images</span></span>](recoloring-images.md)
