---
title: Составные элементы управления
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], constituent controls
- constituent controls [Windows Forms]
- user controls [Windows Forms], constituent controls
ms.assetid: 5565e720-198b-4bbd-a2bd-c447ba641798
ms.openlocfilehash: 6fb708b81089b4fcd3678b35d1bcf7da2244c6d1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="constituent-controls"></a><span data-ttu-id="192ec-102">Составные элементы управления</span><span class="sxs-lookup"><span data-stu-id="192ec-102">Constituent Controls</span></span>
<span data-ttu-id="192ec-103">Элементы управления, составляющие пользовательский элемент управления, или *составные элементы управления*, как они иначе называются, обеспечивают относительную гибкость, когда речь идет об отрисовке пользовательской графики.</span><span class="sxs-lookup"><span data-stu-id="192ec-103">The controls that make up a user control, or *constituent controls* as they are termed, are relatively inflexible when it comes to custom graphics rendering.</span></span> <span data-ttu-id="192ec-104">Все элементы управления Windows Forms производят отрисовку, используя собственный <xref:System.Windows.Forms.Control.OnPaint%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="192ec-104">All Windows Forms controls handle their own rendering through their own <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="192ec-105">Так как этот метод защищен, он недоступен для разработчика и поэтому не может быть заблокирован при рисовании элемента управления.</span><span class="sxs-lookup"><span data-stu-id="192ec-105">Because this method is protected, it is not accessible to the developer, and thus cannot be prevented from executing when the control is painted.</span></span> <span data-ttu-id="192ec-106">Это, однако, не означает, что нельзя добавить код, влияющий на внешний вид составных элементов управления.</span><span class="sxs-lookup"><span data-stu-id="192ec-106">This does not mean, however, that you cannot add code to affect the appearance of constituent controls.</span></span> <span data-ttu-id="192ec-107">Дополнительную отрисовку можно выполнить путем добавления обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="192ec-107">Additional rendering can be accomplished by adding an event handler.</span></span> <span data-ttu-id="192ec-108">Предположим, что разрабатывается <xref:System.Windows.Forms.UserControl> с помощью кнопки с именем `MyButton`.</span><span class="sxs-lookup"><span data-stu-id="192ec-108">For example, suppose you were authoring a <xref:System.Windows.Forms.UserControl> with a button named `MyButton`.</span></span> <span data-ttu-id="192ec-109">Если вы хотели бы иметь дополнительной отрисовки, помимо выполняемой классом <xref:System.Web.UI.WebControls.Button>, можно добавить код в пользовательский элемент управления следующим образом:</span><span class="sxs-lookup"><span data-stu-id="192ec-109">If you wished to have additional rendering beyond what was provided by the <xref:System.Web.UI.WebControls.Button>, you would add code to your user control similar to the following:</span></span>  
  
```vb  
Public Sub MyPaint(ByVal sender as Object, e as PaintEventArgs) Handles _  
   MyButton.Paint  
   'Additional rendering code goes here  
End Sub  
```  
  
```csharp  
// Add the event handler to the button's Paint event.  
MyButton.Paint +=   
   new System.Windows.Forms.PaintEventHandler (this.MyPaint);  
// Create the custom painting method.  
protected void MyPaint (object sender,   
System.Windows.Forms.PaintEventArgs e)  
{  
   // Additional rendering code goes here.  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="192ec-110">Элементы управления некоторые Windows Forms, такие как <xref:System.Windows.Forms.TextBox>, рисуются непосредственно операционной системой Windows.</span><span class="sxs-lookup"><span data-stu-id="192ec-110">Some Windows Forms controls, such as <xref:System.Windows.Forms.TextBox>, are painted directly by Windows.</span></span> <span data-ttu-id="192ec-111">В таких случаях <xref:System.Windows.Forms.Control.OnPaint%2A> никогда не вызывается метод, и таким образом, приведенный выше пример никогда не будет вызываться.</span><span class="sxs-lookup"><span data-stu-id="192ec-111">In these instances, the <xref:System.Windows.Forms.Control.OnPaint%2A> method is never called, and thus the above example will never be called.</span></span>  
  
 <span data-ttu-id="192ec-112">При этом создается метод, который выполняется каждый раз при выполнении события `MyButton.Paint`, таким образом, добавляя дополнительное графическое представление для элемента управления.</span><span class="sxs-lookup"><span data-stu-id="192ec-112">This creates a method that executes every time the `MyButton.Paint` event executes, thereby adding additional graphical representation to your control.</span></span> <span data-ttu-id="192ec-113">Обратите внимание, что это не блокирует выполнение `MyButton.OnPaint` и поэтому все операции рисования, обычно выполняемые кнопкой, по-прежнему будут выполняться наряду с настраиваемым рисованием.</span><span class="sxs-lookup"><span data-stu-id="192ec-113">Note that this does not prevent the execution of `MyButton.OnPaint`, and thus all of the painting usually performed by a button will still be performed in addition to your custom painting.</span></span> <span data-ttu-id="192ec-114">Дополнительные сведения о технологии GDI+ и настраиваемой отрисовке см. в разделе [Создание графических изображений с помощью GDI+](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md).</span><span class="sxs-lookup"><span data-stu-id="192ec-114">For details about GDI+ technology and custom rendering, see the [Creating Graphical Images with GDI+](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md).</span></span> <span data-ttu-id="192ec-115">При необходимости получения уникального представления элемента управления оптимальным решением будет создание наследуемого элемента управления и написание для него собственного кода отрисовки.</span><span class="sxs-lookup"><span data-stu-id="192ec-115">If you wish to have a unique representation of your control, your best course of action is to create an inherited control, and to write custom rendering code for it.</span></span> <span data-ttu-id="192ec-116">Дополнительные сведения см. в разделе [Элементы управления, разработанные пользователем](../../../../docs/framework/winforms/controls/user-drawn-controls.md).</span><span class="sxs-lookup"><span data-stu-id="192ec-116">For details, see [User-Drawn Controls](../../../../docs/framework/winforms/controls/user-drawn-controls.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="192ec-117">См. также</span><span class="sxs-lookup"><span data-stu-id="192ec-117">See Also</span></span>  
 <xref:System.Windows.Forms.UserControl>  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 [<span data-ttu-id="192ec-118">Элементы управления, разработанные пользователем</span><span class="sxs-lookup"><span data-stu-id="192ec-118">User-Drawn Controls</span></span>](../../../../docs/framework/winforms/controls/user-drawn-controls.md)  
 [<span data-ttu-id="192ec-119">Практическое руководство. Создание графических объектов для рисования</span><span class="sxs-lookup"><span data-stu-id="192ec-119">How to: Create Graphics Objects for Drawing</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [<span data-ttu-id="192ec-120">Разновидности пользовательских элементов управления</span><span class="sxs-lookup"><span data-stu-id="192ec-120">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
