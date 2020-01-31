---
title: Пошаговое руководство. выполнение операции перетаскивания
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drag and drop operations
- drag and drop [Windows Forms], Windows Forms
ms.assetid: eb66f6bf-4a7d-4c2d-b276-40fefb2d3b6c
ms.openlocfilehash: 265e6d4f9e3370d28a18b86dea983bb0b556be41
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746789"
---
# <a name="walkthrough-performing-a-drag-and-drop-operation-in-windows-forms"></a><span data-ttu-id="fc3ba-102">Пример. Выполнение операции перетаскивания в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fc3ba-102">Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms</span></span>
<span data-ttu-id="fc3ba-103">Для выполнения операций перетаскивания в приложениях на основе Windows необходимо выполнить обработку ряда событий, особенно в <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave>и <xref:System.Windows.Forms.Control.DragDrop> событий.</span><span class="sxs-lookup"><span data-stu-id="fc3ba-103">To perform drag-and-drop operations within Windows-based applications you must handle a series of events, most notably the <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave>, and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span> <span data-ttu-id="fc3ba-104">Работая со сведениями, доступными через аргументы этих событий, можно значительно упростить операции перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="fc3ba-104">By working with the information available in the event arguments of these events, you can easily facilitate drag-and-drop operations.</span></span>  
  
## <a name="dragging-data"></a><span data-ttu-id="fc3ba-105">Перетаскивание данных</span><span class="sxs-lookup"><span data-stu-id="fc3ba-105">Dragging Data</span></span>  
 <span data-ttu-id="fc3ba-106">Все операции перетаскивания начинаются с переноса данных.</span><span class="sxs-lookup"><span data-stu-id="fc3ba-106">All drag-and-drop operations begin with dragging.</span></span> <span data-ttu-id="fc3ba-107">Функция, позволяющая собирать данные при начале перетаскивания, реализуется в методе <xref:System.Windows.Forms.Control.DoDragDrop%2A>.</span><span class="sxs-lookup"><span data-stu-id="fc3ba-107">The functionality to enable data to be collected when dragging begins is implemented in the <xref:System.Windows.Forms.Control.DoDragDrop%2A> method.</span></span>  
  
 <span data-ttu-id="fc3ba-108">В следующем примере событие <xref:System.Windows.Forms.Control.MouseDown> используется для запуска операции перетаскивания, поскольку оно является наиболее интуитивно понятным (большинство действий по перетаскиванию начинается с нажатия кнопки мыши).</span><span class="sxs-lookup"><span data-stu-id="fc3ba-108">In the following example, the <xref:System.Windows.Forms.Control.MouseDown> event is used to start the drag operation because it is the most intuitive (most drag-and-drop actions begin with the mouse button being depressed).</span></span> <span data-ttu-id="fc3ba-109">Однако не забывайте, что любое событие может использоваться для инициализации процедуры перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="fc3ba-109">However, remember that any event could be used to initiate a drag-and-drop procedure.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fc3ba-110">Некоторые элементы управления имеют собственные события перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="fc3ba-110">Certain controls have custom drag-specific events.</span></span> <span data-ttu-id="fc3ba-111">Например, для элементов управления <xref:System.Windows.Forms.ListView> и <xref:System.Windows.Forms.TreeView> есть событие <xref:System.Windows.Forms.TreeView.ItemDrag>.</span><span class="sxs-lookup"><span data-stu-id="fc3ba-111">The <xref:System.Windows.Forms.ListView> and <xref:System.Windows.Forms.TreeView> controls, for example, have an <xref:System.Windows.Forms.TreeView.ItemDrag> event.</span></span>  
  
#### <a name="to-start-a-drag-operation"></a><span data-ttu-id="fc3ba-112">Начало операции перетаскивания</span><span class="sxs-lookup"><span data-stu-id="fc3ba-112">To start a drag operation</span></span>  
  
