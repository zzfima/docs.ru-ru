---
title: Вложение отношений DataRelation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9530f9c9-dd98-4b93-8cdb-40d7f1e8d0ab
ms.openlocfilehash: 7975e17bd957a822bf3d60d487eb928cee84bd28
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59117213"
---
# <a name="nesting-datarelations"></a><span data-ttu-id="aa9bd-102">Вложение отношений DataRelation</span><span class="sxs-lookup"><span data-stu-id="aa9bd-102">Nesting DataRelations</span></span>
<span data-ttu-id="aa9bd-103">В реляционном представлении данных отдельные таблицы содержат строки, которые связаны друг с другом при помощи столбца или набора столбцов.</span><span class="sxs-lookup"><span data-stu-id="aa9bd-103">In a relational representation of data, individual tables contain rows that are related to one another using a column or set of columns.</span></span> <span data-ttu-id="aa9bd-104">В ADO.NET <xref:System.Data.DataSet> связь между таблицами реализуется при помощи <xref:System.Data.DataRelation>.</span><span class="sxs-lookup"><span data-stu-id="aa9bd-104">In the ADO.NET <xref:System.Data.DataSet>, the relationship between tables is implemented using a <xref:System.Data.DataRelation>.</span></span> <span data-ttu-id="aa9bd-105">При создании **DataRelation**, родительско дочерних отношений столбцов осуществляется только через это отношение.</span><span class="sxs-lookup"><span data-stu-id="aa9bd-105">When you create a **DataRelation**, the parent-child relationships of the columns are managed only through the relation.</span></span> <span data-ttu-id="aa9bd-106">Таблицы и столбцы являются отдельными сущностями.</span><span class="sxs-lookup"><span data-stu-id="aa9bd-106">The tables and columns are separate entities.</span></span> <span data-ttu-id="aa9bd-107">В иерархическом представлении данных, которое делает возможным XML, связи вида «родитель-потомок» представлены родительскими элементами, которые содержат вложенные дочерние элементы.</span><span class="sxs-lookup"><span data-stu-id="aa9bd-107">In the hierarchical representation of data that XML provides, the parent-child relationships are represented by parent elements that contain nested child elements.</span></span>  
  
 <span data-ttu-id="aa9bd-108">Чтобы упростить вложенность дочерних объектов при **набора данных** синхронизируется с <xref:System.Xml.XmlDataDocument> или создается в виде XML-данных с помощью **WriteXml**, **DataRelation** предоставляет **Nested** свойство.</span><span class="sxs-lookup"><span data-stu-id="aa9bd-108">To facilitate the nesting of child objects when a **DataSet** is synchronized with an <xref:System.Xml.XmlDataDocument> or written as XML data using **WriteXml**, the **DataRelation** exposes a **Nested** property.</span></span> <span data-ttu-id="aa9bd-109">Установка **Nested** свойство **DataRelation** для **true** вызывает дочерние строки связи вкладываются в родительский столбец при записи в виде XML-данных или синхронизировать с **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="aa9bd-109">Setting the **Nested** property of a **DataRelation** to **true** causes the child rows of the relation to be nested within the parent column when written as XML data or synchronized with an **XmlDataDocument**.</span></span> <span data-ttu-id="aa9bd-110">**Nested** свойство **DataRelation** — **false**, по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="aa9bd-110">The **Nested** property of the **DataRelation** is **false**, by default.</span></span>  
  
 <span data-ttu-id="aa9bd-111">Например, рассмотрим следующие **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="aa9bd-111">For example, consider the following **DataSet**.</span></span>  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim customerAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT CustomerID, CompanyName FROM Customers", connection)  
Dim orderAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT OrderID, CustomerID, OrderDate FROM Orders", connection)  
  
connection.Open()  
  
Dim dataSet As DataSet = New DataSet("CustomerOrders")  
customerAdapter.Fill(dataSet, "Customers")  
orderAdapter.Fill(dataSet, "Orders")  
  
connection.Close()  
  
Dim customerOrders As DataRelation = dataSet.Relations.Add( _  
  "CustOrders", dataSet.Tables("Customers").Columns("CustomerID"), _  
  dataSet.Tables("Orders").Columns("CustomerID"))  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
SqlDataAdapter customerAdapter = new SqlDataAdapter(  
  "SELECT CustomerID, CompanyName FROM Customers", connection);  
SqlDataAdapter orderAdapter = new SqlDataAdapter(  
  "SELECT OrderID, CustomerID, OrderDate FROM Orders", connection);  
  
connection.Open();  
  
DataSet dataSet = new DataSet("CustomerOrders");  
customerAdapter.Fill(dataSet, "Customers");  
orderAdapter.Fill(dataSet, "Orders");  
  
connection.Close();  
  
DataRelation customerOrders = dataSet.Relations.Add(  
  "CustOrders", dataSet.Tables["Customers"].Columns["CustomerID"],  
  dataSet.Tables["Orders"].Columns["CustomerID"]);  
