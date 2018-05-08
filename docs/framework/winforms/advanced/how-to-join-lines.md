---
title: Практическое руководство. Соединение линий
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- miter line join style
- bevel line join style
- line join
- drawing [Windows Forms], joining lines
- GraphicsPath object
- round line join style
- lines [Windows Forms], joining
- graphics [Windows Forms], joining lines
ms.assetid: 9fc480c2-3c75-4fd1-8ab5-296a99e820e2
ms.openlocfilehash: cecced7b32af7187cb1ef072921f0ff28f04adad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-join-lines"></a>Практическое руководство. Соединение линий
Соединение линий — это общая область, сформированное две строки которого заканчивается соответствуют или перекрываться. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] предоставляет три стиля соединения линий: фацетное скоса и округления. Стиль соединения линий является свойством <xref:System.Drawing.Pen> класса. При указании стиль соединения линий для <xref:System.Drawing.Pen> объекта применения стиля соединения для всех соединенных линий в любом <xref:System.Drawing.Drawing2D.GraphicsPath> объекта, рисуется с помощью этого пера.  
  
 Ниже показаны результаты в примере скошенной строки соединения.  
  
 ![Перья](../../../../docs/framework/winforms/advanced/media/pens5.gif "pens5")  
  
## <a name="example"></a>Пример  
 Стиль соединения линий можно указать с помощью <xref:System.Drawing.Pen.LineJoin%2A> свойство <xref:System.Drawing.Pen> класса. В примере скошенной строки соединения между горизонтальной и вертикальной линии. В следующем коде значение <xref:System.Drawing.Drawing2D.LineJoin.Bevel> назначен <xref:System.Drawing.Pen.LineJoin%2A> входит свойство <xref:System.Drawing.Drawing2D.LineJoin> перечисления. Другие члены <xref:System.Drawing.Drawing2D.LineJoin> перечисления являются <xref:System.Drawing.Drawing2D.LineJoin.Miter> и <xref:System.Drawing.Drawing2D.LineJoin.Round>.  
  
 [!code-csharp[System.Drawing.UsingAPen#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingAPen#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>См. также  
 [Рисование линий и фигур с помощью пера](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
