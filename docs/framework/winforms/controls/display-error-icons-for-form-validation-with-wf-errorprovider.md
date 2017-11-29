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
ms.openlocfilehash: 02638ab59c0ba1c0eb0f8090be118b3d5a9111f8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-error-icons-for-form-validation-with-the-windows-forms-errorprovider-component"></a>Практическое руководство. Отображение значков ошибок при проверке введенных в форму данных с помощью компонента ErrorProvider в Windows Forms
Можно использовать Windows Forms <xref:System.Windows.Forms.ErrorProvider> компонент для отображения значков ошибок при вводе неправильных данных. Необходимо иметь по крайней мере два элемента управления в форме для перехода между ними и вызова таким образом кода проверки.  
  
### <a name="to-display-an-error-icon-when-a-controls-value-is-invalid"></a>Для отображения значков ошибок при недопустимом значение элемента управления  
  
1.  Добавьте два элемента управления — например, текстовые поля, в форму Windows Forms.  
  
2.  Добавить <xref:System.Windows.Forms.ErrorProvider> в форму компонент.  
  
3.  Выберите первый элемент управления и добавить код для его <xref:System.Windows.Forms.Control.Validating> обработчика событий. В порядке для правильного выполнения этого кода процедура должен быть подключен к событию. Дополнительные сведения см. в разделе [как: Создание обработчиков событий в запуска времени для Windows Forms](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md).  
  
     Следующий код проверяет допустимость данных, введенных пользователем; Если данные являются недопустимыми, <xref:System.Windows.Forms.ErrorProvider.SetError%2A> вызывается метод. Первый аргумент <xref:System.Windows.Forms.ErrorProvider.SetError%2A> метод указывает, какой элемент управления для отображения значка рядом с полем. Второй аргумент — отображаемый текст ошибки.  
  
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
  
     ([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Поместите следующий код в конструктор формы для регистрации обработчика событий.  
  
    ```csharp  
    this.textBox1.Validating += new  
    System.ComponentModel.CancelEventHandler(this.textBox1_Validating);  
    ```  
  
    ```cpp  
    this->textBox1->Validating += gcnew  
       System::ComponentModel::CancelEventHandler  
       (this, &Form1::textBox1_Validating);  
    ```  
  
4.  Запустите проект. Введите недопустимые (в этом примере нечисловые) данные в первый элемент управления, а затем перейдите ко второму. Если отображается значок ошибки, установите на нем указатель мыши, чтобы просмотреть текст ошибки.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.ErrorProvider.SetError%2A>  
 [Общие сведения о компоненте ErrorProvider](../../../../docs/framework/winforms/controls/errorprovider-component-overview-windows-forms.md)  
 [Практическое руководство. Индикация ошибок данных, содержащихся в объекте DataSet, с помощью компонента ErrorProvider в Windows Forms](../../../../docs/framework/winforms/controls/view-errors-within-a-dataset-with-wf-errorprovider-component.md)
