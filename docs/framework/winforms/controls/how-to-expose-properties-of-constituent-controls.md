---
title: "Практическое руководство. Обеспечение доступа к свойствам составных элементов управления | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "составляющие элементы управления"
  - "элементы управления [Windows Forms], составляющее"
  - "пользовательские элементы управления [Windows Forms], предоставление доступа к свойствам"
  - "пользовательские элементы управления [Windows Forms], предоставление доступа к составным элементам управления"
ms.assetid: 5c1ec98b-aa48-4823-986e-4712551cfdf1
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Обеспечение доступа к свойствам составных элементов управления
Элементы управления, входящие в состав составных элементов управления, называются *составляющими элементами управления*.  Как правило, такие элементы управления объявляются как закрытые компоненты и не доступны разработчику.  При необходимости обеспечить пользователям доступ к свойствам этих элементов управления, следует предоставить их пользователям.  Свойство составляющего элемента управления предоставляется путем создания свойства в пользовательском элементе управления и использования `get` и `set` средств доступа этого свойства для внесения изменений в закрытое свойство составляющего элемента управления..  
  
 Рассмотрим гипотетический пользовательский элемент управления, содержащий составную кнопку `MyButton`.  В этом примере, когда пользователь обращается к свойству <xref:System.Windows.Forms.Control.BackColor%2A>, он получает значение, хранящееся в свойстве `ConstituentButtonBackColor` компонента `MyButton`.  Если этому свойству присваивается некоторое значение, это значение автоматически передается свойству <xref:System.Windows.Forms.Control.BackColor%2A> компонента `MyButton` и выполняется метод `set`, который изменяет цвет кнопки `MyButton`.  
  
 Следующий пример показывает, как предоставить свойство <xref:System.Windows.Forms.Control.BackColor%2A> составляющей кнопки.  
  
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
  
### Чтобы предоставить свойство составляющего элемента управления, выполните следующие действия.  
  
1.  Создайте открытое свойство пользовательского элемента управления.  
  
2.  В раздел `get` этого свойства следует записать код, загружающий значение свойства, которое необходимо предоставить.  
  
3.  В раздел `set` этого свойства следует записать код, передающий значение свойства, предоставленному свойству составляющего элемента управления.  
  
## См. также  
 <xref:System.Windows.Forms.UserControl>   
 [Свойства элементов управления Windows Forms](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)   
 [Создание собственных элементов управления](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)