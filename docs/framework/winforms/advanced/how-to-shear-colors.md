---
title: Практическое руководство. Сместить цвета
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], transforming with color matrices
- colors [Windows Forms], shearing
ms.assetid: 0a424171-5b8b-45c4-afef-e9720a6c3e22
ms.openlocfilehash: eff468e5761038723e16eddf84bdcf8849ac30d1
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57720229"
---
# <a name="how-to-shear-colors"></a><span data-ttu-id="f8486-102">Практическое руководство. Сместить цвета</span><span class="sxs-lookup"><span data-stu-id="f8486-102">How to: Shear Colors</span></span>
<span data-ttu-id="f8486-103">Пропорциональное изменение увеличивает или уменьшает компонент цвета, обратно пропорционально значению другого компонента цвета.</span><span class="sxs-lookup"><span data-stu-id="f8486-103">Shearing increases or decreases a color component by an amount proportional to another color component.</span></span> <span data-ttu-id="f8486-104">Например рассмотрим преобразования, где красный компонент увеличивается на половину значения синего компонента.</span><span class="sxs-lookup"><span data-stu-id="f8486-104">For example, consider the transformation where the red component is increased by one half the value of the blue component.</span></span> <span data-ttu-id="f8486-105">При таком преобразовании цвет (0,2, 0,5, 1) станет (0,7, 0,5, 1).</span><span class="sxs-lookup"><span data-stu-id="f8486-105">Under such a transformation, the color (0.2, 0.5, 1) would become (0.7, 0.5, 1).</span></span> <span data-ttu-id="f8486-106">Новое значение красного компонента — 0,2 + (1/2)(1) = 0,7.</span><span class="sxs-lookup"><span data-stu-id="f8486-106">The new red component is 0.2 + (1/2)(1) = 0.7.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8486-107">Пример</span><span class="sxs-lookup"><span data-stu-id="f8486-107">Example</span></span>  
 <span data-ttu-id="f8486-108">В следующем примере создается <xref:System.Drawing.Image> объекта из файла ColorBars4.bmp.</span><span class="sxs-lookup"><span data-stu-id="f8486-108">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars4.bmp.</span></span> <span data-ttu-id="f8486-109">Затем код применяет наклон преобразование, описанное в предыдущем абзаце для каждого пикселя в изображении.</span><span class="sxs-lookup"><span data-stu-id="f8486-109">Then the code applies the shearing transformation described in the preceding paragraph to each pixel in the image.</span></span>  
  
 <span data-ttu-id="f8486-110">Ниже показан исходное изображение в левой части и преобразованное изображение справа.</span><span class="sxs-lookup"><span data-stu-id="f8486-110">The following illustration shows the original image on the left and the sheared image on the right.</span></span>  
  
 <span data-ttu-id="f8486-111">![Сдвиг цветов](./media/colortrans6.png "colortrans6")</span><span class="sxs-lookup"><span data-stu-id="f8486-111">![Shear Colors](./media/colortrans6.png "colortrans6")</span></span>  
  
 <span data-ttu-id="f8486-112">Ниже перечислены эти векторы четырех полос до и после преобразования.</span><span class="sxs-lookup"><span data-stu-id="f8486-112">The following table lists the color vectors for the four bars before and after the shearing transformation.</span></span>  
  
|<span data-ttu-id="f8486-113">До преобразования</span><span class="sxs-lookup"><span data-stu-id="f8486-113">Original</span></span>|<span data-ttu-id="f8486-114">Обрезается</span><span class="sxs-lookup"><span data-stu-id="f8486-114">Sheared</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="f8486-115">(0, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="f8486-115">(0, 0, 1, 1)</span></span>|<span data-ttu-id="f8486-116">(0.5, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="f8486-116">(0.5, 0, 1, 1)</span></span>|  
|<span data-ttu-id="f8486-117">(0.5, 1, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="f8486-117">(0.5, 1, 0.5, 1)</span></span>|<span data-ttu-id="f8486-118">(0.75, 1, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="f8486-118">(0.75, 1, 0.5, 1)</span></span>|  
|<span data-ttu-id="f8486-119">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="f8486-119">(1, 1, 0, 1)</span></span>|<span data-ttu-id="f8486-120">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="f8486-120">(1, 1, 0, 1)</span></span>|  
|<span data-ttu-id="f8486-121">(0.4, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="f8486-121">(0.4, 0.4, 0.4, 1)</span></span>|<span data-ttu-id="f8486-122">(0.6, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="f8486-122">(0.6, 0.4, 0.4, 1)</span></span>|  
  
 [!code-csharp[System.Drawing.Misc3#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Misc3/CS/Form1.cs#9)]
 [!code-vb[System.Drawing.Misc3#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Misc3/VB/Form1.vb#9)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f8486-123">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="f8486-123">Compiling the Code</span></span>  
 <span data-ttu-id="f8486-124">Предыдущий пример предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром обработчика события <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="f8486-124">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="f8486-125">Замените `ColorBars.bmp` в вашей системе путь и имя образа.</span><span class="sxs-lookup"><span data-stu-id="f8486-125">Replace `ColorBars.bmp` with an image name and path valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8486-126">См. также</span><span class="sxs-lookup"><span data-stu-id="f8486-126">See also</span></span>
- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="f8486-127">Объекты Graphics и Drawing в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f8486-127">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="f8486-128">перекрашивание изображений</span><span class="sxs-lookup"><span data-stu-id="f8486-128">Recoloring Images</span></span>](recoloring-images.md)
