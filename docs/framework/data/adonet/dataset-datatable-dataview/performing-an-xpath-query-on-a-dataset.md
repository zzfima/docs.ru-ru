---
title: Выполнение запроса XPath к набору данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e828566-fffe-4d38-abb2-4d68fd73f663
ms.openlocfilehash: 6082a171d24c55ea52c153bbd920bb7486be78a7
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784376"
---
# <a name="performing-an-xpath-query-on-a-dataset"></a><span data-ttu-id="ad1eb-102">Выполнение запроса XPath к набору данных</span><span class="sxs-lookup"><span data-stu-id="ad1eb-102">Performing an XPath Query on a DataSet</span></span>
<span data-ttu-id="ad1eb-103">Связь между синхронизированной <xref:System.Data.DataSet> и <xref:System.Xml.XmlDataDocument> позволяет использовать службы XML, такие как запрос языка XML Path (XPath), которые обращаются к **XmlDataDocument** и могут выполнять определенные функции более удобно, чем доступ к **набору данных** напрямую.</span><span class="sxs-lookup"><span data-stu-id="ad1eb-103">The relationship between a synchronized <xref:System.Data.DataSet> and <xref:System.Xml.XmlDataDocument> allows you to make use of XML services, such as the XML Path Language (XPath) query, that access the **XmlDataDocument** and can perform certain functionality more conveniently than accessing the **DataSet** directly.</span></span> <span data-ttu-id="ad1eb-104">Например, вместо использования метода **SELECT** объекта <xref:System.Data.DataTable> для перехода между связями с другими таблицами в **наборе данных**можно выполнить запрос XPath к **XmlDataDocument** , который синхронизируется с **набором данных**, чтобы получить список XML-элементов в виде <xref:System.Xml.XmlNodeList>.</span><span class="sxs-lookup"><span data-stu-id="ad1eb-104">For example, rather than using the **Select** method of a <xref:System.Data.DataTable> to navigate relationships to other tables in a **DataSet**, you can perform an XPath query on an **XmlDataDocument** that is synchronized with the **DataSet**, to get a list of XML elements in the form of an <xref:System.Xml.XmlNodeList>.</span></span> <span data-ttu-id="ad1eb-105">Узлы в **XmlNodeList**, приведенные как <xref:System.Xml.XmlElement> узлы, могут затем передаваться в метод **жетровфромелемент** объекта **XmlDataDocument**для возврата совпадающих <xref:System.Data.DataRow> ссылок на строки таблицы в синхронизированном  **Набор данных**.</span><span class="sxs-lookup"><span data-stu-id="ad1eb-105">The nodes in the **XmlNodeList**, cast as <xref:System.Xml.XmlElement> nodes, can then be passed to the **GetRowFromElement** method of the **XmlDataDocument**, to return matching <xref:System.Data.DataRow> references to the rows of the table in the synchronized **DataSet**.</span></span>  
  
 <span data-ttu-id="ad1eb-106">Например, следующий образец кода выполняет запрос XPath «по внукам».</span><span class="sxs-lookup"><span data-stu-id="ad1eb-106">For example, the following code sample performs a "grandchild" XPath query.</span></span> <span data-ttu-id="ad1eb-107">**Набор данных** заполняется тремя таблицами: **Клиенты**, **заказы**и **OrderDetails**.</span><span class="sxs-lookup"><span data-stu-id="ad1eb-107">The **DataSet** is filled with three tables: **Customers**, **Orders**, and **OrderDetails**.</span></span> <span data-ttu-id="ad1eb-108">В примере сначала создается связь «родители-потомки» между таблицами **Customers** и **Orders** , а также между таблицами **Orders** и **OrderDetails** .</span><span class="sxs-lookup"><span data-stu-id="ad1eb-108">In the sample, a parent-child relation is first created between the **Customers** and **Orders** tables, and between the **Orders** and **OrderDetails** tables.</span></span> <span data-ttu-id="ad1eb-109">Затем выполняется запрос XPath, возвращающий **XmlNodeList** из узлов **Customers** , где узел внучатый **OrderDetails** имеет узел **ProductID** со значением 43.</span><span class="sxs-lookup"><span data-stu-id="ad1eb-109">An XPath query is then performed to return an **XmlNodeList** of **Customers** nodes where a grandchild **OrderDetails** node has a **ProductID** node with the value of 43.</span></span> <span data-ttu-id="ad1eb-110">По сути, в примере используется запрос XPath для определения того, какие клиенты разказали продукт с **ProductID** 43.</span><span class="sxs-lookup"><span data-stu-id="ad1eb-110">In essence, the sample is using the XPath query to determine which customers have ordered the product that has the **ProductID** of 43.</span></span>  
  
