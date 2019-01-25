---
title: Как выполнить Рисование контурной фигуры
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Graphics.DrawEllipse
helpviewer_keywords:
- ellipses [Windows Forms], drawing
- circles [Windows Forms], drawing
- drawing [Windows Forms], shapes
- circular shapes
- forms [Windows Forms], drawing circular shapes
- circles
- outlined shapes [Windows Forms], examples
- outlined shapes [Windows Forms], drawing
- drawing [Windows Forms], circular shapes
- shapes [Windows Forms], drawing
ms.assetid: f4f9214c-607e-407d-8cdd-6549f0278451
ms.openlocfilehash: 8a7bd12fb1bdab6ea429a889521b7dd6c649a5e7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54512597"
---
# <a name="how-to-draw-an-outlined-shape"></a>Как выполнить Рисование контурной фигуры
В этом примере рисование контуров эллипсы и прямоугольники в форме.  
  
## <a name="example"></a>Пример  
 [!code-cpp[System.Drawing.ConceptualHowTos#6](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#6)]
 [!code-csharp[System.Drawing.ConceptualHowTos#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#6)]
 [!code-vb[System.Drawing.ConceptualHowTos#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#6)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Этот метод нельзя вызывать <xref:System.Windows.Forms.Form.Load> обработчик событий. Если скрыта другой формой или изменении размера формы, рисунок перерисовываться не будет. Чтобы сделать автоматическую перерисовку, нужно переопределить <xref:System.Windows.Forms.Control.OnPaint%2A> метод.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Следует всегда вызывать <xref:System.IDisposable.Dispose%2A> на любые объекты, которые потребляют системные ресурсы, такие как <xref:System.Drawing.Pen> и <xref:System.Drawing.Graphics> объектов.  
  
## <a name="see-also"></a>См. также
- <xref:System.Drawing.Graphics.DrawEllipse%2A>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- <xref:System.Drawing.Graphics.DrawRectangle%2A>
- [Приступая к программированию графики](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)
- [Рисование линий и фигур с помощью пера](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
- [Объекты Graphics и Drawing в Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
