---
title: "Практическое руководство. Сдвиг цветов"
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
- colors [Windows Forms], transforming with color matrices
- colors [Windows Forms], shearing
ms.assetid: 0a424171-5b8b-45c4-afef-e9720a6c3e22
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 35f89bb5d87ef58c5ecda7be4cb9fb41da08e8a8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-shear-colors"></a><span data-ttu-id="f8637-102">Практическое руководство. Сдвиг цветов</span><span class="sxs-lookup"><span data-stu-id="f8637-102">How to: Shear Colors</span></span>
<span data-ttu-id="f8637-103">Наклон увеличивает или уменьшает компонент цвета на сумму пропорционально другому компоненту цвета.</span><span class="sxs-lookup"><span data-stu-id="f8637-103">Shearing increases or decreases a color component by an amount proportional to another color component.</span></span> <span data-ttu-id="f8637-104">Например рассмотрим преобразование, в котором красный компонент увеличивается на половину значения синего компонента.</span><span class="sxs-lookup"><span data-stu-id="f8637-104">For example, consider the transformation where the red component is increased by one half the value of the blue component.</span></span> <span data-ttu-id="f8637-105">При таком преобразовании цвет (0,2, 0,5, 1) станут (0,7, 0,5, 1).</span><span class="sxs-lookup"><span data-stu-id="f8637-105">Under such a transformation, the color (0.2, 0.5, 1) would become (0.7, 0.5, 1).</span></span> <span data-ttu-id="f8637-106">Новое значение красного компонента равняется 0,2 + (1/2)(1) = 0,7.</span><span class="sxs-lookup"><span data-stu-id="f8637-106">The new red component is 0.2 + (1/2)(1) = 0.7.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8637-107">Пример</span><span class="sxs-lookup"><span data-stu-id="f8637-107">Example</span></span>  
 <span data-ttu-id="f8637-108">В следующем примере создается <xref:System.Drawing.Image> объекта из файла ColorBars4.bmp.</span><span class="sxs-lookup"><span data-stu-id="f8637-108">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars4.bmp.</span></span> <span data-ttu-id="f8637-109">Затем код применяет наклон преобразование, описанное в предыдущем абзаце к каждой точке в изображении.</span><span class="sxs-lookup"><span data-stu-id="f8637-109">Then the code applies the shearing transformation described in the preceding paragraph to each pixel in the image.</span></span>  
  
 <span data-ttu-id="f8637-110">Ниже показан исходный образ в левой части экрана и преобразованное изображение справа.</span><span class="sxs-lookup"><span data-stu-id="f8637-110">The following illustration shows the original image on the left and the sheared image on the right.</span></span>  
  
 <span data-ttu-id="f8637-111">![Сместить цвета](../../../../docs/framework/winforms/advanced/media/colortrans6.png "colortrans6")</span><span class="sxs-lookup"><span data-stu-id="f8637-111">![Shear Colors](../../../../docs/framework/winforms/advanced/media/colortrans6.png "colortrans6")</span></span>  
  
 <span data-ttu-id="f8637-112">Ниже перечислены эти векторы четырех полос до и после преобразования.</span><span class="sxs-lookup"><span data-stu-id="f8637-112">The following table lists the color vectors for the four bars before and after the shearing transformation.</span></span>  
  
|<span data-ttu-id="f8637-113">До преобразования</span><span class="sxs-lookup"><span data-stu-id="f8637-113">Original</span></span>|<span data-ttu-id="f8637-114">Обрезается</span><span class="sxs-lookup"><span data-stu-id="f8637-114">Sheared</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="f8637-115">(0, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="f8637-115">(0, 0, 1, 1)</span></span>|<span data-ttu-id="f8637-116">(0.5, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="f8637-116">(0.5, 0, 1, 1)</span></span>|  
|<span data-ttu-id="f8637-117">(0.5, 1, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="f8637-117">(0.5, 1, 0.5, 1)</span></span>|<span data-ttu-id="f8637-118">(0.75, 1, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="f8637-118">(0.75, 1, 0.5, 1)</span></span>|  
|<span data-ttu-id="f8637-119">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="f8637-119">(1, 1, 0, 1)</span></span>|<span data-ttu-id="f8637-120">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="f8637-120">(1, 1, 0, 1)</span></span>|  
|<span data-ttu-id="f8637-121">(0.4, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="f8637-121">(0.4, 0.4, 0.4, 1)</span></span>|<span data-ttu-id="f8637-122">(0.6, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="f8637-122">(0.6, 0.4, 0.4, 1)</span></span>|  
  
 [!code-csharp[System.Drawing.Misc3#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Misc3/CS/Form1.cs#9)]
 [!code-vb[System.Drawing.Misc3#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Misc3/VB/Form1.vb#9)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f8637-123">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="f8637-123">Compiling the Code</span></span>  
 <span data-ttu-id="f8637-124">Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs>`e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="f8637-124">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="f8637-125">Замените `ColorBars.bmp` в вашей системе путь и имя образа.</span><span class="sxs-lookup"><span data-stu-id="f8637-125">Replace `ColorBars.bmp` with an image name and path valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8637-126">См. также</span><span class="sxs-lookup"><span data-stu-id="f8637-126">See Also</span></span>  
 <xref:System.Drawing.Imaging.ColorMatrix>  
 <xref:System.Drawing.Imaging.ImageAttributes>  
 [<span data-ttu-id="f8637-127">Объекты Graphics и Drawing в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f8637-127">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="f8637-128">перекрашивание изображений</span><span class="sxs-lookup"><span data-stu-id="f8637-128">Recoloring Images</span></span>](../../../../docs/framework/winforms/advanced/recoloring-images.md)
