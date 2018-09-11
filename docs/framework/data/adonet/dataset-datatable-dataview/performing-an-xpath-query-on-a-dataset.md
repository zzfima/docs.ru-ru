---
title: Выполнение запроса XPath к набору данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e828566-fffe-4d38-abb2-4d68fd73f663
ms.openlocfilehash: a1718429360d79c4628e9948eb1b052c3ac01964
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44270383"
---
# <a name="performing-an-xpath-query-on-a-dataset"></a>Выполнение запроса XPath к набору данных
Связь между синхронизированным <xref:System.Data.DataSet> и <xref:System.Xml.XmlDataDocument> позволяет использовать XML-служб, таких как запрос языка пути XML (XPath), которые обращаются к **XmlDataDocument** и выполнять некоторые функции более удобным, чем доступ к **набора данных** напрямую. Например, вместо использования **выберите** метод <xref:System.Data.DataTable> перехода по связям с другими таблицами в **набора данных**, можно выполнить запрос XPath на **XmlDataDocument**  который синхронизирован с **набора данных**, чтобы получить список элементов XML в виде <xref:System.Xml.XmlNodeList>. Узлы в **XmlNodeList**, приводится к форме <xref:System.Xml.XmlElement> узлов, может быть передан **GetRowFromElement** метод **XmlDataDocument**, чтобы вернуть совпадающие <xref:System.Data.DataRow> ссылки на строки таблицы в синхронизированном **набора данных**.  
  
 Например, следующий образец кода выполняет запрос XPath «по внукам». **Набора данных** заполняется тремя таблицами: **клиентов**, **заказы**, и **OrderDetails**. В этом примере родители потомки сначала создается связь между **клиентов** и **заказы** таблиц и между **заказы** и **OrderDetails** таблиц. Затем выполняется запрос XPath для возврата **XmlNodeList** из **клиентов** узлы где внучатый **OrderDetails** узел имеет **ProductID**узел со значением 43. По существу, образец использует запрос XPath для определения, какие клиенты заказавших продукт, имеющий **ProductID** 43.  
  
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
 [Синхронизация DataSet и XmlDataDocument](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataset-and-xmldatadocument-synchronization.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
