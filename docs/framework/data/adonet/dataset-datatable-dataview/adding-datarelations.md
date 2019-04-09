---
title: Добавление отношений DataRelation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a4a564fb-c1c4-4135-b6c2-b030e51195e4
ms.openlocfilehash: 9cefc97e571f315a6a644e0a058d4283168ecb9f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59199366"
---
# <a name="adding-datarelations"></a><span data-ttu-id="84216-102">Добавление отношений DataRelation</span><span class="sxs-lookup"><span data-stu-id="84216-102">Adding DataRelations</span></span>
<span data-ttu-id="84216-103">В наборе <xref:System.Data.DataSet> с несколькими объектами <xref:System.Data.DataTable> можно использовать объекты <xref:System.Data.DataRelation> для связи таблиц друг с другом, для перехода по таблицам, а также для возвращения дочерних или родительских строк из связанной таблицы.</span><span class="sxs-lookup"><span data-stu-id="84216-103">In a <xref:System.Data.DataSet> with multiple <xref:System.Data.DataTable> objects, you can use <xref:System.Data.DataRelation> objects to relate one table to another, to navigate through the tables, and to return child or parent rows from a related table.</span></span>  
  
 <span data-ttu-id="84216-104">Аргументы, необходимые для создания **DataRelation** : имя **DataRelation** создается и массив из одного или нескольких <xref:System.Data.DataColumn> ссылки на столбцы, которые служат в качестве родительской и дочерней столбцы в связи.</span><span class="sxs-lookup"><span data-stu-id="84216-104">The arguments required to create a **DataRelation** are a name for the **DataRelation** being created, and an array of one or more <xref:System.Data.DataColumn> references to the columns that serve as the parent and child columns in the relationship.</span></span> <span data-ttu-id="84216-105">После создания **DataRelation**, его можно использовать для перехода между таблицами и для получения значений.</span><span class="sxs-lookup"><span data-stu-id="84216-105">After you have created a **DataRelation**, you can use it to navigate between tables and to retrieve values.</span></span>  
  
 <span data-ttu-id="84216-106">Добавление **DataRelation** для <xref:System.Data.DataSet> добавляет по умолчанию <xref:System.Data.UniqueConstraint> с родительской таблицей и <xref:System.Data.ForeignKeyConstraint> к дочерней таблице.</span><span class="sxs-lookup"><span data-stu-id="84216-106">Adding a **DataRelation** to a <xref:System.Data.DataSet> adds, by default, a <xref:System.Data.UniqueConstraint> to the parent table and a <xref:System.Data.ForeignKeyConstraint> to the child table.</span></span> <span data-ttu-id="84216-107">Дополнительные сведения об этих ограничениях по умолчанию см. в разделе [ограничения таблиц данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="84216-107">For more information about these default constraints, see [DataTable Constraints](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).</span></span>  
  
 <span data-ttu-id="84216-108">В следующем примере кода создается **DataRelation** с использованием двух <xref:System.Data.DataTable> объекты в <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="84216-108">The following code example creates a **DataRelation** using two <xref:System.Data.DataTable> objects in a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="84216-109">Каждый <xref:System.Data.DataTable> содержит столбец с именем **CustID**, который используется в качестве связи между двумя <xref:System.Data.DataTable> объектов.</span><span class="sxs-lookup"><span data-stu-id="84216-109">Each <xref:System.Data.DataTable> contains a column named **CustID**, which serves as a link between the two <xref:System.Data.DataTable> objects.</span></span> <span data-ttu-id="84216-110">В примере добавляется один **DataRelation** для **отношений** коллекцию <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="84216-110">The example adds a single **DataRelation** to the **Relations** collection of the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="84216-111">В примере первый аргумент указывает имя **DataRelation** создания.</span><span class="sxs-lookup"><span data-stu-id="84216-111">The first argument in the example specifies the name of the **DataRelation** being created.</span></span> <span data-ttu-id="84216-112">Второй аргумент задает родительский **DataColumn** и третий аргумент задает дочерний элемент **DataColumn**.</span><span class="sxs-lookup"><span data-stu-id="84216-112">The second argument sets the parent **DataColumn** and the third argument sets the child **DataColumn**.</span></span>  
  
```vb  
customerOrders.Relations.Add("CustOrders", _  
  customerOrders.Tables("Customers").Columns("CustID"), _  
  customerOrders.Tables("Orders").Columns("CustID"))  
```  
  
```csharp  
customerOrders.Relations.Add("CustOrders",  
  customerOrders.Tables["Customers"].Columns["CustID"],  
  customerOrders.Tables["Orders"].Columns["CustID"]);  
```  
  
 <span data-ttu-id="84216-113">Объект **DataRelation** также имеет **Nested** свойство, если значение **true**, делает строки из дочерней таблицы вложенными в связанную строку родительской таблицы При записи в виде XML-элементов с помощью <xref:System.Data.DataSet.WriteXml%2A> .</span><span class="sxs-lookup"><span data-stu-id="84216-113">A **DataRelation** also has a **Nested** property which, when set to **true**, causes the rows from the child table to be nested within the associated row from the parent table when written as XML elements using <xref:System.Data.DataSet.WriteXml%2A> .</span></span> <span data-ttu-id="84216-114">Дополнительные сведения см. в статье [Использование XML в наборах данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="84216-114">For more information, see [Using XML in a DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84216-115">См. также</span><span class="sxs-lookup"><span data-stu-id="84216-115">See also</span></span>

- [<span data-ttu-id="84216-116">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="84216-116">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="84216-117">Управляемые поставщики ADO.NET и центр разработчиков DataSet</span><span class="sxs-lookup"><span data-stu-id="84216-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
