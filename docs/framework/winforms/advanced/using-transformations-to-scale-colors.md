---
title: Масштабирование цветов с применением преобразований
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- transformations [Windows Forms], for scaling colors
- colors [Windows Forms], scaling
ms.assetid: df23c887-7fd6-4b15-ad94-e30b5bd4b849
ms.openlocfilehash: 81c0ddf5b937d604559a9eb1a8b598885546c97f
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504963"
---
# <a name="using-transformations-to-scale-colors"></a><span data-ttu-id="c0733-102">Масштабирование цветов с применением преобразований</span><span class="sxs-lookup"><span data-stu-id="c0733-102">Using Transformations to Scale Colors</span></span>
<span data-ttu-id="c0733-103">Преобразование масштабирования умножает одно или несколько из четырех компонентов цвета по номеру.</span><span class="sxs-lookup"><span data-stu-id="c0733-103">A scaling transformation multiplies one or more of the four color components by a number.</span></span> <span data-ttu-id="c0733-104">В следующей таблице приведены элементы матрицы цветов, представляющих масштабирования.</span><span class="sxs-lookup"><span data-stu-id="c0733-104">The color matrix entries that represent scaling are given in the following table.</span></span>  
  
|<span data-ttu-id="c0733-105">Масштабируемый компонент</span><span class="sxs-lookup"><span data-stu-id="c0733-105">Component to be scaled</span></span>|<span data-ttu-id="c0733-106">Элемент матрицы</span><span class="sxs-lookup"><span data-stu-id="c0733-106">Matrix entry</span></span>|  
|----------------------------|------------------|  
|<span data-ttu-id="c0733-107">Красный</span><span class="sxs-lookup"><span data-stu-id="c0733-107">Red</span></span>|<span data-ttu-id="c0733-108">[0][0]</span><span class="sxs-lookup"><span data-stu-id="c0733-108">[0][0]</span></span>|  
|<span data-ttu-id="c0733-109">Зеленый</span><span class="sxs-lookup"><span data-stu-id="c0733-109">Green</span></span>|<span data-ttu-id="c0733-110">[1][1]</span><span class="sxs-lookup"><span data-stu-id="c0733-110">[1][1]</span></span>|  
|<span data-ttu-id="c0733-111">Синий</span><span class="sxs-lookup"><span data-stu-id="c0733-111">Blue</span></span>|<span data-ttu-id="c0733-112">[2][2]</span><span class="sxs-lookup"><span data-stu-id="c0733-112">[2][2]</span></span>|  
|<span data-ttu-id="c0733-113">Коэффициент альфа</span><span class="sxs-lookup"><span data-stu-id="c0733-113">Alpha</span></span>|<span data-ttu-id="c0733-114">[3][3]</span><span class="sxs-lookup"><span data-stu-id="c0733-114">[3][3]</span></span>|  
  
## <a name="scaling-one-color"></a><span data-ttu-id="c0733-115">Масштабирование одного цвета</span><span class="sxs-lookup"><span data-stu-id="c0733-115">Scaling One Color</span></span>  
 <span data-ttu-id="c0733-116">В следующем примере создается <xref:System.Drawing.Image> объекта из файла ColorBars2.bmp.</span><span class="sxs-lookup"><span data-stu-id="c0733-116">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars2.bmp.</span></span> <span data-ttu-id="c0733-117">Затем код масштабирует синего компонента каждого пикселя изображения с коэффициентом 2.</span><span class="sxs-lookup"><span data-stu-id="c0733-117">Then the code scales the blue component of each pixel in the image by a factor of 2.</span></span> <span data-ttu-id="c0733-118">Исходное изображение отображается вместе с преобразованные изображения.</span><span class="sxs-lookup"><span data-stu-id="c0733-118">The original image is drawn alongside the transformed image.</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.RecoloringImages#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#41)]  
  
 <span data-ttu-id="c0733-119">Ниже показан исходное изображение в левой части и масштабированное изображение справа:</span><span class="sxs-lookup"><span data-stu-id="c0733-119">The following illustration shows the original image on the left and the scaled image on the right:</span></span>  
  
 ![Снимок экрана, сравнивает исходные и масштабированное цвета.](./media/using-transformations-to-scale-colors/four-bar-scale-one-color.png)  
  
 <span data-ttu-id="c0733-121">Ниже перечислены эти векторы четырех полос до и после масштабирования.</span><span class="sxs-lookup"><span data-stu-id="c0733-121">The following table lists the color vectors for the four bars before and after the blue scaling.</span></span> <span data-ttu-id="c0733-122">Обратите внимание, что синий компонент цвета четвертой полосы изменился с 0,8 на 0,6.</span><span class="sxs-lookup"><span data-stu-id="c0733-122">Note that the blue component in the fourth color bar went from 0.8 to 0.6.</span></span> <span data-ttu-id="c0733-123">Том, что GDI + сохраняет только дробная часть результата.</span><span class="sxs-lookup"><span data-stu-id="c0733-123">That is because GDI+ retains only the fractional part of the result.</span></span> <span data-ttu-id="c0733-124">Например (2)(0,8) = 1,6, а дробная часть параметра 1.6 равно 0,6.</span><span class="sxs-lookup"><span data-stu-id="c0733-124">For example, (2)(0.8) = 1.6, and the fractional part of 1.6 is 0.6.</span></span> <span data-ttu-id="c0733-125">Сохранение только дробной части гарантирует, что результат всегда находится в интервале [0, 1].</span><span class="sxs-lookup"><span data-stu-id="c0733-125">Retaining only the fractional part ensures that the result is always in the interval [0, 1].</span></span>  
  
