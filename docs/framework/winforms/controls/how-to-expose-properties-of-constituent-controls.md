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
ms.openlocfilehash: eb85cb77c28ad443fb6837a5305a080c450220f5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-expose-properties-of-constituent-controls"></a><span data-ttu-id="3c194-102">Практическое руководство. Обеспечение доступа к свойствам составных элементов управления</span><span class="sxs-lookup"><span data-stu-id="3c194-102">How to: Expose Properties of Constituent Controls</span></span>
<span data-ttu-id="3c194-103">Элементы управления, входящие в состав составного элемента управления, называются *составляющие элементы управления*.</span><span class="sxs-lookup"><span data-stu-id="3c194-103">The controls that make up a composite control are called *constituent controls*.</span></span> <span data-ttu-id="3c194-104">Эти элементы управления обычно являются объявленным как закрытый и не доступны разработчиком.</span><span class="sxs-lookup"><span data-stu-id="3c194-104">These controls are normally declared private, and thus cannot be accessed by the developer.</span></span> <span data-ttu-id="3c194-105">Если вы хотите сделать доступными свойства этих элементов управления для последующих пользователей, их необходимо предоставить пользователю.</span><span class="sxs-lookup"><span data-stu-id="3c194-105">If you want to make properties of these controls available to future users, you must expose them to the user.</span></span> <span data-ttu-id="3c194-106">Свойство составляющего элемента управления предоставляется путем создания свойства в пользовательском элементе управления и с помощью `get` и `set` методы доступа этого свойства для внесения изменений в закрытое свойство составляющего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="3c194-106">A property of a constituent control is exposed by creating a property in the user control, and using the `get` and `set` accessors of that property to effect the change in the private property of the constituent control.</span></span>  
  
 <span data-ttu-id="3c194-107">Рассмотрим гипотетический пользовательский элемент управления, содержащий составную кнопку `MyButton`.</span><span class="sxs-lookup"><span data-stu-id="3c194-107">Consider a hypothetical user control with a constituent button named `MyButton`.</span></span> <span data-ttu-id="3c194-108">В этом примере, когда пользователь запрашивает `ConstituentButtonBackColor` свойство, значение, хранящееся в <xref:System.Windows.Forms.Control.BackColor%2A> свойство `MyButton` доставки.</span><span class="sxs-lookup"><span data-stu-id="3c194-108">In this example, when the user requests the `ConstituentButtonBackColor` property, the value stored in the <xref:System.Windows.Forms.Control.BackColor%2A> property of `MyButton` is delivered.</span></span> <span data-ttu-id="3c194-109">Когда пользователь присваивает значение этого свойства, это значение автоматически передается <xref:System.Windows.Forms.Control.BackColor%2A> свойство `MyButton` и `set` код будет выполнен, изменения цвета `MyButton`.</span><span class="sxs-lookup"><span data-stu-id="3c194-109">When the user assigns a value to this property, that value is automatically passed to the <xref:System.Windows.Forms.Control.BackColor%2A> property of `MyButton` and the `set` code will execute, changing the color of `MyButton`.</span></span>  
  
 <span data-ttu-id="3c194-110">В следующем примере показан способ предоставления <xref:System.Windows.Forms.Control.BackColor%2A> свойства кнопки, составляющих:</span><span class="sxs-lookup"><span data-stu-id="3c194-110">The following example shows how to expose the <xref:System.Windows.Forms.Control.BackColor%2A> property of the constituent button:</span></span>  
  
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
  
### <a name="to-expose-a-property-of-a-constituent-control"></a><span data-ttu-id="3c194-111">Чтобы предоставить свойство составного элемента управления</span><span class="sxs-lookup"><span data-stu-id="3c194-111">To expose a property of a constituent control</span></span>  
  
1.  <span data-ttu-id="3c194-112">Создайте открытое свойство для пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="3c194-112">Create a public property for your user control.</span></span>  
  
2.  <span data-ttu-id="3c194-113">В `get` разделе Свойства написать код, который извлекает значение свойства, которому требуется предоставить доступ.</span><span class="sxs-lookup"><span data-stu-id="3c194-113">In the `get` section of the property, write code that retrieves the value of the property you want to expose.</span></span>  
  
3.  <span data-ttu-id="3c194-114">В `set` разделе Свойства написать код, который передает значение свойства, предоставленному свойству составляющего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="3c194-114">In the `set` section of the property, write code that passes the value of the property to the exposed property of the constituent control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c194-115">См. также</span><span class="sxs-lookup"><span data-stu-id="3c194-115">See Also</span></span>  
 <xref:System.Windows.Forms.UserControl>  
 [<span data-ttu-id="3c194-116">Свойства элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3c194-116">Properties in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)  
 [<span data-ttu-id="3c194-117">Разновидности пользовательских элементов управления</span><span class="sxs-lookup"><span data-stu-id="3c194-117">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
