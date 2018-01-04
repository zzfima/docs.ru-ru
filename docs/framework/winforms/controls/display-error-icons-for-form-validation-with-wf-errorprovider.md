---
title: "Практическое руководство. Отображение значков ошибок при проверке введенных в форму данных с помощью компонента ErrorProvider в Windows Forms"
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
- errors [Windows Forms], displaying to users
- error icons
- ErrorProvider component [Windows Forms], displaying error icons
- error messages [Windows Forms], displaying icons
ms.assetid: 3b681a32-9db4-497b-a34b-34980eabee46
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 738ca9670635f78e8cb04318b192127184766c3c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-error-icons-for-form-validation-with-the-windows-forms-errorprovider-component"></a><span data-ttu-id="d9680-102">Практическое руководство. Отображение значков ошибок при проверке введенных в форму данных с помощью компонента ErrorProvider в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d9680-102">How to: Display Error Icons for Form Validation with the Windows Forms ErrorProvider Component</span></span>
<span data-ttu-id="d9680-103">Можно использовать Windows Forms <xref:System.Windows.Forms.ErrorProvider> компонент для отображения значков ошибок при вводе неправильных данных.</span><span class="sxs-lookup"><span data-stu-id="d9680-103">You can use a Windows Forms <xref:System.Windows.Forms.ErrorProvider> component to display an error icon when the user enters invalid data.</span></span> <span data-ttu-id="d9680-104">Необходимо иметь по крайней мере два элемента управления в форме для перехода между ними и вызова таким образом кода проверки.</span><span class="sxs-lookup"><span data-stu-id="d9680-104">You must have at least two controls on the form in order to tab between them and thereby invoke the validation code.</span></span>  
  
### <a name="to-display-an-error-icon-when-a-controls-value-is-invalid"></a><span data-ttu-id="d9680-105">Для отображения значков ошибок при недопустимом значение элемента управления</span><span class="sxs-lookup"><span data-stu-id="d9680-105">To display an error icon when a control's value is invalid</span></span>  
  
1.  <span data-ttu-id="d9680-106">Добавьте два элемента управления — например, текстовые поля, в форму Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="d9680-106">Add two controls — for example, text boxes — to a Windows Form.</span></span>  
  
2.  <span data-ttu-id="d9680-107">Добавить <xref:System.Windows.Forms.ErrorProvider> в форму компонент.</span><span class="sxs-lookup"><span data-stu-id="d9680-107">Add an <xref:System.Windows.Forms.ErrorProvider> component to the form.</span></span>  
  
3.  <span data-ttu-id="d9680-108">Выберите первый элемент управления и добавить код для его <xref:System.Windows.Forms.Control.Validating> обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="d9680-108">Select the first control and add code to its <xref:System.Windows.Forms.Control.Validating> event handler.</span></span> <span data-ttu-id="d9680-109">В порядке для правильного выполнения этого кода процедура должен быть подключен к событию.</span><span class="sxs-lookup"><span data-stu-id="d9680-109">In order for this code to run properly, the procedure must be connected to the event.</span></span> <span data-ttu-id="d9680-110">Дополнительные сведения см. в разделе [как: Создание обработчиков событий в запуска времени для Windows Forms](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="d9680-110">For more information, see [How to: Create Event Handlers at Run Time for Windows Forms](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span></span>  
  
     <span data-ttu-id="d9680-111">Следующий код проверяет допустимость данных, введенных пользователем; Если данные являются недопустимыми, <xref:System.Windows.Forms.ErrorProvider.SetError%2A> вызывается метод.</span><span class="sxs-lookup"><span data-stu-id="d9680-111">The following code tests the validity of the data the user has entered; if the data is invalid, the <xref:System.Windows.Forms.ErrorProvider.SetError%2A> method is called.</span></span> <span data-ttu-id="d9680-112">Первый аргумент <xref:System.Windows.Forms.ErrorProvider.SetError%2A> метод указывает, какой элемент управления для отображения значка рядом с полем.</span><span class="sxs-lookup"><span data-stu-id="d9680-112">The first argument of the <xref:System.Windows.Forms.ErrorProvider.SetError%2A> method specifies which control to display the icon next to.</span></span> <span data-ttu-id="d9680-113">Второй аргумент — отображаемый текст ошибки.</span><span class="sxs-lookup"><span data-stu-id="d9680-113">The second argument is the error text to display.</span></span>  
  
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
  
     <span data-ttu-id="d9680-114">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Поместите следующий код в конструктор формы для регистрации обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="d9680-114">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.textBox1.Validating += new  
    System.ComponentModel.CancelEventHandler(this.textBox1_Validating);  
    ```  
  
    ```cpp  
    this->textBox1->Validating += gcnew  
       System::ComponentModel::CancelEventHandler  
       (this, &Form1::textBox1_Validating);  
    ```  
  
4.  <span data-ttu-id="d9680-115">Запустите проект.</span><span class="sxs-lookup"><span data-stu-id="d9680-115">Run the project.</span></span> <span data-ttu-id="d9680-116">Введите недопустимые (в этом примере нечисловые) данные в первый элемент управления, а затем перейдите ко второму.</span><span class="sxs-lookup"><span data-stu-id="d9680-116">Type invalid (in this example, non-numeric) data into the first control, and then tab to the second.</span></span> <span data-ttu-id="d9680-117">Если отображается значок ошибки, установите на нем указатель мыши, чтобы просмотреть текст ошибки.</span><span class="sxs-lookup"><span data-stu-id="d9680-117">When the error icon is displayed, point at it with the mouse pointer to see the error text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9680-118">См. также</span><span class="sxs-lookup"><span data-stu-id="d9680-118">See Also</span></span>  
 <xref:System.Windows.Forms.ErrorProvider.SetError%2A>  
 [<span data-ttu-id="d9680-119">Общие сведения о компоненте ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="d9680-119">ErrorProvider Component Overview</span></span>](../../../../docs/framework/winforms/controls/errorprovider-component-overview-windows-forms.md)  
 [<span data-ttu-id="d9680-120">Практическое руководство. Индикация ошибок данных, содержащихся в объекте DataSet, с помощью компонента ErrorProvider в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d9680-120">How to: View Errors Within a DataSet with the Windows Forms ErrorProvider Component</span></span>](../../../../docs/framework/winforms/controls/view-errors-within-a-dataset-with-wf-errorprovider-component.md)
