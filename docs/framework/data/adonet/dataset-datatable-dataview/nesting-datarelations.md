---
title: "Вложение отношений DataRelation"
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
ms.assetid: 9530f9c9-dd98-4b93-8cdb-40d7f1e8d0ab
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: db7df753bf6066d3a89c46a82b66e47281076f95
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="nesting-datarelations"></a>Вложение отношений DataRelation
В реляционном представлении данных отдельные таблицы содержат строки, которые связаны друг с другом при помощи столбца или набора столбцов. В ADO.NET <xref:System.Data.DataSet> связь между таблицами реализуется при помощи <xref:System.Data.DataRelation>. При создании **DataRelation**, родительско дочерних отношений столбцов осуществляется только через это отношение. Таблицы и столбцы являются отдельными сущностями. В иерархическом представлении данных, которое делает возможным XML, связи вида «родитель-потомок» представлены родительскими элементами, которые содержат вложенные дочерние элементы.  
  
 Чтобы упростить вложенность дочерних объектов при **DataSet** синхронизируется с <xref:System.Xml.XmlDataDocument> или создается в виде XML-данных с помощью **WriteXml**, **DataRelation** предоставляет **Nested** свойство. Установка **Nested** свойство **DataRelation** для **true** , дочерние строки связи вкладываются в родительский столбец, когда записываются как XML-данных или синхронизировать с **XmlDataDocument**. **Nested** свойство **DataRelation** — **false**, по умолчанию.  
  
 Например, рассмотрим следующие **набора данных**.  
  
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
  
 Так как **Nested** свойство **DataRelation** объекта не равно **true** для этого **набора данных**, дочерние объекты не являются вложенными в родительские элементы при этом **DataSet** представляется в виде XML-данных. Преобразование XML-представление **DataSet** , содержащий связанные **набора данных**с отношениями невложенных данных может привести к снижению производительности. Рекомендуется вкладывать связи данных. Чтобы сделать это, задайте **Nested** свойства **true**. Затем в таблице стилей XSLT напишите код, в котором для поиска и преобразования данных используются иерархические нисходящие выражения запросов XPath.  
  
 В следующем примере кода показан результат вызова **WriteXml** на **набора данных**.  
  
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
  
 Обратите внимание, что **клиентов** элемент и **заказов** элементы показаны как дочерние элементы. Если вы хотите, чтобы **заказов** элементы отображались как дочерние элементы соответствующих родительских элементов, **Nested** свойство **DataRelation** должен быть установлен в **true** и добавить следующее:  
  
```vb  
customerOrders.Nested = True  
```  
  
```csharp  
customerOrders.Nested = true;  
```  
  
 В следующем коде показано, как результат будет выглядеть, с **заказов** вложены в соответствующие родительские элементы.  
  
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
 [Использование XML в наборах данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [Добавление отношений DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md)  
 [Наборы данных, таблицы данных и объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
