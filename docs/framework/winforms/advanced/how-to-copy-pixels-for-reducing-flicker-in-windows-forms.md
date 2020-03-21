---
title: 'Как: Копировать пикселей для уменьшения мерцания'
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
ms.openlocfilehash: a25295532d7123d92bcacc6828d3e8cfcc839d6e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182589"
---
# <a name="how-to-copy-pixels-for-reducing-flicker-in-windows-forms"></a>Практическое руководство. Копирование пикселов для уменьшения эффекта дрожания изображения в Windows Forms
Когда вы анимируете простой график, пользователи иногда могут столкнуться с мерцание или другие нежелательные визуальные эффекты. Один из способов ограничить эту проблему заключается в использовании "bitblt" процесс на графике. Bitblt — это «перенос бит-блока» цветовых данных из прямоугольника пикселей происхождения в прямоугольник пикселей назначения.  
  
 С Windows Forms, bitblt выполняется с помощью <xref:System.Drawing.Graphics.CopyFromScreen%2A> метода <xref:System.Drawing.Graphics> класса. В параметрах метода указанисточник источника и пункта (в виде точек), размера области, поднимила копироваться, и графического объекта, используемого для рисования новой формы.  
  
 В приведенном ниже примере форма нарисована на форме в обработчике <xref:System.Windows.Forms.Control.Paint> событий. Затем <xref:System.Drawing.Graphics.CopyFromScreen%2A> метод используется для дублирования формы.  
  
> [!NOTE]
> Установка <xref:System.Windows.Forms.Control.DoubleBuffered%2A> свойства формы `true` сделает графический код в <xref:System.Windows.Forms.Control.Paint> случае двойного буфера. Хотя при использовании приведенного ниже кода это не будет иметь заметного повышения производительности, это то, что нужно иметь в виду при работе с более сложным графическим кодом манипуляций.  
  
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
 Приведенный выше код работает в <xref:System.Windows.Forms.Control.Paint> обработчике событий формы, так что графика сохраняется при перерисовке формы. Таким образом, не вызывайте методы, <xref:System.Windows.Forms.Form.Load> связанные с графикой, в обработчике событий, поскольку нарисованное содержимое не будет перерисовано, если форма будет уменьшена или заслонена другой формой.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Drawing.CopyPixelOperation>
- <xref:System.Drawing.Graphics.FillRectangle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.OnPaint%2A?displayProperty=nameWithType>
- [Объекты Graphics и Drawing в Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Рисование линий и фигур с помощью пера](using-a-pen-to-draw-lines-and-shapes.md)
