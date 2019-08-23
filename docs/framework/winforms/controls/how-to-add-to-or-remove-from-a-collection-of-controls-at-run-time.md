---
title: Практическое руководство. Добавление или удаление элемента в коллекции элементов управления во время выполнения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- run time [Windows Forms], removing controls
- controls [Windows Forms], adding using collections
- controls collections
- collections [Windows Forms], adding items
- run time [Windows Forms], adding controls
- controls [Windows Forms], removing using collections
ms.assetid: 771bf895-3d5f-469b-a324-3528f343657e
ms.openlocfilehash: 87ad4c957ac5b99438684d398a0c5ad7d126c406
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925043"
---
# <a name="how-to-add-to-or-remove-from-a-collection-of-controls-at-run-time"></a><span data-ttu-id="2cd13-102">Практическое руководство. Добавление или удаление элемента в коллекции элементов управления во время выполнения</span><span class="sxs-lookup"><span data-stu-id="2cd13-102">How to: Add to or Remove from a Collection of Controls at Run Time</span></span>
<span data-ttu-id="2cd13-103">Распространенные задачи при разработке приложений — это добавление элементов управления и удаление элементов управления из любого контейнера в формах (например <xref:System.Windows.Forms.Panel> , или <xref:System.Windows.Forms.GroupBox> , или даже самой формы).</span><span class="sxs-lookup"><span data-stu-id="2cd13-103">Common tasks in application development are adding controls to and removing controls from any container control on your forms (such as the <xref:System.Windows.Forms.Panel> or <xref:System.Windows.Forms.GroupBox> control, or even the form itself).</span></span> <span data-ttu-id="2cd13-104">Во время разработки элементы управления можно перетаскивать непосредственно на панель или в группу.</span><span class="sxs-lookup"><span data-stu-id="2cd13-104">At design time, controls can be dragged directly onto a panel or group box.</span></span> <span data-ttu-id="2cd13-105">Во время выполнения эти элементы управления поддерживают коллекцию `Controls`, которая отслеживает размещенные в них элементы управления.</span><span class="sxs-lookup"><span data-stu-id="2cd13-105">At run time, these controls maintain a `Controls` collection, which keeps track of what controls are placed on them.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2cd13-106">Следующий пример кода применяется к любому элементу управления, который поддерживает внутри себя коллекцию элементов управления.</span><span class="sxs-lookup"><span data-stu-id="2cd13-106">The following code example applies to any control that maintains a collection of controls within it.</span></span>  
  
### <a name="to-add-a-control-to-a-collection-programmatically"></a><span data-ttu-id="2cd13-107">Программное добавление элемента управления в коллекцию</span><span class="sxs-lookup"><span data-stu-id="2cd13-107">To add a control to a collection programmatically</span></span>  
  
1. <span data-ttu-id="2cd13-108">Создайте экземпляр элемента управления, подлежащий добавлению.</span><span class="sxs-lookup"><span data-stu-id="2cd13-108">Create an instance of the control to be added.</span></span>  
  
2. <span data-ttu-id="2cd13-109">Задайте свойства нового элемента управления.</span><span class="sxs-lookup"><span data-stu-id="2cd13-109">Set properties of the new control.</span></span>  
  
