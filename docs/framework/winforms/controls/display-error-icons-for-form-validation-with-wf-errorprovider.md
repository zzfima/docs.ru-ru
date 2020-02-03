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
# <a name="how-to-display-error-icons-for-form-validation-with-the-windows-forms-errorprovider-component"></a>Практическое руководство. Отображение значков ошибок при проверке введенных в форму данных с помощью компонента ErrorProvider в Windows Forms
Компонент Windows Forms <xref:System.Windows.Forms.ErrorProvider> можно использовать для вывода значка ошибки при вводе пользователем недопустимых данных. Необходимо иметь по крайней мере два элемента управления в форме, чтобы они могли переходить между ними и таким образом вызывать код проверки.  
  
### <a name="to-display-an-error-icon-when-a-controls-value-is-invalid"></a>Отображение значка ошибки при недопустимом значении элемента управления  
  
1. Добавьте два элемента управления, например текстовые поля, в форму Windows.  
  
2. Добавьте в форму компонент <xref:System.Windows.Forms.ErrorProvider>.  
  
3. Выберите первый элемент управления и добавьте код в обработчик событий <xref:System.Windows.Forms.Control.Validating>. Чтобы этот код выполнялся должным образом, процедура должна быть подключена к событию. Дополнительные сведения см. [в разделе инструкции. Создание обработчиков событий во время выполнения для Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).  
  
     Следующий код проверяет допустимость вводимых пользователем данных. Если данные недопустимы, вызывается метод <xref:System.Windows.Forms.ErrorProvider.SetError%2A>. Первый аргумент метода <xref:System.Windows.Forms.ErrorProvider.SetError%2A> указывает, какой элемент управления должен отображать значок рядом с. Вторым аргументом является отображаемый текст ошибки.  
  
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
  
     (Визуальный C#элемент C++, визуальный элемент) Поместите следующий код в конструктор формы для регистрации обработчика событий.  
  
    ```csharp  
    this.textBox1.Validating += new  
    System.ComponentModel.CancelEventHandler(this.textBox1_Validating);  
    ```  
  
    ```cpp  
    this->textBox1->Validating += gcnew  
       System::ComponentModel::CancelEventHandler  
       (this, &Form1::textBox1_Validating);  
    ```  
  
4. Запустите проект. Недопустимый тип (в этом примере нечисловые) данные в первом элементе управления, а затем на вкладку Second. Когда отображается значок ошибки, наведите указатель мыши на него, чтобы увидеть текст ошибки.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.ErrorProvider.SetError%2A>
- [Общие сведения о компоненте ErrorProvider](errorprovider-component-overview-windows-forms.md)
- [Практическое руководство. Индикация ошибок данных, содержащихся в объекте DataSet, с помощью компонента ErrorProvider в Windows Forms](view-errors-within-a-dataset-with-wf-errorprovider-component.md)
