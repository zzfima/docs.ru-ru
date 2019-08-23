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
ms.openlocfilehash: 609fe4896a2b01b8a69ff8a3d0854c85ddbd6a26
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969099"
---
# <a name="defining-default-values-with-the-shouldserialize-and-reset-methods"></a>Определение значений по умолчанию с помощью методов ShouldSerialize и Reset
`ShouldSerialize`и `Reset` являются необязательными методами, которые можно указать для свойства, если свойство не имеет простого значения по умолчанию. Если свойство имеет простое значение по умолчанию, следует применить <xref:System.ComponentModel.DefaultValueAttribute> и предоставить конструктору класса атрибута значение по умолчанию. Любой из этих механизмов предоставляет следующие возможности в конструкторе:

- Свойство предоставляет визуальное обозначение в браузере свойств, если оно было изменено со значения по умолчанию.

- Пользователь может щелкнуть свойство правой кнопкой мыши и выбрать команду **сбросить** , чтобы восстановить свойство до значения по умолчанию.

- Конструктор создает более эффективный код.

    > [!NOTE]
    > Либо примените <xref:System.ComponentModel.DefaultValueAttribute> , либо `Reset`укажите методы `ShouldSerialize` *PropertyName* и *PropertyName* . Не используйте оба.

 Метод PropertyName присваивает свойству значение по умолчанию, как показано в следующем фрагменте кода. `Reset`

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
> Если свойство не `Reset` имеет метода, не помечено <xref:System.ComponentModel.DefaultValueAttribute>атрибутом и не имеет значения по умолчанию `Reset` в его объявлении, параметр для этого свойства будет отключен в контекстном меню окна **свойств** в окне конструктор Windows Forms в Visual Studio.

 Конструкторы, такие как Visual Studio `ShouldSerialize`, используют метод *PropertyName* , чтобы проверить, изменилось ли свойство со значения по умолчанию, и написать код в форме только в том случае, если свойство изменено, что обеспечивает более эффективное создание кода. Например:

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

 Ниже приведен полный пример кода.

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

 В этом случае, даже если значение закрытой переменной, к которой обращается `MyFont` свойство, `null`равно, браузер свойств не отображается `null`; вместо этого он отображает <xref:System.Windows.Forms.Control.Font%2A> свойство родителя, если нет `null`, значение по умолчанию <xref:System.Windows.Forms.Control.Font%2A> , определенное <xref:System.Windows.Forms.Control>в. Поэтому значение по умолчанию `MyFont` для не может быть просто задано <xref:System.ComponentModel.DefaultValueAttribute> и не может быть применено к этому свойству. Вместо этого для `Reset` свойства`MyFont` должны быть реализованы методы и.`ShouldSerialize`

## <a name="see-also"></a>См. также

- [Свойства элементов управления Windows Forms](properties-in-windows-forms-controls.md)
- [Определение свойства](defining-a-property-in-windows-forms-controls.md)
- [События изменения свойств](property-changed-events.md)
