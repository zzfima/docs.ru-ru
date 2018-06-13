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
ms.openlocfilehash: fc41158e9a3d5d331b391f0f28701612012becf7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537220"
---
# <a name="overriding-the-onpaint-method"></a>Переопределение метода OnPaint
Основные шаги для переопределения любого события, определенного в [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] идентичны и обобщены в следующем списке.  
  
#### <a name="to-override-an-inherited-event"></a>Чтобы переопределить наследуемое событие  
  
1.  Переопределите защищенный `On` *EventName* метод.  
  
2.  Вызовите `On` *EventName* метод базового класса из переопределенного `On` *EventName* метод, чтобы зарегистрированные делегаты получили событие.  
  
 <xref:System.Windows.Forms.Control.Paint> Событий описано здесь подробно, так как каждый элемент управления Windows Forms должен переопределять <xref:System.Windows.Forms.Control.Paint> событий, который наследует от <xref:System.Windows.Forms.Control>. Базовый <xref:System.Windows.Forms.Control> класса не знает, как нужно отрисовать производного элемента управления и не предоставляет логику рисования в <xref:System.Windows.Forms.Control.OnPaint%2A> метод. <xref:System.Windows.Forms.Control.OnPaint%2A> Метод <xref:System.Windows.Forms.Control> лишь отправляет <xref:System.Windows.Forms.Control.Paint> событий получателям зарегистрированного события.  
  
 Если вы работали с образцом в [как: разработка простого элемента управления Windows Forms](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md), вы видели пример переопределения <xref:System.Windows.Forms.Control.OnPaint%2A> метод. Следующий фрагмент кода взят из этого примера.  
  
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
public class FirstControl : Control{  
   public FirstControl() {}  
   protected override void OnPaint(PaintEventArgs e) {  
      // Call the OnPaint method of the base class.  
      base.OnPaint(e);  
      // Call methods of the System.Drawing.Graphics object.  
      e.Graphics.DrawString(Text, Font, new SolidBrush(ForeColor), ClientRectangle);  
   }   
}   
```  
  
 <xref:System.Windows.Forms.PaintEventArgs> Класс содержит данные для <xref:System.Windows.Forms.Control.Paint> события. Он имеет два свойства, как показано в следующем коде.  
  
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
  
 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> прямоугольник для рисования и <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> свойство ссылается на <xref:System.Drawing.Graphics> объекта. Классы в <xref:System.Drawing?displayProperty=nameWithType> имен управляемых классов, предоставляющих доступ к функциям [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], новой библиотеки графики Windows. <xref:System.Drawing.Graphics> Объект имеет методы для рисования точек, строк, линий, дуг, эллипсов и многих других форм.  
  
 Элемент управления вызывает его <xref:System.Windows.Forms.Control.OnPaint%2A> метод в случае необходимости изменения его визуального отображения. Этот метод в свою очередь вызывает <xref:System.Windows.Forms.Control.Paint> событий.  
  
## <a name="see-also"></a>См. также  
 [События](../../../../docs/standard/events/index.md)  
 [Отрисовка элементов управления Windows Forms](../../../../docs/framework/winforms/controls/rendering-a-windows-forms-control.md)  
 [Определение событий](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)
