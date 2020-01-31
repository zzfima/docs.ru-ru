---
title: Добавление элементов управления
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, adding to form
- controls [Windows Forms], adding
ms.assetid: 2af86001-9d62-4154-87fb-66db2c3cd9fd
ms.openlocfilehash: 560089a23fbcccb0f0d5683a95ad06dd9c59556d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743956"
---
# <a name="how-to-add-controls-to-windows-forms"></a><span data-ttu-id="4b19e-102">Практическое руководство. Добавление элементов управления в формы Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4b19e-102">How to: Add Controls to Windows Forms</span></span>

<span data-ttu-id="4b19e-103">Большинство форм разрабатываются путем добавления элементов управления на поверхность формы для определения пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="4b19e-103">Most forms are designed by adding controls to the surface of the form to define a user interface (UI).</span></span> <span data-ttu-id="4b19e-104">*Элемент управления* — это компонент в форме, используемый для вывода информации или ввода данных пользователем.</span><span class="sxs-lookup"><span data-stu-id="4b19e-104">A *control* is a component on a form used to display information or accept user input.</span></span> <span data-ttu-id="4b19e-105">Дополнительные сведения об элементах управления см. в разделе [элементы управления Windows Forms](index.md).</span><span class="sxs-lookup"><span data-stu-id="4b19e-105">For more information about controls, see [Windows Forms Controls](index.md).</span></span>

## <a name="to-draw-a-control-on-a-form"></a><span data-ttu-id="4b19e-106">Рисование элемента управления в форме</span><span class="sxs-lookup"><span data-stu-id="4b19e-106">To draw a control on a form</span></span>

