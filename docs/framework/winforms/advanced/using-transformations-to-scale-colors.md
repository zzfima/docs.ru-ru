---
title: "Масштабирование цветов с применением преобразований"
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
- transformations [Windows Forms], for scaling colors
- colors [Windows Forms], scaling
ms.assetid: df23c887-7fd6-4b15-ad94-e30b5bd4b849
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a4584b74cd7a394f7dd04d0cfba150b907ca7c82
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="using-transformations-to-scale-colors"></a><span data-ttu-id="5ae09-102">Масштабирование цветов с применением преобразований</span><span class="sxs-lookup"><span data-stu-id="5ae09-102">Using Transformations to Scale Colors</span></span>
<span data-ttu-id="5ae09-103">Масштабирование умножает одно или несколько из четырех компонентов цвета на число.</span><span class="sxs-lookup"><span data-stu-id="5ae09-103">A scaling transformation multiplies one or more of the four color components by a number.</span></span> <span data-ttu-id="5ae09-104">В следующей таблице приведены элементы матрицы цветов, соответствующие масштабированию.</span><span class="sxs-lookup"><span data-stu-id="5ae09-104">The color matrix entries that represent scaling are given in the following table.</span></span>  
  
|<span data-ttu-id="5ae09-105">Масштабируемый компонент</span><span class="sxs-lookup"><span data-stu-id="5ae09-105">Component to be scaled</span></span>|<span data-ttu-id="5ae09-106">Элемент матрицы</span><span class="sxs-lookup"><span data-stu-id="5ae09-106">Matrix entry</span></span>|  
|----------------------------|------------------|  
|<span data-ttu-id="5ae09-107">Красный</span><span class="sxs-lookup"><span data-stu-id="5ae09-107">Red</span></span>|<span data-ttu-id="5ae09-108">[0][0]</span><span class="sxs-lookup"><span data-stu-id="5ae09-108">[0][0]</span></span>|  
|<span data-ttu-id="5ae09-109">Зеленый</span><span class="sxs-lookup"><span data-stu-id="5ae09-109">Green</span></span>|<span data-ttu-id="5ae09-110">[1][1]</span><span class="sxs-lookup"><span data-stu-id="5ae09-110">[1][1]</span></span>|  
|<span data-ttu-id="5ae09-111">Синий</span><span class="sxs-lookup"><span data-stu-id="5ae09-111">Blue</span></span>|<span data-ttu-id="5ae09-112">[2][2]</span><span class="sxs-lookup"><span data-stu-id="5ae09-112">[2][2]</span></span>|  
|<span data-ttu-id="5ae09-113">Коэффициент альфа</span><span class="sxs-lookup"><span data-stu-id="5ae09-113">Alpha</span></span>|<span data-ttu-id="5ae09-114">[3][3]</span><span class="sxs-lookup"><span data-stu-id="5ae09-114">[3][3]</span></span>|  
  
