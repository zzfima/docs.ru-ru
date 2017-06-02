---
title: "Практическое руководство. Проверка данных, вводимых с помощью элемента управления DataGrid, в Windows Forms | Microsoft Docs"
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
  - "DataGrid - элемент управления [Windows Forms], примеры"
  - "DataGrid - элемент управления [Windows Forms], проверка входных данных"
  - "примеры [Windows Forms], DataGrid - элемент управления"
  - "ввод данных пользователем, проверка"
  - "проверка, ввод данных пользователем"
ms.assetid: f1e9c3a0-d0a1-4893-a615-b4b0db046c63
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Практическое руководство. Проверка данных, вводимых с помощью элемента управления DataGrid, в Windows Forms
> [!NOTE]
>  Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем.  Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Существуют два типа проверки вводимых данных в элементе управления Windows Forms <xref:System.Windows.Forms.DataGrid>.  При попытке пользователя ввести значение, тип которого является недопустимым для данной ячейки, например, строку вместо целого числа, новое неправильное значение заменяется предыдущим значением.  Данная проверка водимых данных выполняется автоматически и ее нельзя изменить.  
  
 Другой тип проверки вводимых данных можно использовать для отклонения любых недопустимых значений, например, нулевого значения для поля, значение которого должно быть больше или равно единице, или неподходящей строки.  Данная операция выполняется в базе данных с помощью обработчика событий <xref:System.Data.DataTable.ColumnChanging> или <xref:System.Data.DataTable.RowChanging>.  В приведенном ниже примере используется событие <xref:System.Data.DataTable.ColumnChanging>, в частности потому, что недопустимые значения запрещены для столбца "Product".  Событие <xref:System.Data.DataTable.RowChanging> можно применять для проверки того, что значение столбца "End Date" более позднее, чем столбца "Start Date" в той же самой строке.  
  
### Проверка вводимых пользователем данных  
  
1.  Напишите код обработки события <xref:System.Data.DataTable.ColumnChanging> для соответствующей таблицы.  При обнаружении несоответствия вводимых данных вызовите метод <xref:System.Data.DataRow.SetColumnError%2A> объекта <xref:System.Data.DataRow>.  
  
    ```vb  
    Private Sub Customers_ColumnChanging(ByVal sender As Object, _  
    ByVal e As System.Data.DataColumnChangeEventArgs)  
       ' Only check for errors in the Product column  
       If (e.Column.ColumnName.Equals("Product")) Then  
          ' Do not allow "Automobile" as a product.  
          If CType(e.ProposedValue, String) = "Automobile" Then  
             Dim badValue As Object = e.ProposedValue  
             e.ProposedValue = "Bad Data"  
             e.Row.RowError = "The Product column contians an error"  
             e.Row.SetColumnError(e.Column, "Product cannot be " & _  
             CType(badValue, String))  
          End If  
       End If  
    End Sub  
  
    ```  
  
    ```csharp  
    //Handle column changing events on the Customers table  
    private void Customers_ColumnChanging(object sender, System.Data.DataColumnChangeEventArgs e) {  
  
       //Only check for errors in the Product column  
       if (e.Column.ColumnName.Equals("Product")) {  
  
          //Do not allow "Automobile" as a product  
          if (e.ProposedValue.Equals("Automobile")) {  
             object badValue = e.ProposedValue;  
             e.ProposedValue = "Bad Data";  
             e.Row.RowError = "The Product column contains an error";  
             e.Row.SetColumnError(e.Column, "Product cannot be " + badValue);  
          }  
       }  
    }  
  
    ```  
  
2.  Подключите обработчик событий к событию.  
  
     Поместите следующий код либо в обработчике события <xref:System.Windows.Forms.Form.Load> формы, либо в ее конструкторе.  
  
    ```vb  
    ' Assumes the grid is bound to a dataset called customersDataSet1  
    ' with a table called Customers.  
    ' Put this code in the form's Load event or its constructor.  
    AddHandler customersDataSet1.Tables("Customers").ColumnChanging, AddressOf Customers_ColumnChanging  
  
    ```  
  
    ```csharp  
    // Assumes the grid is bound to a dataset called customersDataSet1  
    // with a table called Customers.  
    // Put this code in the form's Load event or its constructor.  
    customersDataSet1.Tables["Customers"].ColumnChanging += new DataColumnChangeEventHandler(this.Customers_ColumnChanging);  
  
    ```  
  
## См. также  
 <xref:System.Windows.Forms.DataGrid>   
 <xref:System.Data.DataTable.ColumnChanging>   
 <xref:System.Data.DataRow.SetColumnError%2A>   
 [Элемент управления DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)