|<span data-ttu-id="c0733-126">До преобразования</span><span class="sxs-lookup"><span data-stu-id="c0733-126">Original</span></span>|<span data-ttu-id="c0733-127">Масштабирование</span><span class="sxs-lookup"><span data-stu-id="c0733-127">Scaled</span></span>|  
|--------------|------------|  
|<span data-ttu-id="c0733-128">(0.4, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="c0733-128">(0.4, 0.4, 0.4, 1)</span></span>|<span data-ttu-id="c0733-129">(0.4, 0.4, 0.8, 1)</span><span class="sxs-lookup"><span data-stu-id="c0733-129">(0.4, 0.4, 0.8, 1)</span></span>|  
|<span data-ttu-id="c0733-130">(0.4, 0.2, 0.2, 1)</span><span class="sxs-lookup"><span data-stu-id="c0733-130">(0.4, 0.2, 0.2, 1)</span></span>|<span data-ttu-id="c0733-131">(0.4, 0.2, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="c0733-131">(0.4, 0.2, 0.4, 1)</span></span>|  
|<span data-ttu-id="c0733-132">(0.2, 0.4, 0.2, 1)</span><span class="sxs-lookup"><span data-stu-id="c0733-132">(0.2, 0.4, 0.2, 1)</span></span>|<span data-ttu-id="c0733-133">(0.2, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="c0733-133">(0.2, 0.4, 0.4, 1)</span></span>|  
|<span data-ttu-id="c0733-134">(0.4, 0.4, 0.8, 1)</span><span class="sxs-lookup"><span data-stu-id="c0733-134">(0.4, 0.4, 0.8, 1)</span></span>|<span data-ttu-id="c0733-135">(0.4, 0.4, 0.6, 1)</span><span class="sxs-lookup"><span data-stu-id="c0733-135">(0.4, 0.4, 0.6, 1)</span></span>|  
  
## <a name="scaling-multiple-colors"></a><span data-ttu-id="c0733-136">Масштабирование нескольких цветов</span><span class="sxs-lookup"><span data-stu-id="c0733-136">Scaling Multiple Colors</span></span>  
 <span data-ttu-id="c0733-137">В следующем примере создается <xref:System.Drawing.Image> объекта из файла ColorBars2.bmp.</span><span class="sxs-lookup"><span data-stu-id="c0733-137">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars2.bmp.</span></span> <span data-ttu-id="c0733-138">Затем код масштабирует красного, зеленого и синего компонентов каждого пикселя в изображении.</span><span class="sxs-lookup"><span data-stu-id="c0733-138">Then the code scales the red, green, and blue components of each pixel in the image.</span></span> <span data-ttu-id="c0733-139">Красные компоненты уменьшаются на 25 процентов, зеленые компоненты уменьшаются на 35 процентов и синий компоненты уменьшаются на 50 процентов.</span><span class="sxs-lookup"><span data-stu-id="c0733-139">The red components are scaled down 25 percent, the green components are scaled down 35 percent, and the blue components are scaled down 50 percent.</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.RecoloringImages#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#42)]  
  
 <span data-ttu-id="c0733-140">Ниже показан исходное изображение в левой части и масштабированное изображение справа:</span><span class="sxs-lookup"><span data-stu-id="c0733-140">The following illustration shows the original image on the left and the scaled image on the right:</span></span>  
  
 ![Снимок экрана, сравнивает исходные и масштабированное цвета.](./media/using-transformations-to-scale-colors/four-bar-scale-multiple-colors.png)  
  
 <span data-ttu-id="c0733-142">Ниже перечислены эти векторы четырех полос до и после красного, зеленого и синего масштабирования.</span><span class="sxs-lookup"><span data-stu-id="c0733-142">The following table lists the color vectors for the four bars before and after the red, green and blue scaling.</span></span>  
  
|<span data-ttu-id="c0733-143">До преобразования</span><span class="sxs-lookup"><span data-stu-id="c0733-143">Original</span></span>|<span data-ttu-id="c0733-144">Масштабирование</span><span class="sxs-lookup"><span data-stu-id="c0733-144">Scaled</span></span>|  
|--------------|------------|  
|<span data-ttu-id="c0733-145">(0.6, 0.6, 0.6, 1)</span><span class="sxs-lookup"><span data-stu-id="c0733-145">(0.6, 0.6, 0.6, 1)</span></span>|<span data-ttu-id="c0733-146">(0.45, 0.39, 0.3, 1)</span><span class="sxs-lookup"><span data-stu-id="c0733-146">(0.45, 0.39, 0.3, 1)</span></span>|  
|<span data-ttu-id="c0733-147">(0, 1, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="c0733-147">(0, 1, 1, 1)</span></span>|<span data-ttu-id="c0733-148">(0, 0.65, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="c0733-148">(0, 0.65, 0.5, 1)</span></span>|  
|<span data-ttu-id="c0733-149">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="c0733-149">(1, 1, 0, 1)</span></span>|<span data-ttu-id="c0733-150">(0.75, 0.65, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="c0733-150">(0.75, 0.65, 0, 1)</span></span>|  
|<span data-ttu-id="c0733-151">(1, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="c0733-151">(1, 0, 1, 1)</span></span>|<span data-ttu-id="c0733-152">(0.75, 0, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="c0733-152">(0.75, 0, 0.5, 1)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c0733-153">См. также</span><span class="sxs-lookup"><span data-stu-id="c0733-153">See also</span></span>

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="c0733-154">Объекты Graphics и Drawing в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c0733-154">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="c0733-155">перекрашивание изображений</span><span class="sxs-lookup"><span data-stu-id="c0733-155">Recoloring Images</span></span>](recoloring-images.md)