## <a name="scaling-one-color"></a><span data-ttu-id="5ae09-115">Масштабирование одного цвета</span><span class="sxs-lookup"><span data-stu-id="5ae09-115">Scaling One Color</span></span>  
 <span data-ttu-id="5ae09-116">В следующем примере создается <xref:System.Drawing.Image> объекта из файла ColorBars2.bmp.</span><span class="sxs-lookup"><span data-stu-id="5ae09-116">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars2.bmp.</span></span> <span data-ttu-id="5ae09-117">Затем код масштабирует синий компонент каждого пикселя в изображении с коэффициентом 2.</span><span class="sxs-lookup"><span data-stu-id="5ae09-117">Then the code scales the blue component of each pixel in the image by a factor of 2.</span></span> <span data-ttu-id="5ae09-118">Исходное изображение отображается вместе с преобразованным изображением.</span><span class="sxs-lookup"><span data-stu-id="5ae09-118">The original image is drawn alongside the transformed image.</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.RecoloringImages#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#41)]  
  
 <span data-ttu-id="5ae09-119">Ниже показан исходный образ в левой части экрана и масштабированное изображение справа.</span><span class="sxs-lookup"><span data-stu-id="5ae09-119">The following illustration shows the original image on the left and the scaled image on the right.</span></span>  
  
 <span data-ttu-id="5ae09-120">![Масштабирование цветов](../../../../docs/framework/winforms/advanced/media/colortrans3.png "colortrans3")</span><span class="sxs-lookup"><span data-stu-id="5ae09-120">![Scale Colors](../../../../docs/framework/winforms/advanced/media/colortrans3.png "colortrans3")</span></span>  
  
 <span data-ttu-id="5ae09-121">Ниже перечислены эти векторы четырех полос до и после масштабирования.</span><span class="sxs-lookup"><span data-stu-id="5ae09-121">The following table lists the color vectors for the four bars before and after the blue scaling.</span></span> <span data-ttu-id="5ae09-122">Обратите внимание, что синий компонент цвета четвертой полосы изменился с 0,8 на 0,6.</span><span class="sxs-lookup"><span data-stu-id="5ae09-122">Note that the blue component in the fourth color bar went from 0.8 to 0.6.</span></span> <span data-ttu-id="5ae09-123">Причина этого заключается в [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] сохраняет дробная часть результата.</span><span class="sxs-lookup"><span data-stu-id="5ae09-123">That is because [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] retains only the fractional part of the result.</span></span> <span data-ttu-id="5ae09-124">Например (2)(0,8) = 1,6, а дробная часть 1.6 равно 0,6.</span><span class="sxs-lookup"><span data-stu-id="5ae09-124">For example, (2)(0.8) = 1.6, and the fractional part of 1.6 is 0.6.</span></span> <span data-ttu-id="5ae09-125">Сохранение только дробной части гарантирует, что результат будет в интервале [0, 1].</span><span class="sxs-lookup"><span data-stu-id="5ae09-125">Retaining only the fractional part ensures that the result is always in the interval [0, 1].</span></span>  
  
