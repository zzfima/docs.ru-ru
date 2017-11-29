---
title: "Практическое руководство. Проверка данных, вводимых с помощью элемента управления DataGrid, в Windows Forms"
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
helpviewer_keywords:
- DataGrid control [Windows Forms], examples
- user input [Windows Forms], validating
- examples [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], validating input
- validation [Windows Forms], user input
ms.assetid: f1e9c3a0-d0a1-4893-a615-b4b0db046c63
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f5e0c366f71f602be2bb1508a6abb00d3d0c83ea
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-validate-input-with-the-windows-forms-datagrid-control"></a><span data-ttu-id="3b61e-102">Практическое руководство. Проверка данных, вводимых с помощью элемента управления DataGrid, в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3b61e-102">How to: Validate Input with the Windows Forms DataGrid Control</span></span>
> [!NOTE]
>  <span data-ttu-id="3b61e-103">Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="3b61e-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="3b61e-104">Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="3b61e-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="3b61e-105">Существует два типа проверки входных данных для Windows Forms <xref:System.Windows.Forms.DataGrid> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="3b61e-105">There are two types of input validation available for the Windows Forms <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="3b61e-106">Если пользователь пытается ввести значение, которое имеет тип данных неприемлемой для ячейки, например строки в целое число, новое неправильное значение заменяется старое значение.</span><span class="sxs-lookup"><span data-stu-id="3b61e-106">If the user attempts to enter a value that is of an unacceptable data type for the cell, for example a string into an integer, the new invalid value is replaced with the old value.</span></span> <span data-ttu-id="3b61e-107">Этот вид проверки входных данных выполняется автоматически и не может быть настроено.</span><span class="sxs-lookup"><span data-stu-id="3b61e-107">This kind of input validation is done automatically and cannot be customized.</span></span>  
  
 <span data-ttu-id="3b61e-108">Другие виды проверки входных данных может использоваться для отклонения любых недопустимых значений, например 0 значение в поле, которое должно быть больше или равно 1, или неподходящей строки.</span><span class="sxs-lookup"><span data-stu-id="3b61e-108">The other type of input validation can be used to reject any unacceptable data, for example a 0 value in a field that must be greater than or equal to 1, or an inappropriate string.</span></span> <span data-ttu-id="3b61e-109">Для этого в наборе данных, написав обработчик событий для <xref:System.Data.DataTable.ColumnChanging> или <xref:System.Data.DataTable.RowChanging> событий.</span><span class="sxs-lookup"><span data-stu-id="3b61e-109">This is done in the dataset by writing an event handler for the <xref:System.Data.DataTable.ColumnChanging> or <xref:System.Data.DataTable.RowChanging> event.</span></span> <span data-ttu-id="3b61e-110">В приведенном ниже используется <xref:System.Data.DataTable.ColumnChanging> события так, как недопустимые значения запрещены для столбца «Продукт» в частности.</span><span class="sxs-lookup"><span data-stu-id="3b61e-110">The example below uses the <xref:System.Data.DataTable.ColumnChanging> event because the unacceptable value is disallowed for the "Product" column in particular.</span></span> <span data-ttu-id="3b61e-111">Можно использовать <xref:System.Data.DataTable.RowChanging> событий для проверки, что значение столбца «Дата окончания» является более поздней, чем в той же строке столбца «Дата начала».</span><span class="sxs-lookup"><span data-stu-id="3b61e-111">You might use the <xref:System.Data.DataTable.RowChanging> event for checking that the value of an "End Date" column is later than the "Start Date" column in the same row.</span></span>  
  
### <a name="to-validate-user-input"></a><span data-ttu-id="3b61e-112">Проверка вводимых пользователем данных</span><span class="sxs-lookup"><span data-stu-id="3b61e-112">To validate user input</span></span>  
  
1.  <span data-ttu-id="3b61e-113">Напишите код для обработки <xref:System.Data.DataTable.ColumnChanging> событий для соответствующей таблицы.</span><span class="sxs-lookup"><span data-stu-id="3b61e-113">Write code to handle the <xref:System.Data.DataTable.ColumnChanging> event for the appropriate table.</span></span> <span data-ttu-id="3b61e-114">При обнаружении несоответствия вводимых данных вызовите <xref:System.Data.DataRow.SetColumnError%2A> метод <xref:System.Data.DataRow> объекта.</span><span class="sxs-lookup"><span data-stu-id="3b61e-114">When inappropriate input is detected, call the <xref:System.Data.DataRow.SetColumnError%2A> method of the <xref:System.Data.DataRow> object.</span></span>  
  
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
  
2.  <span data-ttu-id="3b61e-115">Подключите обработчик событий к событию.</span><span class="sxs-lookup"><span data-stu-id="3b61e-115">Connect the event handler to the event.</span></span>  
  
     <span data-ttu-id="3b61e-116">Поместите следующий код либо в виде <xref:System.Windows.Forms.Form.Load> событие или его конструктор.</span><span class="sxs-lookup"><span data-stu-id="3b61e-116">Place the following code within either the form's <xref:System.Windows.Forms.Form.Load> event or its constructor.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3b61e-117">См. также</span><span class="sxs-lookup"><span data-stu-id="3b61e-117">See Also</span></span>  
 <xref:System.Windows.Forms.DataGrid>  
 <xref:System.Data.DataTable.ColumnChanging>  
 <xref:System.Data.DataRow.SetColumnError%2A>  
 [<span data-ttu-id="3b61e-118">Элемент управления DataGrid</span><span class="sxs-lookup"><span data-stu-id="3b61e-118">DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)
