---
title: "Практическое руководство. Отображение значков ошибок при проверке введенных в форму данных с помощью компонента ErrorProvider в Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "значки ошибок"
  - "сообщения об ошибках, отображение значков"
  - "ErrorProvider - компонент [Windows Forms], отображение значков ошибок"
  - "ошибки [Windows Forms], отображение для пользователей"
ms.assetid: 3b681a32-9db4-497b-a34b-34980eabee46
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Практическое руководство. Отображение значков ошибок при проверке введенных в форму данных с помощью компонента ErrorProvider в Windows Forms
Компонент форм Windows <xref:System.Windows.Forms.ErrorProvider> может использоваться для отображения значков ошибок при вводе пользователем неверных данных.  В форме должно быть по крайней мере два элемента управления для перехода между ними и вызова таким образом кода проверки.  
  
### Чтобы отобразить значок ошибки при недопустимом значении элемента управления  
  
1.  Добавьте два элемента управления, например текстовых поля, в форме Windows Forms.  
  
2.  Добавьте компонент <xref:System.Windows.Forms.ErrorProvider> в форму.  
  
3.  Выберите первый элемент управления и добавьте код в его обработчик событий <xref:System.Windows.Forms.Control.Validating>.  Для правильного выполнения этого кода процедура должна быть связана с событием.  Дополнительные сведения см. в разделе [How to: Create Event Handlers at Run Time for Windows Forms](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md).  
  
     Следующий код проверяет допустимость данных, введенных пользователем, и в том случае, если данные неверны, вызывается метод <xref:System.Windows.Forms.ErrorProvider.SetError%2A>.  Первый аргумент метода <xref:System.Windows.Forms.ErrorProvider.SetError%2A> указывает, рядом с каким элементом управления расположить значок.  Второй аргумент определяет отображаемый текст ошибки.  
  
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
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) Добавьте в конструктор формы следующий код, чтобы зарегистрировать обработчик событий.  
  
    ```csharp  
    this.textBox1.Validating += new  
    System.ComponentModel.CancelEventHandler(this.textBox1_Validating);  
  
    ```  
  
    ```cpp  
    this->textBox1->Validating += gcnew  
       System::ComponentModel::CancelEventHandler  
       (this, &Form1::textBox1_Validating);  
    ```  
  
4.  Запустите проект.  Введите недопустимые \(в этом примере нечисловые\) данные в первый элемент управления, затем перейдите ко второму.  После отображения значка ошибки установите на нем курсор мыши для просмотра текста ошибки.  
  
## См. также  
 <xref:System.Windows.Forms.ErrorProvider.SetError%2A>   
 [Общие сведения о компоненте ErrorProvider](../../../../docs/framework/winforms/controls/errorprovider-component-overview-windows-forms.md)   
 [Практическое руководство. Индикация ошибок данных, содержащихся в объекте DataSet, с помощью компонента ErrorProvider в Windows Forms](../../../../docs/framework/winforms/controls/view-errors-within-a-dataset-with-wf-errorprovider-component.md)