---
title: Создание текстового поля для ввода пароля с помощью элемента управления TextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TextBox control [Windows Forms], entering passwords
- password boxes [Windows Forms], creating
- PasswordChar property in text boxes
- passwords [Windows Forms], input mask
- passwords [Windows Forms], password text box
ms.assetid: d105d6b9-3d50-44cd-80d8-2c0e2f486727
ms.openlocfilehash: ff4706a736d15f14cf437c808219e9088773dc6d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731284"
---
# <a name="how-to-create-a-password-text-box-with-the-windows-forms-textbox-control"></a><span data-ttu-id="10ddb-102">Практическое руководство. Создание текстового поля для ввода пароля с помощью элемента управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="10ddb-102">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>

<span data-ttu-id="10ddb-103">Поле пароля — это Windows Forms текстовое поле, которое отображает символы-заместители, когда пользователь вводит строку.</span><span class="sxs-lookup"><span data-stu-id="10ddb-103">A password box is a Windows Forms text box that displays placeholder characters while a user types a string.</span></span>

### <a name="to-create-a-password-text-box"></a><span data-ttu-id="10ddb-104">Создание текстового поля пароля</span><span class="sxs-lookup"><span data-stu-id="10ddb-104">To create a password text box</span></span>

1. <span data-ttu-id="10ddb-105">Задайте для свойства <xref:System.Windows.Forms.TextBox.PasswordChar%2A> элемента управления <xref:System.Windows.Forms.TextBox> конкретный символ.</span><span class="sxs-lookup"><span data-stu-id="10ddb-105">Set the <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property of the <xref:System.Windows.Forms.TextBox> control to a specific character.</span></span>

    <span data-ttu-id="10ddb-106">Свойство <xref:System.Windows.Forms.TextBox.PasswordChar%2A> задает символ, отображаемый в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="10ddb-106">The <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property specifies the character displayed in the text box.</span></span> <span data-ttu-id="10ddb-107">Например, если вы хотите, чтобы в поле пароль отображались звездочки, укажите \* для свойства <xref:System.Windows.Forms.TextBox.PasswordChar%2A> в окно свойств.</span><span class="sxs-lookup"><span data-stu-id="10ddb-107">For example, if you want asterisks displayed in the password box, specify \* for the <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property in the Properties window.</span></span> <span data-ttu-id="10ddb-108">Затем, независимо от того, какой символ пользователь вводит в текстовое поле, отображается звездочка.</span><span class="sxs-lookup"><span data-stu-id="10ddb-108">Then, regardless of what character a user types in the text box, an asterisk is displayed.</span></span>

