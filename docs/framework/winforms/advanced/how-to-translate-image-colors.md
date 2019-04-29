---
title: Практическое руководство. Преобразование цветов изображения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [Windows Forms], changing colors
- images [Windows Forms], changing colors
- image colors [Windows Forms]
ms.assetid: 2106fb9a-4d60-4dcf-9220-9f189a6c4d19
ms.openlocfilehash: 04e61383ef79b17ea6e1523588cd9593ec9b082c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61954633"
---
# <a name="how-to-translate-image-colors"></a>Практическое руководство. Преобразование цветов изображения
Перевод добавляет значение к одному или нескольким из четырех компонентов цвета. В следующей таблице приведены элементы матрицы цветов, представляющих переводы.  
  
|Преобразуемый компонент|Элемент матрицы|  
|--------------------------------|------------------|  
|Красный|[4][0]|  
|Зеленый|[4][1]|  
|Синий|[4][2]|  
|Коэффициент альфа|[4][3]|  
  
## <a name="example"></a>Пример  
 В следующем примере создается <xref:System.Drawing.Image> объекта из файла ColorBars.bmp. Затем код добавляет 0,75 красного компонента каждого пикселя в изображении. Исходное изображение отображается вместе с преобразованные изображения.  
  
 Ниже показан исходное изображение в левой части и преобразованные изображения справа:  
  
 ![Снимок экрана исходные и преобразованные изображения.](./media/how-to-translate-image-colors/original-image-translate-colors.png)  
  
 Ниже перечислены эти векторы четырех полос до и после преобразования. Обратите внимание на то, что так как максимальное значение для компонента цвета равно 1, красный компонент во второй строке остается неизменным. (Аналогичным образом, минимальное значение для компонента цвета — 0).  
  
|До преобразования|Перевод|  
|--------------|----------------|  
|Черный (0, 0, 0, 1)|(0.75, 0, 0, 1)|  
|Красный (1, 0, 0, 1)|(1, 0, 0, 1)|  
|Зеленый (0, 1, 0, 1)|(0.75, 1, 0, 1)|  
|Синий (0, 0, 1, 1)|(0.75, 0, 1, 1)|  
  
 [!code-csharp[System.Drawing.RecoloringImages#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.RecoloringImages#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром обработчика события <xref:System.Windows.Forms.Control.Paint>. Замените `ColorBars.bmp` в вашей системе путь и имя файла изображения.  
  
## <a name="see-also"></a>См. также

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [Объекты Graphics и Drawing в Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [перекрашивание изображений](recoloring-images.md)
