---
title: Вложение отношений DataRelation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9530f9c9-dd98-4b93-8cdb-40d7f1e8d0ab
ms.openlocfilehash: 08149de9222c34928078c0ca9d88096f7a4a88d1
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203272"
---
# <a name="nesting-datarelations"></a>Вложение отношений DataRelation
В реляционном представлении данных отдельные таблицы содержат строки, которые связаны друг с другом при помощи столбца или набора столбцов. В ADO.NET <xref:System.Data.DataSet> связь между таблицами реализуется при помощи <xref:System.Data.DataRelation>. При создании **DataRelation**отношения типа «родители-потомки» для столбцов управляются только через это отношение. Таблицы и столбцы являются отдельными сущностями. В иерархическом представлении данных, которое делает возможным XML, связи вида «родитель-потомок» представлены родительскими элементами, которые содержат вложенные дочерние элементы.  
  
 Для упрощения вложенности дочерних объектов при синхронизации **набора данных** с <xref:System.Xml.XmlDataDocument> или записи в виде XML-данных с помощью метода **WriteXml**объект **DataRelation** предоставляет вложенное свойство. Присвоение свойству Nested объекта **DataRelation** значения **true** приводит к тому, что дочерние строки связи будут вложены в родительский столбец при записи в виде XML-данных или синхронизированы с объектом **XmlDataDocument**. Свойство **Nested** объекта **DataRelation** по умолчанию имеет **значение false**.  
  
 Например, рассмотрим следующий **набор данных**.  
  
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
  
 Поскольку свойство **Nested** объекта **DataRelation** не имеет значение **true** для этого **набора данных**, дочерние объекты не вложены в родительские элементы, если этот **набор** данных представлен в виде XML-данных. Преобразование XML-представления **набора данных** , содержащего связанные **наборы**данных с невложенными связями данных, может привести к снижению производительности. Рекомендуется вкладывать связи данных. Для этого присвойте свойству **Nested** значение **true**. Затем в таблице стилей XSLT напишите код, в котором для поиска и преобразования данных используются иерархические нисходящие выражения запросов XPath.  
  
 В следующем примере кода показан результат вызова метода **WriteXml** для **набора данных**.  
  
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
  
 Обратите внимание , что элемент Customers и элементы **Orders** отображаются как родственные элементы. Если нужно, чтобы элементы Orders отображались как дочерние элементы соответствующих родительских элементов, необходимо установить для **вложенного** свойства **DataRelation** значение **true** , а также добавить следующее:  
  
```vb  
customerOrders.Nested = True  
```  
  
```csharp  
customerOrders.Nested = true;  
```  
  
 В следующем коде показано, как будут выглядеть итоговые выходные данные, с элементами Orders, вложенными в соответствующие им родительские элементы.  
  
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
  
## <a name="see-also"></a>См. также

- [Использование XML в наборах данных](using-xml-in-a-dataset.md)
- [Добавление отношений DataRelation](adding-datarelations.md)
- [Наборы данных, таблицы данных и объекты DataView](index.md)
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