|<span data-ttu-id="5ae09-126">До преобразования</span><span class="sxs-lookup"><span data-stu-id="5ae09-126">Original</span></span>|<span data-ttu-id="5ae09-127">Масштабирование</span><span class="sxs-lookup"><span data-stu-id="5ae09-127">Scaled</span></span>|  
|--------------|------------|  
|<span data-ttu-id="5ae09-128">(0.4, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="5ae09-128">(0.4, 0.4, 0.4, 1)</span></span>|<span data-ttu-id="5ae09-129">(0.4, 0.4, 0.8, 1)</span><span class="sxs-lookup"><span data-stu-id="5ae09-129">(0.4, 0.4, 0.8, 1)</span></span>|  
|<span data-ttu-id="5ae09-130">(0.4, 0.2, 0.2, 1)</span><span class="sxs-lookup"><span data-stu-id="5ae09-130">(0.4, 0.2, 0.2, 1)</span></span>|<span data-ttu-id="5ae09-131">(0.4, 0.2, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="5ae09-131">(0.4, 0.2, 0.4, 1)</span></span>|  
|<span data-ttu-id="5ae09-132">(0.2, 0.4, 0.2, 1)</span><span class="sxs-lookup"><span data-stu-id="5ae09-132">(0.2, 0.4, 0.2, 1)</span></span>|<span data-ttu-id="5ae09-133">(0.2, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="5ae09-133">(0.2, 0.4, 0.4, 1)</span></span>|  
|<span data-ttu-id="5ae09-134">(0.4, 0.4, 0.8, 1)</span><span class="sxs-lookup"><span data-stu-id="5ae09-134">(0.4, 0.4, 0.8, 1)</span></span>|<span data-ttu-id="5ae09-135">(0.4, 0.4, 0.6, 1)</span><span class="sxs-lookup"><span data-stu-id="5ae09-135">(0.4, 0.4, 0.6, 1)</span></span>|  
  
## <a name="scaling-multiple-colors"></a><span data-ttu-id="5ae09-136">Масштабирование нескольких цветов</span><span class="sxs-lookup"><span data-stu-id="5ae09-136">Scaling Multiple Colors</span></span>  
 <span data-ttu-id="5ae09-137">В следующем примере создается <xref:System.Drawing.Image> объекта из файла ColorBars2.bmp.</span><span class="sxs-lookup"><span data-stu-id="5ae09-137">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars2.bmp.</span></span> <span data-ttu-id="5ae09-138">Затем код масштабирует красного, зеленого и синего компонентов каждого пикселя в изображении.</span><span class="sxs-lookup"><span data-stu-id="5ae09-138">Then the code scales the red, green, and blue components of each pixel in the image.</span></span> <span data-ttu-id="5ae09-139">Красные компоненты уменьшаются на 25 процентов, зеленый компоненты уменьшаются на 35 процентов и синий компоненты уменьшаются на 50 процентов.</span><span class="sxs-lookup"><span data-stu-id="5ae09-139">The red components are scaled down 25 percent, the green components are scaled down 35 percent, and the blue components are scaled down 50 percent.</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.RecoloringImages#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#42)]  
  
 <span data-ttu-id="5ae09-140">Ниже показан исходный образ в левой части экрана и масштабированное изображение справа.</span><span class="sxs-lookup"><span data-stu-id="5ae09-140">The following illustration shows the original image on the left and the scaled image on the right.</span></span>  
  
 <span data-ttu-id="5ae09-141">![Масштабирование цветов](../../../../docs/framework/winforms/advanced/media/colortrans4.png "colortrans4")</span><span class="sxs-lookup"><span data-stu-id="5ae09-141">![Scale Colors](../../../../docs/framework/winforms/advanced/media/colortrans4.png "colortrans4")</span></span>  
  
 <span data-ttu-id="5ae09-142">Ниже перечислены эти векторы четырех полос до и после красного, зеленого и синего масштабирования.</span><span class="sxs-lookup"><span data-stu-id="5ae09-142">The following table lists the color vectors for the four bars before and after the red, green and blue scaling.</span></span>  
  
|<span data-ttu-id="5ae09-143">До преобразования</span><span class="sxs-lookup"><span data-stu-id="5ae09-143">Original</span></span>|<span data-ttu-id="5ae09-144">Масштабирование</span><span class="sxs-lookup"><span data-stu-id="5ae09-144">Scaled</span></span>|  
|--------------|------------|  
|<span data-ttu-id="5ae09-145">(0.6, 0.6, 0.6, 1)</span><span class="sxs-lookup"><span data-stu-id="5ae09-145">(0.6, 0.6, 0.6, 1)</span></span>|<span data-ttu-id="5ae09-146">(0.45, 0.39, 0.3, 1)</span><span class="sxs-lookup"><span data-stu-id="5ae09-146">(0.45, 0.39, 0.3, 1)</span></span>|  
|<span data-ttu-id="5ae09-147">(0, 1, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="5ae09-147">(0, 1, 1, 1)</span></span>|<span data-ttu-id="5ae09-148">(0, 0.65, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="5ae09-148">(0, 0.65, 0.5, 1)</span></span>|  
|<span data-ttu-id="5ae09-149">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="5ae09-149">(1, 1, 0, 1)</span></span>|<span data-ttu-id="5ae09-150">(0.75, 0.65, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="5ae09-150">(0.75, 0.65, 0, 1)</span></span>|  
|<span data-ttu-id="5ae09-151">(1, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="5ae09-151">(1, 0, 1, 1)</span></span>|<span data-ttu-id="5ae09-152">(0.75, 0, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="5ae09-152">(0.75, 0, 0.5, 1)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5ae09-153">См. также</span><span class="sxs-lookup"><span data-stu-id="5ae09-153">See Also</span></span>  
 <xref:System.Drawing.Imaging.ColorMatrix>  
 <xref:System.Drawing.Imaging.ImageAttributes>  
 [<span data-ttu-id="5ae09-154">Объекты Graphics и Drawing в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5ae09-154">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="5ae09-155">перекрашивание изображений</span><span class="sxs-lookup"><span data-stu-id="5ae09-155">Recoloring Images</span></span>](../../../../docs/framework/winforms/advanced/recoloring-images.md)
