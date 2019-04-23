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
ms.openlocfilehash: 76a5a4f9b02a71616d247a1bb0f03cc0aec1d70d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59224881"
---
# <a name="constituent-controls"></a><span data-ttu-id="d9839-102">Составные элементы управления</span><span class="sxs-lookup"><span data-stu-id="d9839-102">Constituent Controls</span></span>
<span data-ttu-id="d9839-103">Элементы управления, составляющие пользовательский элемент управления, или *составные элементы управления*, как они иначе называются, обеспечивают относительную гибкость, когда речь идет об отрисовке пользовательской графики.</span><span class="sxs-lookup"><span data-stu-id="d9839-103">The controls that make up a user control, or *constituent controls* as they are termed, are relatively inflexible when it comes to custom graphics rendering.</span></span> <span data-ttu-id="d9839-104">Все элементы управления Windows Forms обрабатывают собственную отрисовку, используя собственный <xref:System.Windows.Forms.Control.OnPaint%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="d9839-104">All Windows Forms controls handle their own rendering through their own <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="d9839-105">Так как этот метод защищен, он недоступен для разработчика и поэтому не может быть заблокирован при рисовании элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d9839-105">Because this method is protected, it is not accessible to the developer, and thus cannot be prevented from executing when the control is painted.</span></span> <span data-ttu-id="d9839-106">Это, однако, не означает, что нельзя добавить код, влияющий на внешний вид составных элементов управления.</span><span class="sxs-lookup"><span data-stu-id="d9839-106">This does not mean, however, that you cannot add code to affect the appearance of constituent controls.</span></span> <span data-ttu-id="d9839-107">Дополнительную отрисовку можно выполнить путем добавления обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="d9839-107">Additional rendering can be accomplished by adding an event handler.</span></span> <span data-ttu-id="d9839-108">Например, предположим, вы создаете <xref:System.Windows.Forms.UserControl> с помощью кнопки с именем `MyButton`.</span><span class="sxs-lookup"><span data-stu-id="d9839-108">For example, suppose you were authoring a <xref:System.Windows.Forms.UserControl> with a button named `MyButton`.</span></span> <span data-ttu-id="d9839-109">Если вы хотели бы отрисовки, которые не предоставляются классом <xref:System.Web.UI.WebControls.Button>, необходимо добавить код в пользовательский элемент управления, аналогичную следующей:</span><span class="sxs-lookup"><span data-stu-id="d9839-109">If you wished to have additional rendering beyond what was provided by the <xref:System.Web.UI.WebControls.Button>, you would add code to your user control similar to the following:</span></span>  
  
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
>  <span data-ttu-id="d9839-110">Некоторые Windows Forms элементы управления, такие как <xref:System.Windows.Forms.TextBox>, рисуются непосредственно с Windows.</span><span class="sxs-lookup"><span data-stu-id="d9839-110">Some Windows Forms controls, such as <xref:System.Windows.Forms.TextBox>, are painted directly by Windows.</span></span> <span data-ttu-id="d9839-111">В таком случае <xref:System.Windows.Forms.Control.OnPaint%2A> никогда не вызывается метод, и таким образом, приведенном выше примере никогда не будет вызываться.</span><span class="sxs-lookup"><span data-stu-id="d9839-111">In these instances, the <xref:System.Windows.Forms.Control.OnPaint%2A> method is never called, and thus the above example will never be called.</span></span>  
  
 <span data-ttu-id="d9839-112">При этом создается метод, который выполняется каждый раз при выполнении события `MyButton.Paint`, таким образом, добавляя дополнительное графическое представление для элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d9839-112">This creates a method that executes every time the `MyButton.Paint` event executes, thereby adding additional graphical representation to your control.</span></span> <span data-ttu-id="d9839-113">Обратите внимание, что это не блокирует выполнение `MyButton.OnPaint` и поэтому все операции рисования, обычно выполняемые кнопкой, по-прежнему будут выполняться наряду с настраиваемым рисованием.</span><span class="sxs-lookup"><span data-stu-id="d9839-113">Note that this does not prevent the execution of `MyButton.OnPaint`, and thus all of the painting usually performed by a button will still be performed in addition to your custom painting.</span></span> <span data-ttu-id="d9839-114">Дополнительные сведения о технологии GDI+ и настраиваемой отрисовке см. в разделе [Создание графических изображений с помощью GDI+](../advanced/how-to-create-graphics-objects-for-drawing.md).</span><span class="sxs-lookup"><span data-stu-id="d9839-114">For details about GDI+ technology and custom rendering, see the [Creating Graphical Images with GDI+](../advanced/how-to-create-graphics-objects-for-drawing.md).</span></span> <span data-ttu-id="d9839-115">При необходимости получения уникального представления элемента управления оптимальным решением будет создание наследуемого элемента управления и написание для него собственного кода отрисовки.</span><span class="sxs-lookup"><span data-stu-id="d9839-115">If you wish to have a unique representation of your control, your best course of action is to create an inherited control, and to write custom rendering code for it.</span></span> <span data-ttu-id="d9839-116">Дополнительные сведения см. в разделе [Элементы управления, разработанные пользователем](user-drawn-controls.md).</span><span class="sxs-lookup"><span data-stu-id="d9839-116">For details, see [User-Drawn Controls](user-drawn-controls.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9839-117">См. также</span><span class="sxs-lookup"><span data-stu-id="d9839-117">See also</span></span>

- <xref:System.Windows.Forms.UserControl>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [<span data-ttu-id="d9839-118">Элементы управления, разработанные пользователем</span><span class="sxs-lookup"><span data-stu-id="d9839-118">User-Drawn Controls</span></span>](user-drawn-controls.md)
- [<span data-ttu-id="d9839-119">Практическое руководство. Создание объектов Graphics для рисования</span><span class="sxs-lookup"><span data-stu-id="d9839-119">How to: Create Graphics Objects for Drawing</span></span>](../advanced/how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="d9839-120">Разновидности пользовательских элементов управления</span><span class="sxs-lookup"><span data-stu-id="d9839-120">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
