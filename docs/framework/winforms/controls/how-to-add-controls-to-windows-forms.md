---
title: Практическое руководство. Добавление элементов управления в формы Windows Forms.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, adding to form
- controls [Windows Forms], adding
ms.assetid: 2af86001-9d62-4154-87fb-66db2c3cd9fd
ms.openlocfilehash: 2dd048fb074d1ec5bb7bc0a67f196d5d51281545
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33528481"
---
# <a name="how-to-add-controls-to-windows-forms"></a><span data-ttu-id="64e8b-102">Практическое руководство. Добавление элементов управления в формы Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="64e8b-102">How to: Add Controls to Windows Forms</span></span>
<span data-ttu-id="64e8b-103">Большинство форм разрабатываются путем добавления элементов управления в область формы для создания пользовательского интерфейса (UI).</span><span class="sxs-lookup"><span data-stu-id="64e8b-103">Most forms are designed by adding controls to the surface of the form to define a user interface (UI).</span></span> <span data-ttu-id="64e8b-104">Объект *управления* — это компонент на форме, использующийся для отображения сведений или ввода пользователя.</span><span class="sxs-lookup"><span data-stu-id="64e8b-104">A *control* is a component on a form used to display information or accept user input.</span></span> <span data-ttu-id="64e8b-105">Дополнительные сведения об элементах управления см. в разделе [элементов управления Windows Forms](../../../../docs/framework/winforms/controls/index.md).</span><span class="sxs-lookup"><span data-stu-id="64e8b-105">For more information about controls, see [Windows Forms Controls](../../../../docs/framework/winforms/controls/index.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="64e8b-106">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="64e8b-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="64e8b-107">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="64e8b-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="64e8b-108">Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="64e8b-108">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-draw-a-control-on-a-form"></a><span data-ttu-id="64e8b-109">Чтобы нарисовать элемент управления на форме</span><span class="sxs-lookup"><span data-stu-id="64e8b-109">To draw a control on a form</span></span>  
  
1.  <span data-ttu-id="64e8b-110">Откройте форму.</span><span class="sxs-lookup"><span data-stu-id="64e8b-110">Open the form.</span></span> <span data-ttu-id="64e8b-111">Дополнительные сведения см. в разделе [Практическое руководство. Отображение форм Windows Forms в конструкторе](http://msdn.microsoft.com/library/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).</span><span class="sxs-lookup"><span data-stu-id="64e8b-111">For more information, see [How to: Display Windows Forms in the Designer](http://msdn.microsoft.com/library/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).</span></span>  
  
2.  <span data-ttu-id="64e8b-112">В **элементов**, щелкните элемент управления, который требуется добавить в форму.</span><span class="sxs-lookup"><span data-stu-id="64e8b-112">In the **Toolbox**, click the control you want to add to your form.</span></span>  
  
3.  <span data-ttu-id="64e8b-113">В области формы нажмите на место желаемого положения верхнего левого угла элемента и перетащите указатель к месту желаемого положения нижнего правого угла элемента.</span><span class="sxs-lookup"><span data-stu-id="64e8b-113">On the form, click where you want the upper-left corner of the control to be located, and drag to where you want the lower-right corner of the control to be located.</span></span>  
  
     <span data-ttu-id="64e8b-114">Элемент управления добавляется в форму с заданным расположением и размером.</span><span class="sxs-lookup"><span data-stu-id="64e8b-114">The control is added to the form with the specified location and size.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="64e8b-115">Каждый элемент управления имеет определенный размер по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="64e8b-115">Each control has a default size defined.</span></span> <span data-ttu-id="64e8b-116">Можно добавить элемент управления на форму с его размером по умолчанию, перетащив его из **панели элементов** на форму.</span><span class="sxs-lookup"><span data-stu-id="64e8b-116">You can add a control to your form in the control's default size by dragging it from the **Toolbox** to the form.</span></span>  
  
### <a name="to-drag-a-control-to-a-form"></a><span data-ttu-id="64e8b-117">Чтобы перетащить элемент управления на форму</span><span class="sxs-lookup"><span data-stu-id="64e8b-117">To drag a control to a form</span></span>  
  
1.  <span data-ttu-id="64e8b-118">Откройте форму.</span><span class="sxs-lookup"><span data-stu-id="64e8b-118">Open the form.</span></span> <span data-ttu-id="64e8b-119">Дополнительные сведения см. в разделе [Практическое руководство. Отображение форм Windows Forms в конструкторе](http://msdn.microsoft.com/library/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).</span><span class="sxs-lookup"><span data-stu-id="64e8b-119">For more information, see [How to: Display Windows Forms in the Designer](http://msdn.microsoft.com/library/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).</span></span>  
  
2.  <span data-ttu-id="64e8b-120">В **элементов**, щелкните и перетащите его в форму элемент управления.</span><span class="sxs-lookup"><span data-stu-id="64e8b-120">In the **Toolbox**, click the control you want and drag it to your form.</span></span>  
  
     <span data-ttu-id="64e8b-121">Элемент управления будет добавлен на форму в указанном месте с размером по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="64e8b-121">The control is added to the form at the specified location in its default size.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="64e8b-122">Можно дважды щелкнуть элемент управления на **нанели элементов**, чтобы добавить его в левом верхнем углу формы с размером по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="64e8b-122">You can double-click a control in the **Toolbox** to add it to the upper-left corner of the form in its default size.</span></span>  
  
     <span data-ttu-id="64e8b-123">Вы можете добавить элементы управления на форму динамически во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="64e8b-123">You can also add controls dynamically to a form at run time.</span></span> <span data-ttu-id="64e8b-124">В следующем примере кода элемент управления <xref:System.Windows.Forms.TextBox> будет добавлен на форму при нажатии элемента управления <xref:System.Windows.Forms.Button>.</span><span class="sxs-lookup"><span data-stu-id="64e8b-124">In the following code example, a <xref:System.Windows.Forms.TextBox> control will be added to the form when a <xref:System.Windows.Forms.Button> control is clicked.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="64e8b-125">Следующая процедура требует наличия формы с уже расположенным на ней элементом управления **button** — `Button1`.</span><span class="sxs-lookup"><span data-stu-id="64e8b-125">The following procedure requires the existence of a form with a **Button** control, `Button1`, already placed on it.</span></span>  
  
### <a name="to-add-a-control-to-a-form-programmatically"></a><span data-ttu-id="64e8b-126">Добавление в форму элемента управления программными средствами</span><span class="sxs-lookup"><span data-stu-id="64e8b-126">To add a control to a form programmatically</span></span>  
  
1.  <span data-ttu-id="64e8b-127">В метод, обрабатывающий событие `Click` кнопки в классе формы, вставьте код, аналогичный приведенному ниже, чтобы создать ссылку на переменную элемента управления, установить его свойство `Location` и добавить элемент управления на форму.</span><span class="sxs-lookup"><span data-stu-id="64e8b-127">In the method that handles the button's `Click` event within your form's class, insert code similar to the following to add a reference to your control variable, set the control's `Location`, and add the control.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       Dim MyText As New TextBox()  
       MyText.Location = New Point(25, 25)  
       Me.Controls.Add(MyText)  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)   
    {  
       TextBox myText = new TextBox();  
       myText.Location = new Point(25,25);  
       this.Controls.Add (myText);  
    }  
    ```  
  
    ```cpp  
    private:  
      System::Void button1_Click(System::Object ^  sender,  
        System::EventArgs ^  e)  
      {  
        TextBox ^ myText = gcnew TextBox();  
        myText->Location = Point(25,25);  
        this->Controls->Add(myText);  
      }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="64e8b-128">Кроме того, можно добавить код для инициализации других свойств элемента управления.</span><span class="sxs-lookup"><span data-stu-id="64e8b-128">You can also add code to initialize other properties of the control.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="64e8b-129">Создание ссылки на вредоносный элемент `UserControl` может поставить локальный компьютер под угрозу атаки по сети.</span><span class="sxs-lookup"><span data-stu-id="64e8b-129">You might expose your local computer to a security risk through the network by referencing a malicious `UserControl`.</span></span> <span data-ttu-id="64e8b-130">Это может произойти только в том случае, если злоумышленник создаст небезопасный пользовательский элемент управления, а затем вы по ошибке добавите его в проект.</span><span class="sxs-lookup"><span data-stu-id="64e8b-130">This would only be a concern in the case of a malicious person creating a damaging custom control, followed by you mistakenly adding it to your project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64e8b-131">См. также</span><span class="sxs-lookup"><span data-stu-id="64e8b-131">See Also</span></span>  
 [<span data-ttu-id="64e8b-132">Элементы управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="64e8b-132">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="64e8b-133">Упорядочение элементов управления в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="64e8b-133">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="64e8b-134">Практическое руководство. Изменение размера элементов управления в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="64e8b-134">How to: Resize Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-resize-controls-on-windows-forms.md)  
 [<span data-ttu-id="64e8b-135">Практическое руководство. Определение текста, отображаемого элементом управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="64e8b-135">How to: Set the Text Displayed by a Windows Forms Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)  
 [<span data-ttu-id="64e8b-136">Элементы управления для использования в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="64e8b-136">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
