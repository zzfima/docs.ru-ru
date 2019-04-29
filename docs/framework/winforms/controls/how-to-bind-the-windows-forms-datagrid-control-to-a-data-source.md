---
title: Практическое руководство. Привязка элемента управления DataGrid в Windows Forms к источнику данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- datasets [Windows Forms], binding to DataGrid control
- data binding [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], data binding
- bound controls [Windows Forms], DataGrid control
- Windows Forms controls, data binding
- bound controls [Windows Forms]
- data-bound controls [Windows Forms], DataGrid
ms.assetid: 128cdb07-dfd3-4d60-9d6a-902847667c36
ms.openlocfilehash: 920a93894cc126f85bc6b618efbe6e9cedea4881
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61666434"
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source"></a><span data-ttu-id="9337d-102">Практическое руководство. Привязка элемента управления DataGrid в Windows Forms к источнику данных</span><span class="sxs-lookup"><span data-stu-id="9337d-102">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>
> [!NOTE]
>  <span data-ttu-id="9337d-103">Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="9337d-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="9337d-104">Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="9337d-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="9337d-105">Windows Forms <xref:System.Windows.Forms.DataGrid> управления разработан специально для отображения сведений из источника данных.</span><span class="sxs-lookup"><span data-stu-id="9337d-105">The Windows Forms <xref:System.Windows.Forms.DataGrid> control is specifically designed to display information from a data source.</span></span> <span data-ttu-id="9337d-106">Привязка элемента управления во время выполнения путем вызова <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="9337d-106">You bind the control at run time by calling the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method.</span></span> <span data-ttu-id="9337d-107">Несмотря на то, что можно отобразить данные из различных источников данных, наиболее обычные параметры являются наборы данных и представления данных.</span><span class="sxs-lookup"><span data-stu-id="9337d-107">Although you can display data from a variety of data sources, the most typical sources are datasets and data views.</span></span>  
  
### <a name="to-data-bind-the-datagrid-control-programmatically"></a><span data-ttu-id="9337d-108">Для привязки данных элемента управления DataGrid программным способом</span><span class="sxs-lookup"><span data-stu-id="9337d-108">To data-bind the DataGrid control programmatically</span></span>  
  
1. <span data-ttu-id="9337d-109">Напишите код для заполнения набора данных.</span><span class="sxs-lookup"><span data-stu-id="9337d-109">Write code to fill the dataset.</span></span>  
  
     <span data-ttu-id="9337d-110">Если источником данных является набор данных или представление данных, на основе таблицы набора данных, добавьте код в форму для заполнения набора данных.</span><span class="sxs-lookup"><span data-stu-id="9337d-110">If the data source is a dataset or a data view based on a dataset table, add code to the form to fill the dataset.</span></span>  
  
     <span data-ttu-id="9337d-111">Использовании программы зависит от того, где данные поступают в набор.</span><span class="sxs-lookup"><span data-stu-id="9337d-111">The exact code you use depends on where the dataset is getting data.</span></span> <span data-ttu-id="9337d-112">Если набор данных заполняется непосредственно из базы данных, обычно вызывается `Fill` метод адаптера данных, как показано в следующем примере, который заполняет набор данных с именем `DsCategories1`:</span><span class="sxs-lookup"><span data-stu-id="9337d-112">If the dataset is being populated directly from a database, you typically call the `Fill` method of a data adapter, as in the following example, which populates a dataset called `DsCategories1`:</span></span>  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
     <span data-ttu-id="9337d-113">Если набор данных заполняется из XML-веб-службы, вы обычно создается экземпляр службы в коде, а затем вызовите один из его методов для возврата набора данных.</span><span class="sxs-lookup"><span data-stu-id="9337d-113">If the dataset is being filled from an XML Web service, you typically create an instance of the service in your code and then call one of its methods to return a dataset.</span></span> <span data-ttu-id="9337d-114">Затем объедините dataset из XML-веб-службы в локальный набор данных.</span><span class="sxs-lookup"><span data-stu-id="9337d-114">You then merge the dataset from the XML Web service into your local dataset.</span></span> <span data-ttu-id="9337d-115">В следующем примере показано, как можно создать экземпляр XML-веб-службы с именем `CategoriesService`, вызовите его `GetCategories` метод и слияния, результирующий набор данных в локальный набор данных называется `DsCategories1`:</span><span class="sxs-lookup"><span data-stu-id="9337d-115">The following example shows how you can create an instance of an XML Web service called `CategoriesService`, call its `GetCategories` method, and merge the resulting dataset into a local dataset called `DsCategories1`:</span></span>  
  
    ```vb  
    Dim ws As New MyProject.localhost.CategoriesService()  
    ws.Credentials = System.Net.CredentialCache.DefaultCredentials  
    DsCategories1.Merge(ws.GetCategories())  
    ```  
  
    ```csharp  
    MyProject.localhost.CategoriesService ws = new MyProject.localhost.CategoriesService();  
    ws.Credentials = System.Net.CredentialCache.DefaultCredentials;  
    DsCategories1.Merge(ws.GetCategories());  
    ```  
  
    ```cpp  
    MyProject::localhost::CategoriesService^ ws =   
       new MyProject::localhost::CategoriesService();  
    ws->Credentials = System::Net::CredentialCache::DefaultCredentials;  
    dsCategories1->Merge(ws->GetCategories());  
    ```  
  
