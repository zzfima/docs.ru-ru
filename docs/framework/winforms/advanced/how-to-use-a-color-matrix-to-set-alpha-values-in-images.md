---
title: Практическое руководство. Использование матрицы цветов для задания значений прозрачности в изображениях
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], using color matrices for semi-transparent
- transparency [Windows Forms], color matrices
- matrices [Windows Forms], alpha values
- bitmaps [Windows Forms], using color matrices for semi-transparent
ms.assetid: a27121e6-f7e9-4c09-84e2-f05aa9d2a1bb
ms.openlocfilehash: 73e820845d040856a0ae367da8b9371ad6afa142
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423744"
---
# <a name="how-to-use-a-color-matrix-to-set-alpha-values-in-images"></a>Практическое руководство. Использование матрицы цветов для задания значений прозрачности в изображениях
Класс <xref:System.Drawing.Bitmap> (который наследует от класса <xref:System.Drawing.Image>) и класс <xref:System.Drawing.Imaging.ImageAttributes> предоставляют функциональные возможности для получения и установки значений пикселей. Можно использовать класс <xref:System.Drawing.Imaging.ImageAttributes>, чтобы изменить альфа-значения для всего изображения, или можно вызвать метод <xref:System.Drawing.Bitmap.SetPixel%2A> класса <xref:System.Drawing.Bitmap>, чтобы изменить отдельные значения пикселей.  
  
## <a name="example"></a>Пример  
 Класс <xref:System.Drawing.Imaging.ImageAttributes> имеет множество свойств, которые можно использовать для изменения изображений во время подготовки к просмотру. В следующем примере объект <xref:System.Drawing.Imaging.ImageAttributes> используется для установки всех альфа-значений равными 80 процентам от того, что они имели. Это делается путем инициализации матрицы цветов и установки значения масштабирования альфа в матрице в 0,8. Адрес матрицы цветов передается методу <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> объекта <xref:System.Drawing.Imaging.ImageAttributes>, а объект <xref:System.Drawing.Imaging.ImageAttributes> передается методу <xref:System.Drawing.Graphics.DrawString%2A> объекта <xref:System.Drawing.Graphics>.  
  
 Во время отрисовки альфа-значения в точечном рисунке преобразуются в 80 процентов от того, что они имели. В результате получается изображение, которое смешивается с фоном. Как показано на рисунке ниже, точечный рисунок выглядит прозрачным. можно увидеть сплошную черную линию.  
  
 ![Снимок экрана альфа-смешения с использованием матрицы.](./media/how-to-use-a-color-matrix-to-set-alpha-values-in-images/alpha-blending-matrix.png "изображение 2")  
  
 Когда изображение находится над белой частью фона, изображение смешивается с белым цветом. Когда изображение пересекает черную линию, изображение смешивается с черным цветом.  
  
 [!code-csharp[System.Drawing.AlphaBlending#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.AlphaBlending#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для использования с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>См. также

- [Объекты Graphics и Drawing в Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Альфа-смешение цвета для линий и заливок](alpha-blending-lines-and-fills.md)
