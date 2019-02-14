---
title: Как выполнить Нарисовать линию в форме Windows
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- Graphics.DrawLine
helpviewer_keywords:
- examples [Windows Forms], drawing lines on forms
- drawing [Windows Forms], lines
- lines [Windows Forms], drawing
- drawing lines
ms.assetid: 55c1dbeb-75d0-430c-9814-a24b8971ad8c
ms.openlocfilehash: 4274072b55c79cfe88e906d1401d275b414ebe97
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54586752"
---
# <a name="how-to-draw-a-line-on-a-windows-form"></a>Практическое руководство: Рисований линий в Windows Forms
Этот пример рисует линию на форме. Как правило, рисование на форме осуществляют, обрабатывая событие <xref:System.Windows.Forms.Control.Paint> формы и выполняя отрисовку с использованием свойства <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> объекта <xref:System.Windows.Forms.PaintEventArgs>, как показано в следующем примере  
  
## <a name="example"></a>Пример  
 [!code-csharp[System.Drawing.UsingAPen#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром обработчика события <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Следует всегда вызывать <xref:System.IDisposable.Dispose%2A> для любых объектов, которые потребляют системные ресурсы, например объектов <xref:System.Drawing.Pen>.  
  
## <a name="see-also"></a>См. также
- <xref:System.Drawing.Graphics.DrawLine%2A>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [Приступая к программированию графики](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)
- [Рисование линий и фигур с помощью пера](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
- [Объекты Graphics и Drawing в Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
