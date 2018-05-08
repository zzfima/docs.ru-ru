---
title: Практическое руководство. Копирование пикселов для уменьшения эффекта дрожания изображения в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitblt
- graphics [Windows Forms], copying
- flicker [Windows Forms], reducing in Windows Forms
- graphics [Windows Forms], reducing flicker
- pixels [Windows Forms], copying
- flicker
- bit-block transfer
ms.assetid: 33b76910-13a3-4521-be98-5c097341ae3b
ms.openlocfilehash: 65428132c885191b62c3b4a76c8937bf8f3f6732
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-copy-pixels-for-reducing-flicker-in-windows-forms"></a>Практическое руководство. Копирование пикселов для уменьшения эффекта дрожания изображения в Windows Forms
При создании простых анимированных могут появиться мерцание или другие нежелательные визуальные эффекты. Ограничить эту проблему можно использовать процесс «bitblt» на рисунок. BitBlt является «перемещение набора битов» данных о цвете из исходного прямоугольника пикселей в прямоугольник назначения пикселей.  
  
 С помощью Windows Forms bitblt достигается использованием <xref:System.Drawing.Graphics.CopyFromScreen%2A> метод <xref:System.Drawing.Graphics> класса. В параметрах метода указания источника и назначения (в виде точек), размер копируемой области и графический объект, используемый для рисования новую фигуру.  
  
 В следующем примере рисование фигуры на форме в его <xref:System.Windows.Forms.Control.Paint> обработчика событий. Затем <xref:System.Drawing.Graphics.CopyFromScreen%2A> метод используется для копирования фигуры.  
  
> [!NOTE]
>  Свойства формы <xref:System.Windows.Forms.Control.DoubleBuffered%2A> свойства `true` сделает графическим интерфейсом кода в <xref:System.Windows.Forms.Control.Paint> событие быть двойная буферизация. Пока это не будет иметь выигрыш в производительности заметно при использовании в приведенном ниже коде, ее стоит помнить при работе с кодом более сложных манипуляций с графикой.  
  
## <a name="example"></a>Пример  
  
```vb  
Private Sub Form1_Paint(ByVal sender As Object, ByVal e As _  
    System.Windows.Forms.PaintEventArgs) Handles MyBase.Paint  
    ' Draw a circle with a bar on top.  
        e.Graphics.FillEllipse(Brushes.DarkBlue, New Rectangle _  
             (10, 10, 60, 60))  
        e.Graphics.FillRectangle(Brushes.Khaki, New Rectangle _  
             (20, 30, 60, 10))  
    ' Copy the graphic to a new location.  
        e.Graphics.CopyFromScreen(New Point(10, 10), New Point _  
             (100, 100), New Size(70, 70))  
End Sub  
```  
  
```csharp  
private void Form1_Paint(System.Object sender,  
    System.Windows.Forms.PaintEventArgs e)  
        {  
        e.Graphics.FillEllipse(Brushes.DarkBlue, new  
            Rectangle(10,10,60,60));  
        e.Graphics.FillRectangle(Brushes.Khaki, new  
            Rectangle(20,30,60,10));  
        e.Graphics.CopyFromScreen(new Point(10, 10), new Point(100, 100),   
            new Size(70, 70));  
}  
```  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Приведенный выше код выполняется в форме <xref:System.Windows.Forms.Control.Paint> обработчик событий, чтобы графики сохраняются при обновлении формы. Таким образом, не вызывать методы, связанные с графикой в <xref:System.Windows.Forms.Form.Load> обработчика событий, так как не будет перерисовываться будет Если формы был изменен или скрыта другой формой.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Drawing.CopyPixelOperation>  
 <xref:System.Drawing.Graphics.FillRectangle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Control.OnPaint%2A?displayProperty=nameWithType>  
 [Объекты Graphics и Drawing в Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [Рисование линий и фигур с помощью пера](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
