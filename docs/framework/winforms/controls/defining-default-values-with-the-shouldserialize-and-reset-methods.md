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
ms.openlocfilehash: 11181bacdb919693ffc82c48c061357463a6343b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74336753"
---
# <a name="defining-default-values-with-the-shouldserialize-and-reset-methods"></a>Определение значений по умолчанию с помощью методов ShouldSerialize и Reset
`ShouldSerialize` и `Reset` являются необязательными методами, которые можно указать для свойства, если свойство не имеет простого значения по умолчанию. Если свойство имеет простое значение по умолчанию, следует применить <xref:System.ComponentModel.DefaultValueAttribute> и указать вместо него значение по умолчанию для конструктора класса атрибута. Любой из этих механизмов предоставляет следующие возможности в конструкторе:

- Свойство предоставляет визуальное обозначение в браузере свойств, если оно было изменено со значения по умолчанию.

- Пользователь может щелкнуть свойство правой кнопкой мыши и выбрать команду **сбросить** , чтобы восстановить свойство до значения по умолчанию.

- Конструктор создает более эффективный код.

    > [!NOTE]
    > Либо примените <xref:System.ComponentModel.DefaultValueAttribute>, либо укажите методы `Reset`*PropertyName* и `ShouldSerialize`*PropertyName* . Не используйте оба.

 Метод `Reset`*PropertyName* присваивает свойству значение по умолчанию, как показано в следующем фрагменте кода.

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
> Если свойство не имеет метода `Reset`, не помечено как <xref:System.ComponentModel.DefaultValueAttribute>и не имеет значения по умолчанию, предоставленного в его объявлении, параметр `Reset` для этого свойства отключается в контекстном меню окна **свойств** конструктор Windows Forms в Visual Studio.

 Конструкторы, такие как Visual Studio, используют метод `ShouldSerialize`*PropertyName* , чтобы проверить, изменилось ли свойство со значения по умолчанию, и написать код в форме только в том случае, если свойство изменено, что позволяет более эффективно создавать код. Пример.

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

Imports System.Drawing
Imports System.Windows.Forms

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
using System.Drawing;
using System.Windows.Forms;

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

 В этом случае, даже если значение закрытой переменной, к которой обращается свойство `MyFont`, равно `null`, браузер свойств не отображает `null`. Вместо этого он отображает свойство <xref:System.Windows.Forms.Control.Font%2A> родительского элемента, если оно не `null`, или значение <xref:System.Windows.Forms.Control.Font%2A> по умолчанию, определенное в <xref:System.Windows.Forms.Control>. Поэтому значение по умолчанию для `MyFont` не может быть просто задано, а <xref:System.ComponentModel.DefaultValueAttribute> не может быть применено к этому свойству. Вместо этого методы `ShouldSerialize` и `Reset` должны быть реализованы для свойства `MyFont`.

## <a name="see-also"></a>См. также

- [Свойства элементов управления Windows Forms](properties-in-windows-forms-controls.md)
- [Определение свойства](defining-a-property-in-windows-forms-controls.md)
- [События изменения свойств](property-changed-events.md)
