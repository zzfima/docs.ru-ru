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
# <a name="overriding-the-onpaint-method"></a><span data-ttu-id="ad3f2-102">Переопределение метода OnPaint</span><span class="sxs-lookup"><span data-stu-id="ad3f2-102">Overriding the OnPaint Method</span></span>
<span data-ttu-id="ad3f2-103">Основные шаги для переопределения любого события, определенного в [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] идентичны и обобщены в следующем списке.</span><span class="sxs-lookup"><span data-stu-id="ad3f2-103">The basic steps for overriding any event defined in the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] are identical and are summarized in the following list.</span></span>  
  
#### <a name="to-override-an-inherited-event"></a><span data-ttu-id="ad3f2-104">Чтобы переопределить наследуемое событие</span><span class="sxs-lookup"><span data-stu-id="ad3f2-104">To override an inherited event</span></span>  
  
1.  <span data-ttu-id="ad3f2-105">Переопределите защищенный `On` *EventName* метод.</span><span class="sxs-lookup"><span data-stu-id="ad3f2-105">Override the protected `On`*EventName* method.</span></span>  
  
2.  <span data-ttu-id="ad3f2-106">Вызовите `On` *EventName* метод базового класса из переопределенного `On` *EventName* метод, чтобы зарегистрированные делегаты получили событие.</span><span class="sxs-lookup"><span data-stu-id="ad3f2-106">Call the `On`*EventName* method of the base class from the overridden `On`*EventName* method, so that registered delegates receive the event.</span></span>  
  
 <span data-ttu-id="ad3f2-107"><xref:System.Windows.Forms.Control.Paint> Событий описано здесь подробно, так как каждый элемент управления Windows Forms должен переопределять <xref:System.Windows.Forms.Control.Paint> событий, который наследует от <xref:System.Windows.Forms.Control>.</span><span class="sxs-lookup"><span data-stu-id="ad3f2-107">The <xref:System.Windows.Forms.Control.Paint> event is discussed in detail here because every Windows Forms control must override the <xref:System.Windows.Forms.Control.Paint> event that it inherits from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="ad3f2-108">Базовый <xref:System.Windows.Forms.Control> класса не знает, как нужно отрисовать производного элемента управления и не предоставляет логику рисования в <xref:System.Windows.Forms.Control.OnPaint%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="ad3f2-108">The base <xref:System.Windows.Forms.Control> class does not know how a derived control needs to be drawn and does not provide any painting logic in the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="ad3f2-109"><xref:System.Windows.Forms.Control.OnPaint%2A> Метод <xref:System.Windows.Forms.Control> лишь отправляет <xref:System.Windows.Forms.Control.Paint> событий получателям зарегистрированного события.</span><span class="sxs-lookup"><span data-stu-id="ad3f2-109">The <xref:System.Windows.Forms.Control.OnPaint%2A> method of <xref:System.Windows.Forms.Control> simply dispatches the <xref:System.Windows.Forms.Control.Paint> event to registered event receivers.</span></span>  
  
 <span data-ttu-id="ad3f2-110">Если вы работали с образцом в [как: разработка простого элемента управления Windows Forms](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md), вы видели пример переопределения <xref:System.Windows.Forms.Control.OnPaint%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="ad3f2-110">If you worked through the sample in [How to: Develop a Simple Windows Forms Control](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md), you have seen an example of overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="ad3f2-111">Следующий фрагмент кода взят из этого примера.</span><span class="sxs-lookup"><span data-stu-id="ad3f2-111">The following code fragment is taken from that sample.</span></span>  
  
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
  
 <span data-ttu-id="ad3f2-112"><xref:System.Windows.Forms.PaintEventArgs> Класс содержит данные для <xref:System.Windows.Forms.Control.Paint> события.</span><span class="sxs-lookup"><span data-stu-id="ad3f2-112">The <xref:System.Windows.Forms.PaintEventArgs> class contains data for the <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="ad3f2-113">Он имеет два свойства, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="ad3f2-113">It has two properties, as shown in the following code.</span></span>  
  
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
  
 <span data-ttu-id="ad3f2-114"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> прямоугольник для рисования и <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> свойство ссылается на <xref:System.Drawing.Graphics> объекта.</span><span class="sxs-lookup"><span data-stu-id="ad3f2-114"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> is the rectangle to be painted, and the <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> property refers to a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="ad3f2-115">Классы в <xref:System.Drawing?displayProperty=nameWithType> имен управляемых классов, предоставляющих доступ к функциям [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], новой библиотеки графики Windows.</span><span class="sxs-lookup"><span data-stu-id="ad3f2-115">The classes in the <xref:System.Drawing?displayProperty=nameWithType> namespace are managed classes that provide access to the functionality of [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], the new Windows graphics library.</span></span> <span data-ttu-id="ad3f2-116"><xref:System.Drawing.Graphics> Объект имеет методы для рисования точек, строк, линий, дуг, эллипсов и многих других форм.</span><span class="sxs-lookup"><span data-stu-id="ad3f2-116">The <xref:System.Drawing.Graphics> object has methods to draw points, strings, lines, arcs, ellipses, and many other shapes.</span></span>  
  
 <span data-ttu-id="ad3f2-117">Элемент управления вызывает его <xref:System.Windows.Forms.Control.OnPaint%2A> метод в случае необходимости изменения его визуального отображения.</span><span class="sxs-lookup"><span data-stu-id="ad3f2-117">A control invokes its <xref:System.Windows.Forms.Control.OnPaint%2A> method whenever it needs to change its visual display.</span></span> <span data-ttu-id="ad3f2-118">Этот метод в свою очередь вызывает <xref:System.Windows.Forms.Control.Paint> событий.</span><span class="sxs-lookup"><span data-stu-id="ad3f2-118">This method in turn raises the <xref:System.Windows.Forms.Control.Paint> event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad3f2-119">См. также</span><span class="sxs-lookup"><span data-stu-id="ad3f2-119">See Also</span></span>  
 [<span data-ttu-id="ad3f2-120">События</span><span class="sxs-lookup"><span data-stu-id="ad3f2-120">Events</span></span>](../../../../docs/standard/events/index.md)  
 [<span data-ttu-id="ad3f2-121">Отрисовка элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ad3f2-121">Rendering a Windows Forms Control</span></span>](../../../../docs/framework/winforms/controls/rendering-a-windows-forms-control.md)  
 [<span data-ttu-id="ad3f2-122">Определение событий</span><span class="sxs-lookup"><span data-stu-id="ad3f2-122">Defining an Event</span></span>](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)
