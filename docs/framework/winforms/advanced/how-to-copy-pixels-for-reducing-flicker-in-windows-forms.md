---
title: Как копировать пиксели для снижения мерцания
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
ms.openlocfilehash: 299041e7038d5bd5b9824d668b3f47d842030ac7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746483"
---
# <a name="how-to-copy-pixels-for-reducing-flicker-in-windows-forms"></a>Практическое руководство. Копирование пикселов для уменьшения эффекта дрожания изображения в Windows Forms
При анимации простого графика пользователи иногда могут столкнуться с мерцанием или другими нежелательными визуальными эффектами. Одним из способов ограничения этой проблемы является использование на графике процесса "BitBlt". BitBlt — это перенос битовых блоков цветовых данных из исходного прямоугольника пикселей в целевой прямоугольник пикселей.  
  
 С Windows Forms BitBlt выполняется с помощью метода <xref:System.Drawing.Graphics.CopyFromScreen%2A> класса <xref:System.Drawing.Graphics>. В параметрах метода указываются источник и назначение (точки), размер копируемой области и графический объект, используемый для рисования новой фигуры.  
  
 В приведенном ниже примере фигура рисуется на форме в своем <xref:System.Windows.Forms.Control.Paint> обработчике событий. Затем для дублирования фигуры используется метод <xref:System.Drawing.Graphics.CopyFromScreen%2A>.  
  
> [!NOTE]
> Присвоение свойству <xref:System.Windows.Forms.Control.DoubleBuffered%2A> формы значения `true` приведет к двойному буферизации графического кода в событии <xref:System.Windows.Forms.Control.Paint>. Несмотря на то, что при использовании приведенного ниже кода не будет выигрыша в производительности различимый, при работе с более сложным графическим кодом следует учитывать следующее.  
  
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
 Приведенный выше код выполняется в обработчике событий <xref:System.Windows.Forms.Control.Paint> формы, чтобы графические объекты сохранялись при перерисовке формы. Таким образом, не следует вызывать методы, связанные с графикой, в обработчике событий <xref:System.Windows.Forms.Form.Load>, поскольку рисуемое содержимое не будет перерисовано при изменении размера формы или ее скрытии другой формой.  
  
## <a name="see-also"></a>См. также:

- <xref:System.Drawing.CopyPixelOperation>
- <xref:System.Drawing.Graphics.FillRectangle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.OnPaint%2A?displayProperty=nameWithType>
- [Объекты Graphics и Drawing в Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Рисование линий и фигур с помощью пера](using-a-pen-to-draw-lines-and-shapes.md)
