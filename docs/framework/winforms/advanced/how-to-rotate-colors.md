---
title: Как выполнить Вращать цвета
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], rotating
- examples [Windows Forms], rotating colors
ms.assetid: e2e4c300-159c-4f4a-9b56-103b0f7cbc05
ms.openlocfilehash: 6c4f41504911e94673707d99d804fad5b228599e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54503086"
---
# <a name="how-to-rotate-colors"></a>Как выполнить Вращать цвета
Поворот в четырехмерный цветовом пространстве сложно представить. Мы можно упростить, если договориться сохранять один из компонентов цвета неизменным. Предположим, что требуется сохранить альфа-компонент, составляет 1 (полностью непрозрачный). Затем мы можете визуализировать трехмерное цветовое пространство с осями красного, зеленого и синего, как показано на следующем рисунке.  
  
 ![Перекрашивание](../../../../docs/framework/winforms/advanced/media/recoloring03.gif "recoloring03")  
  
 Цвет может рассматриваться как точка в трехмерном пространстве. Например точка (1, 0, 0) в пространстве представляет красный цвет, а точки (0, 1, 0) в пространстве представляет зеленый цвет.  
  
 Ниже показан последствия поворот цвета (1, 0, 0) через угол 60 градусов в плоскости красный-зеленый. Поворот в плоскости плоскости красный-зеленый может рассматриваться как поворот относительно оси синий.  
  
 ![Перекрашивание](../../../../docs/framework/winforms/advanced/media/recoloring04.gif "recoloring04")  
  
 Ниже показано, как создать матрицу цветов для выполнения поворотов о каждой из трех осей координат (красный, зеленый, синий).  
  
 ![Перекрашивание](../../../../docs/framework/winforms/advanced/media/recoloring05.gif "recoloring05")  
  
## <a name="example"></a>Пример  
 В следующем примере выполняются изображения, только один цвет (1 0, 0.6) и применяет поворот на 60 градусов относительно оси синий. Угол поворота заметает плоскость, параллельную плоскости красный зеленый.  
  
 Ниже показан исходного изображения в левой части и изображение преобразованное в правой части.  
  
 ![Поворот цветов](../../../../docs/framework/winforms/advanced/media/colortrans5.png "colortrans5")  
  
 Следующий рисунок иллюстрирует поворот цветов, выполняемый в следующем коде.  
  
 ![Перекрашивание](../../../../docs/framework/winforms/advanced/media/recoloring06.gif "recoloring06")  
  
 [!code-csharp[System.Drawing.RotateColors#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RotateColors/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.RotateColors#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RotateColors/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.Control.Paint> обработчик событий. Замените `RotationInput.bmp` в вашей системе путь и имя файла изображения.  
  
## <a name="see-also"></a>См. также
- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [Объекты Graphics и Drawing в Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
- [перекрашивание изображений](../../../../docs/framework/winforms/advanced/recoloring-images.md)
