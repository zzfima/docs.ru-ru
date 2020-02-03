---
title: Отображение значков ошибок для проверки формы с помощью компонента ErrorProvider
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- errors [Windows Forms], displaying to users
- error icons
- ErrorProvider component [Windows Forms], displaying error icons
- error messages [Windows Forms], displaying icons
ms.assetid: 3b681a32-9db4-497b-a34b-34980eabee46
ms.openlocfilehash: a1e346e332db489351f59c9a0c03ae731baf3dc3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745910"
---
# <a name="how-to-display-error-icons-for-form-validation-with-the-windows-forms-errorprovider-component"></a><span data-ttu-id="4411f-102">Практическое руководство. Отображение значков ошибок при проверке введенных в форму данных с помощью компонента ErrorProvider в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4411f-102">How to: Display Error Icons for Form Validation with the Windows Forms ErrorProvider Component</span></span>
<span data-ttu-id="4411f-103">Компонент Windows Forms <xref:System.Windows.Forms.ErrorProvider> можно использовать для вывода значка ошибки при вводе пользователем недопустимых данных.</span><span class="sxs-lookup"><span data-stu-id="4411f-103">You can use a Windows Forms <xref:System.Windows.Forms.ErrorProvider> component to display an error icon when the user enters invalid data.</span></span> <span data-ttu-id="4411f-104">Необходимо иметь по крайней мере два элемента управления в форме, чтобы они могли переходить между ними и таким образом вызывать код проверки.</span><span class="sxs-lookup"><span data-stu-id="4411f-104">You must have at least two controls on the form in order to tab between them and thereby invoke the validation code.</span></span>  
  
### <a name="to-display-an-error-icon-when-a-controls-value-is-invalid"></a><span data-ttu-id="4411f-105">Отображение значка ошибки при недопустимом значении элемента управления</span><span class="sxs-lookup"><span data-stu-id="4411f-105">To display an error icon when a control's value is invalid</span></span>  
  
1. <span data-ttu-id="4411f-106">Добавьте два элемента управления, например текстовые поля, в форму Windows.</span><span class="sxs-lookup"><span data-stu-id="4411f-106">Add two controls — for example, text boxes — to a Windows Form.</span></span>  
  
2. <span data-ttu-id="4411f-107">Добавьте в форму компонент <xref:System.Windows.Forms.ErrorProvider>.</span><span class="sxs-lookup"><span data-stu-id="4411f-107">Add an <xref:System.Windows.Forms.ErrorProvider> component to the form.</span></span>  
  
3. <span data-ttu-id="4411f-108">Выберите первый элемент управления и добавьте код в обработчик событий <xref:System.Windows.Forms.Control.Validating>.</span><span class="sxs-lookup"><span data-stu-id="4411f-108">Select the first control and add code to its <xref:System.Windows.Forms.Control.Validating> event handler.</span></span> <span data-ttu-id="4411f-109">Чтобы этот код выполнялся должным образом, процедура должна быть подключена к событию.</span><span class="sxs-lookup"><span data-stu-id="4411f-109">In order for this code to run properly, the procedure must be connected to the event.</span></span> <span data-ttu-id="4411f-110">Дополнительные сведения см. [в разделе инструкции. Создание обработчиков событий во время выполнения для Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="4411f-110">For more information, see [How to: Create Event Handlers at Run Time for Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span></span>  
  
     <span data-ttu-id="4411f-111">Следующий код проверяет допустимость вводимых пользователем данных. Если данные недопустимы, вызывается метод <xref:System.Windows.Forms.ErrorProvider.SetError%2A>.</span><span class="sxs-lookup"><span data-stu-id="4411f-111">The following code tests the validity of the data the user has entered; if the data is invalid, the <xref:System.Windows.Forms.ErrorProvider.SetError%2A> method is called.</span></span> <span data-ttu-id="4411f-112">Первый аргумент метода <xref:System.Windows.Forms.ErrorProvider.SetError%2A> указывает, какой элемент управления должен отображать значок рядом с.</span><span class="sxs-lookup"><span data-stu-id="4411f-112">The first argument of the <xref:System.Windows.Forms.ErrorProvider.SetError%2A> method specifies which control to display the icon next to.</span></span> <span data-ttu-id="4411f-113">Вторым аргументом является отображаемый текст ошибки.</span><span class="sxs-lookup"><span data-stu-id="4411f-113">The second argument is the error text to display.</span></span>  
  
    ```vb  
    Private Sub TextBox1_Validating(ByVal Sender As Object, _  
       ByVal e As System.ComponentModel.CancelEventArgs) Handles _  
       TextBox1.Validating  
          If Not IsNumeric(TextBox1.Text) Then  
             ErrorProvider1.SetError(TextBox1, "Not a numeric value.")  
          Else  
             ' Clear the error.  
             ErrorProvider1.SetError(TextBox1, "")  
          End If  
    End Sub  
    ```  
  
    ```csharp  
    protected void textBox1_Validating (object sender,  
       System.ComponentModel.CancelEventArgs e)  
    {  
       try  
       {  
          int x = Int32.Parse(textBox1.Text);  
          errorProvider1.SetError(textBox1, "");  
       }  
       catch (Exception ex)  
       {  
          errorProvider1.SetError(textBox1, "Not an integer value.");  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void textBox1_Validating(System::Object ^  sender,  
          System::ComponentModel::CancelEventArgs ^  e)  
       {  
          try  
          {  
             int x = Int32::Parse(textBox1->Text);  
             errorProvider1->SetError(textBox1, "");  
          }  
          catch (System::Exception ^ ex)  
          {  
             errorProvider1->SetError(textBox1, "Not an integer value.");  
          }  
       }  
    ```  
  
     <span data-ttu-id="4411f-114">(Визуальный C#элемент C++, визуальный элемент) Поместите следующий код в конструктор формы для регистрации обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="4411f-114">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.textBox1.Validating += new  
    System.ComponentModel.CancelEventHandler(this.textBox1_Validating);  
    ```  
  
    ```cpp  
    this->textBox1->Validating += gcnew  
       System::ComponentModel::CancelEventHandler  
       (this, &Form1::textBox1_Validating);  
    ```  
  
4. <span data-ttu-id="4411f-115">Запустите проект.</span><span class="sxs-lookup"><span data-stu-id="4411f-115">Run the project.</span></span> <span data-ttu-id="4411f-116">Недопустимый тип (в этом примере нечисловые) данные в первом элементе управления, а затем на вкладку Second.</span><span class="sxs-lookup"><span data-stu-id="4411f-116">Type invalid (in this example, non-numeric) data into the first control, and then tab to the second.</span></span> <span data-ttu-id="4411f-117">Когда отображается значок ошибки, наведите указатель мыши на него, чтобы увидеть текст ошибки.</span><span class="sxs-lookup"><span data-stu-id="4411f-117">When the error icon is displayed, point at it with the mouse pointer to see the error text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4411f-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4411f-118">See also</span></span>

- <xref:System.Windows.Forms.ErrorProvider.SetError%2A>
- [<span data-ttu-id="4411f-119">Общие сведения о компоненте ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="4411f-119">ErrorProvider Component Overview</span></span>](errorprovider-component-overview-windows-forms.md)
- [<span data-ttu-id="4411f-120">Практическое руководство. Индикация ошибок данных, содержащихся в объекте DataSet, с помощью компонента ErrorProvider в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4411f-120">How to: View Errors Within a DataSet with the Windows Forms ErrorProvider Component</span></span>](view-errors-within-a-dataset-with-wf-errorprovider-component.md)
