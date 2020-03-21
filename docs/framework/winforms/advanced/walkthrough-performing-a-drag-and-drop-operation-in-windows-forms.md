---
title: 'Прохождение: Выполните операцию перетаскивания'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drag and drop operations
- drag and drop [Windows Forms], Windows Forms
ms.assetid: eb66f6bf-4a7d-4c2d-b276-40fefb2d3b6c
ms.openlocfilehash: b5e4bf753733cb9bd010672f40e8fbeb0cf036bf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182441"
---
# <a name="walkthrough-performing-a-drag-and-drop-operation-in-windows-forms"></a><span data-ttu-id="936d3-102">Пример. Выполнение операции перетаскивания в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="936d3-102">Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms</span></span>
<span data-ttu-id="936d3-103">Для выполнения операций перетаскивания в приложениях на базе Windows необходимо <xref:System.Windows.Forms.Control.DragEnter>обрабатывать <xref:System.Windows.Forms.Control.DragLeave>ряд <xref:System.Windows.Forms.Control.DragDrop> событий, в первую очередь , и события.</span><span class="sxs-lookup"><span data-stu-id="936d3-103">To perform drag-and-drop operations within Windows-based applications you must handle a series of events, most notably the <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave>, and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span> <span data-ttu-id="936d3-104">Работая со сведениями, доступными через аргументы этих событий, можно значительно упростить операции перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="936d3-104">By working with the information available in the event arguments of these events, you can easily facilitate drag-and-drop operations.</span></span>  
  
## <a name="dragging-data"></a><span data-ttu-id="936d3-105">Перетаскивание данных</span><span class="sxs-lookup"><span data-stu-id="936d3-105">Dragging Data</span></span>  
 <span data-ttu-id="936d3-106">Все операции перетаскивания начинаются с переноса данных.</span><span class="sxs-lookup"><span data-stu-id="936d3-106">All drag-and-drop operations begin with dragging.</span></span> <span data-ttu-id="936d3-107">Функциональность, позволяющая собирать данные при начале <xref:System.Windows.Forms.Control.DoDragDrop%2A> перетаскивания, реализована в методе.</span><span class="sxs-lookup"><span data-stu-id="936d3-107">The functionality to enable data to be collected when dragging begins is implemented in the <xref:System.Windows.Forms.Control.DoDragDrop%2A> method.</span></span>  
  
 <span data-ttu-id="936d3-108">В следующем примере <xref:System.Windows.Forms.Control.MouseDown> событие используется для запуска операции перетаскивания, поскольку оно является наиболее интуитивным (большинство действий перетаскивания начинаются с нажатия кнопки мыши).</span><span class="sxs-lookup"><span data-stu-id="936d3-108">In the following example, the <xref:System.Windows.Forms.Control.MouseDown> event is used to start the drag operation because it is the most intuitive (most drag-and-drop actions begin with the mouse button being depressed).</span></span> <span data-ttu-id="936d3-109">Однако не забывайте, что любое событие может использоваться для инициализации процедуры перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="936d3-109">However, remember that any event could be used to initiate a drag-and-drop procedure.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="936d3-110">Некоторые элементы управления имеют собственные события перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="936d3-110">Certain controls have custom drag-specific events.</span></span> <span data-ttu-id="936d3-111">Например, <xref:System.Windows.Forms.ListView> в <xref:System.Windows.Forms.TreeView> элементах <xref:System.Windows.Forms.TreeView.ItemDrag> управления есть событие.</span><span class="sxs-lookup"><span data-stu-id="936d3-111">The <xref:System.Windows.Forms.ListView> and <xref:System.Windows.Forms.TreeView> controls, for example, have an <xref:System.Windows.Forms.TreeView.ItemDrag> event.</span></span>  
  
#### <a name="to-start-a-drag-operation"></a><span data-ttu-id="936d3-112">Начало операции перетаскивания</span><span class="sxs-lookup"><span data-stu-id="936d3-112">To start a drag operation</span></span>  
  