1. <span data-ttu-id="fc3ba-113">В событии <xref:System.Windows.Forms.Control.MouseDown> для элемента управления, в котором начнется перетаскивание, используйте метод `DoDragDrop`, чтобы задать перетаскиваемые данные и разрешить перетаскивание разрешенных эффектов.</span><span class="sxs-lookup"><span data-stu-id="fc3ba-113">In the <xref:System.Windows.Forms.Control.MouseDown> event for the control where the drag will begin, use the `DoDragDrop` method to set the data to be dragged and the allowed effect dragging will have.</span></span> <span data-ttu-id="fc3ba-114">Дополнительные сведения см. в разделах <xref:System.Windows.Forms.DragEventArgs.Data%2A> и <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.</span><span class="sxs-lookup"><span data-stu-id="fc3ba-114">For more information, see <xref:System.Windows.Forms.DragEventArgs.Data%2A> and <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.</span></span>  
  
     <span data-ttu-id="fc3ba-115">В следующем примере показан запуск операции перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="fc3ba-115">The following example shows how to initiate a drag operation.</span></span> <span data-ttu-id="fc3ba-116">Элемент управления, в котором начинается перетаскивание, является элементом управления <xref:System.Windows.Forms.Button>, перетаскиваемые данные — это строка, представляющая свойство <xref:System.Windows.Forms.Control.Text%2A> элемента управления <xref:System.Windows.Forms.Button>, а допустимые эффекты — копирование или перемещение.</span><span class="sxs-lookup"><span data-stu-id="fc3ba-116">The control where the drag begins is a <xref:System.Windows.Forms.Button> control, the data being dragged is the string representing the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.Button> control, and the allowed effects are either copying or moving.</span></span>  
  
    ```vb  
    Private Sub Button1_MouseDown(ByVal sender As Object, ByVal e As System.Windows.Forms.MouseEventArgs) Handles Button1.MouseDown  
       Button1.DoDragDrop(Button1.Text, DragDropEffects.Copy Or DragDropEffects.Move)  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_MouseDown(object sender,   
    System.Windows.Forms.MouseEventArgs e)  
    {  
       button1.DoDragDrop(button1.Text, DragDropEffects.Copy |   
          DragDropEffects.Move);  
    }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="fc3ba-117">Любые данные можно использовать в качестве параметра в методе `DoDragDrop`; в приведенном выше примере использовалось свойство <xref:System.Windows.Forms.Control.Text%2A> элемента управления <xref:System.Windows.Forms.Button> (вместо того, чтобы жестко кодировать значение или извлечь данные из набора данных), так как свойство было связано с расположением, которое перетаскивается из (элемент управления <xref:System.Windows.Forms.Button>).</span><span class="sxs-lookup"><span data-stu-id="fc3ba-117">Any data can be used as a parameter in the `DoDragDrop` method; in the example above, the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.Button> control was used (rather than hard-coding a value or retrieving data from a dataset) because the property was related to the location being dragged from (the <xref:System.Windows.Forms.Button> control).</span></span> <span data-ttu-id="fc3ba-118">Учитывайте это при реализации операций перетаскивания в приложениях Windows.</span><span class="sxs-lookup"><span data-stu-id="fc3ba-118">Keep this in mind as you incorporate drag-and-drop operations into your Windows-based applications.</span></span>  
  
 <span data-ttu-id="fc3ba-119">Пока действует операция перетаскивания, можно выполнить обработку события <xref:System.Windows.Forms.Control.QueryContinueDrag>, которое "запрашивает разрешение", чтобы продолжить операцию перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="fc3ba-119">While a drag operation is in effect, you can handle the <xref:System.Windows.Forms.Control.QueryContinueDrag> event, which "asks permission" of the system to continue the drag operation.</span></span> <span data-ttu-id="fc3ba-120">При обработке этого метода также можно вызвать методы, которые влияют на операцию перетаскивания, например, расширение <xref:System.Windows.Forms.TreeNode> в элементе управления <xref:System.Windows.Forms.TreeView>, когда курсор наведен на него.</span><span class="sxs-lookup"><span data-stu-id="fc3ba-120">When handling this method, it is also the appropriate point for you to call methods that will have an effect on the drag operation, such as expanding a <xref:System.Windows.Forms.TreeNode> in a <xref:System.Windows.Forms.TreeView> control when the cursor hovers over it.</span></span>  
  
## <a name="dropping-data"></a><span data-ttu-id="fc3ba-121">Завершение перетаскивания данных</span><span class="sxs-lookup"><span data-stu-id="fc3ba-121">Dropping Data</span></span>  
 <span data-ttu-id="fc3ba-122">После начала перетаскивания данных из расположения в форме Windows Forms или элементе управления их требуется куда-то поместить.</span><span class="sxs-lookup"><span data-stu-id="fc3ba-122">Once you have begun dragging data from a location on a Windows Form or control, you will naturally want to drop it somewhere.</span></span> <span data-ttu-id="fc3ba-123">При попадании курсора в область формы или элемента управления, которые правильно настроены для размещения данных, вид курсора изменится.</span><span class="sxs-lookup"><span data-stu-id="fc3ba-123">The cursor will change when it crosses an area of a form or control that is correctly configured for dropping data.</span></span> <span data-ttu-id="fc3ba-124">Любую область внутри формы или элемента управления Windows можно сделать для приема пропущенных данных, задав свойство <xref:System.Windows.Forms.Control.AllowDrop%2A> и обрабатывая события <xref:System.Windows.Forms.Control.DragEnter> и <xref:System.Windows.Forms.Control.DragDrop>.</span><span class="sxs-lookup"><span data-stu-id="fc3ba-124">Any area within a Windows Form or control can be made to accept dropped data by setting the <xref:System.Windows.Forms.Control.AllowDrop%2A> property and handling the <xref:System.Windows.Forms.Control.DragEnter> and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span>  
  
#### <a name="to-perform-a-drop"></a><span data-ttu-id="fc3ba-125">Завершение операции перетаскивания</span><span class="sxs-lookup"><span data-stu-id="fc3ba-125">To perform a drop</span></span>  
  
1. <span data-ttu-id="fc3ba-126">Присвойте свойству <xref:System.Windows.Forms.Control.AllowDrop%2A> значение true.</span><span class="sxs-lookup"><span data-stu-id="fc3ba-126">Set the <xref:System.Windows.Forms.Control.AllowDrop%2A> property to true.</span></span>  
  
2. <span data-ttu-id="fc3ba-127">В событии `DragEnter` для элемента управления, в котором будет выполняться перетаскивание, убедитесь, что перетаскиваемые данные имеют допустимый тип (в данном случае <xref:System.Windows.Forms.Control.Text%2A>).</span><span class="sxs-lookup"><span data-stu-id="fc3ba-127">In the `DragEnter` event for the control where the drop will occur, ensure that the data being dragged is of an acceptable type (in this case, <xref:System.Windows.Forms.Control.Text%2A>).</span></span> <span data-ttu-id="fc3ba-128">Затем код задает результат, который будет выполняться при выполнении перетаскивания в значение в перечислении <xref:System.Windows.Forms.DragDropEffects>.</span><span class="sxs-lookup"><span data-stu-id="fc3ba-128">The code then sets the effect that will happen when the drop occurs to a value in the <xref:System.Windows.Forms.DragDropEffects> enumeration.</span></span> <span data-ttu-id="fc3ba-129">Для получения дополнительной информации см. <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.</span><span class="sxs-lookup"><span data-stu-id="fc3ba-129">For more information, see <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.</span></span>  
  
    ```vb  
    Private Sub TextBox1_DragEnter(ByVal sender As Object, ByVal e As System.Windows.Forms.DragEventArgs) Handles TextBox1.DragEnter  
       If (e.Data.GetDataPresent(DataFormats.Text)) Then  
         e.Effect = DragDropEffects.Copy  
       Else  
         e.Effect = DragDropEffects.None  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_DragEnter(object sender,   
    System.Windows.Forms.DragEventArgs e)  
    {  
       if (e.Data.GetDataPresent(DataFormats.Text))   
          e.Effect = DragDropEffects.Copy;  
       else  
          e.Effect = DragDropEffects.None;  
    }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="fc3ba-130">Вы можете определить собственный <xref:System.Windows.Forms.DataFormats>, указав собственный объект в качестве параметра <xref:System.Object> метода <xref:System.Windows.Forms.DataObject.SetData%2A>.</span><span class="sxs-lookup"><span data-stu-id="fc3ba-130">You can define your own <xref:System.Windows.Forms.DataFormats> by specifying your own object as the <xref:System.Object> parameter of the <xref:System.Windows.Forms.DataObject.SetData%2A> method.</span></span> <span data-ttu-id="fc3ba-131">При этом необходимо убедиться, что указанный объект является сериализуемым.</span><span class="sxs-lookup"><span data-stu-id="fc3ba-131">Be sure, when doing this, that the object specified is serializable.</span></span> <span data-ttu-id="fc3ba-132">Для получения дополнительной информации см. <xref:System.Runtime.Serialization.ISerializable>.</span><span class="sxs-lookup"><span data-stu-id="fc3ba-132">For more information, see <xref:System.Runtime.Serialization.ISerializable>.</span></span>  
  
