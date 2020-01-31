---
title: Изменение отображаемых данных во время выполнения в элементе управления DataGrid
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
ms.openlocfilehash: f91e2ea01ef4a52dd649efed70319017efb8368a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740589"
---
# <a name="how-to-change-displayed-data-at-run-time-in-the-windows-forms-datagrid-control"></a><span data-ttu-id="01327-102">Практическое руководство. Изменение данных, отображаемых во время выполнения, в элементе управления DataGrid в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="01327-102">How to: Change Displayed Data at Run Time in the Windows Forms DataGrid Control</span></span>
> [!NOTE]
> <span data-ttu-id="01327-103">Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="01327-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="01327-104">Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="01327-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="01327-105">После создания Windows Forms <xref:System.Windows.Forms.DataGrid> с помощью функций времени разработки, может также потребоваться динамическое изменение элементов <xref:System.Data.DataSet> объекта Grid во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="01327-105">After you have created a Windows Forms <xref:System.Windows.Forms.DataGrid> using the design-time features, you may also wish to dynamically change elements of the <xref:System.Data.DataSet> object of the grid at run time.</span></span> <span data-ttu-id="01327-106">Это может быть изменение либо отдельных значений таблицы, либо изменением источника данных, привязанного к элементу управления <xref:System.Windows.Forms.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="01327-106">This can include changes to either individual values of the table or changing which data source is bound to the <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="01327-107">Изменения отдельных значений выполняются с помощью объекта <xref:System.Data.DataSet>, а не <xref:System.Windows.Forms.DataGrid> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="01327-107">Changes to individual values are done through the <xref:System.Data.DataSet> object, not the <xref:System.Windows.Forms.DataGrid> control.</span></span>  
  
### <a name="to-change-data-programmatically"></a><span data-ttu-id="01327-108">Программное изменение данных</span><span class="sxs-lookup"><span data-stu-id="01327-108">To change data programmatically</span></span>  
  
1. <span data-ttu-id="01327-109">Укажите нужную таблицу из объекта <xref:System.Data.DataSet>, а также нужную строку и поле из таблицы и установите ячейку, равную новому значению.</span><span class="sxs-lookup"><span data-stu-id="01327-109">Specify the desired table from the <xref:System.Data.DataSet> object and the desired row and field from the table and set the cell equal to the new value.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="01327-110">Чтобы указать первую таблицу <xref:System.Data.DataSet> или первую строку таблицы, используйте значение 0.</span><span class="sxs-lookup"><span data-stu-id="01327-110">To specify the first table of the <xref:System.Data.DataSet> or the first row of the table, use 0.</span></span>  
  
     <span data-ttu-id="01327-111">В следующем примере показано, как изменить вторую запись первой строки первой таблицы набора данных, нажав кнопку `Button1`.</span><span class="sxs-lookup"><span data-stu-id="01327-111">The following example shows how to change the second entry of the first row of the first table of a dataset by clicking `Button1`.</span></span> <span data-ttu-id="01327-112">Ранее были созданы <xref:System.Data.DataSet> (`ds`) и таблицы (`0` и `1`).</span><span class="sxs-lookup"><span data-stu-id="01327-112">The <xref:System.Data.DataSet> (`ds`) and Tables (`0` and `1`) were previously created.</span></span>  
  
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
  
     <span data-ttu-id="01327-113">(Визуальный C#элемент C++, визуальный элемент) Поместите следующий код в конструктор формы для регистрации обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="01327-113">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=  
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     <span data-ttu-id="01327-114">Во время выполнения можно использовать метод <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> для привязки элемента управления <xref:System.Windows.Forms.DataGrid> к другому источнику данных.</span><span class="sxs-lookup"><span data-stu-id="01327-114">At run time you can use the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to bind the <xref:System.Windows.Forms.DataGrid> control to a different data source.</span></span> <span data-ttu-id="01327-115">Например, у вас может быть несколько элементов управления данными ADO.NET, каждый из которых подключен к другой базе данных.</span><span class="sxs-lookup"><span data-stu-id="01327-115">For example, you may have several ADO.NET data controls, each connected to a different database.</span></span>  
  
### <a name="to-change-the-datasource-programmatically"></a><span data-ttu-id="01327-116">Изменение источника данных программным способом</span><span class="sxs-lookup"><span data-stu-id="01327-116">To change the DataSource programmatically</span></span>  
  
1. <span data-ttu-id="01327-117">Задайте методу <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> имя источника данных и таблицы, к которым необходимо выполнить привязку.</span><span class="sxs-lookup"><span data-stu-id="01327-117">Set the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to the name of the data source and table you want to bind to.</span></span>  
  
     <span data-ttu-id="01327-118">В следующем примере показано, как изменить источник даты с помощью метода <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> к элементу управления данными ADO.NET (Адопубсаусорс), который подключен к таблице authors в базе данных Pubs.</span><span class="sxs-lookup"><span data-stu-id="01327-118">The following example shows how to change the date source using the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to an ADO.NET data control (adoPubsAuthors) that is connected to the Authors table in the Pubs database.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="01327-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="01327-119">See also</span></span>

- [<span data-ttu-id="01327-120">DataSets в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="01327-120">ADO.NET DataSets</span></span>](../../data/adonet/ado-net-datasets.md)
- [<span data-ttu-id="01327-121">Практическое руководство. Удаление или скрытие столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="01327-121">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="01327-122">Практическое руководство. Добавление таблиц и столбцов в элемент управления DataGrid в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="01327-122">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="01327-123">Практическое руководство. Привязка элемента управления DataGrid в Windows Forms к источнику данных</span><span class="sxs-lookup"><span data-stu-id="01327-123">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
