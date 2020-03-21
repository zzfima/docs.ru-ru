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
ms.openlocfilehash: 825e5a90ebb0d9df3b894ce7bd353e917b676939
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142398"
---
# <a name="how-to-shear-colors"></a><span data-ttu-id="4507b-102">Практическое руководство. Сдвиг цветов</span><span class="sxs-lookup"><span data-stu-id="4507b-102">How to: Shear Colors</span></span>
<span data-ttu-id="4507b-103">Стрижка увеличивает или уменьшает цветовую составляющую на сумму, пропорциональную другому цветовому компоненту.</span><span class="sxs-lookup"><span data-stu-id="4507b-103">Shearing increases or decreases a color component by an amount proportional to another color component.</span></span> <span data-ttu-id="4507b-104">Например, рассмотрим преобразование, при котором красный компонент увеличивается на половину значения синего компонента.</span><span class="sxs-lookup"><span data-stu-id="4507b-104">For example, consider the transformation where the red component is increased by one half the value of the blue component.</span></span> <span data-ttu-id="4507b-105">При таком преобразовании цветом (0,2, 0,5, 1) станет (0,7, 0,5, 1).</span><span class="sxs-lookup"><span data-stu-id="4507b-105">Under such a transformation, the color (0.2, 0.5, 1) would become (0.7, 0.5, 1).</span></span> <span data-ttu-id="4507b-106">Новый красный компонент составляет 0,2 х (1/2)(1) и 0,7.</span><span class="sxs-lookup"><span data-stu-id="4507b-106">The new red component is 0.2 + (1/2)(1) = 0.7.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4507b-107">Пример</span><span class="sxs-lookup"><span data-stu-id="4507b-107">Example</span></span>  
 <span data-ttu-id="4507b-108">Следующий пример строит <xref:System.Drawing.Image> объект из файла ColorBars4.bmp.</span><span class="sxs-lookup"><span data-stu-id="4507b-108">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars4.bmp.</span></span> <span data-ttu-id="4507b-109">Затем код применяет преобразование сдвига, описанное в предыдущем абзаце, к каждому пикселю на изображении.</span><span class="sxs-lookup"><span data-stu-id="4507b-109">Then the code applies the shearing transformation described in the preceding paragraph to each pixel in the image.</span></span>  
  
 <span data-ttu-id="4507b-110">На следующем рисунке показано исходное изображение слева и сдещевое изображение справа:</span><span class="sxs-lookup"><span data-stu-id="4507b-110">The following illustration shows the original image on the left and the sheared image on the right:</span></span>
  
 ![Два квадрата с цветными полосами бок о бок, иллюстрирующие исходное изображение и сложистые изображения.](./media/how-to-shear-colors/original-image-sheared-image.png)  
  
 <span data-ttu-id="4507b-112">В следующей таблице перечислены цветовые векторы для четырех баров до и после преобразования стрижки.</span><span class="sxs-lookup"><span data-stu-id="4507b-112">The following table lists the color vectors for the four bars before and after the shearing transformation.</span></span>  
  
|<span data-ttu-id="4507b-113">Исходное значение</span><span class="sxs-lookup"><span data-stu-id="4507b-113">Original</span></span>|<span data-ttu-id="4507b-114">Стриженой</span><span class="sxs-lookup"><span data-stu-id="4507b-114">Sheared</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="4507b-115">(0, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="4507b-115">(0, 0, 1, 1)</span></span>|<span data-ttu-id="4507b-116">(0.5, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="4507b-116">(0.5, 0, 1, 1)</span></span>|  
|<span data-ttu-id="4507b-117">(0.5, 1, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="4507b-117">(0.5, 1, 0.5, 1)</span></span>|<span data-ttu-id="4507b-118">(0.75, 1, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="4507b-118">(0.75, 1, 0.5, 1)</span></span>|  
|<span data-ttu-id="4507b-119">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="4507b-119">(1, 1, 0, 1)</span></span>|<span data-ttu-id="4507b-120">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="4507b-120">(1, 1, 0, 1)</span></span>|  
|<span data-ttu-id="4507b-121">(0.4, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="4507b-121">(0.4, 0.4, 0.4, 1)</span></span>|<span data-ttu-id="4507b-122">(0.6, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="4507b-122">(0.6, 0.4, 0.4, 1)</span></span>|  
  
 [!code-csharp[System.Drawing.Misc3#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Misc3/CS/Form1.cs#9)]
 [!code-vb[System.Drawing.Misc3#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Misc3/VB/Form1.vb#9)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4507b-123">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="4507b-123">Compiling the Code</span></span>  
 <span data-ttu-id="4507b-124">Предыдущий пример предназначен для использования с формами Windows, и он требует, <xref:System.Windows.Forms.PaintEventArgs> `e`который является параметром <xref:System.Windows.Forms.Control.Paint> обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="4507b-124">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="4507b-125">Замените `ColorBars.bmp` имя изображения и путь, действительный в вашей системе.</span><span class="sxs-lookup"><span data-stu-id="4507b-125">Replace `ColorBars.bmp` with an image name and path valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4507b-126">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4507b-126">See also</span></span>

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="4507b-127">Объекты Graphics и Drawing в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4507b-127">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="4507b-128">Перекрашивание изображений</span><span class="sxs-lookup"><span data-stu-id="4507b-128">Recoloring Images</span></span>](recoloring-images.md)
