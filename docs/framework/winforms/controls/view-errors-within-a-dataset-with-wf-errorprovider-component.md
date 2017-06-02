---
title: "Практическое руководство. Индикация ошибок данных, содержащихся в объекте DataSet, с помощью компонента ErrorProvider в Windows Forms | Microsoft Docs"
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
  - "сообщения об ошибках, просмотр в наборе данных"
  - "ErrorProvider - компонент [Windows Forms], ошибки в DataSet"
  - "ошибки [Windows Forms], ошибки в DataSet"
ms.assetid: cbae023f-d651-4210-bdea-bcc5f037e321
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Индикация ошибок данных, содержащихся в объекте DataSet, с помощью компонента ErrorProvider в Windows Forms
Компонент Windows Forms <xref:System.Windows.Forms.ErrorProvider> может использоваться для просмотра ошибок в столбцах набора данных или другого источника данных.  Для отображения ошибок данных в форме компонент <xref:System.Windows.Forms.ErrorProvider> не должен быть непосредственно связан с элементом управления.  После привязки к источнику данных он может отображать значок ошибки рядом с элементом управления, привязанным к тому же источнику данных.  
  
> [!NOTE]
>  Если свойства <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> и <xref:System.Windows.Forms.ErrorProvider.DataMember%2A> поставщика ошибок изменены во время выполнения, для предотвращения конфликтов необходимо использовать метод <xref:System.Windows.Forms.ErrorProvider.BindToDataAndErrors%2A>.  
  
### Чтобы отобразить ошибки данных  
  
1.  Привяжите этот компонент к конкретному столбцу в таблице данных.  
  
    ```vb  
    ' Assumes existence of DataSet1, DataTable1  
    TextBox1.DataBindings.Add("Text", DataSet1, "Customers.Name")  
    ErrorProvider1.DataSource = DataSet1  
    ErrorProvider1.DataMember = "Customers"  
  
    ```  
  
    ```csharp  
    // Assumes existence of DataSet1, DataTable1  
    textBox1.DataBindings.Add("Text", DataSet1, "Customers.Name");  
    errorProvider1.DataSource = DataSet1;  
    errorProvider1.DataMember = "Customers";  
  
    ```  
  
2.  Укажите в свойстве <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> форму.  
  
    ```vb  
    ErrorProvider1.ContainerControl = Me  
  
    ```  
  
    ```csharp  
    errorProvider1.ContainerControl = this;  
  
    ```  
  
3.  Задайте в качестве позиции текущей записи строку, содержащую ошибку столбца.  
  
    ```vb  
    DataTable1.Rows(5).SetColumnError("Name", "Bad data in this row.")  
    Me.BindingContext(DataTable1).Position = 5  
  
    ```  
  
    ```csharp  
    DataTable1.Rows[5].SetColumnError("Name", "Bad data in this row.");  
    this.BindingContext [DataTable1].Position = 5;  
  
    ```  
  
## См. также  
 [Общие сведения о компоненте ErrorProvider](../../../../docs/framework/winforms/controls/errorprovider-component-overview-windows-forms.md)   
 [Практическое руководство. Отображение значков ошибок при проверке введенных в форму данных с помощью компонента ErrorProvider в Windows Forms](../../../../docs/framework/winforms/controls/display-error-icons-for-form-validation-with-wf-errorprovider.md)