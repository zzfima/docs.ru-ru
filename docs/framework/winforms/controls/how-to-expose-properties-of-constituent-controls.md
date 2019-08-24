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
# <a name="how-to-expose-properties-of-constituent-controls"></a><span data-ttu-id="69524-102">Практическое руководство. Обеспечение доступа к свойствам составных элементов управления</span><span class="sxs-lookup"><span data-stu-id="69524-102">How to: Expose Properties of Constituent Controls</span></span>
<span data-ttu-id="69524-103">Элементы управления, составляющие составной элемент управления, называются *составляющими элементами управления*.</span><span class="sxs-lookup"><span data-stu-id="69524-103">The controls that make up a composite control are called *constituent controls*.</span></span> <span data-ttu-id="69524-104">Эти элементы управления обычно объявляются частными, и поэтому разработчик не может получить к ним доступ.</span><span class="sxs-lookup"><span data-stu-id="69524-104">These controls are normally declared private, and thus cannot be accessed by the developer.</span></span> <span data-ttu-id="69524-105">Если вы хотите, чтобы свойства этих элементов управления были доступны для будущих пользователей, необходимо предоставить их пользователю.</span><span class="sxs-lookup"><span data-stu-id="69524-105">If you want to make properties of these controls available to future users, you must expose them to the user.</span></span> <span data-ttu-id="69524-106">Свойство составного элемента управления предоставляется путем создания свойства в пользовательском элементе управления и использования `get` методов доступа и `set` этого свойства для изменения закрытого свойства составляющего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="69524-106">A property of a constituent control is exposed by creating a property in the user control, and using the `get` and `set` accessors of that property to effect the change in the private property of the constituent control.</span></span>

 <span data-ttu-id="69524-107">Рассмотрим гипотетический пользовательский элемент управления с составной кнопкой `MyButton`с именем.</span><span class="sxs-lookup"><span data-stu-id="69524-107">Consider a hypothetical user control with a constituent button named `MyButton`.</span></span> <span data-ttu-id="69524-108">В этом примере, когда пользователь запрашивает `ConstituentButtonBackColor` свойство, значение, хранящееся <xref:System.Windows.Forms.Control.BackColor%2A> в свойстве `MyButton` , доставляется.</span><span class="sxs-lookup"><span data-stu-id="69524-108">In this example, when the user requests the `ConstituentButtonBackColor` property, the value stored in the <xref:System.Windows.Forms.Control.BackColor%2A> property of `MyButton` is delivered.</span></span> <span data-ttu-id="69524-109">Когда пользователь присваивает значение <xref:System.Windows.Forms.Control.BackColor%2A> этому свойству, это значение автоматически передается свойству объекта `MyButton` , и `set` `MyButton`код будет выполнен, изменив цвет.</span><span class="sxs-lookup"><span data-stu-id="69524-109">When the user assigns a value to this property, that value is automatically passed to the <xref:System.Windows.Forms.Control.BackColor%2A> property of `MyButton` and the `set` code will execute, changing the color of `MyButton`.</span></span>

 <span data-ttu-id="69524-110">В следующем примере показано, <xref:System.Windows.Forms.Control.BackColor%2A> как предоставить свойство составной кнопки:</span><span class="sxs-lookup"><span data-stu-id="69524-110">The following example shows how to expose the <xref:System.Windows.Forms.Control.BackColor%2A> property of the constituent button:</span></span>

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

### <a name="to-expose-a-property-of-a-constituent-control"></a><span data-ttu-id="69524-111">Предоставление свойства составного элемента управления</span><span class="sxs-lookup"><span data-stu-id="69524-111">To expose a property of a constituent control</span></span>

1. <span data-ttu-id="69524-112">Создайте открытое свойство для пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="69524-112">Create a public property for your user control.</span></span>

2. <span data-ttu-id="69524-113">`get` В разделе Свойства напишите код, который получает значение свойства, которое необходимо предоставить.</span><span class="sxs-lookup"><span data-stu-id="69524-113">In the `get` section of the property, write code that retrieves the value of the property you want to expose.</span></span>

3. <span data-ttu-id="69524-114">`set` В разделе Свойства напишите код, который передает значение свойства в предоставляемое свойство составляющего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="69524-114">In the `set` section of the property, write code that passes the value of the property to the exposed property of the constituent control.</span></span>

## <a name="see-also"></a><span data-ttu-id="69524-115">См. также</span><span class="sxs-lookup"><span data-stu-id="69524-115">See also</span></span>

- <xref:System.Windows.Forms.UserControl>
- [<span data-ttu-id="69524-116">Свойства элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="69524-116">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)
- [<span data-ttu-id="69524-117">Разновидности пользовательских элементов управления</span><span class="sxs-lookup"><span data-stu-id="69524-117">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
