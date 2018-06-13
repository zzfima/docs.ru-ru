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
ms.openlocfilehash: 6fb708b81089b4fcd3678b35d1bcf7da2244c6d1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525566"
---
# <a name="constituent-controls"></a>Составные элементы управления
Элементы управления, составляющие пользовательский элемент управления, или *составные элементы управления*, как они иначе называются, обеспечивают относительную гибкость, когда речь идет об отрисовке пользовательской графики. Все элементы управления Windows Forms производят отрисовку, используя собственный <xref:System.Windows.Forms.Control.OnPaint%2A> метод. Так как этот метод защищен, он недоступен для разработчика и поэтому не может быть заблокирован при рисовании элемента управления. Это, однако, не означает, что нельзя добавить код, влияющий на внешний вид составных элементов управления. Дополнительную отрисовку можно выполнить путем добавления обработчика событий. Предположим, что разрабатывается <xref:System.Windows.Forms.UserControl> с помощью кнопки с именем `MyButton`. Если вы хотели бы иметь дополнительной отрисовки, помимо выполняемой классом <xref:System.Web.UI.WebControls.Button>, можно добавить код в пользовательский элемент управления следующим образом:  
  
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
>  Элементы управления некоторые Windows Forms, такие как <xref:System.Windows.Forms.TextBox>, рисуются непосредственно операционной системой Windows. В таких случаях <xref:System.Windows.Forms.Control.OnPaint%2A> никогда не вызывается метод, и таким образом, приведенный выше пример никогда не будет вызываться.  
  
 При этом создается метод, который выполняется каждый раз при выполнении события `MyButton.Paint`, таким образом, добавляя дополнительное графическое представление для элемента управления. Обратите внимание, что это не блокирует выполнение `MyButton.OnPaint` и поэтому все операции рисования, обычно выполняемые кнопкой, по-прежнему будут выполняться наряду с настраиваемым рисованием. Дополнительные сведения о технологии GDI+ и настраиваемой отрисовке см. в разделе [Создание графических изображений с помощью GDI+](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md). При необходимости получения уникального представления элемента управления оптимальным решением будет создание наследуемого элемента управления и написание для него собственного кода отрисовки. Дополнительные сведения см. в разделе [Элементы управления, разработанные пользователем](../../../../docs/framework/winforms/controls/user-drawn-controls.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.UserControl>  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 [Элементы управления, разработанные пользователем](../../../../docs/framework/winforms/controls/user-drawn-controls.md)  
 [Практическое руководство. Создание графических объектов для рисования](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [Разновидности пользовательских элементов управления](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