```  
  
 <span data-ttu-id="aa9bd-112">Так как **Nested** свойство **DataRelation** объекта не присвоено **true** для данного **набора данных**, дочерние объекты не являются вложенными в родительские элементы при этом **набора данных** представляется в виде XML-данных.</span><span class="sxs-lookup"><span data-stu-id="aa9bd-112">Because the **Nested** property of the **DataRelation** object is not set to **true** for this **DataSet**, the child objects are not nested within the parent elements when this **DataSet** is represented as XML data.</span></span> <span data-ttu-id="aa9bd-113">Преобразование XML-представление **набора данных** , содержащий связанные **набора данных**s с отношениями невложенными данных может привести к снижению производительности.</span><span class="sxs-lookup"><span data-stu-id="aa9bd-113">Transforming the XML representation of a **DataSet** that contains related **DataSet**s with non-nested data relations can cause slow performance.</span></span> <span data-ttu-id="aa9bd-114">Рекомендуется вкладывать связи данных.</span><span class="sxs-lookup"><span data-stu-id="aa9bd-114">We recommend that you nest the data relations.</span></span> <span data-ttu-id="aa9bd-115">Чтобы сделать это, установите **Nested** свойства **true**.</span><span class="sxs-lookup"><span data-stu-id="aa9bd-115">To do this, set the **Nested** property to **true**.</span></span> <span data-ttu-id="aa9bd-116">Затем в таблице стилей XSLT напишите код, в котором для поиска и преобразования данных используются иерархические нисходящие выражения запросов XPath.</span><span class="sxs-lookup"><span data-stu-id="aa9bd-116">Then write code in the XSLT style sheet that uses top-down hierarchical XPath query expressions to locate and transform the data.</span></span>  
  
 <span data-ttu-id="aa9bd-117">В следующем примере кода показано, в результате вызова **WriteXml** на **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="aa9bd-117">The following code example shows the result from calling **WriteXml** on the **DataSet**.</span></span>  
  
```xml  
<CustomerOrders>  
  <Customers>  
    <CustomerID>ALFKI</CustomerID>  
    <CompanyName>Alfreds Futterkiste</CompanyName>  
  </Customers>  
  <Customers>  
    <CustomerID>ANATR</CustomerID>  
    <CompanyName>Ana Trujillo Emparedados y helados</CompanyName>  
  </Customers>  
  <Orders>  
    <OrderID>10643</OrderID>  
    <CustomerID>ALFKI</CustomerID>  
    <OrderDate>1997-08-25T00:00:00</OrderDate>  
  </Orders>  
  <Orders>  
    <OrderID>10692</OrderID>  
    <CustomerID>ALFKI</CustomerID>  
    <OrderDate>1997-10-03T00:00:00</OrderDate>  
  </Orders>  
  <Orders>  
    <OrderID>10308</OrderID>  
    <CustomerID>ANATR</CustomerID>  
    <OrderDate>1996-09-18T00:00:00</OrderDate>  
  </Orders>  
</CustomerOrders>  
```  
  
 <span data-ttu-id="aa9bd-118">Обратите внимание, что **клиентов** элемент и **заказы** элементы показаны как дочерние элементы.</span><span class="sxs-lookup"><span data-stu-id="aa9bd-118">Note that the **Customers** element and the **Orders** elements are shown as sibling elements.</span></span> <span data-ttu-id="aa9bd-119">Если вы хотите, чтобы **заказы** элементы отображались как дочерние элементы соответствующих родительских элементов, **Nested** свойство **DataRelation** необходимо присвоить **true** и необходимо добавить следующее:</span><span class="sxs-lookup"><span data-stu-id="aa9bd-119">If you wanted the **Orders** elements to show up as children of their respective parent elements, the **Nested** property of the **DataRelation** would need to be set to **true** and you would add the following:</span></span>  
  
```vb  
customerOrders.Nested = True  
```  
  
```csharp  
customerOrders.Nested = true;  
```  
  
 <span data-ttu-id="aa9bd-120">В следующем коде показано, как полученный результат будет выглядеть, с помощью **заказы** вложены в соответствующие родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="aa9bd-120">The following code shows what the resulting output would look like, with the **Orders** elements nested within their respective parent elements.</span></span>  
  
```xml  
<CustomerOrders>  
  <Customers>  
    <CustomerID>ALFKI</CustomerID>  
    <Orders>  
      <OrderID>10643</OrderID>  
      <CustomerID>ALFKI</CustomerID>  
      <OrderDate>1997-08-25T00:00:00</OrderDate>  
    </Orders>  
    <Orders>  
      <OrderID>10692</OrderID>  
      <CustomerID>ALFKI</CustomerID>  
      <OrderDate>1997-10-03T00:00:00</OrderDate>  
    </Orders>  
    <CompanyName>Alfreds Futterkiste</CompanyName>  
  </Customers>  
  <Customers>  
    <CustomerID>ANATR</CustomerID>  
    <Orders>  
      <OrderID>10308</OrderID>  
      <CustomerID>ANATR</CustomerID>  
      <OrderDate>1996-09-18T00:00:00</OrderDate>  
    </Orders>  
    <CompanyName>Ana Trujillo Emparedados y helados</CompanyName>  
  </Customers>  
</CustomerOrders>  
```  
  
## <a name="see-also"></a><span data-ttu-id="aa9bd-121">См. также</span><span class="sxs-lookup"><span data-stu-id="aa9bd-121">See also</span></span>

- [<span data-ttu-id="aa9bd-122">Использование XML в наборах данных</span><span class="sxs-lookup"><span data-stu-id="aa9bd-122">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [<span data-ttu-id="aa9bd-123">Добавление отношений DataRelation</span><span class="sxs-lookup"><span data-stu-id="aa9bd-123">Adding DataRelations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md)
- [<span data-ttu-id="aa9bd-124">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="aa9bd-124">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="aa9bd-125">Управляемые поставщики ADO.NET и центр разработчиков DataSet</span><span class="sxs-lookup"><span data-stu-id="aa9bd-125">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
