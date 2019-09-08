---
title: Добавление столбцов в таблицу данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e85c4a0e-4f3f-458c-b58b-0ddbc06bf974
ms.openlocfilehash: 6e0dcd819dc354e1fd23b244692dff5091142004
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784855"
---
# <a name="adding-columns-to-a-datatable"></a><span data-ttu-id="79e54-102">Добавление столбцов в таблицу данных</span><span class="sxs-lookup"><span data-stu-id="79e54-102">Adding Columns to a DataTable</span></span>
<span data-ttu-id="79e54-103">Объект <xref:System.Data.DataTable> содержит<xref:System.Data.DataColumn> коллекцию объектов, на которые ссылается свойство **Columns** таблицы.</span><span class="sxs-lookup"><span data-stu-id="79e54-103">A <xref:System.Data.DataTable> contains a collection of <xref:System.Data.DataColumn> objects referenced by the **Columns** property of the table.</span></span> <span data-ttu-id="79e54-104">Эта коллекция столбцов наряду с ограничениями определяет схему, или структуру, таблицы.</span><span class="sxs-lookup"><span data-stu-id="79e54-104">This collection of columns, along with any constraints, defines the schema, or structure, of the table.</span></span>  
  
 <span data-ttu-id="79e54-105">Объекты **DataColumn** создаются в таблице с помощью конструктора **DataColumn** или путем вызова метода **Add** свойства **Columns** таблицы, то есть <xref:System.Data.DataColumnCollection>.</span><span class="sxs-lookup"><span data-stu-id="79e54-105">You create **DataColumn** objects within a table by using the **DataColumn** constructor, or by calling the **Add** method of the **Columns** property of the table, which is a <xref:System.Data.DataColumnCollection>.</span></span> <span data-ttu-id="79e54-106">Метод **Add** принимает необязательные аргументы **ColumnName**, **DataType**и **Expression** и создает новый **столбец** данных в качестве члена коллекции.</span><span class="sxs-lookup"><span data-stu-id="79e54-106">The **Add** method accepts optional **ColumnName**, **DataType**, and **Expression** arguments and creates a new **DataColumn** as a member of the collection.</span></span> <span data-ttu-id="79e54-107">Он также принимает существующий объект **DataColumn** и добавляет его в коллекцию и возвращает ссылку на добавленный **DataColumn-столбец** по запросу.</span><span class="sxs-lookup"><span data-stu-id="79e54-107">It also accepts an existing **DataColumn** object and adds it to the collection, and returns a reference to the added **DataColumn** if requested.</span></span> <span data-ttu-id="79e54-108">Поскольку объекты **DataTable** не относятся к какому-либо источнику данных, .NET Framework типы используются при указании типа данных **DataColumn**.</span><span class="sxs-lookup"><span data-stu-id="79e54-108">Because **DataTable** objects are not specific to any data source, .NET Framework types are used when specifying the data type of a **DataColumn**.</span></span>  
  
 <span data-ttu-id="79e54-109">В следующем примере в **таблицу DataTable**добавляются четыре столбца.</span><span class="sxs-lookup"><span data-stu-id="79e54-109">The following example adds four columns to a **DataTable**.</span></span>  
  
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
  
 <span data-ttu-id="79e54-110">Обратите внимание, что в этом примере свойству для столбца **CustID** присвоено значение, которое не разрешает значения **DBNull** и ограничивает значения уникальными.</span><span class="sxs-lookup"><span data-stu-id="79e54-110">In the example, notice that the properties for the **CustID** column are set to not allow **DBNull** values and to constrain values to be unique.</span></span> <span data-ttu-id="79e54-111">Однако если определить столбец **CustID** в качестве первичного ключевого столбца таблицы, то свойству **AllowDbNull** автоматически будет присвоено значение **false** , а свойству **UNIQUE** будет автоматически присвоено значение **true**.</span><span class="sxs-lookup"><span data-stu-id="79e54-111">However, if you define the **CustID** column as the primary key column of the table, the **AllowDBNull** property will automatically be set to **false** and the **Unique** property will automatically be set to **true**.</span></span> <span data-ttu-id="79e54-112">Дополнительные сведения см. в разделе [Определение первичных ключей](defining-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="79e54-112">For more information, see [Defining Primary Keys](defining-primary-keys.md).</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="79e54-113">Если имя столбца не указано для столбца, то столбцу присваивается добавочное имя по умолчанию для столбца*N,* начинающееся с «Column1», при добавлении в **датаколумнколлектион**.</span><span class="sxs-lookup"><span data-stu-id="79e54-113">If a column name is not supplied for a column, the column is given an incremental default name of Column*N,* starting with "Column1", when it is added to the **DataColumnCollection**.</span></span> <span data-ttu-id="79e54-114">Рекомендуется избегать использования соглашения об именовании "Column*N*" при указании имени столбца, так как указываемое имя может конфликтовать с существующим именем столбца по умолчанию в **датаколумнколлектион**.</span><span class="sxs-lookup"><span data-stu-id="79e54-114">We recommend that you avoid the naming convention of "Column*N*" when you supply a column name, because the name you supply may conflict with an existing default column name in the **DataColumnCollection**.</span></span> <span data-ttu-id="79e54-115">Если указанное имя уже существует, вызывается исключение.</span><span class="sxs-lookup"><span data-stu-id="79e54-115">If the supplied name already exists, an exception is thrown.</span></span>  
  
 <span data-ttu-id="79e54-116">Если элемент <xref:System.Xml.Linq.XElement> используется в качестве <xref:System.Data.DataColumn.DataType%2A> объекта <xref:System.Data.DataColumn> в <xref:System.Data.DataTable>, то XML-сериализация не будет работать при считывании данных.</span><span class="sxs-lookup"><span data-stu-id="79e54-116">If you are using <xref:System.Xml.Linq.XElement> as the <xref:System.Data.DataColumn.DataType%2A> of a <xref:System.Data.DataColumn> in the <xref:System.Data.DataTable>, XML serialization will not work when you read in data.</span></span> <span data-ttu-id="79e54-117">Например, если документ <xref:System.Xml.XmlDocument> записывается методом `DataTable.WriteXml`, то во время сериализации в XML-код создается дополнительный родительский узел в элементе <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="79e54-117">For example, if you write out a <xref:System.Xml.XmlDocument> by using the `DataTable.WriteXml` method, upon serialization to XML there is an additional parent node in the <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="79e54-118">Чтобы избежать этой проблемы, используйте тип <xref:System.Data.SqlTypes.SqlXml> вместо <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="79e54-118">To work around this problem, use the <xref:System.Data.SqlTypes.SqlXml> type instead of <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="79e54-119">Методы `ReadXml` и `WriteXml` правильно работают с <xref:System.Data.SqlTypes.SqlXml>.</span><span class="sxs-lookup"><span data-stu-id="79e54-119">`ReadXml` and `WriteXml` work correctly with <xref:System.Data.SqlTypes.SqlXml>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79e54-120">См. также</span><span class="sxs-lookup"><span data-stu-id="79e54-120">See also</span></span>

- <xref:System.Data.DataColumn>
- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="79e54-121">Определение схемы DataTable</span><span class="sxs-lookup"><span data-stu-id="79e54-121">DataTable Schema Definition</span></span>](datatable-schema-definition.md)
- [<span data-ttu-id="79e54-122">DataTables</span><span class="sxs-lookup"><span data-stu-id="79e54-122">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="79e54-123">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="79e54-123">ADO.NET Overview</span></span>](../ado-net-overview.md)
