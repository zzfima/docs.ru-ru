---
title: "Добавление столбцов в таблицу данных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: e85c4a0e-4f3f-458c-b58b-0ddbc06bf974
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 423b9ed389a5a3750c8e9b0339e0887d6b650741
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="adding-columns-to-a-datatable"></a><span data-ttu-id="ce957-102">Добавление столбцов в таблицу данных</span><span class="sxs-lookup"><span data-stu-id="ce957-102">Adding Columns to a DataTable</span></span>
<span data-ttu-id="ce957-103">Объект <xref:System.Data.DataTable> содержит коллекцию <xref:System.Data.DataColumn> объекты, упоминаемые **столбцы** свойство таблицы.</span><span class="sxs-lookup"><span data-stu-id="ce957-103">A <xref:System.Data.DataTable> contains a collection of <xref:System.Data.DataColumn> objects referenced by the **Columns** property of the table.</span></span> <span data-ttu-id="ce957-104">Эта коллекция столбцов наряду с ограничениями определяет схему, или структуру, таблицы.</span><span class="sxs-lookup"><span data-stu-id="ce957-104">This collection of columns, along with any constraints, defines the schema, or structure, of the table.</span></span>  
  
 <span data-ttu-id="ce957-105">Вы создаете **DataColumn** объектов в пределах таблицы с помощью **DataColumn** конструктор, или путем вызова **добавить** метод **столбцы**свойство таблицы, которое является <xref:System.Data.DataColumnCollection>.</span><span class="sxs-lookup"><span data-stu-id="ce957-105">You create **DataColumn** objects within a table by using the **DataColumn** constructor, or by calling the **Add** method of the **Columns** property of the table, which is a <xref:System.Data.DataColumnCollection>.</span></span> <span data-ttu-id="ce957-106">**Добавить** принимает необязательные **ColumnName**, **DataType**, и **выражение** аргументы и создает новый  **DataColumn** как член коллекции.</span><span class="sxs-lookup"><span data-stu-id="ce957-106">The **Add** method accepts optional **ColumnName**, **DataType**, and **Expression** arguments and creates a new **DataColumn** as a member of the collection.</span></span> <span data-ttu-id="ce957-107">Он также принимает существующий **DataColumn** и добавляет его в коллекцию и возвращает ссылку на добавленный **DataColumn** по запросу.</span><span class="sxs-lookup"><span data-stu-id="ce957-107">It also accepts an existing **DataColumn** object and adds it to the collection, and returns a reference to the added **DataColumn** if requested.</span></span> <span data-ttu-id="ce957-108">Поскольку **DataTable** объекты не относятся к любому источнику данных, типы .NET Framework используются при задании типа данных **DataColumn**.</span><span class="sxs-lookup"><span data-stu-id="ce957-108">Because **DataTable** objects are not specific to any data source, .NET Framework types are used when specifying the data type of a **DataColumn**.</span></span>  
  
 <span data-ttu-id="ce957-109">В следующем примере добавляется четыре столбца, чтобы **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="ce957-109">The following example adds four columns to a **DataTable**.</span></span>  
  