2. <span data-ttu-id="10ddb-109">Используемых Задайте свойство <xref:System.Windows.Forms.TextBoxBase.MaxLength%2A>.</span><span class="sxs-lookup"><span data-stu-id="10ddb-109">(Optional) Set the <xref:System.Windows.Forms.TextBoxBase.MaxLength%2A> property.</span></span> <span data-ttu-id="10ddb-110">Свойство определяет, сколько символов можно ввести в текстовое поле.</span><span class="sxs-lookup"><span data-stu-id="10ddb-110">The property determines how many characters can be typed in the text box.</span></span> <span data-ttu-id="10ddb-111">Если превышена максимальная длина, система выдает звуковой сигнал, и текстовое поле не принимает больше символов.</span><span class="sxs-lookup"><span data-stu-id="10ddb-111">If the maximum length is exceeded, the system emits a beep and the text box does not accept any more characters.</span></span> <span data-ttu-id="10ddb-112">Обратите внимание, что это может быть нежелательно, так как максимальная длина пароля может быть использована хакерами, пытающимися угадать пароль.</span><span class="sxs-lookup"><span data-stu-id="10ddb-112">Note that you may not wish to do this as the maximum length of a password may be of use to hackers who are trying to guess the password.</span></span>

    <span data-ttu-id="10ddb-113">В следующем примере кода показано, как инициализировать текстовое поле, которое будет принимать строку длиной до 14 символов и отображать звездочки вместо строки.</span><span class="sxs-lookup"><span data-stu-id="10ddb-113">The following code example shows how to initialize a text box that will accept a string up to 14 characters long and display asterisks in place of the string.</span></span> <span data-ttu-id="10ddb-114">Процедура `InitializeMyControl` не будет выполняться автоматически; Он должен быть вызван.</span><span class="sxs-lookup"><span data-stu-id="10ddb-114">The `InitializeMyControl` procedure will not execute automatically; it must be called.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="10ddb-115">Использование свойства <xref:System.Windows.Forms.TextBox.PasswordChar%2A> в текстовом поле помогает гарантировать, что другие пользователи не смогут определить пароль пользователя, если он следит за его вводом.</span><span class="sxs-lookup"><span data-stu-id="10ddb-115">Using the <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property on a text box can help ensure that other people will not be able to determine a user's password if they observe the user entering it.</span></span> <span data-ttu-id="10ddb-116">Эта мера безопасности не охватывает никаких операций хранения или передачи пароля, которые могут возникать из-за логики приложения.</span><span class="sxs-lookup"><span data-stu-id="10ddb-116">This security measure does not cover any sort of storage or transmission of the password that can occur due to your application logic.</span></span> <span data-ttu-id="10ddb-117">Поскольку введенный текст не шифруется каким-либо образом, его следует обрабатывать так же, как любые другие конфиденциальные данные.</span><span class="sxs-lookup"><span data-stu-id="10ddb-117">Because the text entered is not encrypted in any way, you should treat it as you would any other confidential data.</span></span> <span data-ttu-id="10ddb-118">Несмотря на то, что он не отображается, пароль по-прежнему обрабатывается как обычный текст (если не была реализована дополнительная мера безопасности).</span><span class="sxs-lookup"><span data-stu-id="10ddb-118">Even though it does not appear as such, the password is still being treated as a plain-text string (unless you have implemented some additional security measure).</span></span>

    ```vb
    Private Sub InitializeMyControl()
       ' Set to no text.
       TextBox1.Text = ""
       ' The password character is an asterisk.
       TextBox1.PasswordChar = "*"
       ' The control will allow no more than 14 characters.
       TextBox1.MaxLength = 14
    End Sub
    ```

    ```csharp
    private void InitializeMyControl()
    {
       // Set to no text.
       textBox1.Text = "";
       // The password character is an asterisk.
       textBox1.PasswordChar = '*';
       // The control will allow no more than 14 characters.
       textBox1.MaxLength = 14;
    }
    ```

    ```cpp
    private:
       void InitializeMyControl()
       {
          // Set to no text.
          textBox1->Text = "";
          // The password character is an asterisk.
          textBox1->PasswordChar = '*';
          // The control will allow no more than 14 characters.
          textBox1->MaxLength = 14;
       }
    ```

## <a name="see-also"></a><span data-ttu-id="10ddb-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="10ddb-119">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="10ddb-120">Общие сведения об элементе управления TextBox</span><span class="sxs-lookup"><span data-stu-id="10ddb-120">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="10ddb-121">Практическое руководство. Управление положением курсора в элементе управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="10ddb-121">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="10ddb-122">Практическое руководство. Создание текстового поля только для чтения</span><span class="sxs-lookup"><span data-stu-id="10ddb-122">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="10ddb-123">Практическое руководство. Добавление кавычек в строку</span><span class="sxs-lookup"><span data-stu-id="10ddb-123">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="10ddb-124">Практическое руководство. Выделение текста в элементе управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="10ddb-124">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="10ddb-125">Практическое руководство. Многострочные элементы управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="10ddb-125">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="10ddb-126">Элемент управления TextBox</span><span class="sxs-lookup"><span data-stu-id="10ddb-126">TextBox Control</span></span>](textbox-control-windows-forms.md)
