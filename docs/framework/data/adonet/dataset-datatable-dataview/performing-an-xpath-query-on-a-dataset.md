---
title: Выполнение запроса XPath к набору данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e828566-fffe-4d38-abb2-4d68fd73f663
ms.openlocfilehash: 5e9a00ab78a57c3c1686d7c87ed8b45d9b2649af
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150835"
---
# <a name="performing-an-xpath-query-on-a-dataset"></a>Выполнение запроса XPath к набору данных
Взаимосвязь между синхронизированным <xref:System.Data.DataSet> <xref:System.Xml.XmlDataDocument> и позволяет использовать службы XML, такие как запрос XML Path Language (XPath), которые имеют доступ к **XmlDataDocument** и могут выполнять определенные функциональные возможности более удобно, чем напрямую получить доступ к **DataSet.** Например, вместо того, <xref:System.Data.DataTable> чтобы использовать метод **Выбора** для навигации по отношениям с другими таблицами в **DataSet,** можно выполнить запрос XPath на **XmlDataDocument,** который <xref:System.Xml.XmlNodeList>синхронизирован с **DataSet,** чтобы получить список элементов XML в виде . Узлы в **XmlNodeList**, <xref:System.Xml.XmlElement> отлитые в виде узлов, могут быть переданы методу **GetRowFromElement** **XmlDataDocument**, чтобы вернуть соответствующие <xref:System.Data.DataRow> ссылки на строки таблицы в синхронизированном **DataSet**.  
  
 Например, следующий образец кода выполняет запрос XPath «по внукам». **DataSet** заполнен тремя таблицами: **Клиенты,** **Заказы**и **OrderDetails**. В выборке сначала создается отношение родителя и ребенка между таблицами **Заказчиков** и **Заказов,** а также между таблицами **заказов** и **orderDetails.** Затем выполняется запрос XPath, чтобы вернуть **узлы XmlNodeList** **клиентов,** где узла **OrderDetails** grandchild имеет узлы **ProductID** со значением 43. В сущности, образец использует запрос XPath, чтобы определить, какие клиенты заказали продукт, который имеет **ProductID** 43.  
  
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
  
## <a name="see-also"></a>См. также раздел

- [Синхронизация набора данных и XmlDataDocument](dataset-and-xmldatadocument-synchronization.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
