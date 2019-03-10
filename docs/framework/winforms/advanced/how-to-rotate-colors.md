---
title: Практическое руководство. Вращать цвета
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], rotating
- examples [Windows Forms], rotating colors
ms.assetid: e2e4c300-159c-4f4a-9b56-103b0f7cbc05
ms.openlocfilehash: cb3824d8a5a5674b83124301dbfbd5a3ba60effa
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57720622"
---
# <a name="how-to-rotate-colors"></a>Практическое руководство. Вращать цвета
Поворот в четырехмерный цветовом пространстве сложно представить. Мы можно упростить, если договориться сохранять один из компонентов цвета неизменным. Предположим, что требуется сохранить альфа-компонент, составляет 1 (полностью непрозрачный). Затем мы можете визуализировать трехмерное цветовое пространство с осями красного, зеленого и синего, как показано на следующем рисунке.  
  
 ![Перекрашивание](./media/recoloring03.gif "recoloring03")  
  
 Цвет может рассматриваться как точка в трехмерном пространстве. Например точка (1, 0, 0) в пространстве представляет красный цвет, а точки (0, 1, 0) в пространстве представляет зеленый цвет.  
  
 Ниже показан последствия поворот цвета (1, 0, 0) через угол 60 градусов в плоскости красный-зеленый. Поворот в плоскости плоскости красный-зеленый может рассматриваться как поворот относительно оси синий.  
  
 ![Перекрашивание](./media/recoloring04.gif "recoloring04")  
  
 Ниже показано, как создать матрицу цветов для выполнения поворотов о каждой из трех осей координат (красный, зеленый, синий).  
  
 ![Перекрашивание](./media/recoloring05.gif "recoloring05")  
  
## <a name="example"></a>Пример  
 В следующем примере выполняются изображения, только один цвет (1 0, 0.6) и применяет поворот на 60 градусов относительно оси синий. Угол поворота заметает плоскость, параллельную плоскости красный зеленый.  
  
 Ниже показан исходного изображения в левой части и изображение преобразованное в правой части.  
  
 ![Поворот цветов](./media/colortrans5.png "colortrans5")  
  
 Следующий рисунок иллюстрирует поворот цветов, выполняемый в следующем коде.  
  
 ![Перекрашивание](./media/recoloring06.gif "recoloring06")  
  
 [!code-csharp[System.Drawing.RotateColors#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RotateColors/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.RotateColors#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RotateColors/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром обработчика события <xref:System.Windows.Forms.Control.Paint>. Замените `RotationInput.bmp` в вашей системе путь и имя файла изображения.  
  
## <a name="see-also"></a>См. также
- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [Объекты Graphics и Drawing в Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [перекрашивание изображений](recoloring-images.md)
