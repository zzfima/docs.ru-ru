---
title: Как выполнить Включение операций перетаскивания и вставки с помощью элемента управления RichTextBox в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], text boxes
- drag and drop [Windows Forms], richTextBox control
- text boxes [Windows Forms], drag-and-drop operations
- RichTextBox control [Windows Forms], drag-and-drop operations
ms.assetid: ca167d1c-2014-4cf0-96a0-20598470be3b
ms.openlocfilehash: ccf98ee1afe82b2e76679406a08e98e6f4e6fb15
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54637470"
---
# <a name="how-to-enable-drag-and-drop-operations-with-the-windows-forms-richtextbox-control"></a><span data-ttu-id="fe4cd-102">Как выполнить Включение операций перетаскивания и вставки с помощью элемента управления RichTextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fe4cd-102">How to: Enable Drag-and-Drop Operations with the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="fe4cd-103">Операции перетаскивания для элемента управления <xref:System.Windows.Forms.RichTextBox> Windows Forms выполняются путем обработки событий <xref:System.Windows.Forms.RichTextBox.DragEnter> и <xref:System.Windows.Forms.RichTextBox.DragDrop> .</span><span class="sxs-lookup"><span data-stu-id="fe4cd-103">Drag-and-drop operations with the Windows Forms <xref:System.Windows.Forms.RichTextBox> control are done by handling the <xref:System.Windows.Forms.RichTextBox.DragEnter> and <xref:System.Windows.Forms.RichTextBox.DragDrop> events.</span></span> <span data-ttu-id="fe4cd-104">Таким образом, операции перетаскивания для элемента управления <xref:System.Windows.Forms.RichTextBox> являются очень простыми.</span><span class="sxs-lookup"><span data-stu-id="fe4cd-104">Thus, drag-and-drop operations are extremely simple with the <xref:System.Windows.Forms.RichTextBox> control.</span></span>  
  
### <a name="to-enable-drag-operations-in-a-richtextbox-control"></a><span data-ttu-id="fe4cd-105">Включение операций перетаскивания в элементе управления RichTextBox</span><span class="sxs-lookup"><span data-stu-id="fe4cd-105">To enable drag operations in a RichTextBox control</span></span>  
  
1.  <span data-ttu-id="fe4cd-106">Задайте для свойства <xref:System.Windows.Forms.RichTextBox.AllowDrop%2A> элемента управления <xref:System.Windows.Forms.RichTextBox> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="fe4cd-106">Set the <xref:System.Windows.Forms.RichTextBox.AllowDrop%2A> property of the <xref:System.Windows.Forms.RichTextBox> control to `true`.</span></span>  
  