3. <span data-ttu-id="2cd13-110">Добавьте этот элемент управления в коллекцию `Controls` родительского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="2cd13-110">Add the control to the `Controls` collection of the parent control.</span></span>  
  
     <span data-ttu-id="2cd13-111">В следующем примере кода показано, как создать экземпляр <xref:System.Windows.Forms.Button> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="2cd13-111">The following code example shows how to create an instance of the <xref:System.Windows.Forms.Button> control.</span></span> <span data-ttu-id="2cd13-112">Для этого требуется форма с <xref:System.Windows.Forms.Panel> элементом управления и метод обработки событий для `NewPanelButton_Click`создаваемой кнопки, уже существует.</span><span class="sxs-lookup"><span data-stu-id="2cd13-112">It requires a form with a <xref:System.Windows.Forms.Panel> control and that the event-handling method for the button being created, `NewPanelButton_Click`, already exists.</span></span>  
  
    ```vb  
    Public NewPanelButton As New Button()  
  
    Public Sub AddNewControl()  
       ' The Add method will accept as a parameter any object that derives  
       ' from the Control class. In this case, it is a Button control.  
       Panel1.Controls.Add(NewPanelButton)  
       ' The event handler indicated for the Click event in the code   
       ' below is used as an example. Substite the appropriate event  
       ' handler for your application.  
       AddHandler NewPanelButton.Click, AddressOf NewPanelButton_Click  
    End Sub  
    ```  
  
    ```csharp  
    public Button newPanelButton = new Button();  
  
    public void addNewControl()  
    {   
       // The Add method will accept as a parameter any object that derives  
       // from the Control class. In this case, it is a Button control.  
       panel1.Controls.Add(newPanelButton);  
       // The event handler indicated for the Click event in the code   
       // below is used as an example. Substitute the appropriate event  
       // handler for your application.  
       this.newPanelButton.Click += new System.EventHandler(this. NewPanelButton_Click);  
    }  
    ```  
  
### <a name="to-remove-controls-from-a-collection-programmatically"></a><span data-ttu-id="2cd13-113">Программное удаление элементов управления из коллекции</span><span class="sxs-lookup"><span data-stu-id="2cd13-113">To remove controls from a collection programmatically</span></span>  
  
1. <span data-ttu-id="2cd13-114">Удалите обработчик событий из события.</span><span class="sxs-lookup"><span data-stu-id="2cd13-114">Remove the event handler from the event.</span></span> <span data-ttu-id="2cd13-115">В Visual Basic используйте ключевое слово [оператора RemoveHandler](../../../visual-basic/language-reference/statements/removehandler-statement.md) . в C#используйте [оператор-=](../../../csharp/language-reference/operators/subtraction-operator.md).</span><span class="sxs-lookup"><span data-stu-id="2cd13-115">In Visual Basic, use the [RemoveHandler Statement](../../../visual-basic/language-reference/statements/removehandler-statement.md) keyword; in C#, use the [-= operator](../../../csharp/language-reference/operators/subtraction-operator.md).</span></span>  
  
2. <span data-ttu-id="2cd13-116">Используйте метод `Remove` для удаления требуемого элемента управления из коллекции `Controls` панели.</span><span class="sxs-lookup"><span data-stu-id="2cd13-116">Use the `Remove` method to delete the desired control from the panel's `Controls` collection.</span></span>  
  
3. <span data-ttu-id="2cd13-117">Вызовите <xref:System.Windows.Forms.Control.Dispose%2A> метод, чтобы освободить все ресурсы, используемые элементом управления.</span><span class="sxs-lookup"><span data-stu-id="2cd13-117">Call the <xref:System.Windows.Forms.Control.Dispose%2A> method to release all the resources used by the control.</span></span>  
  
    ```vb  
    Public Sub RemoveControl()  
    ' NOTE: The code below uses the instance of   
    ' the button (NewPanelButton) from the previous example.  
       If Panel1.Controls.Contains(NewPanelButton) Then  
          RemoveHandler NewPanelButton.Click, AddressOf _   
             NewPanelButton_Click  
          Panel1.Controls.Remove(NewPanelButton)  
          NewPanelButton.Dispose()  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void removeControl(object sender, System.EventArgs e)  
    {  
    // NOTE: The code below uses the instance of   
    // the button (newPanelButton) from the previous example.  
       if(panel1.Controls.Contains(newPanelButton))  
       {  
          this.newPanelButton.Click -= new System.EventHandler(this.   
             NewPanelButton_Click);  
          panel1.Controls.Remove(newPanelButton);  
          newPanelButton.Dispose();  
       }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="2cd13-118">См. также</span><span class="sxs-lookup"><span data-stu-id="2cd13-118">See also</span></span>

- <xref:System.Windows.Forms.Panel>
- [<span data-ttu-id="2cd13-119">Элемент управления Panel</span><span class="sxs-lookup"><span data-stu-id="2cd13-119">Panel Control</span></span>](panel-control-windows-forms.md)
