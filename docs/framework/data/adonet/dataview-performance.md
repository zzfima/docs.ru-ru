---
title: Производительность объекта DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 90820e49-9d46-41f6-9a3d-6c0741bbd8eb
ms.openlocfilehash: 7c81619bf4ac6ed084ea63349345dbf3b7f139b0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150692"
---
# <a name="dataview-performance"></a><span data-ttu-id="dee12-102">Производительность объекта DataView</span><span class="sxs-lookup"><span data-stu-id="dee12-102">DataView Performance</span></span>
<span data-ttu-id="dee12-103">В этом разделе обсуждается повышение производительности при использования методов <xref:System.Data.DataView.Find%2A> и <xref:System.Data.DataView.FindRows%2A> класса <xref:System.Data.DataView>, а также при кэшировании объекта <xref:System.Data.DataView> в веб-приложении.</span><span class="sxs-lookup"><span data-stu-id="dee12-103">This topic discusses the performance benefits of using the <xref:System.Data.DataView.Find%2A> and <xref:System.Data.DataView.FindRows%2A> methods of the <xref:System.Data.DataView> class, and of caching a <xref:System.Data.DataView> in a Web application.</span></span>  
  
## <a name="find-and-findrows"></a><span data-ttu-id="dee12-104">Find и FindRows</span><span class="sxs-lookup"><span data-stu-id="dee12-104">Find and FindRows</span></span>  
 <span data-ttu-id="dee12-105">Объект <xref:System.Data.DataView> создает индекс.</span><span class="sxs-lookup"><span data-stu-id="dee12-105"><xref:System.Data.DataView> constructs an index.</span></span> <span data-ttu-id="dee12-106">Индекс содержит ключи, построенные из одного или нескольких столбцов в таблице или представлении.</span><span class="sxs-lookup"><span data-stu-id="dee12-106">An index contains keys built from one or more columns in the table or view.</span></span> <span data-ttu-id="dee12-107">Эти ключи хранятся в виде структуры сбалансированного дерева, которая поддерживает быстрый поиск строк по их ключевым значениям в объекте <xref:System.Data.DataView>.</span><span class="sxs-lookup"><span data-stu-id="dee12-107">These keys are stored in a structure that enables the <xref:System.Data.DataView> to find the row or rows associated with the key values quickly and efficiently.</span></span> <span data-ttu-id="dee12-108">Операции, в которые используется индекс, такие как фильтрация и сортировка, значительно повышают производительность.</span><span class="sxs-lookup"><span data-stu-id="dee12-108">Operations that use the index, such as filtering and sorting, see significant performance increases.</span></span> <span data-ttu-id="dee12-109">Индекс для <xref:System.Data.DataView> формируется как при создании <xref:System.Data.DataView>, так и при изменении каких-либо сведений о сортировке или фильтрации.</span><span class="sxs-lookup"><span data-stu-id="dee12-109">The index for a <xref:System.Data.DataView> is built both when the <xref:System.Data.DataView> is created and when any of the sorting or filtering information is modified.</span></span> <span data-ttu-id="dee12-110">Создание <xref:System.Data.DataView> и последующее задание сведений о сортировке или фильтрации приводит как минимум к двукратному построению индекса - при создании <xref:System.Data.DataView> и при изменении каких-либо свойств сортировки или фильтрации.</span><span class="sxs-lookup"><span data-stu-id="dee12-110">Creating a <xref:System.Data.DataView> and then setting the sorting or filtering information later causes the index to be built at least twice: once when the <xref:System.Data.DataView> is created, and again when any of the sort or filter properties are modified.</span></span> <span data-ttu-id="dee12-111">Для получения дополнительной информации о <xref:System.Data.DataView>фильтрации и сортировке с помощью, см. [Фильтрация с DataView](filtering-with-dataview-linq-to-dataset.md) и [сортировка с DataView](sorting-with-dataview-linq-to-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="dee12-111">For more information about filtering and sorting with <xref:System.Data.DataView>, see [Filtering with DataView](filtering-with-dataview-linq-to-dataset.md) and [Sorting with DataView](sorting-with-dataview-linq-to-dataset.md).</span></span>  
  
 <span data-ttu-id="dee12-112">Чтобы вернуть результаты определенного запроса к данным в противоположность динамическому представлению подмножества данным, можно воспользоваться методами <xref:System.Data.DataView.Find%2A> или <xref:System.Data.DataView.FindRows%2A> класса <xref:System.Data.DataView> вместо установки свойства <xref:System.Data.DataView.RowFilter%2A>.</span><span class="sxs-lookup"><span data-stu-id="dee12-112">If you want to return the results of a particular query on the data, as opposed to providing a dynamic view of a subset of the data, you can use the <xref:System.Data.DataView.Find%2A> or <xref:System.Data.DataView.FindRows%2A> methods of the <xref:System.Data.DataView>, rather than setting the <xref:System.Data.DataView.RowFilter%2A> property.</span></span> <span data-ttu-id="dee12-113">Свойство <xref:System.Data.DataView.RowFilter%2A> используется наилучшим образом в приложении, связываемом с данными, где элемент связывания отображает отфильтрованные результаты.</span><span class="sxs-lookup"><span data-stu-id="dee12-113">The <xref:System.Data.DataView.RowFilter%2A> property is best used in a data-bound application where a bound control displays filtered results.</span></span> <span data-ttu-id="dee12-114">При установке свойства <xref:System.Data.DataView.RowFilter%2A> перестраивается индекс данных, что добавляет нагрузку на приложение и снижает производительность.</span><span class="sxs-lookup"><span data-stu-id="dee12-114">Setting the <xref:System.Data.DataView.RowFilter%2A> property rebuilds the index for the data, adding overhead to your application and decreasing performance.</span></span> <span data-ttu-id="dee12-115">Методы <xref:System.Data.DataView.Find%2A> и <xref:System.Data.DataView.FindRows%2A> используют текущий индекс, не требуя его перестроения.</span><span class="sxs-lookup"><span data-stu-id="dee12-115">The <xref:System.Data.DataView.Find%2A> and <xref:System.Data.DataView.FindRows%2A> methods use the current index without requiring the index to be rebuilt.</span></span> <span data-ttu-id="dee12-116">Если <xref:System.Data.DataView.Find%2A> или <xref:System.Data.DataView.FindRows%2A> планируется вызвать только один раз, следует использовать существующий объект <xref:System.Data.DataView>.</span><span class="sxs-lookup"><span data-stu-id="dee12-116">If you are going to call <xref:System.Data.DataView.Find%2A> or <xref:System.Data.DataView.FindRows%2A> only once, then you should use the existing <xref:System.Data.DataView>.</span></span> <span data-ttu-id="dee12-117">Если методы <xref:System.Data.DataView.Find%2A> или <xref:System.Data.DataView.FindRows%2A> планируется вызывать несколько раз, следует создать новый объект <xref:System.Data.DataView> для перестроения индекса столбца, в котором необходимо выполнить поиск, а затем вызвать методы <xref:System.Data.DataView.Find%2A> или <xref:System.Data.DataView.FindRows%2A>.</span><span class="sxs-lookup"><span data-stu-id="dee12-117">If you are going to call <xref:System.Data.DataView.Find%2A> or <xref:System.Data.DataView.FindRows%2A> multiple times, you should create a new <xref:System.Data.DataView> to rebuild the index on the column you want to search on, and then call the <xref:System.Data.DataView.Find%2A> or <xref:System.Data.DataView.FindRows%2A> methods.</span></span> <span data-ttu-id="dee12-118">Для получения дополнительной <xref:System.Data.DataView.Find%2A> <xref:System.Data.DataView.FindRows%2A> информации о методах и методах, [см.](./dataset-datatable-dataview/finding-rows.md)</span><span class="sxs-lookup"><span data-stu-id="dee12-118">For more information about the <xref:System.Data.DataView.Find%2A> and <xref:System.Data.DataView.FindRows%2A> methods, see [Finding Rows](./dataset-datatable-dataview/finding-rows.md).</span></span>  
  
 <span data-ttu-id="dee12-119">В следующем примере метод <xref:System.Data.DataView.Find%2A> используется для поиска контактного лица с фамилией «Zhu».</span><span class="sxs-lookup"><span data-stu-id="dee12-119">The following example uses the <xref:System.Data.DataView.Find%2A> method to find a contact with the last name "Zhu".</span></span>  
  
 [!code-csharp[DP DataView Samples#LDVFromQueryOrderByFind](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvfromqueryorderbyfind)]
 [!code-vb[DP DataView Samples#LDVFromQueryOrderByFind](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvfromqueryorderbyfind)]  
  
 <span data-ttu-id="dee12-120">В следующем примере метод <xref:System.Data.DataView.FindRows%2A> используется для поиска всех продуктов красного цвета.</span><span class="sxs-lookup"><span data-stu-id="dee12-120">The following example uses the <xref:System.Data.DataView.FindRows%2A> method to find all the red colored products.</span></span>  
  
 [!code-csharp[DP DataView Samples#LDVFromQueryFindRows](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvfromqueryfindrows)]
 [!code-vb[DP DataView Samples#LDVFromQueryFindRows](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvfromqueryfindrows)]  
  
## <a name="aspnet"></a><span data-ttu-id="dee12-121">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="dee12-121">ASP.NET</span></span>  
 <span data-ttu-id="dee12-122">ASP.NET имеет механизм кэширования, позволяющий сохранять объекты, для создания которых в памяти требуются значительные ресурсы сервера.</span><span class="sxs-lookup"><span data-stu-id="dee12-122">ASP.NET has a caching mechanism that allows you to store objects that require extensive server resources to create in memory.</span></span> <span data-ttu-id="dee12-123">Кэширование таких типов ресурсов может значительно повысить производительность приложения.</span><span class="sxs-lookup"><span data-stu-id="dee12-123">Caching these types of resources can significantly improve the performance of your application.</span></span> <span data-ttu-id="dee12-124">Кэширование реализовано с помощью класса <xref:System.Web.Caching.Cache> с собственными экземплярами кэша для каждого приложения.</span><span class="sxs-lookup"><span data-stu-id="dee12-124">Caching is implemented by the <xref:System.Web.Caching.Cache> class, with cache instances that are private to each application.</span></span> <span data-ttu-id="dee12-125">Поскольку создание нового объекта <xref:System.Data.DataView> требует больших ресурсов, в веб-приложениях может быть полезным использование кэширования, чтобы объект <xref:System.Data.DataView> не приходилось перестраивать при каждом обновлении веб-страницы.</span><span class="sxs-lookup"><span data-stu-id="dee12-125">Because creating a new <xref:System.Data.DataView> object can be resource intensive, you might want to use this caching functionality in Web applications so that the <xref:System.Data.DataView> does not have to be rebuilt every time the Web page is refreshed.</span></span>  
  
 <span data-ttu-id="dee12-126">В следующем примере объект <xref:System.Data.DataView> кэшируется, поэтому данные не приходится сортировать заново при обновлении страницы.</span><span class="sxs-lookup"><span data-stu-id="dee12-126">In the following example, the <xref:System.Data.DataView> is cached so that the data does not have to be re-sorted when the page is refreshed.</span></span>  
  
```vb  
If (Cache("ordersView") = Nothing) Then  
  
Dim dataSet As New DataSet()  
  
   FillDataSet(dataSet)  
  
   Dim orders As DataTable = dataSet.Tables("SalesOrderHeader")  
  
   Dim query = _  
                    From order In orders.AsEnumerable() _  
                    Where order.Field(Of Boolean)("OnlineOrderFlag") = True _  
                    Order By order.Field(Of Decimal)("TotalDue") _  
                    Select order  
  
   Dim view As DataView = query.AsDataView()  
  
   Cache.Insert("ordersView", view)  
  
End If  
  
Dim ordersView = CType(Cache("ordersView"), DataView)  
  
GridView1.DataSource = ordersView  
GridView1.DataBind()  
```  
  
```csharp  
if (Cache["ordersView"] == null)  
{  
   // Fill the DataSet.
   DataSet dataSet = FillDataSet();  
  
   DataTable orders = dataSet.Tables["SalesOrderHeader"];  
  
   EnumerableRowCollection<DataRow> query =  
                        from order in orders.AsEnumerable()  
                        where order.Field<bool>("OnlineOrderFlag") == true  
                        orderby order.Field<decimal>("TotalDue")  
                        select order;  
  
   DataView view = query.AsDataView();  
   Cache.Insert("ordersView", view);  
}  
  
DataView ordersView = (DataView)Cache["ordersView"];  
  
GridView1.DataSource = ordersView;  
GridView1.DataBind();  
```  
  
## <a name="see-also"></a><span data-ttu-id="dee12-127">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="dee12-127">See also</span></span>

- [<span data-ttu-id="dee12-128">Привязка данных и LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="dee12-128">Data Binding and LINQ to DataSet</span></span>](data-binding-and-linq-to-dataset.md)
