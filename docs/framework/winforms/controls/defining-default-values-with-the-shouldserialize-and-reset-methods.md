---
title: "Определение значений по умолчанию с помощью методов ShouldSerialize и Reset | Microsoft Docs"
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
  - "пользовательские элементы управления [Windows Forms], методы свойств"
  - "Reset - метод"
  - "ShouldPersist - метод"
ms.assetid: 7b6c5e00-3771-46b4-9142-5a80d5864a5e
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Определение значений по умолчанию с помощью методов ShouldSerialize и Reset
`ShouldSerialize` и `Reset` — необязательные методы, которые могут использоваться свойством, если оно не имеет простого значения по умолчанию.  Если свойство имеет простое значение по умолчанию, следует воспользоваться атрибутом <xref:System.ComponentModel.DefaultValueAttribute> и применить значение по умолчанию для конструктора класса атрибутов.  Любой из этих механизмов позволяет реализовать следующие возможности конструктора.  
  
-   При изменении значения свойства по умолчанию в обозревателе свойств появляется соответствующая визуальная индикация.  
  
-   Пользователь может восстановить значение свойства по умолчанию, щелкнув его правой кнопкой мыши и выбрав **Сброс**.  
  
-   Конструктор создает более эффективный код.  
  
    > [!NOTE]
    >  Применение атрибута <xref:System.ComponentModel.DefaultValueAttribute> либо добавление методов `Reset`*имяСвойства* и `ShouldSerialize`*имяСвойства*.  Не используйте их вместе.  
  
 Метод `Reset`*имяСвойства* восстанавливает значение свойства по умолчанию, как показано в следующем фрагменте кода.  
  
```vb  
Public Sub ResetMyFont()  
   MyFont = Nothing  
End Sub  
```  
  
```csharp  
public void ResetMyFont() {  
   MyFont = null;  
}  
```  
  
> [!NOTE]
>  Если свойство не имеет метода `Reset`, не помечено атрибутом <xref:System.ComponentModel.DefaultValueAttribute> и не имеет значения по умолчанию, указанного в его объявлении, параметр `Reset` для этого свойства отключается в контекстном меню окна **Свойства** в конструкторе Windows Forms в [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].  
  
 Конструкторы, такие как [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], с помощью метода `ShouldSerialize`*имяСвойства* проверяют, было ли изменено значение свойства по умолчанию, и записывают код в форму только в случае положительного ответа. Таким образом обеспечивается более эффективное создание кода.  Примеры.  
  
```vb  
'Returns true if the font has changed; otherwise, returns false.  
' The designer writes code to the form only if true is returned.  
Public Function ShouldSerializeMyFont() As Boolean  
   Return Not (thefont Is Nothing)  
End Function  
```  
  
```csharp  
// Returns true if the font has changed; otherwise, returns false.  
// The designer writes code to the form only if true is returned.  
public bool ShouldSerializeMyFont() {  
   return thefont != null;  
}  
```  
  
 Пример готового кода выглядит следующим образом.  
  
```vb  
Option Explicit  
Option Strict  
  
Imports System  
Imports System.Windows.Forms  
Imports System.Drawing  
  
Public Class MyControl  
   Inherits Control  
  
   ' Declare an instance of the Font class  
   ' and set its default value to Nothing.  
   Private thefont As Font = Nothing  
  
   ' The MyFont property.   
   Public Property MyFont() As Font  
      ' Note that the Font property never  
      ' returns null.  
      Get  
         If Not (thefont Is Nothing) Then  
            Return thefont  
         End If  
         If Not (Parent Is Nothing) Then  
            Return Parent.Font  
         End If  
         Return Control.DefaultFont  
      End Get  
      Set  
         thefont = value  
      End Set  
   End Property  
  
   Public Function ShouldSerializeMyFont() As Boolean  
      Return Not (thefont Is Nothing)  
   End Function  
  
   Public Sub ResetMyFont()  
      MyFont = Nothing  
   End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.Windows.Forms;  
using System.Drawing;  
  
public class MyControl : Control {  
   // Declare an instance of the Font class  
   // and set its default value to null.  
   private Font thefont = null;  
  
   // The MyFont property.      
   public Font MyFont {  
      // Note that the MyFont property never  
      // returns null.  
      get {  
         if (thefont != null) return thefont;  
         if (Parent != null) return Parent.Font;  
         return Control.DefaultFont;  
      }  
      set {  
         thefont = value;  
      }  
   }  
  
   public bool ShouldSerializeMyFont() {  
      return thefont != null;  
   }  
  
   public void ResetMyFont() {  
      MyFont = null;  
   }  
}  
```  
  
 В этом случае, даже если закрытая переменная, полученная при обращении к свойству `MyFont`, имеет значение `null`, в обозревателе это значение `null` не отображается, а отображается свойство <xref:System.Windows.Forms.Control.Font%2A> родительского элемента, если оно отлично от значения `null`, либо значение <xref:System.Windows.Forms.Control.Font%2A> по умолчанию, определенное в <xref:System.Windows.Forms.Control>.  Таким образом, значение по умолчанию для свойства `MyFont` нельзя просто установить; также к нему нельзя применить атрибут <xref:System.ComponentModel.DefaultValueAttribute>.  Вместо этого для свойства `MyFont` должны быть реализованы методы `ShouldSerialize` и `Reset`.  
  
## См. также  
 [Свойства элементов управления Windows Forms](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)   
 [Определение свойства](../../../../docs/framework/winforms/controls/defining-a-property-in-windows-forms-controls.md)   
 [События изменения свойств](../../../../docs/framework/winforms/controls/property-changed-events.md)