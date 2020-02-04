---
title: Проверка входных данных с помощью элемента управления DataGrid
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
ms.openlocfilehash: 3958089007401d2e977c9c96f07c9196e6216596
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728295"
---
# <a name="how-to-validate-input-with-the-windows-forms-datagrid-control"></a>Практическое руководство. Проверка данных, вводимых с помощью элемента управления DataGrid, в Windows Forms

> [!NOTE]
> Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем. Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).

Для элемента управления Windows Forms <xref:System.Windows.Forms.DataGrid> доступны два типа проверки входных данных. Если пользователь пытается ввести значение, имеющее недопустимый тип данных для ячейки, например строку в целое число, новое недопустимое значение заменяется на старое значение. Такой тип проверки ввода выполняется автоматически и не может быть настроен.

Другой тип проверки ввода можно использовать для отклонения любых неприемлемых данных, например значения 0 в поле, которое должно быть больше или равно 1, или недопустимой строки. Это делается в наборе данных путем написания обработчика событий для события <xref:System.Data.DataTable.ColumnChanging> или <xref:System.Data.DataTable.RowChanging>. В приведенном ниже примере используется событие <xref:System.Data.DataTable.ColumnChanging>, поскольку неприемлемое значение не разрешено для столбца «Product» в частности. Событие <xref:System.Data.DataTable.RowChanging> можно использовать для проверки того, что значение столбца "Дата окончания" позже, чем столбец "Дата начала" в той же строке.

## <a name="to-validate-user-input"></a>Проверка вводимых пользователем данных

1. Напишите код, обрабатывающий событие <xref:System.Data.DataTable.ColumnChanging> для соответствующей таблицы. При обнаружении недопустимых входных данных вызовите метод <xref:System.Data.DataRow.SetColumnError%2A> объекта <xref:System.Data.DataRow>.

    ```vb
    Private Sub Customers_ColumnChanging(ByVal sender As Object, _
    ByVal e As System.Data.DataColumnChangeEventArgs)
       ' Only check for errors in the Product column
       If (e.Column.ColumnName.Equals("Product")) Then
          ' Do not allow "Automobile" as a product.
          If CType(e.ProposedValue, String) = "Automobile" Then
             Dim badValue As Object = e.ProposedValue
             e.ProposedValue = "Bad Data"
             e.Row.RowError = "The Product column contains an error"
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

2. Подключите обработчик событий к событию.

    Поместите следующий код в событие <xref:System.Windows.Forms.Form.Load> формы или в конструктор.

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

## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.DataGrid>
- <xref:System.Data.DataTable.ColumnChanging>
- <xref:System.Data.DataRow.SetColumnError%2A>
- [Элемент управления DataGrid](datagrid-control-windows-forms.md)
