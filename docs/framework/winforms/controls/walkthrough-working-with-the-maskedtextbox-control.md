---
title: Пример. Работа с элементом управления MaskedTextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- input [Windows Forms], controlling to ensure validity
- MaskedTextBox control [Windows Forms], walkthroughs
- MaskedTextBox control [Windows Forms], validation
- user input [Windows Forms], controlling
- text [Windows Forms], controls for input
ms.assetid: df60565e-5447-4110-92a6-be1f6ff5faa3
ms.openlocfilehash: bcca6c5f5481d351a39a4e71532cc0f006075128
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-working-with-the-maskedtextbox-control"></a><span data-ttu-id="8f9ec-102">Пример. Работа с элементом управления MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="8f9ec-102">Walkthrough: Working with the MaskedTextBox Control</span></span>
<span data-ttu-id="8f9ec-103">В данном пошаговом руководстве представлены следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="8f9ec-103">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="8f9ec-104">Инициализация <xref:System.Windows.Forms.MaskedTextBox> управления</span><span class="sxs-lookup"><span data-stu-id="8f9ec-104">Initializing the <xref:System.Windows.Forms.MaskedTextBox> control</span></span>  
  
-   <span data-ttu-id="8f9ec-105">С помощью <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> обработчик событий для оповещения пользователя, когда символ не соответствует маске</span><span class="sxs-lookup"><span data-stu-id="8f9ec-105">Using the <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> event handler to alert the user when a character does not conform to the mask</span></span>  
  
-   <span data-ttu-id="8f9ec-106">Присвоение типа <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> свойство и с помощью <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> обработчик событий, чтобы предупреждать пользователей при попытках зафиксировать значение недопустимо для типа</span><span class="sxs-lookup"><span data-stu-id="8f9ec-106">Assigning a type to the <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> property and using the <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> event handler to alert the user when the value they're attempting to commit is not valid for the type</span></span>  
  
## <a name="creating-the-project-and-adding-a-control"></a><span data-ttu-id="8f9ec-107">Создание проекта и добавление элемента управления</span><span class="sxs-lookup"><span data-stu-id="8f9ec-107">Creating the Project and Adding a Control</span></span>  
  
#### <a name="to-add-a-maskedtextbox-control-to-your-form"></a><span data-ttu-id="8f9ec-108">Чтобы добавить элемент управления MaskedTextBox в форму</span><span class="sxs-lookup"><span data-stu-id="8f9ec-108">To add a MaskedTextBox control to your form</span></span>  
  
1.  <span data-ttu-id="8f9ec-109">Откройте форму, на котором требуется разместить <xref:System.Windows.Forms.MaskedTextBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="8f9ec-109">Open the form on which you want to place the <xref:System.Windows.Forms.MaskedTextBox> control.</span></span>  
  
2.  <span data-ttu-id="8f9ec-110">Перетащите <xref:System.Windows.Forms.MaskedTextBox> управления из **элементов** в форму.</span><span class="sxs-lookup"><span data-stu-id="8f9ec-110">Drag a <xref:System.Windows.Forms.MaskedTextBox> control from the **Toolbox** to your form.</span></span>  
  
3.  <span data-ttu-id="8f9ec-111">Щелкните правой кнопкой мыши элемент управления и выберите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="8f9ec-111">Right-click the control and choose **Properties**.</span></span> <span data-ttu-id="8f9ec-112">В **свойства** выберите **маска** свойство и нажмите кнопку **...**  (многоточие) рядом с именем свойства.</span><span class="sxs-lookup"><span data-stu-id="8f9ec-112">In the **Properties** window, select the **Mask** property and click the **...** (ellipsis) button next to the property name.</span></span>  
  
4.  <span data-ttu-id="8f9ec-113">В **маска ввода** выберите **короткого формата даты** маску и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8f9ec-113">In the **Input Mask** dialog box, select the **Short Date** mask and click **OK**.</span></span>  
  
5.  <span data-ttu-id="8f9ec-114">В **свойства** задайте <xref:System.Windows.Forms.MaskedTextBox.BeepOnError%2A> свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="8f9ec-114">In the **Properties** window set the <xref:System.Windows.Forms.MaskedTextBox.BeepOnError%2A> property to `true`.</span></span> <span data-ttu-id="8f9ec-115">Это свойство создает короткий звуковой сигнал всякий раз когда пользователь пытается ввести знак, нарушающий определение маски.</span><span class="sxs-lookup"><span data-stu-id="8f9ec-115">This property causes a short beep to sound every time the user attempts to input a character that violates the mask definition.</span></span>  
  
 <span data-ttu-id="8f9ec-116">Сводка символов, которые поддерживает свойство маски, в разделе «Примечания» <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="8f9ec-116">For a summary of the characters that the Mask property supports, see the Remarks section of the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
## <a name="alert-the-user-to-input-errors"></a><span data-ttu-id="8f9ec-117">Оповещать пользователя об ошибках ввода</span><span class="sxs-lookup"><span data-stu-id="8f9ec-117">Alert the User to Input Errors</span></span>  
  
#### <a name="add-a-balloon-tip-for-rejected-mask-input"></a><span data-ttu-id="8f9ec-118">Добавьте всплывающую подсказку об отклоненном вводе</span><span class="sxs-lookup"><span data-stu-id="8f9ec-118">Add a balloon tip for rejected mask input</span></span>  
  
