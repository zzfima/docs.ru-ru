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
ms.openlocfilehash: 6cfe90cef42086672990c45c99961db3d29c3ff3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525971"
---
# <a name="using-transformations-to-scale-colors"></a>Масштабирование цветов с применением преобразований
Масштабирование умножает одно или несколько из четырех компонентов цвета на число. В следующей таблице приведены элементы матрицы цветов, соответствующие масштабированию.  
  
|Масштабируемый компонент|Элемент матрицы|  
|----------------------------|------------------|  
|Красный|[0][0]|  
|Зеленый|[1][1]|  
|Синий|[2][2]|  
|Коэффициент альфа|[3][3]|  
  
## <a name="scaling-one-color"></a>Масштабирование одного цвета  
 В следующем примере создается <xref:System.Drawing.Image> объекта из файла ColorBars2.bmp. Затем код масштабирует синий компонент каждого пикселя в изображении с коэффициентом 2. Исходное изображение отображается вместе с преобразованным изображением.  
  
 [!code-csharp[System.Drawing.RecoloringImages#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.RecoloringImages#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#41)]  
  
 Ниже показан исходный образ в левой части экрана и масштабированное изображение справа.  
  
 ![Масштабирование цветов](../../../../docs/framework/winforms/advanced/media/colortrans3.png "colortrans3")  
  
 Ниже перечислены эти векторы четырех полос до и после масштабирования. Обратите внимание, что синий компонент цвета четвертой полосы изменился с 0,8 на 0,6. Причина этого заключается в [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] сохраняет дробная часть результата. Например (2)(0,8) = 1,6, а дробная часть 1.6 равно 0,6. Сохранение только дробной части гарантирует, что результат будет в интервале [0, 1].  
  
|До преобразования|Масштабирование|  
|--------------|------------|  
|(0.4, 0.4, 0.4, 1)|(0.4, 0.4, 0.8, 1)|  
|(0.4, 0.2, 0.2, 1)|(0.4, 0.2, 0.4, 1)|  
|(0.2, 0.4, 0.2, 1)|(0.2, 0.4, 0.4, 1)|  
|(0.4, 0.4, 0.8, 1)|(0.4, 0.4, 0.6, 1)|  
  
## <a name="scaling-multiple-colors"></a>Масштабирование нескольких цветов  
 В следующем примере создается <xref:System.Drawing.Image> объекта из файла ColorBars2.bmp. Затем код масштабирует красного, зеленого и синего компонентов каждого пикселя в изображении. Красные компоненты уменьшаются на 25 процентов, зеленый компоненты уменьшаются на 35 процентов и синий компоненты уменьшаются на 50 процентов.  
  
 [!code-csharp[System.Drawing.RecoloringImages#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.RecoloringImages#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#42)]  
  
 Ниже показан исходный образ в левой части экрана и масштабированное изображение справа.  
  
 ![Масштабирование цветов](../../../../docs/framework/winforms/advanced/media/colortrans4.png "colortrans4")  
  
 Ниже перечислены эти векторы четырех полос до и после красного, зеленого и синего масштабирования.  
  
|До преобразования|Масштабирование|  
|--------------|------------|  
|(0.6, 0.6, 0.6, 1)|(0.45, 0.39, 0.3, 1)|  
|(0, 1, 1, 1)|(0, 0.65, 0.5, 1)|  
|(1, 1, 0, 1)|(0.75, 0.65, 0, 1)|  
|(1, 0, 1, 1)|(0.75, 0, 0.5, 1)|  
  
## <a name="see-also"></a>См. также  
 <xref:System.Drawing.Imaging.ColorMatrix>  
 <xref:System.Drawing.Imaging.ImageAttributes>  
 [Объекты Graphics и Drawing в Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [перекрашивание изображений](../../../../docs/framework/winforms/advanced/recoloring-images.md)
