---
title: Практическое руководство. Обеспечение доступа к свойствам составных элементов управления
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
ms.openlocfilehash: f006e42771a5ecc71f6a508fd78d0e2dd8f2d2f2
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015882"
---
# <a name="how-to-expose-properties-of-constituent-controls"></a>Практическое руководство. Обеспечение доступа к свойствам составных элементов управления
Элементы управления, составляющие составной элемент управления, называются *составляющими элементами управления*. Эти элементы управления обычно объявляются частными, и поэтому разработчик не может получить к ним доступ. Если вы хотите, чтобы свойства этих элементов управления были доступны для будущих пользователей, необходимо предоставить их пользователю. Свойство составного элемента управления предоставляется путем создания свойства в пользовательском элементе управления и использования `get` методов доступа и `set` этого свойства для изменения закрытого свойства составляющего элемента управления.

 Рассмотрим гипотетический пользовательский элемент управления с составной кнопкой `MyButton`с именем. В этом примере, когда пользователь запрашивает `ConstituentButtonBackColor` свойство, значение, хранящееся <xref:System.Windows.Forms.Control.BackColor%2A> в свойстве `MyButton` , доставляется. Когда пользователь присваивает значение <xref:System.Windows.Forms.Control.BackColor%2A> этому свойству, это значение автоматически передается свойству объекта `MyButton` , и `set` `MyButton`код будет выполнен, изменив цвет.

 В следующем примере показано, <xref:System.Windows.Forms.Control.BackColor%2A> как предоставить свойство составной кнопки:

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

### <a name="to-expose-a-property-of-a-constituent-control"></a>Предоставление свойства составного элемента управления

1. Создайте открытое свойство для пользовательского элемента управления.

2. `get` В разделе Свойства напишите код, который получает значение свойства, которое необходимо предоставить.

3. `set` В разделе Свойства напишите код, который передает значение свойства в предоставляемое свойство составляющего элемента управления.

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.UserControl>
- [Свойства элементов управления Windows Forms](properties-in-windows-forms-controls.md)
- [Разновидности пользовательских элементов управления](varieties-of-custom-controls.md)
