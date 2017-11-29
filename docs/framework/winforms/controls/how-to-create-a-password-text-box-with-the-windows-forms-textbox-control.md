---
title: "Практическое руководство. Создание текстового поля для ввода пароля с помощью элемента управления TextBox в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: caf5cef9e23134715101545902e32e72d63c0aac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-password-text-box-with-the-windows-forms-textbox-control"></a><span data-ttu-id="3b950-102">Практическое руководство. Создание текстового поля для ввода пароля с помощью элемента управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3b950-102">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>
<span data-ttu-id="3b950-103">Поле пароля — это текстовое поле Windows Forms, выводит заполнителем, когда пользователь вводит строку.</span><span class="sxs-lookup"><span data-stu-id="3b950-103">A password box is a Windows Forms text box that displays placeholder characters while a user types a string.</span></span>  
  
### <a name="to-create-a-password-text-box"></a><span data-ttu-id="3b950-104">Чтобы создать текстовое поле пароля</span><span class="sxs-lookup"><span data-stu-id="3b950-104">To create a password text box</span></span>  
  
1.  <span data-ttu-id="3b950-105">Задать <xref:System.Windows.Forms.TextBox.PasswordChar%2A> свойства <xref:System.Windows.Forms.TextBox> элемента управления к определенному символу.</span><span class="sxs-lookup"><span data-stu-id="3b950-105">Set the <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property of the <xref:System.Windows.Forms.TextBox> control to a specific character.</span></span>  
  
     <span data-ttu-id="3b950-106"><xref:System.Windows.Forms.TextBox.PasswordChar%2A> Свойство определяет знак, используемый в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="3b950-106">The <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property specifies the character displayed in the text box.</span></span> <span data-ttu-id="3b950-107">К примеру, если вы хотите звездочки, отображается в поле "пароль", указать * для <xref:System.Windows.Forms.TextBox.PasswordChar%2A> в окне свойств.</span><span class="sxs-lookup"><span data-stu-id="3b950-107">For example, if you want asterisks displayed in the password box, specify * for the <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property in the Properties window.</span></span> <span data-ttu-id="3b950-108">То какие бы знаки пользователь вводит в текстовое поле, отображается звездочка.</span><span class="sxs-lookup"><span data-stu-id="3b950-108">Then, regardless of what character a user types in the text box, an asterisk is displayed.</span></span>  
  
2.  <span data-ttu-id="3b950-109">(Необязательно) Задать <xref:System.Windows.Forms.TextBoxBase.MaxLength%2A> свойства.</span><span class="sxs-lookup"><span data-stu-id="3b950-109">(Optional) Set the <xref:System.Windows.Forms.TextBoxBase.MaxLength%2A> property.</span></span> <span data-ttu-id="3b950-110">Это свойство определяет, сколько символов можно ввести в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="3b950-110">The property determines how many characters can be typed in the text box.</span></span> <span data-ttu-id="3b950-111">В случае превышения максимального система издает звуковой сигнал и текстовое поле не принимает любые дополнительные символы.</span><span class="sxs-lookup"><span data-stu-id="3b950-111">If the maximum length is exceeded, the system emits a beep and the text box does not accept any more characters.</span></span> <span data-ttu-id="3b950-112">Обратите внимание, что вы можете делать это в качестве максимальной длины пароля не может быть использована злоумышленниками, пытающимися подобрать пароль.</span><span class="sxs-lookup"><span data-stu-id="3b950-112">Note that you may not wish to do this as the maximum length of a password may be of use to hackers who are trying to guess the password.</span></span>  
  
     <span data-ttu-id="3b950-113">В следующем примере кода показано, как инициализировать текстовое поле, будет принимать строку до 14 символов и должны отображаться звездочки вместо строки.</span><span class="sxs-lookup"><span data-stu-id="3b950-113">The following code example shows how to initialize a text box that will accept a string up to 14 characters long and display asterisks in place of the string.</span></span> <span data-ttu-id="3b950-114">`InitializeMyControl` Процедура не выполняется автоматически; он должен быть вызван.</span><span class="sxs-lookup"><span data-stu-id="3b950-114">The `InitializeMyControl` procedure will not execute automatically; it must be called.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="3b950-115">С помощью <xref:System.Windows.Forms.TextBox.PasswordChar%2A> свойство текстового поля может помочь обеспечить пользователям не может определить пароль пользователя, наблюдая за его вводом.</span><span class="sxs-lookup"><span data-stu-id="3b950-115">Using the <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property on a text box can help ensure that other people will not be able to determine a user's password if they observe the user entering it.</span></span> <span data-ttu-id="3b950-116">Эта мера безопасности не влияет на процесс сохранения или передачи пароля, может произойти из-за логики приложения.</span><span class="sxs-lookup"><span data-stu-id="3b950-116">This security measure does not cover any sort of storage or transmission of the password that can occur due to your application logic.</span></span> <span data-ttu-id="3b950-117">Поскольку введенный текст не зашифрован каким-либо образом, необходимо рассматривать его как и другие конфиденциальные данные.</span><span class="sxs-lookup"><span data-stu-id="3b950-117">Because the text entered is not encrypted in any way, you should treat it as you would any other confidential data.</span></span> <span data-ttu-id="3b950-118">Несмотря на то, что он не отображается таким образом, пароль по-прежнему обрабатывается как обычный текст (если не реализовано дополнительные меры безопасности).</span><span class="sxs-lookup"><span data-stu-id="3b950-118">Even though it does not appear as such, the password is still being treated as a plain-text string (unless you have implemented some additional security measure).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3b950-119">См. также</span><span class="sxs-lookup"><span data-stu-id="3b950-119">See Also</span></span>  
 <xref:System.Windows.Forms.TextBox>  
 [<span data-ttu-id="3b950-120">Общие сведения об элементе управления TextBox</span><span class="sxs-lookup"><span data-stu-id="3b950-120">TextBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)  
 [<span data-ttu-id="3b950-121">Практическое руководство. Управление положением курсора в элементе управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3b950-121">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 [<span data-ttu-id="3b950-122">Практическое руководство. Создание текстового поля только для чтения</span><span class="sxs-lookup"><span data-stu-id="3b950-122">How to: Create a Read-Only Text Box</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)  
 [<span data-ttu-id="3b950-123">Практическое руководство. Добавление кавычек в строку</span><span class="sxs-lookup"><span data-stu-id="3b950-123">How to: Put Quotation Marks in a String</span></span>](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 [<span data-ttu-id="3b950-124">Практическое руководство. Выделение текста в элементе управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3b950-124">How to: Select Text in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="3b950-125">Практическое руководство. Многострочные элементы управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3b950-125">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="3b950-126">Элемент управления TextBox</span><span class="sxs-lookup"><span data-stu-id="3b950-126">TextBox Control</span></span>](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
