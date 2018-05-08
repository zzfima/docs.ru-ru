---
title: Практическое руководство. Рисование линий с помощью пера
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines [Windows Forms], drawing
- pens [Windows Forms], drawing lines
ms.assetid: 0828c331-a438-4bdd-a4d6-3ef1e59e8795
ms.openlocfilehash: 6a728bcaf9946b2b92ce0ee97599f4c4fd0fea69
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-a-pen-to-draw-lines"></a>Практическое руководство. Рисование линий с помощью пера
Чтобы нарисовать линии, нужно <xref:System.Drawing.Graphics> объекта и <xref:System.Drawing.Pen> объекта. <xref:System.Drawing.Graphics> Объект предоставляет <xref:System.Drawing.Graphics.DrawLine%2A> метода и <xref:System.Drawing.Pen> объект сохраняет функции строки, таких как цвет и ширину.  
  
## <a name="example"></a>Пример  
 В следующем примере рисуется строку из (20, 10) для (300, 100). В первом операторе используется <xref:System.Drawing.Pen.%23ctor%2A> конструктор класса для создания черного пера. Один аргумент, передаваемый <xref:System.Drawing.Pen.%23ctor%2A> конструктор является <xref:System.Drawing.Color> объектом, созданным с помощью <xref:System.Drawing.Color.FromArgb%2A> метод. Значения, используемые для создания <xref:System.Drawing.Color> объекта — (255, 0, 0, 0), соответствуют альфа, красного, зеленого и синего компонентов цвета. Эти значения определяют непрозрачное черного пера.  
  
 [!code-csharp[System.Drawing.UsingAPen#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, и для него необходим <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.Control.Paint> обработчика событий.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Drawing.Pen>  
 [Рисование линий и фигур с помощью пера](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [Перья, линии и прямоугольники в GDI+](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)
