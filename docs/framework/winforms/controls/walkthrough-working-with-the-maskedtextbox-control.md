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
ms.openlocfilehash: db32b3ec88a07747ea3e286af9f04edce3f1ba3b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182057"
---
# <a name="walkthrough-working-with-the-maskedtextbox-control"></a><span data-ttu-id="80878-102">Пример. Работа с элементом управления MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="80878-102">Walkthrough: Working with the MaskedTextBox Control</span></span>
<span data-ttu-id="80878-103">В данном пошаговом руководстве представлены следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="80878-103">Tasks illustrated in this walkthrough include:</span></span>  
  
- <span data-ttu-id="80878-104">Инициализация <xref:System.Windows.Forms.MaskedTextBox> управления</span><span class="sxs-lookup"><span data-stu-id="80878-104">Initializing the <xref:System.Windows.Forms.MaskedTextBox> control</span></span>  
  
- <span data-ttu-id="80878-105">Использование <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> обработчика событий для оповещения пользователя о том, что персонаж не соответствует маске</span><span class="sxs-lookup"><span data-stu-id="80878-105">Using the <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> event handler to alert the user when a character does not conform to the mask</span></span>  
  
- <span data-ttu-id="80878-106">Назначение типа <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> к свойству и <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> использование обработчика событий для оповещения пользователя о том, что значение, которое он пытается совершить, не является действительным для типа</span><span class="sxs-lookup"><span data-stu-id="80878-106">Assigning a type to the <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> property and using the <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> event handler to alert the user when the value they're attempting to commit is not valid for the type</span></span>  
  
## <a name="creating-the-project-and-adding-a-control"></a><span data-ttu-id="80878-107">Создание проекта и добавление элемента управления</span><span class="sxs-lookup"><span data-stu-id="80878-107">Creating the Project and Adding a Control</span></span>  
  
#### <a name="to-add-a-maskedtextbox-control-to-your-form"></a><span data-ttu-id="80878-108">Добавление элемента управления MaskedTextBox в форму</span><span class="sxs-lookup"><span data-stu-id="80878-108">To add a MaskedTextBox control to your form</span></span>  
  
1. <span data-ttu-id="80878-109">Откройте форму, на которой <xref:System.Windows.Forms.MaskedTextBox> вы хотите разместить элемент управления.</span><span class="sxs-lookup"><span data-stu-id="80878-109">Open the form on which you want to place the <xref:System.Windows.Forms.MaskedTextBox> control.</span></span>  
  
2. <span data-ttu-id="80878-110">Перетащите <xref:System.Windows.Forms.MaskedTextBox> элемент управления из **ящика инструментов** в форму.</span><span class="sxs-lookup"><span data-stu-id="80878-110">Drag a <xref:System.Windows.Forms.MaskedTextBox> control from the **Toolbox** to your form.</span></span>  
  
3. <span data-ttu-id="80878-111">Нажмите правой кнопкой мыши управления и выбрать **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="80878-111">Right-click the control and choose **Properties**.</span></span> <span data-ttu-id="80878-112">В окне **Свойства** выберите свойство **Маска** и нажмите кнопку **...** (ellipsis) рядом с именем свойства.</span><span class="sxs-lookup"><span data-stu-id="80878-112">In the **Properties** window, select the **Mask** property and click the **...** (ellipsis) button next to the property name.</span></span>  
  
4. <span data-ttu-id="80878-113">В диалоговом окне **ввода маски** выберите маску **«Короткая дата»** и **нажмите OK.**</span><span class="sxs-lookup"><span data-stu-id="80878-113">In the **Input Mask** dialog box, select the **Short Date** mask and click **OK**.</span></span>  
  
