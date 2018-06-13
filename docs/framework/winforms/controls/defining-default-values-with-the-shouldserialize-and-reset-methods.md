---
title: Определение значений по умолчанию с помощью методов ShouldSerialize и Reset
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property methods
- ShouldPersist method
ms.assetid: 7b6c5e00-3771-46b4-9142-5a80d5864a5e
ms.openlocfilehash: 8d7645e8de5edee711c30bbe7edde8ba7b5b1dab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529796"
---
# <a name="defining-default-values-with-the-shouldserialize-and-reset-methods"></a>Определение значений по умолчанию с помощью методов ShouldSerialize и Reset
`ShouldSerialize` и `Reset` — необязательные методы, которые могут использоваться для свойства, в том случае, если свойство не имеет значения по умолчанию. Если свойство имеет значение по умолчанию, необходимо применить <xref:System.ComponentModel.DefaultValueAttribute> и вместо этого укажите значение по умолчанию для конструктора класса атрибутов. Любой из этих механизмов обеспечивает следующие возможности в конструкторе:  
  
-   Свойство позволяет получить визуальное представление в браузере свойств, если он был изменен со значения по умолчанию.  
  
-   Пользователь может щелкнуть свойство и выберите **Сброс** восстановить значение по умолчанию значение свойства.  
  
-   Конструктор создает более эффективный код.  
  
    > [!NOTE]
    >  Либо применить <xref:System.ComponentModel.DefaultValueAttribute> или предоставить `Reset` *PropertyName* и `ShouldSerialize` *PropertyName* методы. Не используйте их вместе.  
  
 `Reset` *PropertyName* метод задает свойство к значению по умолчанию, как показано в следующем фрагменте кода.  
  
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
>  Если свойство не имеет `Reset` метод, не помеченный <xref:System.ComponentModel.DefaultValueAttribute>и не имеет значения по умолчанию, указанного в его объявлении `Reset` для этого свойства отключен в контекстном меню **свойства** окно конструктора Windows Forms в Visual Studio.  
  
 Конструкторы, такой как Visual Studio используют `ShouldSerialize` *PropertyName* метода проверьте, изменено ли значение свойства по умолчанию, и писать код в форме, только если свойство изменяется, что позволяет более эффективный код поколение. Пример:  
  
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
  
 Полный пример кода ниже.  
  
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
  
 В этом случае даже в том случае, если значение переменной закрытого обращается к `MyFont` свойство `null`, не отображается в обозревателе свойств `null`; вместо этого отображается <xref:System.Windows.Forms.Control.Font%2A> свойство родительского элемента, если он не `null`, или значение по умолчанию <xref:System.Windows.Forms.Control.Font%2A> значения, определенного в <xref:System.Windows.Forms.Control>. Таким образом, значение по умолчанию для `MyFont` нельзя просто установить и <xref:System.ComponentModel.DefaultValueAttribute> не может применяться к этому свойству. Вместо этого `ShouldSerialize` и `Reset` методы должны быть реализованы для `MyFont` свойства.  
  
## <a name="see-also"></a>См. также  
 [Свойства элементов управления Windows Forms](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)  
 [Определение свойства](../../../../docs/framework/winforms/controls/defining-a-property-in-windows-forms-controls.md)  
 [События изменения свойств](../../../../docs/framework/winforms/controls/property-changed-events.md)
