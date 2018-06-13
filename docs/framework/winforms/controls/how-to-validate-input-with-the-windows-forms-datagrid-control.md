---
title: Практическое руководство. Проверка данных, вводимых с помощью элемента управления DataGrid, в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid control [Windows Forms], examples
- user input [Windows Forms], validating
- examples [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], validating input
- validation [Windows Forms], user input
ms.assetid: f1e9c3a0-d0a1-4893-a615-b4b0db046c63
ms.openlocfilehash: a01cb90b7cba596dafa56963dcf9c489deb3e21a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33535897"
---
# <a name="how-to-validate-input-with-the-windows-forms-datagrid-control"></a>Практическое руководство. Проверка данных, вводимых с помощью элемента управления DataGrid, в Windows Forms
> [!NOTE]
>  Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем. Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Существует два типа проверки входных данных для Windows Forms <xref:System.Windows.Forms.DataGrid> элемента управления. Если пользователь пытается ввести значение, которое имеет тип данных неприемлемой для ячейки, например строки в целое число, новое неправильное значение заменяется старое значение. Этот вид проверки входных данных выполняется автоматически и не может быть настроено.  
  
 Другие виды проверки входных данных может использоваться для отклонения любых недопустимых значений, например 0 значение в поле, которое должно быть больше или равно 1, или неподходящей строки. Для этого в наборе данных, написав обработчик событий для <xref:System.Data.DataTable.ColumnChanging> или <xref:System.Data.DataTable.RowChanging> событий. В приведенном ниже используется <xref:System.Data.DataTable.ColumnChanging> события так, как недопустимые значения запрещены для столбца «Продукт» в частности. Можно использовать <xref:System.Data.DataTable.RowChanging> событий для проверки, что значение столбца «Дата окончания» является более поздней, чем в той же строке столбца «Дата начала».  
  
### <a name="to-validate-user-input"></a>Проверка вводимых пользователем данных  
  
1.  Напишите код для обработки <xref:System.Data.DataTable.ColumnChanging> событий для соответствующей таблицы. При обнаружении несоответствия вводимых данных вызовите <xref:System.Data.DataRow.SetColumnError%2A> метод <xref:System.Data.DataRow> объекта.  
  
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
  
     Поместите следующий код либо в виде <xref:System.Windows.Forms.Form.Load> событие или его конструктор.  
  
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
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.DataGrid>  
 <xref:System.Data.DataTable.ColumnChanging>  
 <xref:System.Data.DataRow.SetColumnError%2A>  
 [Элемент управления DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)