3. <span data-ttu-id="fc3ba-133">В событии <xref:System.Windows.Forms.Control.DragDrop> для элемента управления, в котором будет выполняться перетаскивание, используйте метод <xref:System.Windows.Forms.DataObject.GetData%2A> для получения перетаскиваемых данных.</span><span class="sxs-lookup"><span data-stu-id="fc3ba-133">In the <xref:System.Windows.Forms.Control.DragDrop> event for the control where the drop will occur, use the <xref:System.Windows.Forms.DataObject.GetData%2A> method to retrieve the data being dragged.</span></span> <span data-ttu-id="fc3ba-134">Для получения дополнительной информации см. <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>.</span><span class="sxs-lookup"><span data-stu-id="fc3ba-134">For more information, see <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>.</span></span>  
  
     <span data-ttu-id="fc3ba-135">В приведенном ниже примере элемент управления <xref:System.Windows.Forms.TextBox> — это элемент управления, к которому выполняется перетаскивание (где произойдет перетаскивание).</span><span class="sxs-lookup"><span data-stu-id="fc3ba-135">In the example below, a <xref:System.Windows.Forms.TextBox> control is the control being dragged to (where the drop will occur).</span></span> <span data-ttu-id="fc3ba-136">Этот код задает <xref:System.Windows.Forms.Control.Text%2A> свойство элемента управления <xref:System.Windows.Forms.TextBox>, равное перетаскиваемых данным.</span><span class="sxs-lookup"><span data-stu-id="fc3ba-136">The code sets the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.TextBox> control equal to the data being dragged.</span></span>  
  
    ```vb  
    Private Sub TextBox1_DragDrop(ByVal sender As Object, ByVal e As System.Windows.Forms.DragEventArgs) Handles TextBox1.DragDrop  
       TextBox1.Text = e.Data.GetData(DataFormats.Text).ToString  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_DragDrop(object sender,   
    System.Windows.Forms.DragEventArgs e)  
    {  
       textBox1.Text = e.Data.GetData(DataFormats.Text).ToString();  
    }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="fc3ba-137">Кроме того, можно работать со свойством <xref:System.Windows.Forms.DragEventArgs.KeyState%2A>, чтобы в зависимости от нажатых клавиш во время операции перетаскивания были выполнены определенные эффекты (например, при нажатии клавиши CTRL в стандартном режиме копируется перетаскивание данных).</span><span class="sxs-lookup"><span data-stu-id="fc3ba-137">Additionally, you can work with the <xref:System.Windows.Forms.DragEventArgs.KeyState%2A> property, so that, depending on keys depressed during the drag-and-drop operation, certain effects occur (for example, it is standard to copy the dragged data when the CTRL key is pressed).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc3ba-138">См. также:</span><span class="sxs-lookup"><span data-stu-id="fc3ba-138">See also</span></span>

- [<span data-ttu-id="fc3ba-139">Практическое руководство. Добавление данных в буфер обмена</span><span class="sxs-lookup"><span data-stu-id="fc3ba-139">How to: Add Data to the Clipboard</span></span>](how-to-add-data-to-the-clipboard.md)
- [<span data-ttu-id="fc3ba-140">Практическое руководство. Извлечение данных из буфера обмена</span><span class="sxs-lookup"><span data-stu-id="fc3ba-140">How to: Retrieve Data from the Clipboard</span></span>](how-to-retrieve-data-from-the-clipboard.md)
- [<span data-ttu-id="fc3ba-141">Операции перетаскивания и поддержка буфера обмена</span><span class="sxs-lookup"><span data-stu-id="fc3ba-141">Drag-and-Drop Operations and Clipboard Support</span></span>](drag-and-drop-operations-and-clipboard-support.md)