```vb  
' Assumes that connection is a valid SqlConnection.  
connection.Open()  
Dim dataSet As DataSet = New DataSet("CustomerOrders")  
Dim customerAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM Customers", connection)  
customerAdapter.Fill(dataSet, "Customers")  
  
Dim orderAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM Orders", connection)  
orderAdapter.Fill(dataSet, "Orders")  
  
Dim detailAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM [Order Details]", connection)  
detailAdapter.Fill(dataSet, "OrderDetails")  
  
connection.Close()  
  
dataSet.Relations.Add("CustOrders", _  
dataSet.Tables("Customers").Columns("CustomerID"), _  
dataSet.Tables("Orders").Columns("CustomerID")).Nested = true  
  
dataSet.Relations.Add("OrderDetail", _  
  dataSet.Tables("Orders").Columns("OrderID"), _  
dataSet.Tables("OrderDetails").Columns("OrderID"), false).Nested = true  
  
Dim xmlDoc As XmlDataDocument = New XmlDataDocument(dataSet)   
  
Dim nodeList As XmlNodeList = xmlDoc.DocumentElement.SelectNodes( _  
  "descendant::Customers[*/OrderDetails/ProductID=43]")  
  
Dim dataRow As DataRow  
Dim xmlNode As XmlNode  
  
For Each xmlNode In nodeList  
  dataRow = xmlDoc.GetRowFromElement(CType(xmlNode, XmlElement))  
  
  If Not dataRow Is Nothing then Console.WriteLine(xmlRow(0).ToString())  
Next  
```  
  
```csharp  
// Assumes that connection is a valid SqlConnection.  
connection.Open();  
  
DataSet dataSet = new DataSet("CustomerOrders");  
  
SqlDataAdapter customerAdapter = new SqlDataAdapter(  
  "SELECT * FROM Customers", connection);  
customerAdapter.Fill(dataSet, "Customers");  
  
SqlDataAdapter orderAdapter = new SqlDataAdapter(  
  "SELECT * FROM Orders", connection);  
orderAdapter.Fill(dataSet, "Orders");  
  
SqlDataAdapter detailAdapter = new SqlDataAdapter(  
  "SELECT * FROM [Order Details]", connection);  
detailAdapter.Fill(dataSet, "OrderDetails");  
  
connection.Close();  
  
dataSet.Relations.Add("CustOrders",  
  dataSet.Tables["Customers"].Columns["CustomerID"],  
 dataSet.Tables["Orders"].Columns["CustomerID"]).Nested = true;  
  
dataSet.Relations.Add("OrderDetail",  
  dataSet.Tables["Orders"].Columns["OrderID"],  
  dataSet.Tables["OrderDetails"].Columns["OrderID"],   
  false).Nested = true;  
  
XmlDataDocument xmlDoc = new XmlDataDocument(dataSet);   
  
XmlNodeList nodeList = xmlDoc.DocumentElement.SelectNodes(  
  "descendant::Customers[*/OrderDetails/ProductID=43]");  
  
DataRow dataRow;  
foreach (XmlNode xmlNode in nodeList)  
{  
  dataRow = xmlDoc.GetRowFromElement((XmlElement)xmlNode);  
  if (dataRow != null)  
    Console.WriteLine(dataRow[0]);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="ad1eb-111">См. также</span><span class="sxs-lookup"><span data-stu-id="ad1eb-111">See also</span></span>

- [<span data-ttu-id="ad1eb-112">Синхронизация DataSet и XmlDataDocument</span><span class="sxs-lookup"><span data-stu-id="ad1eb-112">DataSet and XmlDataDocument Synchronization</span></span>](dataset-and-xmldatadocument-synchronization.md)
- [<span data-ttu-id="ad1eb-113">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ad1eb-113">ADO.NET Overview</span></span>](../ado-net-overview.md)