```vb  
Dim workTable As DataTable = New DataTable("Customers")  
  
Dim workCol As DataColumn = workTable.Columns.Add( _  
    "CustID", Type.GetType("System.Int32"))  
workCol.AllowDBNull = false  
workCol.Unique = true  
  
workTable.Columns.Add("CustLName", Type.GetType("System.String"))  
workTable.Columns.Add("CustFName", Type.GetType("System.String"))  
workTable.Columns.Add("Purchases", Type.GetType("System.Double"))  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
  
DataColumn workCol = workTable.Columns.Add("CustID", typeof(Int32));  
workCol.AllowDBNull = false;  
workCol.Unique = true;  
  
workTable.Columns.Add("CustLName", typeof(String));  
workTable.Columns.Add("CustFName", typeof(String));  
workTable.Columns.Add("Purchases", typeof(Double));  
```  
  
 <span data-ttu-id="ce957-110">В примере обратите внимание, что свойства **CustID** задаются запрещено **DBNull** значения и значениям ограничений быть уникальными.</span><span class="sxs-lookup"><span data-stu-id="ce957-110">In the example, notice that the properties for the **CustID** column are set to not allow **DBNull** values and to constrain values to be unique.</span></span> <span data-ttu-id="ce957-111">Тем не менее если определить **CustID** столбец как столбец первичного ключа таблицы, **AllowDBNull** свойство будет автоматически присвоено **false** и **Unique** свойство будет автоматически присвоено **true**.</span><span class="sxs-lookup"><span data-stu-id="ce957-111">However, if you define the **CustID** column as the primary key column of the table, the **AllowDBNull** property will automatically be set to **false** and the **Unique** property will automatically be set to **true**.</span></span> <span data-ttu-id="ce957-112">Дополнительные сведения см. в разделе [Определение первичных ключей](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="ce957-112">For more information, see [Defining Primary Keys](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="ce957-113">Если для столбца не указано имя столбца, столбца присваивается имя по умолчанию столбца*N,* начиная с «Column1», когда он добавляется в **DataColumnCollection**.</span><span class="sxs-lookup"><span data-stu-id="ce957-113">If a column name is not supplied for a column, the column is given an incremental default name of Column*N,* starting with "Column1", when it is added to the **DataColumnCollection**.</span></span> <span data-ttu-id="ce957-114">Мы рекомендуем избегать именования «столбец*N*» при задании имени столбца, так как предоставляемое имя может конфликтовать с существующим именем столбца по умолчанию в **DataColumnCollection**.</span><span class="sxs-lookup"><span data-stu-id="ce957-114">We recommend that you avoid the naming convention of "Column*N*" when you supply a column name, because the name you supply may conflict with an existing default column name in the **DataColumnCollection**.</span></span> <span data-ttu-id="ce957-115">Если указанное имя уже существует, вызывается исключение.</span><span class="sxs-lookup"><span data-stu-id="ce957-115">If the supplied name already exists, an exception is thrown.</span></span>  
  
 <span data-ttu-id="ce957-116">Если элемент <xref:System.Xml.Linq.XElement> используется в качестве <xref:System.Data.DataColumn.DataType%2A> объекта <xref:System.Data.DataColumn> в <xref:System.Data.DataTable>, то XML-сериализация не будет работать при считывании данных.</span><span class="sxs-lookup"><span data-stu-id="ce957-116">If you are using <xref:System.Xml.Linq.XElement> as the <xref:System.Data.DataColumn.DataType%2A> of a <xref:System.Data.DataColumn> in the <xref:System.Data.DataTable>, XML serialization will not work when you read in data.</span></span> <span data-ttu-id="ce957-117">Например, если документ <xref:System.Xml.XmlDocument> записывается методом `DataTable.WriteXml`, то во время сериализации в XML-код создается дополнительный родительский узел в элементе <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="ce957-117">For example, if you write out a <xref:System.Xml.XmlDocument> by using the `DataTable.WriteXml` method, upon serialization to XML there is an additional parent node in the <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="ce957-118">Чтобы избежать этой проблемы, используйте тип <xref:System.Data.SqlTypes.SqlXml> вместо <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="ce957-118">To work around this problem, use the <xref:System.Data.SqlTypes.SqlXml> type instead of <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="ce957-119">Методы `ReadXml` и `WriteXml` правильно работают с <xref:System.Data.SqlTypes.SqlXml>.</span><span class="sxs-lookup"><span data-stu-id="ce957-119">`ReadXml` and `WriteXml` work correctly with <xref:System.Data.SqlTypes.SqlXml>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce957-120">См. также</span><span class="sxs-lookup"><span data-stu-id="ce957-120">See Also</span></span>  
 <xref:System.Data.DataColumn>  
 <xref:System.Data.DataColumnCollection>  
 <xref:System.Data.DataTable>  
 [<span data-ttu-id="ce957-121">Определение схемы DataTable</span><span class="sxs-lookup"><span data-stu-id="ce957-121">DataTable Schema Definition</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 [<span data-ttu-id="ce957-122">DataTables</span><span class="sxs-lookup"><span data-stu-id="ce957-122">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [<span data-ttu-id="ce957-123">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ce957-123">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