2. <span data-ttu-id="9337d-116">Вызовите <xref:System.Windows.Forms.DataGrid> элемента управления <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> метод, передав ему в источнике данных и элемент данных.</span><span class="sxs-lookup"><span data-stu-id="9337d-116">Call the <xref:System.Windows.Forms.DataGrid> control's <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method, passing it the data source and a data member.</span></span> <span data-ttu-id="9337d-117">Если вам не нужно явным образом передать данные-член, передайте пустую строку.</span><span class="sxs-lookup"><span data-stu-id="9337d-117">If you do not need to explicitly pass a data member, pass an empty string.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9337d-118">При привязке сетки в первый раз, можно задать элемент управления <xref:System.Windows.Forms.DataGrid.DataSource%2A> и <xref:System.Windows.Forms.DataGrid.DataMember%2A> свойства.</span><span class="sxs-lookup"><span data-stu-id="9337d-118">If you are binding the grid for the first time, you can set the control's <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties.</span></span> <span data-ttu-id="9337d-119">Тем не менее нельзя восстановить эти свойства, как только они были заданы.</span><span class="sxs-lookup"><span data-stu-id="9337d-119">However, you cannot reset these properties once they have been set.</span></span> <span data-ttu-id="9337d-120">Таким образом, рекомендуется всегда использовать <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="9337d-120">Therefore, it is recommended that you always use the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method.</span></span>  
  
     <span data-ttu-id="9337d-121">В следующем примере показано, как программным способом можно привязать к таблице Customers в набор данных с именем `DsCustomers1`:</span><span class="sxs-lookup"><span data-stu-id="9337d-121">The following example shows how you can programmatically bind to the Customers table in a dataset called `DsCustomers1`:</span></span>  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "Customers");  
    ```  
  
     <span data-ttu-id="9337d-122">Если в таблице Customers только таблицу в наборе данных, можно также привязать сетке таким образом:</span><span class="sxs-lookup"><span data-stu-id="9337d-122">If the Customers table is the only table in the dataset, you could alternatively bind the grid this way:</span></span>  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "");  
    ```  
  
3. <span data-ttu-id="9337d-123">(Необязательно) Добавьте соответствующую таблицу стилей и столбцов в сетку.</span><span class="sxs-lookup"><span data-stu-id="9337d-123">(Optional) Add the appropriate table styles and column styles to the grid.</span></span> <span data-ttu-id="9337d-124">Если стили таблиц отсутствуют, вы увидите таблицу с минимальным форматированием и со всеми столбцами видимым.</span><span class="sxs-lookup"><span data-stu-id="9337d-124">If there are no table styles, you will see the table, but with minimal formatting and with all columns visible.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9337d-125">См. также</span><span class="sxs-lookup"><span data-stu-id="9337d-125">See also</span></span>

- [<span data-ttu-id="9337d-126">Общие сведения об элементе управления DataGrid</span><span class="sxs-lookup"><span data-stu-id="9337d-126">DataGrid Control Overview</span></span>](datagrid-control-overview-windows-forms.md)
- [<span data-ttu-id="9337d-127">Практическое руководство. Добавление таблиц и столбцов элемента управления DataGrid в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9337d-127">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="9337d-128">Элемент управления DataGrid</span><span class="sxs-lookup"><span data-stu-id="9337d-128">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
- [<span data-ttu-id="9337d-129">Привязка данных Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9337d-129">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
