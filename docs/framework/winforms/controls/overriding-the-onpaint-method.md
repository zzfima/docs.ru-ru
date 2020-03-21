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
# <a name="overriding-the-onpaint-method"></a><span data-ttu-id="0cd18-102">Переопределение метода OnPaint</span><span class="sxs-lookup"><span data-stu-id="0cd18-102">Overriding the OnPaint Method</span></span>
<span data-ttu-id="0cd18-103">Основные шаги для переопределения любого события, определяемого в рамочном варианте .NET, идентичны и суммируются в следующем списке.</span><span class="sxs-lookup"><span data-stu-id="0cd18-103">The basic steps for overriding any event defined in the .NET Framework are identical and are summarized in the following list.</span></span>  
  
#### <a name="to-override-an-inherited-event"></a><span data-ttu-id="0cd18-104">Переопределить унаследованный случай</span><span class="sxs-lookup"><span data-stu-id="0cd18-104">To override an inherited event</span></span>  
  
1. <span data-ttu-id="0cd18-105">Переопределить защищенный `On`метод *EventName.*</span><span class="sxs-lookup"><span data-stu-id="0cd18-105">Override the protected `On`*EventName* method.</span></span>  
  
2. <span data-ttu-id="0cd18-106">Вызовите `On`метод *EventName* базового класса `On`из переочерванного метода *EventName,* чтобы зарегистрированные делегаты получили событие.</span><span class="sxs-lookup"><span data-stu-id="0cd18-106">Call the `On`*EventName* method of the base class from the overridden `On`*EventName* method, so that registered delegates receive the event.</span></span>  
  
 <span data-ttu-id="0cd18-107">Событие <xref:System.Windows.Forms.Control.Paint> подробно обсуждается здесь, потому что каждый элемент управления Windows Forms должен переопределить <xref:System.Windows.Forms.Control.Paint> событие, которое оно наследует. <xref:System.Windows.Forms.Control></span><span class="sxs-lookup"><span data-stu-id="0cd18-107">The <xref:System.Windows.Forms.Control.Paint> event is discussed in detail here because every Windows Forms control must override the <xref:System.Windows.Forms.Control.Paint> event that it inherits from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="0cd18-108">Базовый <xref:System.Windows.Forms.Control> класс не знает, как необходимо нарисовать производный элемент <xref:System.Windows.Forms.Control.OnPaint%2A> управления, и не дает никакой логики рисования в методе.</span><span class="sxs-lookup"><span data-stu-id="0cd18-108">The base <xref:System.Windows.Forms.Control> class does not know how a derived control needs to be drawn and does not provide any painting logic in the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="0cd18-109">Метод <xref:System.Windows.Forms.Control.OnPaint%2A> <xref:System.Windows.Forms.Control> просто отправляет <xref:System.Windows.Forms.Control.Paint> событие зарегистрированным приемникам событий.</span><span class="sxs-lookup"><span data-stu-id="0cd18-109">The <xref:System.Windows.Forms.Control.OnPaint%2A> method of <xref:System.Windows.Forms.Control> simply dispatches the <xref:System.Windows.Forms.Control.Paint> event to registered event receivers.</span></span>  
  
 <span data-ttu-id="0cd18-110">Если вы работали над образцом в [Как: Разработка простого управления формами Windows,](how-to-develop-a-simple-windows-forms-control.md)вы видели пример переопределения метода. <xref:System.Windows.Forms.Control.OnPaint%2A></span><span class="sxs-lookup"><span data-stu-id="0cd18-110">If you worked through the sample in [How to: Develop a Simple Windows Forms Control](how-to-develop-a-simple-windows-forms-control.md), you have seen an example of overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="0cd18-111">Из этого образца взят следующий фрагмент кода.</span><span class="sxs-lookup"><span data-stu-id="0cd18-111">The following code fragment is taken from that sample.</span></span>  
  
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
  
 <span data-ttu-id="0cd18-112">Класс <xref:System.Windows.Forms.PaintEventArgs> содержит данные <xref:System.Windows.Forms.Control.Paint> для события.</span><span class="sxs-lookup"><span data-stu-id="0cd18-112">The <xref:System.Windows.Forms.PaintEventArgs> class contains data for the <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="0cd18-113">Он имеет два свойства, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="0cd18-113">It has two properties, as shown in the following code.</span></span>  
  
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
  
 <span data-ttu-id="0cd18-114"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>прямоугольник, который должен быть <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> окрашен, и <xref:System.Drawing.Graphics> свойство относится к объекту.</span><span class="sxs-lookup"><span data-stu-id="0cd18-114"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> is the rectangle to be painted, and the <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> property refers to a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="0cd18-115">Классы в <xref:System.Drawing?displayProperty=nameWithType> пространстве имен являются управляемыми классами, которые обеспечивают доступ к функциональности GDI, новой графической библиотеки Windows.</span><span class="sxs-lookup"><span data-stu-id="0cd18-115">The classes in the <xref:System.Drawing?displayProperty=nameWithType> namespace are managed classes that provide access to the functionality of GDI+, the new Windows graphics library.</span></span> <span data-ttu-id="0cd18-116">Объект <xref:System.Drawing.Graphics> имеет методы рисования точек, строк, линий, дуг, эллипсов и многих других форм.</span><span class="sxs-lookup"><span data-stu-id="0cd18-116">The <xref:System.Drawing.Graphics> object has methods to draw points, strings, lines, arcs, ellipses, and many other shapes.</span></span>  
  
 <span data-ttu-id="0cd18-117">Элемент управления вызывает <xref:System.Windows.Forms.Control.OnPaint%2A> свой метод всякий раз, когда ему необходимо изменить свой визуальный дисплей.</span><span class="sxs-lookup"><span data-stu-id="0cd18-117">A control invokes its <xref:System.Windows.Forms.Control.OnPaint%2A> method whenever it needs to change its visual display.</span></span> <span data-ttu-id="0cd18-118">Этот метод, в <xref:System.Windows.Forms.Control.Paint> свою очередь, поднимает событие.</span><span class="sxs-lookup"><span data-stu-id="0cd18-118">This method in turn raises the <xref:System.Windows.Forms.Control.Paint> event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cd18-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0cd18-119">See also</span></span>

- [<span data-ttu-id="0cd18-120">События</span><span class="sxs-lookup"><span data-stu-id="0cd18-120">Events</span></span>](../../../standard/events/index.md)
- [<span data-ttu-id="0cd18-121">Отрисовка элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0cd18-121">Rendering a Windows Forms Control</span></span>](rendering-a-windows-forms-control.md)
- [<span data-ttu-id="0cd18-122">Определение событий</span><span class="sxs-lookup"><span data-stu-id="0cd18-122">Defining an Event</span></span>](defining-an-event-in-windows-forms-controls.md)
