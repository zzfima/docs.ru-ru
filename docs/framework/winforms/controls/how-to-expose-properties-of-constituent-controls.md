---
title: "Практическое руководство. Обеспечение доступа к свойствам составных элементов управления"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- user controls [Windows Forms], exposing constituent controls
- controls [Windows Forms], constituent
- custom controls [Windows Forms], exposing properties
- constituent controls
ms.assetid: 5c1ec98b-aa48-4823-986e-4712551cfdf1
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a970864a406f98477fa3e09bdefcf959d2078fe6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-expose-properties-of-constituent-controls"></a>Практическое руководство. Обеспечение доступа к свойствам составных элементов управления
Элементы управления, входящие в состав составного элемента управления, называются *составляющие элементы управления*. Эти элементы управления обычно являются объявленным как закрытый и не доступны разработчиком. Если вы хотите сделать доступными свойства этих элементов управления для последующих пользователей, их необходимо предоставить пользователю. Свойство составляющего элемента управления предоставляется путем создания свойства в пользовательском элементе управления и с помощью `get` и `set` методы доступа этого свойства для внесения изменений в закрытое свойство составляющего элемента управления.  
  
 Рассмотрим гипотетический пользовательский элемент управления, содержащий составную кнопку `MyButton`. В этом примере, когда пользователь запрашивает `ConstituentButtonBackColor` свойство, значение, хранящееся в <xref:System.Windows.Forms.Control.BackColor%2A> свойство `MyButton` доставки. Когда пользователь присваивает значение этого свойства, это значение автоматически передается <xref:System.Windows.Forms.Control.BackColor%2A> свойство `MyButton` и `set` код будет выполнен, изменения цвета `MyButton`.  
  
 В следующем примере показан способ предоставления <xref:System.Windows.Forms.Control.BackColor%2A> свойства кнопки, составляющих:  
  
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
  
1.  Создайте открытое свойство для пользовательского элемента управления.  
  
2.  В `get` разделе Свойства написать код, который извлекает значение свойства, которому требуется предоставить доступ.  
  
3.  В `set` разделе Свойства написать код, который передает значение свойства, предоставленному свойству составляющего элемента управления.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.UserControl>  
 [Свойства элементов управления Windows Forms](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)  
 [Разновидности пользовательских элементов управления](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
