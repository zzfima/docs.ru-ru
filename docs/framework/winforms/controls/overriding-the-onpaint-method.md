---
title: Переопределение метода OnPaint
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Paint event [Windows Forms], handling in Windows Forms custom control
- OnPaint method [Windows Forms], overriding in Windows Forms custom controls
ms.assetid: e9ca2723-0107-4540-bb21-4f5ffb4a9906
ms.openlocfilehash: 863726a6264f01de9f00296b4a64b9fd1bb96765
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182034"
---
# <a name="overriding-the-onpaint-method"></a>Переопределение метода OnPaint
Основные шаги для переопределения любого события, определяемого в рамочном варианте .NET, идентичны и суммируются в следующем списке.  
  
#### <a name="to-override-an-inherited-event"></a>Переопределить унаследованный случай  
  
1. Переопределить защищенный `On`метод *EventName.*  
  
2. Вызовите `On`метод *EventName* базового класса `On`из переочерванного метода *EventName,* чтобы зарегистрированные делегаты получили событие.  
  
 Событие <xref:System.Windows.Forms.Control.Paint> подробно обсуждается здесь, потому что каждый элемент управления Windows Forms должен переопределить <xref:System.Windows.Forms.Control.Paint> событие, которое оно наследует. <xref:System.Windows.Forms.Control> Базовый <xref:System.Windows.Forms.Control> класс не знает, как необходимо нарисовать производный элемент <xref:System.Windows.Forms.Control.OnPaint%2A> управления, и не дает никакой логики рисования в методе. Метод <xref:System.Windows.Forms.Control.OnPaint%2A> <xref:System.Windows.Forms.Control> просто отправляет <xref:System.Windows.Forms.Control.Paint> событие зарегистрированным приемникам событий.  
  
 Если вы работали над образцом в [Как: Разработка простого управления формами Windows,](how-to-develop-a-simple-windows-forms-control.md)вы видели пример переопределения метода. <xref:System.Windows.Forms.Control.OnPaint%2A> Из этого образца взят следующий фрагмент кода.  
  
```vb  
Public Class FirstControl  
   Inherits Control  
  
   Public Sub New()  
   End Sub  
  
   Protected Overrides Sub OnPaint(e As PaintEventArgs)  
      ' Call the OnPaint method of the base class.  
      MyBase.OnPaint(e)  
      ' Call methods of the System.Drawing.Graphics object.  
      e.Graphics.DrawString(Text, Font, New SolidBrush(ForeColor), RectangleF.op_Implicit(ClientRectangle))  
   End Sub  
End Class
```  
  
```csharp  
public class FirstControl : Control {  
   public FirstControl() {}  
   protected override void OnPaint(PaintEventArgs e) {  
      // Call the OnPaint method of the base class.  
      base.OnPaint(e);  
      // Call methods of the System.Drawing.Graphics object.  
      e.Graphics.DrawString(Text, Font, new SolidBrush(ForeColor), ClientRectangle);  
   }
}
```  
  
 Класс <xref:System.Windows.Forms.PaintEventArgs> содержит данные <xref:System.Windows.Forms.Control.Paint> для события. Он имеет два свойства, как показано в следующем коде.  
  
```vb  
Public Class PaintEventArgs  
   Inherits EventArgs  
   ...  
   Public ReadOnly Property ClipRectangle() As System.Drawing.Rectangle  
      ...  
   End Property  
  
   Public ReadOnly Property Graphics() As System.Drawing.Graphics  
      ...  
   End Property
   ...  
End Class  
```  
  
```csharp  
public class PaintEventArgs : EventArgs {  
...  
    public System.Drawing.Rectangle ClipRectangle {}  
    public System.Drawing.Graphics Graphics {}  
...  
}  
```  
  
 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>прямоугольник, который должен быть <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> окрашен, и <xref:System.Drawing.Graphics> свойство относится к объекту. Классы в <xref:System.Drawing?displayProperty=nameWithType> пространстве имен являются управляемыми классами, которые обеспечивают доступ к функциональности GDI, новой графической библиотеки Windows. Объект <xref:System.Drawing.Graphics> имеет методы рисования точек, строк, линий, дуг, эллипсов и многих других форм.  
  
 Элемент управления вызывает <xref:System.Windows.Forms.Control.OnPaint%2A> свой метод всякий раз, когда ему необходимо изменить свой визуальный дисплей. Этот метод, в <xref:System.Windows.Forms.Control.Paint> свою очередь, поднимает событие.  
  
## <a name="see-also"></a>См. также раздел

- [События](../../../standard/events/index.md)
- [Отрисовка элементов управления Windows Forms](rendering-a-windows-forms-control.md)
- [Определение событий](defining-an-event-in-windows-forms-controls.md)
