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
# <a name="alpha-blending-lines-and-fills"></a>Альфа-смешение цвета для линий и заливок
В [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], цвет является 32-разрядное значение с 8 бит для альфа-канал, красный, зеленый и синий. Значение альфа определяет прозрачность цвета, области, к которому цвет смешивается с цветами фона. При значениях альфа диапазон от 0 до 255, где 0 соответствует полностью прозрачный цвет, а 255 — полностью непрозрачный цвету.  
  
 Альфа-смешение представляет собой пикселей на точек смешение данных исходного и фонового цвета. Каждый из трех компонентов (красный, зеленый, синий) исходного цвета смешивается с соответствующим компонентом фонового цвета по следующей формуле:  
  
 Отображаемый_цвет = Исходный_цвет × альфа / 255 + backgroundColor × (255 – альфа) / 255  
  
 Например предположим, красного компонента цвета источника 150 и красного компонента цвета фона — 100. Если значение альфа составляет 200, красный компонент отображаемого цвета вычисляется следующим образом:  
  
 150 × 200 / 255 + 100 × (255 – 200) / 255 = 139  
  
## <a name="in-this-section"></a>В этом разделе  
 [Практическое руководство. Рисование непрозрачных и полупрозрачных линий](../../../../docs/framework/winforms/advanced/how-to-draw-opaque-and-semitransparent-lines.md)  
 Показано, как рисование линий с альфа смешением.  
  
 [Практическое руководство. Рисование непрозрачными и полупрозрачными кистями](../../../../docs/framework/winforms/advanced/how-to-draw-with-opaque-and-semitransparent-brushes.md)  
 Объясняется, как альфа смешение для кистей.  
  
 [Практическое руководство. Использование режима комбинирования для управления альфа-смешением](../../../../docs/framework/winforms/advanced/how-to-use-compositing-mode-to-control-alpha-blending.md)  
 Описание управления альфа-смешение цвета с помощью <xref:System.Drawing.Drawing2D.CompositingMode>.  
  
 [Практическое руководство. Использование матрицы цветов для задания альфа-факторов в изображениях](../../../../docs/framework/winforms/advanced/how-to-use-a-color-matrix-to-set-alpha-values-in-images.md)  
 Описание способов использования <xref:System.Drawing.Imaging.ColorMatrix> объекта для управления альфа-смешение цвета.
