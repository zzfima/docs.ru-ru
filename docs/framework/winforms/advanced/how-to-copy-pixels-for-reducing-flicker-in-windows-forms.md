---
title: "Практическое руководство. Копирование пикселов для уменьшения эффекта дрожания изображения в Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "перемещение набора битов"
  - "bitblt"
  - "мерцание"
  - "мерцание, сокращение в Windows Forms"
  - "графика, копирование"
  - "графика, снижение мерцания"
  - "пиксели, копирование"
ms.assetid: 33b76910-13a3-4521-be98-5c097341ae3b
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Копирование пикселов для уменьшения эффекта дрожания изображения в Windows Forms
При создании простых анимированных изображений могут появиться мерцание или другие нежелательные визуальные эффекты.  Один из способов ограничения этих эффектов — применение к изображению процесса bitblt.  Функция Bitblt выполняет перемещение набора битов с информацией о цвете из исходного прямоугольника пикселей в конечный прямоугольник.  
  
 В Windows Forms для реализации функции bitblt используется метод <xref:System.Drawing.Graphics.CopyFromScreen%2A> класса <xref:System.Drawing.Graphics>.  В списке параметров метода указываются координаты исходной и конечной областей \(в виде точек\), размер копируемой области и графический объект, с помощью которого рисуется новая форма.  
  
 В следующем примере рисование фигуры на форме происходит в обработчике события <xref:System.Windows.Forms.Control.Paint> этой формы.  После этого фигура копируется с помощью метода <xref:System.Drawing.Graphics.CopyFromScreen%2A>.  
  
> [!NOTE]
>  Установка значения свойства <xref:System.Windows.Forms.Control.DoubleBuffered%2A> формы равным `true` включает двойную буферизацию для кода обработки графики в обработчике события <xref:System.Windows.Forms.Control.Paint>.  Хотя использование такого подхода в приведенном ниже коде не дает заметного выигрыша в производительности, о нем все равно стоит помнить при работе с кодом, управляющим более сложными графическими конструкциями.  
  
## Пример  
  
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
  
## Компиляция кода  
 Приведенный выше код выполняется в обработчике события <xref:System.Windows.Forms.Control.Paint> формы, поэтому изображение остается и после перерисовки формы.  По этой причине не стоит вызывать методы, связанные с графикой в обработчике события <xref:System.Windows.Forms.Form.Load>, поскольку нарисованные элементы не будут перерисовываться при изменении размера формы, или если форма будет закрыта другой формой.  
  
## См. также  
 <xref:System.Drawing.CopyPixelOperation>   
 <xref:System.Drawing.Graphics.FillRectangle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.Control.OnPaint%2A?displayProperty=fullName>   
 [Объекты Graphics и Drawing в Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [Рисование линий и фигур с помощью пера](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)