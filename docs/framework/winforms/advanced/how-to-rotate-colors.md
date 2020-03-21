---
title: Практическое руководство. Поворот цветов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], rotating
- examples [Windows Forms], rotating colors
ms.assetid: e2e4c300-159c-4f4a-9b56-103b0f7cbc05
ms.openlocfilehash: 8d2717dd7b819e963126072279b361fda02188bc
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111339"
---
# <a name="how-to-rotate-colors"></a>Практическое руководство. Поворот цветов
Вращение в четырехмерном цветовом пространстве трудно визуализировать. Мы можем упростить визуализацию вращения, согласившись сохранить один из компонентов цвета фиксированной. Предположим, мы согласны сохранить альфа-компонент фиксированной на 1 (полностью непрозрачный). Затем мы можем визуализировать трехмерное цветовое пространство с красными, зелеными и синими топорами, как показано на следующей иллюстрации.  
  
 ![Иллюстрация, которая показывает вращение с красными, зелеными и синими осями.](./media/how-to-rotate-colors/rotation-red-green-blue-axes.gif)  
  
 Цвет можно рассматривать как точку в 3D пространстве. Например, точка (1, 0, 0) в пространстве представляет красный цвет, а точка (0, 1, 0) в пространстве представляет зеленый цвет.  
  
 На следующей иллюстрации показано, что значит вращать цвет (1, 0, 0) под углом 60 градусов в красно-зеленой плоскости. Вращение в плоскости параллельно красно-зеленой плоскости можно рассматривать как вращение вокруг синей оси.  
  
 ![Иллюстрация, которая показывает вращение о синей оси.](./media/how-to-rotate-colors/rotation-about-blue-axis.gif)  
  
 На следующей иллюстрации показано, как инициализировать цветовую матрицу для выполнения вращений о каждой из трех осей координат (красный, зеленый, синий):  
  
 ![Инициализируем цветовую матрицу для выполнения вращений около трех осей.](./media/how-to-rotate-colors/rotation-about-three-axes.gif)  
  
## <a name="example"></a>Пример  
 Следующий пример приводит изображение, которое является одним цветом (1, 0, 0,6) и применяет 60-градусное вращение вокруг синей оси. Угол вращения сметен в плоскости, параллельной красно-зеленой плоскости.  
  
 На следующей иллюстрации показано исходное изображение слева и повернутое в цвет изображение справа:  
  
 ![Иллюстрация, которая показывает исходное изображение и цвет-повернутое изображение.](./media/how-to-rotate-colors/original-color-rotated-images.png)  
  
 Следующая иллюстрация показывает визуализацию вращения цвета, выполненную в следующем коде:
  
 ![Иллюстрация, которая показывает визуализацию вращения цвета.](./media/how-to-rotate-colors/visualization-color-rotation.gif)  
  
 [!code-csharp[System.Drawing.RotateColors#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RotateColors/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.RotateColors#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RotateColors/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для использования с формами Windows, и он требует, <xref:System.Windows.Forms.PaintEventArgs> `e`который является параметром <xref:System.Windows.Forms.Control.Paint> обработчика событий. Замените `RotationInput.bmp` имя файла изображения и путь, действительный в вашей системе.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [Объекты Graphics и Drawing в Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Перекрашивание изображений](recoloring-images.md)
