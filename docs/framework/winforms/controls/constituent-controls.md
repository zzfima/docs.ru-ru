---
title: Составные элементы управления
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], constituent controls
- constituent controls [Windows Forms]
- user controls [Windows Forms], constituent controls
ms.assetid: 5565e720-198b-4bbd-a2bd-c447ba641798
ms.openlocfilehash: 2865a3d85bd56151038ee90c18d199d3a584b5d4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182417"
---
# <a name="constituent-controls"></a>Составные элементы управления
Элементы управления, составляющие пользовательский элемент управления, или *составные элементы управления*, как они иначе называются, обеспечивают относительную гибкость, когда речь идет об отрисовке пользовательской графики. Все элементы управления Windows Forms обрабатывают <xref:System.Windows.Forms.Control.OnPaint%2A> свою собственную визуализацию с помощью собственного метода. Так как этот метод защищен, он недоступен для разработчика и поэтому не может быть заблокирован при рисовании элемента управления. Это, однако, не означает, что нельзя добавить код, влияющий на внешний вид составных элементов управления. Дополнительную отрисовку можно выполнить путем добавления обработчика событий. Например, предположим, что <xref:System.Windows.Forms.UserControl> вы были `MyButton`автор с кнопкой под названием . Если вы хотите иметь дополнительную визуализацию <xref:System.Web.UI.WebControls.Button>сверх того, что было предоставлено, вы добавите код в пользовательский контроль, аналогичный следующему:  
  
```vb  
Public Sub MyPaint(ByVal sender as Object, e as PaintEventArgs) Handles _  
   MyButton.Paint  
   'Additional rendering code goes here  
End Sub  
```  
  
```csharp  
// Add the event handler to the button's Paint event.  
MyButton.Paint +=
   new System.Windows.Forms.PaintEventHandler (this.MyPaint);  
// Create the custom painting method.  
protected void MyPaint (object sender,
System.Windows.Forms.PaintEventArgs e)  
{  
   // Additional rendering code goes here.  
}  
```  
  
> [!NOTE]
> Некоторые элементы управления <xref:System.Windows.Forms.TextBox>Windows Forms, такие как, окрашены непосредственно Windows. В этих случаях <xref:System.Windows.Forms.Control.OnPaint%2A> метод никогда не вызывается, и, таким образом, приведенный выше пример никогда не будет вызываться.  
  
 При этом создается метод, который выполняется каждый раз при выполнении события `MyButton.Paint`, таким образом, добавляя дополнительное графическое представление для элемента управления. Обратите внимание, что это не блокирует выполнение `MyButton.OnPaint` и поэтому все операции рисования, обычно выполняемые кнопкой, по-прежнему будут выполняться наряду с настраиваемым рисованием. Дополнительные сведения о технологии GDI+ и настраиваемой отрисовке см. в разделе [Создание графических изображений с помощью GDI+](../advanced/how-to-create-graphics-objects-for-drawing.md). При необходимости получения уникального представления элемента управления оптимальным решением будет создание наследуемого элемента управления и написание для него собственного кода отрисовки. Дополнительные сведения см. в разделе [Элементы управления, разработанные пользователем](user-drawn-controls.md).  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.UserControl>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [Элементы управления, разработанные пользователем](user-drawn-controls.md)
- [Практическое руководство. Создание объектов Graphics для рисования](../advanced/how-to-create-graphics-objects-for-drawing.md)
- [Создание собственных элементов управления](varieties-of-custom-controls.md)