1. <span data-ttu-id="4b19e-107">Откройте форму.</span><span class="sxs-lookup"><span data-stu-id="4b19e-107">Open the form.</span></span> <span data-ttu-id="4b19e-108">Дополнительные сведения см. в разделе [Практическое руководство. Отображение форм Windows Forms в конструкторе](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="4b19e-108">For more information, see [How to: Display Windows Forms in the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span></span>

2. <span data-ttu-id="4b19e-109">В **области элементов**щелкните элемент управления, который необходимо добавить в форму.</span><span class="sxs-lookup"><span data-stu-id="4b19e-109">In the **Toolbox**, click the control you want to add to your form.</span></span>

3. <span data-ttu-id="4b19e-110">В области формы нажмите на место желаемого положения верхнего левого угла элемента и перетащите указатель к месту желаемого положения нижнего правого угла элемента.</span><span class="sxs-lookup"><span data-stu-id="4b19e-110">On the form, click where you want the upper-left corner of the control to be located, and drag to where you want the lower-right corner of the control to be located.</span></span>

    <span data-ttu-id="4b19e-111">Элемент управления добавляется в форму с указанными расположением и размером.</span><span class="sxs-lookup"><span data-stu-id="4b19e-111">The control is added to the form with the specified location and size.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4b19e-112">Каждый элемент управления имеет определенный размер по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4b19e-112">Each control has a default size defined.</span></span> <span data-ttu-id="4b19e-113">Можно добавить элемент управления на форму с его размером по умолчанию, перетащив его из **панели элементов** на форму.</span><span class="sxs-lookup"><span data-stu-id="4b19e-113">You can add a control to your form in the control's default size by dragging it from the **Toolbox** to the form.</span></span>

## <a name="to-drag-a-control-to-a-form"></a><span data-ttu-id="4b19e-114">Чтобы перетащить элемент управления на форму</span><span class="sxs-lookup"><span data-stu-id="4b19e-114">To drag a control to a form</span></span>

1. <span data-ttu-id="4b19e-115">Откройте форму.</span><span class="sxs-lookup"><span data-stu-id="4b19e-115">Open the form.</span></span> <span data-ttu-id="4b19e-116">Дополнительные сведения см. в разделе [Практическое руководство. Отображение форм Windows Forms в конструкторе](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="4b19e-116">For more information, see [How to: Display Windows Forms in the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span></span>

2. <span data-ttu-id="4b19e-117">На **панели элементов**щелкните нужный элемент управления и перетащите его в форму.</span><span class="sxs-lookup"><span data-stu-id="4b19e-117">In the **Toolbox**, click the control you want and drag it to your form.</span></span>

    <span data-ttu-id="4b19e-118">Элемент управления будет добавлен на форму в указанном месте с размером по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4b19e-118">The control is added to the form at the specified location in its default size.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4b19e-119">Можно дважды щелкнуть элемент управления на **нанели элементов**, чтобы добавить его в левом верхнем углу формы с размером по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4b19e-119">You can double-click a control in the **Toolbox** to add it to the upper-left corner of the form in its default size.</span></span>

    <span data-ttu-id="4b19e-120">Вы можете добавить элементы управления на форму динамически во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="4b19e-120">You can also add controls dynamically to a form at run time.</span></span> <span data-ttu-id="4b19e-121">В следующем примере кода элемент управления <xref:System.Windows.Forms.TextBox> будет добавлен на форму при нажатии элемента управления <xref:System.Windows.Forms.Button>.</span><span class="sxs-lookup"><span data-stu-id="4b19e-121">In the following code example, a <xref:System.Windows.Forms.TextBox> control will be added to the form when a <xref:System.Windows.Forms.Button> control is clicked.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4b19e-122">Следующая процедура требует наличия формы с уже расположенным на ней элементом управления **button** — `Button1`.</span><span class="sxs-lookup"><span data-stu-id="4b19e-122">The following procedure requires the existence of a form with a **Button** control, `Button1`, already placed on it.</span></span>

## <a name="to-add-a-control-to-a-form-programmatically"></a><span data-ttu-id="4b19e-123">Добавление элемента управления в форму программным способом</span><span class="sxs-lookup"><span data-stu-id="4b19e-123">To add a control to a form programmatically</span></span>

1. <span data-ttu-id="4b19e-124">В метод, обрабатывающий событие `Click` кнопки в классе формы, вставьте код, аналогичный приведенному ниже, чтобы создать ссылку на переменную элемента управления, установить его свойство `Location` и добавить элемент управления на форму.</span><span class="sxs-lookup"><span data-stu-id="4b19e-124">In the method that handles the button's `Click` event within your form's class, insert code similar to the following to add a reference to your control variable, set the control's `Location`, and add the control.</span></span>

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
    > <span data-ttu-id="4b19e-125">Кроме того, можно добавить код для инициализации других свойств элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4b19e-125">You can also add code to initialize other properties of the control.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="4b19e-126">Создание ссылки на вредоносный элемент `UserControl` может поставить локальный компьютер под угрозу атаки по сети.</span><span class="sxs-lookup"><span data-stu-id="4b19e-126">You might expose your local computer to a security risk through the network by referencing a malicious `UserControl`.</span></span> <span data-ttu-id="4b19e-127">Это может произойти только в том случае, если злоумышленник создаст небезопасный пользовательский элемент управления, а затем вы по ошибке добавите его в проект.</span><span class="sxs-lookup"><span data-stu-id="4b19e-127">This would only be a concern in the case of a malicious person creating a damaging custom control, followed by you mistakenly adding it to your project.</span></span>

## <a name="see-also"></a><span data-ttu-id="4b19e-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="4b19e-128">See also</span></span>

- [<span data-ttu-id="4b19e-129">Элементы управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4b19e-129">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="4b19e-130">Практическое руководство. Изменение размера элементов управления в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4b19e-130">How to: Resize Controls on Windows Forms</span></span>](how-to-resize-controls-on-windows-forms.md)
- [<span data-ttu-id="4b19e-131">Практическое руководство. Определение текста, отображаемого элементом управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4b19e-131">How to: Set the Text Displayed by a Windows Forms Control</span></span>](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [<span data-ttu-id="4b19e-132">Элементы управления для использования в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4b19e-132">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
