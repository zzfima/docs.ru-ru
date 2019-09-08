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
# <a name="performing-an-xpath-query-on-a-dataset"></a>Выполнение запроса XPath к набору данных
Связь между синхронизированной <xref:System.Data.DataSet> и <xref:System.Xml.XmlDataDocument> позволяет использовать службы XML, такие как запрос языка XML Path (XPath), которые обращаются к **XmlDataDocument** и могут выполнять определенные функции более удобно, чем доступ к **набору данных** напрямую. Например, вместо использования метода **SELECT** объекта <xref:System.Data.DataTable> для перехода между связями с другими таблицами в **наборе данных**можно выполнить запрос XPath к **XmlDataDocument** , который синхронизируется с **набором данных**, чтобы получить список XML-элементов в виде <xref:System.Xml.XmlNodeList>. Узлы в **XmlNodeList**, приведенные как <xref:System.Xml.XmlElement> узлы, могут затем передаваться в метод **жетровфромелемент** объекта **XmlDataDocument**для возврата совпадающих <xref:System.Data.DataRow> ссылок на строки таблицы в синхронизированном  **Набор данных**.  
  
 Например, следующий образец кода выполняет запрос XPath «по внукам». **Набор данных** заполняется тремя таблицами: **Клиенты**, **заказы**и **OrderDetails**. В примере сначала создается связь «родители-потомки» между таблицами **Customers** и **Orders** , а также между таблицами **Orders** и **OrderDetails** . Затем выполняется запрос XPath, возвращающий **XmlNodeList** из узлов **Customers** , где узел внучатый **OrderDetails** имеет узел **ProductID** со значением 43. По сути, в примере используется запрос XPath для определения того, какие клиенты разказали продукт с **ProductID** 43.  
  
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
  
## <a name="see-also"></a>См. также

- [Синхронизация DataSet и XmlDataDocument](dataset-and-xmldatadocument-synchronization.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
