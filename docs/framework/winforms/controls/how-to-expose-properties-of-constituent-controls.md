---
title: Как выполнить Обеспечение доступа к свойствам составных элементов управления
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- user controls [Windows Forms], exposing constituent controls
- controls [Windows Forms], constituent
- custom controls [Windows Forms], exposing properties
- constituent controls
ms.assetid: 5c1ec98b-aa48-4823-986e-4712551cfdf1
ms.openlocfilehash: f3ad37032ee2bb85f37a0eb754277cc9bc040a38
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54532166"
---
# <a name="how-to-expose-properties-of-constituent-controls"></a>Как выполнить Обеспечение доступа к свойствам составных элементов управления
Элементы управления, составляющих составной элемент управления, называются *составные элементы управления*. Эти элементы управления обычно объявляются частных и таким образом, не может использоваться разработчиком. Если вы хотите сделать доступными свойства этих элементов управления для последующих пользователей, их необходимо предоставить пользователю. Свойство составного элемента управления предоставляется путем создания свойства в пользовательский элемент управления и использования `get` и `set` методы доступа этого свойства для внесения изменений в закрытое свойство составляющего элемента управления.  
  
 Рассмотрим гипотетический пользовательский элемент управления, содержащий составную кнопку `MyButton`. В этом примере, когда пользователь запрашивает `ConstituentButtonBackColor` свойство, значение, хранящееся в <xref:System.Windows.Forms.Control.BackColor%2A> свойство `MyButton` доставляется. Когда пользователь назначает значение этого свойства, это значение автоматически передается <xref:System.Windows.Forms.Control.BackColor%2A> свойство `MyButton` и `set` код будет выполнен, изменения цвета `MyButton`.  
  
 Следующий пример показывает способ предоставления <xref:System.Windows.Forms.Control.BackColor%2A> составных кнопки:  
  
```vb  
Public Property ButtonColor() as System.Drawing.Color  
   Get  
      Return MyButton.BackColor  
   End Get  
   Set(Value as System.Drawing.Color)  
      MyButton.BackColor = Value  
   End Set  
End Property  
```  
  
```csharp  
public Color ButtonColor  
{  
   get  
   {  
      return(myButton.BackColor);  
   }  
   set  
   {  
      myButton.BackColor = value;  
   }  
}  
```  
  
### <a name="to-expose-a-property-of-a-constituent-control"></a>Чтобы предоставить свойство составного элемента управления  
  
1.  Создайте общедоступное свойство пользовательского элемента управления.  
  
2.  В `get` раздел свойства, написать код, который извлекает значение свойства, которому требуется предоставить доступ.  
  
3.  В `set` раздел свойства, написать код, который передает значение свойства, предоставленному свойству составляющего элемента управления.  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Forms.UserControl>
- [Свойства элементов управления Windows Forms](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)
- [Разновидности пользовательских элементов управления](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
