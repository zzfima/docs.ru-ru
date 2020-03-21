---
title: Изменение отображаемых данных во время выполнения в управлении DataGrid
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
ms.openlocfilehash: 6b788c10784082a0c74ee09f8cd85d540c670b84
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142385"
---
# <a name="how-to-change-displayed-data-at-run-time-in-the-windows-forms-datagrid-control"></a><span data-ttu-id="501fc-102">Практическое руководство. Изменение данных, отображаемых во время выполнения, в элементе управления DataGrid в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="501fc-102">How to: Change Displayed Data at Run Time in the Windows Forms DataGrid Control</span></span>
> [!NOTE]
> <span data-ttu-id="501fc-103">Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="501fc-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="501fc-104">Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="501fc-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="501fc-105">После создания форм <xref:System.Windows.Forms.DataGrid> Windows с использованием функций времени проектирования можно также <xref:System.Data.DataSet> динамически изменить элементы объекта сетки во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="501fc-105">After you have created a Windows Forms <xref:System.Windows.Forms.DataGrid> using the design-time features, you may also wish to dynamically change elements of the <xref:System.Data.DataSet> object of the grid at run time.</span></span> <span data-ttu-id="501fc-106">Это может включать изменения либо отдельных значений таблицы, либо <xref:System.Windows.Forms.DataGrid> изменение источника данных, привязанного к элементу управления.</span><span class="sxs-lookup"><span data-stu-id="501fc-106">This can include changes to either individual values of the table or changing which data source is bound to the <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="501fc-107">Изменения в отдельных значениях <xref:System.Data.DataSet> выполняются <xref:System.Windows.Forms.DataGrid> через объект, а не через элемент управления.</span><span class="sxs-lookup"><span data-stu-id="501fc-107">Changes to individual values are done through the <xref:System.Data.DataSet> object, not the <xref:System.Windows.Forms.DataGrid> control.</span></span>  
  
### <a name="to-change-data-programmatically"></a><span data-ttu-id="501fc-108">Программно еменять данные</span><span class="sxs-lookup"><span data-stu-id="501fc-108">To change data programmatically</span></span>  
  
1. <span data-ttu-id="501fc-109">Укажите нужную <xref:System.Data.DataSet> таблицу от объекта и желаемую строку и поле из таблицы и установите ячейку, равную новому значению.</span><span class="sxs-lookup"><span data-stu-id="501fc-109">Specify the desired table from the <xref:System.Data.DataSet> object and the desired row and field from the table and set the cell equal to the new value.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="501fc-110">Чтобы указать первую <xref:System.Data.DataSet> таблицу или первый ряд таблицы, используйте 0.</span><span class="sxs-lookup"><span data-stu-id="501fc-110">To specify the first table of the <xref:System.Data.DataSet> or the first row of the table, use 0.</span></span>  
  
     <span data-ttu-id="501fc-111">Ниже приводится следующий пример, как изменить вторую запись первой строки `Button1`первой таблицы набора данных, нажав кнопку .</span><span class="sxs-lookup"><span data-stu-id="501fc-111">The following example shows how to change the second entry of the first row of the first table of a dataset by clicking `Button1`.</span></span> <span data-ttu-id="501fc-112">Ранее <xref:System.Data.DataSet> `ds`были созданы`0` `1`() и таблицы (и )</span><span class="sxs-lookup"><span data-stu-id="501fc-112">The <xref:System.Data.DataSet> (`ds`) and Tables (`0` and `1`) were previously created.</span></span>  
  
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
  
     <span data-ttu-id="501fc-113">(Визуальный СЗ, Визуальный СЗ) Поместите следующий код в конструктор формы для регистрации обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="501fc-113">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=  
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     <span data-ttu-id="501fc-114">Во время выполнения можно <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> использовать метод <xref:System.Windows.Forms.DataGrid> для привязки элемента управления к другому источнику данных.</span><span class="sxs-lookup"><span data-stu-id="501fc-114">At run time you can use the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to bind the <xref:System.Windows.Forms.DataGrid> control to a different data source.</span></span> <span data-ttu-id="501fc-115">Например, у вас может быть несколько ADO.NET управления данными, каждый из которых подключен к другой базе данных.</span><span class="sxs-lookup"><span data-stu-id="501fc-115">For example, you may have several ADO.NET data controls, each connected to a different database.</span></span>  
  
### <a name="to-change-the-datasource-programmatically"></a><span data-ttu-id="501fc-116">Изменить DataSource программно</span><span class="sxs-lookup"><span data-stu-id="501fc-116">To change the DataSource programmatically</span></span>  
  
1. <span data-ttu-id="501fc-117">Установите <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> метод к названию источника данных и таблице, к которой вы хотите привязать.</span><span class="sxs-lookup"><span data-stu-id="501fc-117">Set the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to the name of the data source and table you want to bind to.</span></span>  
  
     <span data-ttu-id="501fc-118">В следующем примере показано, как <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> изменить источник даты с помощью метода на ADO.NET управления данными (adoPubsAuthors), который подключен к таблице Авторов в базе данных Pubs.</span><span class="sxs-lookup"><span data-stu-id="501fc-118">The following example shows how to change the date source using the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to an ADO.NET data control (adoPubsAuthors) that is connected to the Authors table in the Pubs database.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="501fc-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="501fc-119">See also</span></span>

- [<span data-ttu-id="501fc-120">DataSets в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="501fc-120">ADO.NET DataSets</span></span>](../../data/adonet/ado-net-datasets.md)
- [<span data-ttu-id="501fc-121">Практическое руководство. Удаление или скрытие столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="501fc-121">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="501fc-122">Практическое руководство. Добавление таблиц и столбцов в элемент управления DataGrid в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="501fc-122">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="501fc-123">Практическое руководство. Привязка элемента управления DataGrid в Windows Forms к источнику данных</span><span class="sxs-lookup"><span data-stu-id="501fc-123">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
