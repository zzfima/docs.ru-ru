---
title: Практическое руководство. Связывание объекта DataView с элементом управления DataGridView в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2b73d60a-6049-446a-85a7-3e5a68b183e2
ms.openlocfilehash: 3a3089073cdc5afb4ee51caca9114b401c740b45
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795003"
---
# <a name="how-to-bind-a-dataview-object-to-a-windows-forms-datagridview-control"></a><span data-ttu-id="37152-102">Практическое руководство. Связывание объекта DataView с элементом управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="37152-102">How to: Bind a DataView Object to a Windows Forms DataGridView Control</span></span>
<span data-ttu-id="37152-103">Элемент управления <xref:System.Windows.Forms.DataGridView> предоставляет мощный и гибкий способ отображения данных в табличном формате.</span><span class="sxs-lookup"><span data-stu-id="37152-103">The <xref:System.Windows.Forms.DataGridView> control provides a powerful and flexible way to display data in a tabular format.</span></span> <span data-ttu-id="37152-104">Элемент управления <xref:System.Windows.Forms.DataGridView> поддерживает стандартную модель привязки данных Windows Forms, поэтому он выполняет привязку к <xref:System.Data.DataView> и другим различным источникам данных.</span><span class="sxs-lookup"><span data-stu-id="37152-104">The <xref:System.Windows.Forms.DataGridView> control supports the standard Windows Forms data binding model, so it will bind to <xref:System.Data.DataView> and a variety of other data sources.</span></span> <span data-ttu-id="37152-105">Однако в большинстве случаев выполняется привязка к компоненту <xref:System.Windows.Forms.BindingSource>, управляющему взаимодействием с источником данных.</span><span class="sxs-lookup"><span data-stu-id="37152-105">In most situations, however, you will bind to a <xref:System.Windows.Forms.BindingSource> component that will manage the details of interacting with the data source.</span></span>  
  
 <span data-ttu-id="37152-106">Дополнительные сведения об элементе управления <xref:System.Windows.Forms.DataGridView> см. в разделе [Общие сведения о элементе управления DataGridView](../../winforms/controls/datagridview-control-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="37152-106">For more information about the <xref:System.Windows.Forms.DataGridView> control, see [DataGridView Control Overview](../../winforms/controls/datagridview-control-overview-windows-forms.md).</span></span>  
  
### <a name="to-connect-a-datagridview-control-to-a-dataview"></a><span data-ttu-id="37152-107">Соединение элемента управления DataGridView с объектом DataView</span><span class="sxs-lookup"><span data-stu-id="37152-107">To connect a DataGridView control to a DataView</span></span>  
  
1. <span data-ttu-id="37152-108">Реализуйте метод, обрабатывающий получение данных из базы данных.</span><span class="sxs-lookup"><span data-stu-id="37152-108">Implement a method to handle the details of retrieving data from a database.</span></span> <span data-ttu-id="37152-109">В следующем примере реализован метод `GetData`, инициализирующий компонент <xref:System.Data.SqlClient.SqlDataAdapter> и использующий его для заполнения объекта <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="37152-109">The following code example implements a `GetData` method that initializes a <xref:System.Data.SqlClient.SqlDataAdapter> component and uses it to fill a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="37152-110">Убедитесь, что переменной `connectionString` присвоено значение, соответствующее базе данных.</span><span class="sxs-lookup"><span data-stu-id="37152-110">Be sure to set the `connectionString` variable to a value that is appropriate for your database.</span></span> <span data-ttu-id="37152-111">Потребуется доступ к SQL Server с установленным образцом базы данных AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="37152-111">You will need access to a server with the AdventureWorks SQL Server sample database installed.</span></span>  
  
     [!code-csharp[DP DataViewWinForms Sample#LDVSample1GetData](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/CS/Form1.cs#ldvsample1getdata)]
     [!code-vb[DP DataViewWinForms Sample#LDVSample1GetData](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/VB/Form1.vb#ldvsample1getdata)]  
  
2. <span data-ttu-id="37152-112">В обработчике событий <xref:System.Windows.Forms.Form.Load> формы привяжите элемент управления <xref:System.Windows.Forms.DataGridView> к компоненту <xref:System.Windows.Forms.BindingSource> и вызовите метод `GetData` для получения данных из базы данных.</span><span class="sxs-lookup"><span data-stu-id="37152-112">In the <xref:System.Windows.Forms.Form.Load> event handler of your form, bind the <xref:System.Windows.Forms.DataGridView> control to the <xref:System.Windows.Forms.BindingSource> component and call the `GetData` method to retrieve the data from the database.</span></span> <span data-ttu-id="37152-113">Объект <xref:System.Data.DataView> создается из LINQ to DataSet запроса к контакту <xref:System.Data.DataTable> и затем привязывается к <xref:System.Windows.Forms.BindingSource> компоненту.</span><span class="sxs-lookup"><span data-stu-id="37152-113">The <xref:System.Data.DataView> is created from a LINQ to DataSet query over the Contact <xref:System.Data.DataTable> and is then bound to the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
     [!code-csharp[DP DataViewWinForms Sample#LDVSample1FormLoad](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/CS/Form1.cs#ldvsample1formload)]
     [!code-vb[DP DataViewWinForms Sample#LDVSample1FormLoad](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/VB/Form1.vb#ldvsample1formload)]  
  
## <a name="see-also"></a><span data-ttu-id="37152-114">См. также</span><span class="sxs-lookup"><span data-stu-id="37152-114">See also</span></span>

- [<span data-ttu-id="37152-115">Привязка данных и LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="37152-115">Data Binding and LINQ to DataSet</span></span>](data-binding-and-linq-to-dataset.md)
