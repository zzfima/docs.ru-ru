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
# <a name="defining-default-values-with-the-shouldserialize-and-reset-methods"></a><span data-ttu-id="96e9c-102">Определение значений по умолчанию с помощью методов ShouldSerialize и Reset</span><span class="sxs-lookup"><span data-stu-id="96e9c-102">Defining Default Values with the ShouldSerialize and Reset Methods</span></span>
<span data-ttu-id="96e9c-103">`ShouldSerialize`и `Reset` являются необязательными методами, которые можно указать для свойства, если свойство не имеет простого значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="96e9c-103">`ShouldSerialize` and `Reset` are optional methods that you can provide for a property, if the property does not a have simple default value.</span></span> <span data-ttu-id="96e9c-104">Если свойство имеет простое значение по умолчанию, следует применить <xref:System.ComponentModel.DefaultValueAttribute> и предоставить конструктору класса атрибута значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="96e9c-104">If the property has a simple default value, you should apply the <xref:System.ComponentModel.DefaultValueAttribute> and supply the default value to the attribute class constructor instead.</span></span> <span data-ttu-id="96e9c-105">Любой из этих механизмов предоставляет следующие возможности в конструкторе:</span><span class="sxs-lookup"><span data-stu-id="96e9c-105">Either of these mechanisms enables the following features in the designer:</span></span>

- <span data-ttu-id="96e9c-106">Свойство предоставляет визуальное обозначение в браузере свойств, если оно было изменено со значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="96e9c-106">The property provides visual indication in the property browser if it has been modified from its default value.</span></span>

- <span data-ttu-id="96e9c-107">Пользователь может щелкнуть свойство правой кнопкой мыши и выбрать команду **сбросить** , чтобы восстановить свойство до значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="96e9c-107">The user can right-click on the property and choose **Reset** to restore the property to its default value.</span></span>

- <span data-ttu-id="96e9c-108">Конструктор создает более эффективный код.</span><span class="sxs-lookup"><span data-stu-id="96e9c-108">The designer generates more efficient code.</span></span>

    > [!NOTE]
    > <span data-ttu-id="96e9c-109">Либо примените <xref:System.ComponentModel.DefaultValueAttribute> , либо `Reset`укажите методы `ShouldSerialize` *PropertyName* и *PropertyName* .</span><span class="sxs-lookup"><span data-stu-id="96e9c-109">Either apply the <xref:System.ComponentModel.DefaultValueAttribute> or provide `Reset`*PropertyName* and `ShouldSerialize`*PropertyName* methods.</span></span> <span data-ttu-id="96e9c-110">Не используйте оба.</span><span class="sxs-lookup"><span data-stu-id="96e9c-110">Do not use both.</span></span>

 <span data-ttu-id="96e9c-111">Метод PropertyName присваивает свойству значение по умолчанию, как показано в следующем фрагменте кода. `Reset`</span><span class="sxs-lookup"><span data-stu-id="96e9c-111">The `Reset`*PropertyName* method sets a property to its default value, as shown in the following code fragment.</span></span>

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
> <span data-ttu-id="96e9c-112">Если свойство не `Reset` имеет метода, не помечено <xref:System.ComponentModel.DefaultValueAttribute>атрибутом и не имеет значения по умолчанию `Reset` в его объявлении, параметр для этого свойства будет отключен в контекстном меню окна **свойств** в окне конструктор Windows Forms в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="96e9c-112">If a property does not have a `Reset` method, is not marked with a <xref:System.ComponentModel.DefaultValueAttribute>, and does not have a default value supplied in its declaration, the `Reset` option for that property is disabled in the shortcut menu of the **Properties** window of the Windows Forms Designer in Visual Studio.</span></span>

 <span data-ttu-id="96e9c-113">Конструкторы, такие как Visual Studio `ShouldSerialize`, используют метод *PropertyName* , чтобы проверить, изменилось ли свойство со значения по умолчанию, и написать код в форме только в том случае, если свойство изменено, что обеспечивает более эффективное создание кода.</span><span class="sxs-lookup"><span data-stu-id="96e9c-113">Designers such as Visual Studio use the `ShouldSerialize`*PropertyName* method to check whether a property has changed from its default value and write code into the form only if a property is changed, thus allowing for more efficient code generation.</span></span> <span data-ttu-id="96e9c-114">Например:</span><span class="sxs-lookup"><span data-stu-id="96e9c-114">For example:</span></span>

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

 <span data-ttu-id="96e9c-115">Ниже приведен полный пример кода.</span><span class="sxs-lookup"><span data-stu-id="96e9c-115">A complete code example follows.</span></span>

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

 <span data-ttu-id="96e9c-116">В этом случае, даже если значение закрытой переменной, к которой обращается `MyFont` свойство, `null`равно, браузер свойств не отображается `null`; вместо этого он отображает <xref:System.Windows.Forms.Control.Font%2A> свойство родителя, если нет `null`, значение по умолчанию <xref:System.Windows.Forms.Control.Font%2A> , определенное <xref:System.Windows.Forms.Control>в.</span><span class="sxs-lookup"><span data-stu-id="96e9c-116">In this case, even when the value of the private variable accessed by the `MyFont` property is `null`, the property browser does not display `null`; instead, it displays the <xref:System.Windows.Forms.Control.Font%2A> property of the parent, if it is not `null`, or the default <xref:System.Windows.Forms.Control.Font%2A> value defined in <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="96e9c-117">Поэтому значение по умолчанию `MyFont` для не может быть просто задано <xref:System.ComponentModel.DefaultValueAttribute> и не может быть применено к этому свойству.</span><span class="sxs-lookup"><span data-stu-id="96e9c-117">Thus the default value for `MyFont` cannot be simply set, and a <xref:System.ComponentModel.DefaultValueAttribute> cannot be applied to this property.</span></span> <span data-ttu-id="96e9c-118">Вместо этого для `Reset` свойства`MyFont` должны быть реализованы методы и.`ShouldSerialize`</span><span class="sxs-lookup"><span data-stu-id="96e9c-118">Instead, the `ShouldSerialize` and `Reset` methods must be implemented for the `MyFont` property.</span></span>

## <a name="see-also"></a><span data-ttu-id="96e9c-119">См. также</span><span class="sxs-lookup"><span data-stu-id="96e9c-119">See also</span></span>

- [<span data-ttu-id="96e9c-120">Свойства элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="96e9c-120">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)
- [<span data-ttu-id="96e9c-121">Определение свойства</span><span class="sxs-lookup"><span data-stu-id="96e9c-121">Defining a Property</span></span>](defining-a-property-in-windows-forms-controls.md)
- [<span data-ttu-id="96e9c-122">События изменения свойств</span><span class="sxs-lookup"><span data-stu-id="96e9c-122">Property-Changed Events</span></span>](property-changed-events.md)