1. <span data-ttu-id="936d3-113">В <xref:System.Windows.Forms.Control.MouseDown> случае, если элемент управления начнется, `DoDragDrop` используйте метод для установки данных, которые будут перетасканы, и допустимый эффект перетаскивания будет иметь.</span><span class="sxs-lookup"><span data-stu-id="936d3-113">In the <xref:System.Windows.Forms.Control.MouseDown> event for the control where the drag will begin, use the `DoDragDrop` method to set the data to be dragged and the allowed effect dragging will have.</span></span> <span data-ttu-id="936d3-114">Дополнительные сведения см. в разделе <xref:System.Windows.Forms.DragEventArgs.Data%2A> и <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.</span><span class="sxs-lookup"><span data-stu-id="936d3-114">For more information, see <xref:System.Windows.Forms.DragEventArgs.Data%2A> and <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.</span></span>  
  
     <span data-ttu-id="936d3-115">В следующем примере показан запуск операции перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="936d3-115">The following example shows how to initiate a drag operation.</span></span> <span data-ttu-id="936d3-116">Элемент управления, в котором <xref:System.Windows.Forms.Button> начинается перетащивание, является <xref:System.Windows.Forms.Control.Text%2A> элементом <xref:System.Windows.Forms.Button> управления, перетаскивание множец данных — строкой, представляющей свойство элемента управления, а допустимые эффекты — копированием или перемещением.</span><span class="sxs-lookup"><span data-stu-id="936d3-116">The control where the drag begins is a <xref:System.Windows.Forms.Button> control, the data being dragged is the string representing the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.Button> control, and the allowed effects are either copying or moving.</span></span>  
  
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
    > <span data-ttu-id="936d3-117">Любые данные могут быть `DoDragDrop` использованы в качестве параметра в методе; в приведенном выше <xref:System.Windows.Forms.Control.Text%2A> примере <xref:System.Windows.Forms.Button> использовалось свойство элемента управления (а не жесткое кодирование значения или извлечение данных из <xref:System.Windows.Forms.Button> набора данных), поскольку свойство было связано с местом, перетащенным из (элементуправления).</span><span class="sxs-lookup"><span data-stu-id="936d3-117">Any data can be used as a parameter in the `DoDragDrop` method; in the example above, the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.Button> control was used (rather than hard-coding a value or retrieving data from a dataset) because the property was related to the location being dragged from (the <xref:System.Windows.Forms.Button> control).</span></span> <span data-ttu-id="936d3-118">Учитывайте это при реализации операций перетаскивания в приложениях Windows.</span><span class="sxs-lookup"><span data-stu-id="936d3-118">Keep this in mind as you incorporate drag-and-drop operations into your Windows-based applications.</span></span>  
  
 <span data-ttu-id="936d3-119">В то время как операция перетаскивания действует, можно обрабатывать <xref:System.Windows.Forms.Control.QueryContinueDrag> событие, которое "запрашивает разрешение" системы на продолжение операции перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="936d3-119">While a drag operation is in effect, you can handle the <xref:System.Windows.Forms.Control.QueryContinueDrag> event, which "asks permission" of the system to continue the drag operation.</span></span> <span data-ttu-id="936d3-120">При обработке этого метода, это также подходящий момент для вызова методов, которые будут <xref:System.Windows.Forms.TreeNode> иметь <xref:System.Windows.Forms.TreeView> влияние на операцию перетаскивания, такие как расширение в элементе управления, когда курсор парит над ним.</span><span class="sxs-lookup"><span data-stu-id="936d3-120">When handling this method, it is also the appropriate point for you to call methods that will have an effect on the drag operation, such as expanding a <xref:System.Windows.Forms.TreeNode> in a <xref:System.Windows.Forms.TreeView> control when the cursor hovers over it.</span></span>  
  
## <a name="dropping-data"></a><span data-ttu-id="936d3-121">Завершение перетаскивания данных</span><span class="sxs-lookup"><span data-stu-id="936d3-121">Dropping Data</span></span>  
 <span data-ttu-id="936d3-122">После начала перетаскивания данных из расположения в форме Windows Forms или элементе управления их требуется куда-то поместить.</span><span class="sxs-lookup"><span data-stu-id="936d3-122">Once you have begun dragging data from a location on a Windows Form or control, you will naturally want to drop it somewhere.</span></span> <span data-ttu-id="936d3-123">При попадании курсора в область формы или элемента управления, которые правильно настроены для размещения данных, вид курсора изменится.</span><span class="sxs-lookup"><span data-stu-id="936d3-123">The cursor will change when it crosses an area of a form or control that is correctly configured for dropping data.</span></span> <span data-ttu-id="936d3-124">Любая область в форме или элементе управления Windows <xref:System.Windows.Forms.Control.AllowDrop%2A> может быть <xref:System.Windows.Forms.Control.DragEnter> сделана для принятия отброшенных данных путем установки свойства и обработки и <xref:System.Windows.Forms.Control.DragDrop> событий.</span><span class="sxs-lookup"><span data-stu-id="936d3-124">Any area within a Windows Form or control can be made to accept dropped data by setting the <xref:System.Windows.Forms.Control.AllowDrop%2A> property and handling the <xref:System.Windows.Forms.Control.DragEnter> and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span>  
  
#### <a name="to-perform-a-drop"></a><span data-ttu-id="936d3-125">Завершение операции перетаскивания</span><span class="sxs-lookup"><span data-stu-id="936d3-125">To perform a drop</span></span>  
  
1. <span data-ttu-id="936d3-126">Установите <xref:System.Windows.Forms.Control.AllowDrop%2A> свойство на истину.</span><span class="sxs-lookup"><span data-stu-id="936d3-126">Set the <xref:System.Windows.Forms.Control.AllowDrop%2A> property to true.</span></span>  
  