5. <span data-ttu-id="80878-114">В **Properties** окне Свойства <xref:System.Windows.Forms.MaskedTextBox.BeepOnError%2A> установить свойство `true`.</span><span class="sxs-lookup"><span data-stu-id="80878-114">In the **Properties** window set the <xref:System.Windows.Forms.MaskedTextBox.BeepOnError%2A> property to `true`.</span></span> <span data-ttu-id="80878-115">Это свойство вызывает короткий звуковой сигнал, чтобы звучать каждый раз, когда пользователь пытается ввести символ, который нарушает определение маски.</span><span class="sxs-lookup"><span data-stu-id="80878-115">This property causes a short beep to sound every time the user attempts to input a character that violates the mask definition.</span></span>  
  
 <span data-ttu-id="80878-116">Для краткого изложения символов, которые поддерживает свойство <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> Маска, см.</span><span class="sxs-lookup"><span data-stu-id="80878-116">For a summary of the characters that the Mask property supports, see the Remarks section of the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
## <a name="alert-the-user-to-input-errors"></a><span data-ttu-id="80878-117">Предупредите пользователя об ошибках ввода</span><span class="sxs-lookup"><span data-stu-id="80878-117">Alert the User to Input Errors</span></span>  
  
#### <a name="add-a-balloon-tip-for-rejected-mask-input"></a><span data-ttu-id="80878-118">Добавить наконечник шара для отклоненного ввода маски</span><span class="sxs-lookup"><span data-stu-id="80878-118">Add a balloon tip for rejected mask input</span></span>  
  
1. <span data-ttu-id="80878-119">Вернитесь в **Toolbox** <xref:System.Windows.Forms.ToolTip> и добавьте в свою форму.</span><span class="sxs-lookup"><span data-stu-id="80878-119">Return to the **Toolbox** and add a <xref:System.Windows.Forms.ToolTip> to your form.</span></span>  
  
2. <span data-ttu-id="80878-120">Создайте обработчик <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> событий, <xref:System.Windows.Forms.ToolTip> который повышает, когда происходит ошибка ввода.</span><span class="sxs-lookup"><span data-stu-id="80878-120">Create an event handler for the <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> event that raises the <xref:System.Windows.Forms.ToolTip> when an input error occurs.</span></span> <span data-ttu-id="80878-121">Наконечник шарика остается видимым в течение пяти секунд, или до тех пор, пока пользователь не нажмет на него.</span><span class="sxs-lookup"><span data-stu-id="80878-121">The balloon tip remains visible for five seconds, or until the user clicks it.</span></span>  
  
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
  
## <a name="alert-the-user-to-a-type-that-is-not-valid"></a><span data-ttu-id="80878-122">Оповещение пользователя о недопустимом типе</span><span class="sxs-lookup"><span data-stu-id="80878-122">Alert the User to a Type that Is Not Valid</span></span>  
  
#### <a name="add-a-balloon-tip-for-invalid-data-types"></a><span data-ttu-id="80878-123">Добавление наконечника шара для недействительных типов данных</span><span class="sxs-lookup"><span data-stu-id="80878-123">Add a balloon tip for invalid data types</span></span>  
  
1. <span data-ttu-id="80878-124">В обработчике <xref:System.Windows.Forms.Form.Load> событий вашей <xref:System.Type> формы присвоите объекту, представляющему <xref:System.DateTime> тип, свойство <xref:System.Windows.Forms.MaskedTextBox> <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> управления:</span><span class="sxs-lookup"><span data-stu-id="80878-124">In your form's <xref:System.Windows.Forms.Form.Load> event handler, assign a <xref:System.Type> object representing the <xref:System.DateTime> type to the <xref:System.Windows.Forms.MaskedTextBox> control's <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> property:</span></span>  
  
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
  
2. <span data-ttu-id="80878-125">Добавьте обработчик событий для события <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted>.</span><span class="sxs-lookup"><span data-stu-id="80878-125">Add an event handler for the <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> event:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="80878-126">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="80878-126">See also</span></span>

- <xref:System.Windows.Forms.MaskedTextBox>
- [<span data-ttu-id="80878-127">Элемент управления MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="80878-127">MaskedTextBox Control</span></span>](maskedtextbox-control-windows-forms.md)