1.  <span data-ttu-id="8f9ec-119">Вернитесь к **элементов** и добавьте <xref:System.Windows.Forms.ToolTip> в форму.</span><span class="sxs-lookup"><span data-stu-id="8f9ec-119">Return to the **Toolbox** and add a <xref:System.Windows.Forms.ToolTip> to your form.</span></span>  
  
2.  <span data-ttu-id="8f9ec-120">Создайте обработчик событий для <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> событие, вызываемое <xref:System.Windows.Forms.ToolTip> при возникновении ошибок на входе.</span><span class="sxs-lookup"><span data-stu-id="8f9ec-120">Create an event handler for the <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> event that raises the <xref:System.Windows.Forms.ToolTip> when an input error occurs.</span></span> <span data-ttu-id="8f9ec-121">Всплывающая подсказка остается видимым пять секунд, или пока пользователь его щелкает.</span><span class="sxs-lookup"><span data-stu-id="8f9ec-121">The balloon tip remains visible for five seconds, or until the user clicks it.</span></span>  
  
    ```csharp  
    public void Form1_Load(Object sender, EventArgs e)   
    {  
        ... // Other initialization code  
        maskedTextBox1.Mask = "00/00/0000";  
        maskedTextBox1.MaskInputRejected += new MaskInputRejectedEventHandler(maskedTextBox1_MaskInputRejected)  
    }  
  
    void maskedTextBox1_MaskInputRejected(object sender, MaskInputRejectedEventArgs e)  
    {  
        toolTip1.ToolTipTitle = "Invalid Input";  
        toolTip1.Show("We're sorry, but only digits (0-9) are allowed in dates.", maskedTextBox1, maskedTextBox1.Location, 5000);  
    }  
    ```  
  
    ```vb  
    Private Sub Form1_Load(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MyBase.Load  
        Me.ToolTip1.IsBalloon = True  
        Me.MaskedTextBox1.Mask = "00/00/0000"  
    End Sub  
  
    Private Sub MaskedTextBox1_MaskInputRejected(sender as Object, e as MaskInputRejectedEventArgs) Handles MaskedTextBox1.MaskInputRejected  
        ToolTip1.ToolTipTitle = "Invalid Input"  
        ToolTip1.Show("We're sorry, but only digits (0-9) are allowed in dates.", MaskedTextBox1, 5000)  
    End Sub  
    ```  
  
## <a name="alert-the-user-to-a-type-that-is-not-valid"></a><span data-ttu-id="8f9ec-122">Предупредить пользователя о тип, который является недопустимым</span><span class="sxs-lookup"><span data-stu-id="8f9ec-122">Alert the User to a Type that Is Not Valid</span></span>  
  
#### <a name="add-a-balloon-tip-for-invalid-data-types"></a><span data-ttu-id="8f9ec-123">Добавьте всплывающую подсказку о недопустимых типах данных</span><span class="sxs-lookup"><span data-stu-id="8f9ec-123">Add a balloon tip for invalid data types</span></span>  
  
1.  <span data-ttu-id="8f9ec-124">На форме <xref:System.Windows.Forms.Form.Load> обработчика событий, назначьте <xref:System.Type> , представляющий <xref:System.DateTime> тип <xref:System.Windows.Forms.MaskedTextBox> элемента управления <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> свойство:</span><span class="sxs-lookup"><span data-stu-id="8f9ec-124">In your form's <xref:System.Windows.Forms.Form.Load> event handler, assign a <xref:System.Type> object representing the <xref:System.DateTime> type to the <xref:System.Windows.Forms.MaskedTextBox> control's <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> property:</span></span>  
  
    ```csharp  
    private void Form1_Load(Object sender, EventArgs e)  
    {  
        // Other code  
        maskedTextBox1.ValidatingType = typeof(System.DateTime);  
        maskedTextBox1.TypeValidationCompleted += new TypeValidationEventHandler(maskedTextBox1_TypeValidationCompleted);  
    }  
    ```  
  
    ```vb  
    Private Sub Form1_Load(sender as Object, e as EventArgs)  
        // Other code  
        MaskedTextBox1.ValidatingType = GetType(System.DateTime)  
    End Sub  
    ```  
  
2.  <span data-ttu-id="8f9ec-125">Добавьте обработчик событий для события <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted>.</span><span class="sxs-lookup"><span data-stu-id="8f9ec-125">Add an event handler for the <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> event:</span></span>  
  
    ```csharp  
    public void maskedTextBox1_TypeValidationCompleted(object sender, TypeValidationEventArgs e)  
    {  
        if (!e.IsValidInput)  
        {  
           toolTip1.ToolTipTitle = "Invalid Date Value";  
           toolTip1.Show("We're sorry, but the value you entered is not a valid date. Please change the value.", maskedTextBox1, 5000);  
           e.Cancel = true;  
        }  
    }  
    ```  
  
    ```vb  
    Public Sub MaskedTextBox1_TypeValidationCompleted(sender as Object, e as TypeValidationEventArgs)  
        If Not e.IsValidInput Then  
           ToolTip1.ToolTipTitle = "Invalid Date Value"  
           ToolTip1.Show("We're sorry, but the value you entered is not a valid date. Please change the value.", maskedTextBox1, 5000)  
           e.Cancel = True  
        End If  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="8f9ec-126">См. также</span><span class="sxs-lookup"><span data-stu-id="8f9ec-126">See Also</span></span>  
 <xref:System.Windows.Forms.MaskedTextBox>  
 [<span data-ttu-id="8f9ec-127">Элемент управления MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="8f9ec-127">MaskedTextBox Control</span></span>](../../../../docs/framework/winforms/controls/maskedtextbox-control-windows-forms.md)
