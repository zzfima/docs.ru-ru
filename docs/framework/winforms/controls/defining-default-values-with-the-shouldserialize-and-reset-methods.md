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
# <a name="defining-default-values-with-the-shouldserialize-and-reset-methods"></a><span data-ttu-id="71db2-102">Определение значений по умолчанию с помощью методов ShouldSerialize и Reset</span><span class="sxs-lookup"><span data-stu-id="71db2-102">Defining Default Values with the ShouldSerialize and Reset Methods</span></span>
<span data-ttu-id="71db2-103">`ShouldSerialize` и `Reset` являются необязательными методами, которые можно указать для свойства, если свойство не имеет простого значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="71db2-103">`ShouldSerialize` and `Reset` are optional methods that you can provide for a property, if the property does not a have simple default value.</span></span> <span data-ttu-id="71db2-104">Если свойство имеет простое значение по умолчанию, следует применить <xref:System.ComponentModel.DefaultValueAttribute> и указать вместо него значение по умолчанию для конструктора класса атрибута.</span><span class="sxs-lookup"><span data-stu-id="71db2-104">If the property has a simple default value, you should apply the <xref:System.ComponentModel.DefaultValueAttribute> and supply the default value to the attribute class constructor instead.</span></span> <span data-ttu-id="71db2-105">Любой из этих механизмов предоставляет следующие возможности в конструкторе:</span><span class="sxs-lookup"><span data-stu-id="71db2-105">Either of these mechanisms enables the following features in the designer:</span></span>

- <span data-ttu-id="71db2-106">Свойство предоставляет визуальное обозначение в браузере свойств, если оно было изменено со значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="71db2-106">The property provides visual indication in the property browser if it has been modified from its default value.</span></span>

- <span data-ttu-id="71db2-107">Пользователь может щелкнуть свойство правой кнопкой мыши и выбрать команду **сбросить** , чтобы восстановить свойство до значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="71db2-107">The user can right-click on the property and choose **Reset** to restore the property to its default value.</span></span>

- <span data-ttu-id="71db2-108">Конструктор создает более эффективный код.</span><span class="sxs-lookup"><span data-stu-id="71db2-108">The designer generates more efficient code.</span></span>

    > [!NOTE]
    > <span data-ttu-id="71db2-109">Либо примените <xref:System.ComponentModel.DefaultValueAttribute>, либо укажите методы `Reset`*PropertyName* и `ShouldSerialize`*PropertyName* .</span><span class="sxs-lookup"><span data-stu-id="71db2-109">Either apply the <xref:System.ComponentModel.DefaultValueAttribute> or provide `Reset`*PropertyName* and `ShouldSerialize`*PropertyName* methods.</span></span> <span data-ttu-id="71db2-110">Не используйте оба.</span><span class="sxs-lookup"><span data-stu-id="71db2-110">Do not use both.</span></span>

 <span data-ttu-id="71db2-111">Метод `Reset`*PropertyName* присваивает свойству значение по умолчанию, как показано в следующем фрагменте кода.</span><span class="sxs-lookup"><span data-stu-id="71db2-111">The `Reset`*PropertyName* method sets a property to its default value, as shown in the following code fragment.</span></span>

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
> <span data-ttu-id="71db2-112">Если свойство не имеет метода `Reset`, не помечено как <xref:System.ComponentModel.DefaultValueAttribute>и не имеет значения по умолчанию, предоставленного в его объявлении, параметр `Reset` для этого свойства отключается в контекстном меню окна **свойств** конструктор Windows Forms в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="71db2-112">If a property does not have a `Reset` method, is not marked with a <xref:System.ComponentModel.DefaultValueAttribute>, and does not have a default value supplied in its declaration, the `Reset` option for that property is disabled in the shortcut menu of the **Properties** window of the Windows Forms Designer in Visual Studio.</span></span>

 <span data-ttu-id="71db2-113">Конструкторы, такие как Visual Studio, используют метод `ShouldSerialize`*PropertyName* , чтобы проверить, изменилось ли свойство со значения по умолчанию, и написать код в форме только в том случае, если свойство изменено, что позволяет более эффективно создавать код.</span><span class="sxs-lookup"><span data-stu-id="71db2-113">Designers such as Visual Studio use the `ShouldSerialize`*PropertyName* method to check whether a property has changed from its default value and write code into the form only if a property is changed, thus allowing for more efficient code generation.</span></span> <span data-ttu-id="71db2-114">Пример.</span><span class="sxs-lookup"><span data-stu-id="71db2-114">For example:</span></span>

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

 <span data-ttu-id="71db2-115">Ниже приведен полный пример кода.</span><span class="sxs-lookup"><span data-stu-id="71db2-115">A complete code example follows.</span></span>

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

 <span data-ttu-id="71db2-116">В этом случае, даже если значение закрытой переменной, к которой обращается свойство `MyFont`, равно `null`, браузер свойств не отображает `null`. Вместо этого он отображает свойство <xref:System.Windows.Forms.Control.Font%2A> родительского элемента, если оно не `null`, или значение <xref:System.Windows.Forms.Control.Font%2A> по умолчанию, определенное в <xref:System.Windows.Forms.Control>.</span><span class="sxs-lookup"><span data-stu-id="71db2-116">In this case, even when the value of the private variable accessed by the `MyFont` property is `null`, the property browser does not display `null`; instead, it displays the <xref:System.Windows.Forms.Control.Font%2A> property of the parent, if it is not `null`, or the default <xref:System.Windows.Forms.Control.Font%2A> value defined in <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="71db2-117">Поэтому значение по умолчанию для `MyFont` не может быть просто задано, а <xref:System.ComponentModel.DefaultValueAttribute> не может быть применено к этому свойству.</span><span class="sxs-lookup"><span data-stu-id="71db2-117">Thus the default value for `MyFont` cannot be simply set, and a <xref:System.ComponentModel.DefaultValueAttribute> cannot be applied to this property.</span></span> <span data-ttu-id="71db2-118">Вместо этого методы `ShouldSerialize` и `Reset` должны быть реализованы для свойства `MyFont`.</span><span class="sxs-lookup"><span data-stu-id="71db2-118">Instead, the `ShouldSerialize` and `Reset` methods must be implemented for the `MyFont` property.</span></span>

## <a name="see-also"></a><span data-ttu-id="71db2-119">См. также</span><span class="sxs-lookup"><span data-stu-id="71db2-119">See also</span></span>

- [<span data-ttu-id="71db2-120">Свойства элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="71db2-120">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)
- [<span data-ttu-id="71db2-121">Определение свойства</span><span class="sxs-lookup"><span data-stu-id="71db2-121">Defining a Property</span></span>](defining-a-property-in-windows-forms-controls.md)
- [<span data-ttu-id="71db2-122">События изменения свойств</span><span class="sxs-lookup"><span data-stu-id="71db2-122">Property-Changed Events</span></span>](property-changed-events.md)
