---
title: Как выполнить Соединение линий
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
ms.openlocfilehash: 55551a78f37a5179b24eda28a9fc5d0a0c640a9b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54543387"
---
# <a name="how-to-join-lines"></a>Как выполнить Соединение линий
Соединение линий — это общая область, сформированное две строки, в которых заканчивается достигают или перекрываться. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] предоставляет три стиля соединения линий: фацетное соединение, рельеф и округления. Стиль соединения линий — это свойство <xref:System.Drawing.Pen> класса. При указании стиль соединения линий для <xref:System.Drawing.Pen> объекта, что стиль будет применяться для всех соединенных линий в любом <xref:System.Drawing.Drawing2D.GraphicsPath> объекта, отображаются с помощью этого пера.  
  
 Ниже показаны результаты в примере скошенные строки соединения.  
  
 ![Перья](../../../../docs/framework/winforms/advanced/media/pens5.gif "pens5")  
  
## <a name="example"></a>Пример  
 Можно указать стиль соединения линий с помощью <xref:System.Drawing.Pen.LineJoin%2A> свойство <xref:System.Drawing.Pen> класса. В примере скошенное соединение линий между горизонтальной и вертикальной линией. В следующем коде значение <xref:System.Drawing.Drawing2D.LineJoin.Bevel> назначенные <xref:System.Drawing.Pen.LineJoin%2A> свойства является членом <xref:System.Drawing.Drawing2D.LineJoin> перечисления. Другие члены <xref:System.Drawing.Drawing2D.LineJoin> перечисления являются <xref:System.Drawing.Drawing2D.LineJoin.Miter> и <xref:System.Drawing.Drawing2D.LineJoin.Round>.  
  
 [!code-csharp[System.Drawing.UsingAPen#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingAPen#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>См. также
- [Рисование линий и фигур с помощью пера](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