2. <span data-ttu-id="936d3-127">В `DragEnter` случае элемента управления, <xref:System.Windows.Forms.Control.Text%2A>где произойдет падение, убедитесь, что перетаскиваемые данные являются приемлемым типом (в данном случае).</span><span class="sxs-lookup"><span data-stu-id="936d3-127">In the `DragEnter` event for the control where the drop will occur, ensure that the data being dragged is of an acceptable type (in this case, <xref:System.Windows.Forms.Control.Text%2A>).</span></span> <span data-ttu-id="936d3-128">Затем код устанавливает эффект, который произойдет, когда происходит <xref:System.Windows.Forms.DragDropEffects> падение к значению в перечислении.</span><span class="sxs-lookup"><span data-stu-id="936d3-128">The code then sets the effect that will happen when the drop occurs to a value in the <xref:System.Windows.Forms.DragDropEffects> enumeration.</span></span> <span data-ttu-id="936d3-129">Дополнительные сведения см. в разделе <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.</span><span class="sxs-lookup"><span data-stu-id="936d3-129">For more information, see <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.</span></span>  
  
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
    > <span data-ttu-id="936d3-130">Вы можете определить <xref:System.Windows.Forms.DataFormats> свой собственный, указав свой собственный объект в <xref:System.Object> качестве параметра метода. <xref:System.Windows.Forms.DataObject.SetData%2A></span><span class="sxs-lookup"><span data-stu-id="936d3-130">You can define your own <xref:System.Windows.Forms.DataFormats> by specifying your own object as the <xref:System.Object> parameter of the <xref:System.Windows.Forms.DataObject.SetData%2A> method.</span></span> <span data-ttu-id="936d3-131">При этом необходимо убедиться, что указанный объект является сериализуемым.</span><span class="sxs-lookup"><span data-stu-id="936d3-131">Be sure, when doing this, that the object specified is serializable.</span></span> <span data-ttu-id="936d3-132">Дополнительные сведения см. в разделе <xref:System.Runtime.Serialization.ISerializable>.</span><span class="sxs-lookup"><span data-stu-id="936d3-132">For more information, see <xref:System.Runtime.Serialization.ISerializable>.</span></span>  
  
3. <span data-ttu-id="936d3-133">В <xref:System.Windows.Forms.Control.DragDrop> случае элемента управления, где произойдет <xref:System.Windows.Forms.DataObject.GetData%2A> падение, используйте метод для извлечения перетаскиваемых данных.</span><span class="sxs-lookup"><span data-stu-id="936d3-133">In the <xref:System.Windows.Forms.Control.DragDrop> event for the control where the drop will occur, use the <xref:System.Windows.Forms.DataObject.GetData%2A> method to retrieve the data being dragged.</span></span> <span data-ttu-id="936d3-134">Дополнительные сведения см. в разделе <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>.</span><span class="sxs-lookup"><span data-stu-id="936d3-134">For more information, see <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>.</span></span>  
  
     <span data-ttu-id="936d3-135">В приведенном ниже <xref:System.Windows.Forms.TextBox> примере элемент управления, перетащаемый в (там, где происходит падение).</span><span class="sxs-lookup"><span data-stu-id="936d3-135">In the example below, a <xref:System.Windows.Forms.TextBox> control is the control being dragged to (where the drop will occur).</span></span> <span data-ttu-id="936d3-136">Код устанавливает <xref:System.Windows.Forms.Control.Text%2A> свойство <xref:System.Windows.Forms.TextBox> элемента управления, равное перетаскиваемым данным.</span><span class="sxs-lookup"><span data-stu-id="936d3-136">The code sets the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.TextBox> control equal to the data being dragged.</span></span>  
  
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
    > <span data-ttu-id="936d3-137">Кроме того, вы можете <xref:System.Windows.Forms.DragEventArgs.KeyState%2A> работать с свойством, так что, в зависимости от ключей, подавленных во время операции перетаскивания, возникают определенные эффекты (например, обычно копирование перетащенных данных при нажатии ключа CTRL).</span><span class="sxs-lookup"><span data-stu-id="936d3-137">Additionally, you can work with the <xref:System.Windows.Forms.DragEventArgs.KeyState%2A> property, so that, depending on keys depressed during the drag-and-drop operation, certain effects occur (for example, it is standard to copy the dragged data when the CTRL key is pressed).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="936d3-138">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="936d3-138">See also</span></span>

- [<span data-ttu-id="936d3-139">Практическое руководство. Добавление данных в буфер обмена</span><span class="sxs-lookup"><span data-stu-id="936d3-139">How to: Add Data to the Clipboard</span></span>](how-to-add-data-to-the-clipboard.md)
- [<span data-ttu-id="936d3-140">Практическое руководство. Извлечение данных из буфера обмена</span><span class="sxs-lookup"><span data-stu-id="936d3-140">How to: Retrieve Data from the Clipboard</span></span>](how-to-retrieve-data-from-the-clipboard.md)
- [<span data-ttu-id="936d3-141">Операции перетаскивания и поддержка буфера обмена</span><span class="sxs-lookup"><span data-stu-id="936d3-141">Drag-and-Drop Operations and Clipboard Support</span></span>](drag-and-drop-operations-and-clipboard-support.md)
