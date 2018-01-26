---
title: "Практическое руководство. Поворот цветов"
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
- colors [Windows Forms], rotating
- examples [Windows Forms], rotating colors
ms.assetid: e2e4c300-159c-4f4a-9b56-103b0f7cbc05
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 81b022011bd5613b8e956aa83482d2836508a4f1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-rotate-colors"></a>Практическое руководство. Поворот цветов
Угол поворота в четырехмерный цветовое пространство сложно визуализировать. Мы можно упростить, если договориться сохранять один из компонентов цвета неизменным. Предположим, нам требуется сохранить альфа-компонент неизменным и равным 1 (полная непрозрачность). Тогда можно представить трехмерное цветовое пространство с осями красного, зеленого и синего как показано на следующем рисунке.  
  
 ![Перекрашивание](../../../../docs/framework/winforms/advanced/media/recoloring03.gif "recoloring03")  
  
 Цвет может рассматриваться как точка объема пространства. Например точка (1, 0, 0) в пространстве представляет красный цвет, а точки (0, 1, 0) в пространстве представляет зеленый цвет.  
  
 На следующем рисунке значит поворот цвета (1, 0, 0) через угол 60 градусов в плоскости красный-зеленый. Поворот в плоскости плоскости красный-зеленый может рассматриваться как поворот относительно оси синий.  
  
 ![Перекрашивание](../../../../docs/framework/winforms/advanced/media/recoloring04.gif "recoloring04")  
  
 Ниже показано, как создать матрицу цветов для выполнения поворотов относительно каждой из трех координатных осей (красный, зеленый, синий).  
  
 ![Перекрашивание](../../../../docs/framework/winforms/advanced/media/recoloring05.gif "recoloring05")  
  
## <a name="example"></a>Пример  
 В следующем примере выполняются изображения, содержащему только один цвет (1, 0, 0,6), применяется поворот на 60 градусов относительно оси синий. Угол поворота заметает плоскость, параллельную плоскости красный зеленый.  
  
 На следующем рисунке исходное изображение в левой части и преобразованное изображение справа.  
  
 ![Вращать цвета](../../../../docs/framework/winforms/advanced/media/colortrans5.png "colortrans5")  
  
 Следующий рисунок иллюстрирует поворот цветов, выполняемый в следующем коде.  
  
 ![Перекрашивание](../../../../docs/framework/winforms/advanced/media/recoloring06.gif "recoloring06")  
  
 [!code-csharp[System.Drawing.RotateColors#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RotateColors/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.RotateColors#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RotateColors/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, и для него необходим <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.Control.Paint> обработчика событий. Замените `RotationInput.bmp` в вашей системе путь и имя файла изображения.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Drawing.Imaging.ColorMatrix>  
 <xref:System.Drawing.Imaging.ImageAttributes>  
 [Объекты Graphics и Drawing в Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [перекрашивание изображений](../../../../docs/framework/winforms/advanced/recoloring-images.md)
