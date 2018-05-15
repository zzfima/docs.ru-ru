---
title: Альфа-смешение цвета для линий и заливок
ms.date: 03/30/2017
helpviewer_keywords:
- lines [Windows Forms], adding transparency
- examples [Windows Forms], alpha blending
- alpha blending [Windows Forms], using with lines
- alpha blending
- lines [Windows Forms], alpha blending
- fills [Windows Forms], alpha blending
- alpha blending [Windows Forms], using with fills
- shapes [Windows Forms], adding transparency
ms.assetid: 5440f48c-3ac9-44c3-b170-c1c110bdbab8
ms.openlocfilehash: f58fa2d105492c6c72d3d6906c3c35f89130fe91
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="alpha-blending-lines-and-fills"></a><span data-ttu-id="d72f8-102">Альфа-смешение цвета для линий и заливок</span><span class="sxs-lookup"><span data-stu-id="d72f8-102">Alpha Blending Lines and Fills</span></span>
<span data-ttu-id="d72f8-103">В [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], цвет является 32-разрядное значение с 8 бит для альфа-канал, красный, зеленый и синий.</span><span class="sxs-lookup"><span data-stu-id="d72f8-103">In [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], a color is a 32-bit value with 8 bits each for alpha, red, green, and blue.</span></span> <span data-ttu-id="d72f8-104">Значение альфа определяет прозрачность цвета, области, к которому цвет смешивается с цветами фона.</span><span class="sxs-lookup"><span data-stu-id="d72f8-104">The alpha value indicates the transparency of the color — the extent to which the color is blended with the background color.</span></span> <span data-ttu-id="d72f8-105">При значениях альфа диапазон от 0 до 255, где 0 соответствует полностью прозрачный цвет, а 255 — полностью непрозрачный цвету.</span><span class="sxs-lookup"><span data-stu-id="d72f8-105">Alpha values range from 0 through 255, where 0 represents a fully transparent color, and 255 represents a fully opaque color.</span></span>  
  
 <span data-ttu-id="d72f8-106">Альфа-смешение представляет собой пикселей на точек смешение данных исходного и фонового цвета.</span><span class="sxs-lookup"><span data-stu-id="d72f8-106">Alpha blending is a pixel-by-pixel blending of source and background color data.</span></span> <span data-ttu-id="d72f8-107">Каждый из трех компонентов (красный, зеленый, синий) исходного цвета смешивается с соответствующим компонентом фонового цвета по следующей формуле:</span><span class="sxs-lookup"><span data-stu-id="d72f8-107">Each of the three components (red, green, blue) of a given source color is blended with the corresponding component of the background color according to the following formula:</span></span>  
  
 <span data-ttu-id="d72f8-108">Отображаемый_цвет = Исходный_цвет × альфа / 255 + backgroundColor × (255 – альфа) / 255</span><span class="sxs-lookup"><span data-stu-id="d72f8-108">displayColor = sourceColor × alpha / 255 + backgroundColor × (255 – alpha) / 255</span></span>  
  
 <span data-ttu-id="d72f8-109">Например предположим, красного компонента цвета источника 150 и красного компонента цвета фона — 100.</span><span class="sxs-lookup"><span data-stu-id="d72f8-109">For example, suppose the red component of the source color is 150 and the red component of the background color is 100.</span></span> <span data-ttu-id="d72f8-110">Если значение альфа составляет 200, красный компонент отображаемого цвета вычисляется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d72f8-110">If the alpha value is 200, the red component of the resultant color is calculated as follows:</span></span>  
  
 <span data-ttu-id="d72f8-111">150 × 200 / 255 + 100 × (255 – 200) / 255 = 139</span><span class="sxs-lookup"><span data-stu-id="d72f8-111">150 × 200 / 255 + 100 × (255 – 200) / 255 = 139</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d72f8-112">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="d72f8-112">In This Section</span></span>  
 [<span data-ttu-id="d72f8-113">Практическое руководство. Рисование непрозрачных и полупрозрачных линий</span><span class="sxs-lookup"><span data-stu-id="d72f8-113">How to: Draw Opaque and Semitransparent Lines</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-opaque-and-semitransparent-lines.md)  
 <span data-ttu-id="d72f8-114">Показано, как рисование линий с альфа смешением.</span><span class="sxs-lookup"><span data-stu-id="d72f8-114">Shows how to draw alpha-blended lines.</span></span>  
  
 [<span data-ttu-id="d72f8-115">Практическое руководство. Рисование непрозрачными и полупрозрачными кистями</span><span class="sxs-lookup"><span data-stu-id="d72f8-115">How to: Draw with Opaque and Semitransparent Brushes</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-with-opaque-and-semitransparent-brushes.md)  
 <span data-ttu-id="d72f8-116">Объясняется, как альфа смешение для кистей.</span><span class="sxs-lookup"><span data-stu-id="d72f8-116">Explains how to alpha-blend with brushes.</span></span>  
  
 [<span data-ttu-id="d72f8-117">Практическое руководство. Использование режима комбинирования для управления альфа-смешением</span><span class="sxs-lookup"><span data-stu-id="d72f8-117">How to: Use Compositing Mode to Control Alpha Blending</span></span>](../../../../docs/framework/winforms/advanced/how-to-use-compositing-mode-to-control-alpha-blending.md)  
 <span data-ttu-id="d72f8-118">Описание управления альфа-смешение цвета с помощью <xref:System.Drawing.Drawing2D.CompositingMode>.</span><span class="sxs-lookup"><span data-stu-id="d72f8-118">Describes how to control alpha blending using <xref:System.Drawing.Drawing2D.CompositingMode>.</span></span>  
  
 [<span data-ttu-id="d72f8-119">Практическое руководство. Использование матрицы цветов для задания альфа-факторов в изображениях</span><span class="sxs-lookup"><span data-stu-id="d72f8-119">How to: Use a Color Matrix to Set Alpha Values in Images</span></span>](../../../../docs/framework/winforms/advanced/how-to-use-a-color-matrix-to-set-alpha-values-in-images.md)  
 <span data-ttu-id="d72f8-120">Описание способов использования <xref:System.Drawing.Imaging.ColorMatrix> объекта для управления альфа-смешение цвета.</span><span class="sxs-lookup"><span data-stu-id="d72f8-120">Explains how to use a <xref:System.Drawing.Imaging.ColorMatrix> object to control alpha blending.</span></span>
