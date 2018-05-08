---
title: Практическое руководство. Рисование прямоугольников с помощью пера
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- rectangles [Windows Forms], drawing
- pens [Windows Forms], drawing rectangles
ms.assetid: 54a7fa14-3ad8-4d64-b424-2a12005b250c
ms.openlocfilehash: ad5b436f7162c282198c7a9d3cce4d3ce3fd3c6f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-a-pen-to-draw-rectangles"></a>Практическое руководство. Рисование прямоугольников с помощью пера
Рисование прямоугольников, необходимо <xref:System.Drawing.Graphics> объекта и <xref:System.Drawing.Pen> объекта. <xref:System.Drawing.Graphics> Объект предоставляет <xref:System.Drawing.Graphics.DrawRectangle%2A> метода и <xref:System.Drawing.Pen> объект сохраняет функции строки, таких как цвет и ширину.  
  
## <a name="example"></a>Пример  
 В следующем примере рисуется прямоугольник с его верхнего левого угла в (10, 10). Прямоугольник имеет ширину 100 и высотой 50. Второй аргумент, переданный <xref:System.Drawing.Pen.%23ctor%2A> конструктор указывает, что толщина пера 5 пикселей.  
  
 При рисовании прямоугольника перо располагается по центру границы данного прямоугольника. Поскольку толщина пера равна 5, стороны прямоугольника, формируемого 5 точек шириной 1 точка рисуется по самой границе, 2 пикселя рисуются внутри и рисования 2 пикселя снаружи. Дополнительные сведения о возможностях выравнивания пера см. в разделе [как: значение толщины и выравнивания пера](../../../../docs/framework/winforms/advanced/how-to-set-pen-width-and-alignment.md).  
  
 На следующем рисунке полученный прямоугольник. Пунктирные линии показывают, где был бы нарисован прямоугольник, если толщина пера была равна одному пикселю. Увеличенное верхнего левого угла прямоугольника показывает толстой черные линии выравниваются по центру на этих пунктирными линиями.  
  
 ![Перья](../../../../docs/framework/winforms/advanced/media/pens1.gif "pens1")  
  
 [!code-csharp[System.Drawing.UsingAPen#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingAPen#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, и для него необходим <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.Control.Paint> обработчика событий.  
  
## <a name="see-also"></a>См. также  
 [Рисование линий и фигур с помощью пера](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
