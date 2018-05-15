---
title: Практическое руководство. Изменение данных, отображаемых во время выполнения, в элементе управления DataGrid в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DataGrid control [Windows Forms], dynamically changing at run time
- DataGrid control [Windows Forms], data binding
- cells [Windows Forms], changing DataGrid cell values
ms.assetid: 0c7a6d00-30de-416e-8223-0a81ddb4c1f8
ms.openlocfilehash: 1059f774ae8d2c203d7a4f5c02c597b4686304f7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-change-displayed-data-at-run-time-in-the-windows-forms-datagrid-control"></a><span data-ttu-id="26543-102">Практическое руководство. Изменение данных, отображаемых во время выполнения, в элементе управления DataGrid в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="26543-102">How to: Change Displayed Data at Run Time in the Windows Forms DataGrid Control</span></span>
> [!NOTE]
>  <span data-ttu-id="26543-103">Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="26543-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="26543-104">Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="26543-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="26543-105">После создания формы Windows <xref:System.Windows.Forms.DataGrid> с помощью функции времени разработки, вы также можете динамического изменения элементов управления <xref:System.Data.DataSet> объекта сетки во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="26543-105">After you have created a Windows Forms <xref:System.Windows.Forms.DataGrid> using the design-time features, you may also wish to dynamically change elements of the <xref:System.Data.DataSet> object of the grid at run time.</span></span> <span data-ttu-id="26543-106">Это может быть изменение как отдельных значений таблицы или источник данных, привязанного к <xref:System.Windows.Forms.DataGrid> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="26543-106">This can include changes to either individual values of the table or changing which data source is bound to the <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="26543-107">Изменение отдельных значений выполняется с помощью <xref:System.Data.DataSet> объекта, не <xref:System.Windows.Forms.DataGrid> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="26543-107">Changes to individual values are done through the <xref:System.Data.DataSet> object, not the <xref:System.Windows.Forms.DataGrid> control.</span></span>  
  
### <a name="to-change-data-programmatically"></a><span data-ttu-id="26543-108">Изменение данных программными средствами</span><span class="sxs-lookup"><span data-stu-id="26543-108">To change data programmatically</span></span>  
  
1.  <span data-ttu-id="26543-109">Выберите требуемую таблицу из <xref:System.Data.DataSet> объекта и нужную строку и поле в таблице и укажите в ячейке новое значение.</span><span class="sxs-lookup"><span data-stu-id="26543-109">Specify the desired table from the <xref:System.Data.DataSet> object and the desired row and field from the table and set the cell equal to the new value.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="26543-110">Чтобы указать в первой таблице <xref:System.Data.DataSet> или первой строки таблицы, укажите 0.</span><span class="sxs-lookup"><span data-stu-id="26543-110">To specify the first table of the <xref:System.Data.DataSet> or the first row of the table, use 0.</span></span>  
  
     <span data-ttu-id="26543-111">В следующем примере показано, как изменить вторую запись первой строки первой таблицы набора данных, щелкнув `Button1`.</span><span class="sxs-lookup"><span data-stu-id="26543-111">The following example shows how to change the second entry of the first row of the first table of a dataset by clicking `Button1`.</span></span> <span data-ttu-id="26543-112"><xref:System.Data.DataSet> (`ds`) И таблиц (`0` и `1`) были созданы ранее.</span><span class="sxs-lookup"><span data-stu-id="26543-112">The <xref:System.Data.DataSet> (`ds`) and Tables (`0` and `1`) were previously created.</span></span>  
  
    ```vb  
    Protected Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       ds.tables(0).rows(0)(1) = "NewEntry"  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       ds.Tables[0].Rows[0][1]="NewEntry";  
    }  
    ```  
  
    ```cpp  
    private:   
       void button1_Click(System::Object^ sender, System::EventArgs^ e)  
       {  
          dataSet1->Tables[0]->Rows[0][1] = "NewEntry";  
       }  
    ```  
  
     <span data-ttu-id="26543-113">(Visual C# [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) поместите следующий код в конструктор формы для регистрации обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="26543-113">(Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=  
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     <span data-ttu-id="26543-114">При своем выполнении можно использовать <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> метод привязки <xref:System.Windows.Forms.DataGrid> управления для источника данных.</span><span class="sxs-lookup"><span data-stu-id="26543-114">At run time you can use the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to bind the <xref:System.Windows.Forms.DataGrid> control to a different data source.</span></span> <span data-ttu-id="26543-115">Например, могут иметь несколько [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] элементами управления данными, каждый подключен к другой базе данных.</span><span class="sxs-lookup"><span data-stu-id="26543-115">For example, you may have several [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] data controls, each connected to a different database.</span></span>  
  
### <a name="to-change-the-datasource-programmatically"></a><span data-ttu-id="26543-116">Чтобы изменить источник данных программными средствами</span><span class="sxs-lookup"><span data-stu-id="26543-116">To change the DataSource programmatically</span></span>  
  
1.  <span data-ttu-id="26543-117">Задать <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> метод имя источника данных и вы хотите привязать к таблице.</span><span class="sxs-lookup"><span data-stu-id="26543-117">Set the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to the name of the data source and table you want to bind to.</span></span>  
  
     <span data-ttu-id="26543-118">Приведенный ниже показано, как изменить исходную дату с помощью <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> метод [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] управления данными (adoPubsAuthors), который подключен к таблице Authors базы данных Pubs.</span><span class="sxs-lookup"><span data-stu-id="26543-118">The following example shows how to change the date source using the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to an [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] data control (adoPubsAuthors) that is connected to the Authors table in the Pubs database.</span></span>  
  
    ```vb  
    Private Sub ResetSource()  
       DataGrid1.SetDataBinding(adoPubsAuthors, "Authors")  
    End Sub  
    ```  
  
    ```csharp  
    private void ResetSource()  
    {  
       DataGrid1.SetDataBinding(adoPubsAuthors, "Authors");  
    }  
    ```  
  
    ```cpp  
    private:  
       void ResetSource()  
       {  
          dataGrid1->SetDataBinding(adoPubsAuthors, "Authors");  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="26543-119">См. также</span><span class="sxs-lookup"><span data-stu-id="26543-119">See Also</span></span>  
 [<span data-ttu-id="26543-120">DataSets в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="26543-120">ADO.NET DataSets</span></span>](../../../../docs/framework/data/adonet/ado-net-datasets.md)  
 [<span data-ttu-id="26543-121">Практическое руководство. Удаление или скрытие столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="26543-121">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)  
 [<span data-ttu-id="26543-122">Практическое руководство. Добавление таблиц и столбцов в элемент управления DataGrid в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="26543-122">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)  
 [<span data-ttu-id="26543-123">Практическое руководство. Привязка элемента управления DataGrid в Windows Forms к источнику данных</span><span class="sxs-lookup"><span data-stu-id="26543-123">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
