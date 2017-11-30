---
title: "Альфа-смешение цвета для линий и заливок"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5b3c0ee3ec82d4d8447c43b7dc9b275591ebe890
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="alpha-blending-lines-and-fills"></a>Альфа-смешение цвета для линий и заливок
В [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], цвет является 32-разрядное значение с 8 бит для альфа-канал, красный, зеленый и синий. Значение альфа определяет прозрачность цвета, области, к которому цвет смешивается с цветами фона. При значениях альфа диапазон от 0 до 255, где 0 соответствует полностью прозрачный цвет, а 255 — полностью непрозрачный цвету.  
  
 Альфа-смешение представляет собой пикселей на точек смешение данных исходного и фонового цвета. Каждый из трех компонентов (красный, зеленый, синий) исходного цвета смешивается с соответствующим компонентом фонового цвета по следующей формуле:  
  
 Отображаемый_цвет = Исходный_цвет × альфа / 255 + backgroundColor × (255 – альфа) / 255  
  
 Например предположим, красного компонента цвета источника 150 и красного компонента цвета фона — 100. Если значение альфа составляет 200, красный компонент отображаемого цвета вычисляется следующим образом:  
  
 150 × 200 / 255 + 100 × (255 – 200) / 255 = 139  
  
## <a name="in-this-section"></a>Содержание  
 [Практическое руководство. Рисование непрозрачных и полупрозрачных линий](../../../../docs/framework/winforms/advanced/how-to-draw-opaque-and-semitransparent-lines.md)  
 Показано, как рисование линий с альфа смешением.  
  
 [Практическое руководство. Рисование непрозрачными и полупрозрачными кистями](../../../../docs/framework/winforms/advanced/how-to-draw-with-opaque-and-semitransparent-brushes.md)  
 Объясняется, как альфа смешение для кистей.  
  
 [Практическое руководство. Использование режима комбинирования для управления альфа-смешением](../../../../docs/framework/winforms/advanced/how-to-use-compositing-mode-to-control-alpha-blending.md)  
 Описание управления альфа-смешение цвета с помощью <xref:System.Drawing.Drawing2D.CompositingMode>.  
  
 [Практическое руководство. Использование матрицы цветов для задания альфа-факторов в изображениях](../../../../docs/framework/winforms/advanced/how-to-use-a-color-matrix-to-set-alpha-values-in-images.md)  
 Описание способов использования <xref:System.Drawing.Imaging.ColorMatrix> объекта для управления альфа-смешение цвета.