2.  <span data-ttu-id="fe4cd-107">Напишите код в обработчике событий для события <xref:System.Windows.Forms.RichTextBox.DragEnter> .</span><span class="sxs-lookup"><span data-stu-id="fe4cd-107">Write code in the event handler of the <xref:System.Windows.Forms.RichTextBox.DragEnter> event.</span></span> <span data-ttu-id="fe4cd-108">Используйте инструкцию `if` , чтобы проверить допустимость типа перетаскиваемых данных (в данном случае это текст).</span><span class="sxs-lookup"><span data-stu-id="fe4cd-108">Use an `if` statement to ensure that the data being dragged is of an acceptable type (in this case, text).</span></span> <span data-ttu-id="fe4cd-109">Свойство <xref:System.Windows.Forms.DragEventArgs.Effect%2A?displayProperty=nameWithType> может иметь одно из значений перечисления <xref:System.Windows.Forms.DragDropEffects> .</span><span class="sxs-lookup"><span data-stu-id="fe4cd-109">The <xref:System.Windows.Forms.DragEventArgs.Effect%2A?displayProperty=nameWithType> property can be set to any value of the <xref:System.Windows.Forms.DragDropEffects> enumeration.</span></span>  
  
    ```vb  
    Private Sub RichTextBox1_DragEnter(ByVal sender As Object, _   
       ByVal e As System.Windows.Forms.DragEventArgs) _   
       Handles RichTextBox1.DragEnter  
       If (e.Data.GetDataPresent(DataFormats.Text)) Then  
          e.Effect = DragDropEffects.Copy  
       Else  
          e.Effect = DragDropEffects.None  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void richTextBox1_DragEnter(object sender,   
    System.Windows.Forms.DragEventArgs e)  
    {  
       if (e.Data.GetDataPresent(DataFormats.Text))   
          e.Effect = DragDropEffects.Copy;  
       else  
          e.Effect = DragDropEffects.None;  
    }  
    ```  
  
    ```cpp  
    private:  
       void richTextBox1_DragEnter(System::Object ^  sender,  
          System::Windows::Forms::DragEventArgs ^  e)  
       {  
          if (e->Data->GetDataPresent(DataFormats::Text))  
             e->Effect = DragDropEffects::Copy;  
          else  
             e->Effect = DragDropEffects::None;  
       }  
    ```  
  
     <span data-ttu-id="fe4cd-110">(Visual C# и [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) поместите следующий код в конструктор формы для регистрации обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="fe4cd-110">(Visual C# and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.richTextBox1.DragEnter += new  
        System.Windows.Forms.DragEventHandler  
        (this.richTextBox1_DragEnter);  
    ```  
  
    ```cpp  
    this->richTextBox1->DragEnter += gcnew  
       System::Windows::Forms::DragEventHandler  
       (this, &Form1::richTextBox1_DragEnter);  
    ```  
  
3.  <span data-ttu-id="fe4cd-111">Напишите код для обработки события <xref:System.Windows.Forms.RichTextBox.DragDrop> .</span><span class="sxs-lookup"><span data-stu-id="fe4cd-111">Write code to handle the <xref:System.Windows.Forms.RichTextBox.DragDrop> event.</span></span> <span data-ttu-id="fe4cd-112">Используйте метод <xref:System.Windows.Forms.DataObject.GetData%2A?displayProperty=nameWithType> для получения перетаскиваемых данных.</span><span class="sxs-lookup"><span data-stu-id="fe4cd-112">Use the <xref:System.Windows.Forms.DataObject.GetData%2A?displayProperty=nameWithType> method to retrieve the data being dragged.</span></span>  
  
     <span data-ttu-id="fe4cd-113">В примере ниже код задает перетаскиваемые данные в свойстве <xref:System.Windows.Forms.RichTextBox.Text%2A> элемента управления <xref:System.Windows.Forms.RichTextBox> .</span><span class="sxs-lookup"><span data-stu-id="fe4cd-113">In the example below, the code sets the <xref:System.Windows.Forms.RichTextBox.Text%2A> property of the <xref:System.Windows.Forms.RichTextBox> control equal to the data being dragged.</span></span> <span data-ttu-id="fe4cd-114">Если в элементе управления <xref:System.Windows.Forms.RichTextBox> уже существует текст, перетаскиваемый текст вставляется в точку вставки.</span><span class="sxs-lookup"><span data-stu-id="fe4cd-114">If there is already text in the <xref:System.Windows.Forms.RichTextBox> control, the dragged text is inserted at the insertion point.</span></span>  
  
    ```vb  
    Private Sub RichTextBox1_DragDrop(ByVal sender As Object, _   
       ByVal e As System.Windows.Forms.DragEventArgs) _   
       Handles RichTextBox1.DragDrop  
       Dim i As Int16   
       Dim s As String  
  
       ' Get start position to drop the text.  
       i = RichTextBox1.SelectionStart  
       s = RichTextBox1.Text.Substring(i)  
       RichTextBox1.Text = RichTextBox1.Text.Substring(0, i)  
  
       ' Drop the text on to the RichTextBox.  
       RichTextBox1.Text = RichTextBox1.Text + _  
          e.Data.GetData(DataFormats.Text).ToString()  
       RichTextBox1.Text = RichTextBox1.Text + s  
    End Sub  
    ```  
  
    ```csharp  
    private void richTextBox1_DragDrop(object sender,   
    System.Windows.Forms.DragEventArgs e)  
    {  
       int i;  
       String s;  
  
       // Get start position to drop the text.  
       i = richTextBox1.SelectionStart;  
       s = richTextBox1.Text.Substring(i);  
       richTextBox1.Text = richTextBox1.Text.Substring(0,i);  
  
       // Drop the text on to the RichTextBox.  
       richTextBox1.Text = richTextBox1.Text +   
          e.Data.GetData(DataFormats.Text).ToString();  
       richTextBox1.Text = richTextBox1.Text + s;  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void richTextBox1_DragDrop(System::Object ^  sender,  
          System::Windows::Forms::DragEventArgs ^  e)  
       {  
          int i;  
          String ^s;  
  
       // Get start position to drop the text.  
       i = richTextBox1->SelectionStart;  
       s = richTextBox1->Text->Substring(i);  
       richTextBox1->Text = richTextBox1->Text->Substring(0,i);  
  
       // Drop the text on to the RichTextBox.  
       String ^str = String::Concat(richTextBox1->Text, e->Data  
       ->GetData(DataFormats->Text)->ToString());   
       richTextBox1->Text = String::Concat(str, s);  
       }  
    ```  
  
     <span data-ttu-id="fe4cd-115">(Visual C# и [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) поместите следующий код в конструктор формы для регистрации обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="fe4cd-115">(Visual C# and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.richTextBox1.DragDrop += new  
        System.Windows.Forms.DragEventHandler  
        (this.richTextBox1_DragDrop);  
    ```  
  
    ```cpp  
    this->richTextBox1->DragDrop += gcnew   
       System::Windows::Forms::DragEventHandler  
       (this, &Form1::richTextBox1_DragDrop);  
    ```  
  
### <a name="to-test-the-drag-and-drop-functionality-in-your-application"></a><span data-ttu-id="fe4cd-116">Тестирование функциональности перетаскивания в приложении</span><span class="sxs-lookup"><span data-stu-id="fe4cd-116">To test the drag-and-drop functionality in your application</span></span>  
  
1.  <span data-ttu-id="fe4cd-117">Сохраните приложение и выполните его сборку.</span><span class="sxs-lookup"><span data-stu-id="fe4cd-117">Save and build your application.</span></span> <span data-ttu-id="fe4cd-118">Пока сборка выполняется, запустите WordPad.</span><span class="sxs-lookup"><span data-stu-id="fe4cd-118">While it is running, run WordPad.</span></span>  
  
     <span data-ttu-id="fe4cd-119">WordPad — это текстовый редактор, установленный операционной системой Windows, который позволяет выполнять операции перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="fe4cd-119">WordPad is a text editor installed by Windows that allows drag-and-drop operations.</span></span> <span data-ttu-id="fe4cd-120">Чтобы открыть его, нажмите кнопку **Пуск** , выберите пункт **Выполнить**, введите `WordPad` в текстовом поле диалогового окна **Выполнить** и затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fe4cd-120">It is accessible by clicking the **Start** button, selecting **Run**, typing `WordPad` in the text box of the **Run** dialog box, and then clicking **OK**.</span></span>  
  
2.  <span data-ttu-id="fe4cd-121">После открытия WordPad введите в нем строку текста.</span><span class="sxs-lookup"><span data-stu-id="fe4cd-121">Once WordPad is open, type a string of text in it.</span></span> <span data-ttu-id="fe4cd-122">С помощью мыши выделите этот текст и перетащите его в элемент управления <xref:System.Windows.Forms.RichTextBox> в вашем приложении Windows.</span><span class="sxs-lookup"><span data-stu-id="fe4cd-122">Using the mouse, select the text, and then drag the selected text over to the <xref:System.Windows.Forms.RichTextBox> control in your Windows application.</span></span>  
  
     <span data-ttu-id="fe4cd-123">Обратите внимание, что когда вы переводите указатель мыши в элемент управления <xref:System.Windows.Forms.RichTextBox> (и, следовательно, инициируете событие <xref:System.Windows.Forms.RichTextBox.DragEnter> ), курсор изменяется, и можно вставить выделенный текст в элемент управления <xref:System.Windows.Forms.RichTextBox> .</span><span class="sxs-lookup"><span data-stu-id="fe4cd-123">Notice that when you point the mouse at the <xref:System.Windows.Forms.RichTextBox> control (and, consequently, raise the <xref:System.Windows.Forms.RichTextBox.DragEnter> event), the mouse pointer changes and you can drop the selected text into the <xref:System.Windows.Forms.RichTextBox> control.</span></span>  
  
     <span data-ttu-id="fe4cd-124">После отпускания кнопки мыши выделенный текст удаляется (то есть инициируется событие <xref:System.Windows.Forms.RichTextBox.DragDrop> ) и вставляется в элемент управления <xref:System.Windows.Forms.RichTextBox> .</span><span class="sxs-lookup"><span data-stu-id="fe4cd-124">When you release the mouse button, the selected text is dropped (that is, the <xref:System.Windows.Forms.RichTextBox.DragDrop> event is raised) and is inserted within the <xref:System.Windows.Forms.RichTextBox> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe4cd-125">См. также</span><span class="sxs-lookup"><span data-stu-id="fe4cd-125">See also</span></span>
- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="fe4cd-126">Практическое руководство. Выполнение операции перетаскивания и вставки между приложениями</span><span class="sxs-lookup"><span data-stu-id="fe4cd-126">How to: Perform Drag-and-Drop Operations Between Applications</span></span>](../../../../docs/framework/winforms/advanced/how-to-perform-drag-and-drop-operations-between-applications.md)
- [<span data-ttu-id="fe4cd-127">Элемент управления RichTextBox</span><span class="sxs-lookup"><span data-stu-id="fe4cd-127">RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)
- [<span data-ttu-id="fe4cd-128">Элементы управления для использования в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fe4cd-128">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
