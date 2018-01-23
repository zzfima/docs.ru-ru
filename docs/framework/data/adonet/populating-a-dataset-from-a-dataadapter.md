---
title: "Заполнение набора данных с помощью адаптера данных DataAdapter"
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
ms.assetid: 3fa0ac7d-e266-4954-bfac-3fbe2f913153
caps.latest.revision: "6"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: c0991398a28e491d381d10dea8a14ed463c67c89
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="populating-a-dataset-from-a-dataadapter"></a>Заполнение набора данных с помощью адаптера данных DataAdapter
[!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]<xref:System.Data.DataSet> является резидентным представлением данных, предоставляющим согласованную реляционную программную модель, независимую от источника данных. Набор данных `DataSet` представляет собой полную совокупность данных, которая включает таблицы, ограничения и связи между таблицами. Набор данных `DataSet` является независимым от источника данных, поэтому `DataSet` может включать данные, локальные по отношению к приложению, а также данные из нескольких источников данных. Управление взаимодействием с существующими источниками данных осуществляется с помощью `DataAdapter`.  
  
 Свойство `SelectCommand` объекта `DataAdapter` представляет собой объект `Command` , получающий данные из источника данных. Свойства `InsertCommand`, `UpdateCommand`и `DeleteCommand` , принадлежащие `DataAdapter` , являются объектами `Command` , которые управляют обновлением данных в источнике данных в соответствии с изменениями данных в `DataSet`. Эти свойства описаны более подробно в [обновление источников данных с помощью DataAdapter](../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md).  
  
 Метод `Fill` объекта `DataAdapter` служит для заполнения набора данных `DataSet` результатами выполнения метода `SelectCommand` объекта `DataAdapter`. Метод`Fill` принимает в качестве аргумента подлежащий заполнению набор данных `DataSet` , а также объект `DataTable` или имя объекта `DataTable` , который должен быть заполнен строками, возвращенными методом `SelectCommand`.  
  
> [!NOTE]
>  Использование `DataAdapter` для получения всей таблицы требует времени, особенно при наличии в ней большого числа строк. Это происходит вследствие того, что обращение к базе данных, обнаружение и обработка данных, а также передача данных клиенту занимают длительное время. Передача по запросу всей таблицы клиенту приводит также к блокировке всех строк на сервере. Для повышения производительности можно использовать предложение `WHERE` , что позволяет значительно уменьшить количество строк, возвращаемых клиенту. Можно также уменьшить количество данных, возвращаемых клиенту, с помощью явно заданного списка требуемых столбцов в инструкции `SELECT` . Еще одним хорошим решением проблемы является получение строк в пакетах (например, содержащих несколько сотен строк одновременно), а также получение следующего пакета только после завершения обработки текущего.  
  
 Метод `Fill` неявно использует объект `DataReader` для возврата имен и типов столбцов, используемых для создания таблиц в `DataSet`, и данных для заполнения строк таблиц в `DataSet`. Таблицы и столбцы создаются только в том случае, если они еще не существуют. В противном случае метод `Fill` использует существующую схему `DataSet` . Типы столбцов, создаются в виде [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] типов в соответствии с таблицами в [сопоставления типов данных в ADO.NET](../../../../docs/framework/data/adonet/data-type-mappings-in-ado-net.md). Первичные ключи создаются, только если они существуют в источнике данных и свойство `DataAdapter`**.**`MissingSchemaAction` имеет значение `MissingSchemaAction`**.**`AddWithKey`. Если `Fill` обнаруживает, что для таблицы существует первичный ключ, то данные в `DataSet` для строк, в которых значения столбцов первичного ключа совпадают со значениями в строках, возвращенных из источника данных, будут перезаписаны данными из источника данных. Если первичный ключ не найден, то данные добавляются в таблицы `DataSet`. `Fill`использует все сопоставления, которые могут существовать при заполнении `DataSet` (см. [DataAdapter DataTable и DataColumn сопоставления](../../../../docs/framework/data/adonet/dataadapter-datatable-and-datacolumn-mappings.md)).  
  
> [!NOTE]
>  Если `SelectCommand` возвращает результаты OUTER JOIN, то `DataAdapter` не задает значение `PrimaryKey` для результирующего объекта `DataTable`. Чтобы обеспечить правильное обнаружение повторяющихся строк, пользователь должен определить первичный ключ, `PrimaryKey` . Дополнительные сведения см. в разделе [Определение первичных ключей](../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).  
  
 В следующем примере кода создается экземпляр <xref:System.Data.SqlClient.SqlDataAdapter> , в котором используется соединение <xref:System.Data.SqlClient.SqlConnection> для базы данных `Northwind` Microsoft SQL Server и заполняется <xref:System.Data.DataTable> в наборе данных `DataSet` списком клиентов. Инструкция SQL и аргументы <xref:System.Data.SqlClient.SqlConnection> , переданные в конструктор <xref:System.Data.SqlClient.SqlDataAdapter> , используются для создания свойства <xref:System.Data.SqlClient.SqlDataAdapter.SelectCommand%2A> объекта <xref:System.Data.SqlClient.SqlDataAdapter>.  
  
## <a name="example"></a>Пример  
  
```vb  
' Assumes that connection is a valid SqlConnection object.  
Dim queryString As String = _  
  "SELECT CustomerID, CompanyName FROM dbo.Customers"  
Dim adapter As SqlDataAdapter = New SqlDataAdapter( _  
  queryString, connection)  
  
Dim customers As DataSet = New DataSet  
adapter.Fill(customers, "Customers")  
```  
  
```csharp  
// Assumes that connection is a valid SqlConnection object.  
string queryString =   
  "SELECT CustomerID, CompanyName FROM dbo.Customers";  
SqlDataAdapter adapter = new SqlDataAdapter(queryString, connection);  
  
DataSet customers = new DataSet();  
adapter.Fill(customers, "Customers");  
```  
  
> [!NOTE]
>  Код, показанный в данном примере, не открывает и закрывает `Connection`явным образом. Если соединение еще не открыто, то метод `Fill` неявно открывает `Connection` , которое используется `DataAdapter` . Если операция `Fill` открыла соединение, она также закрывает его при завершении `Fill` . Это позволяет упростить код при использовании отдельной операции, такой как `Fill` или `Update`. Однако при выполнении нескольких операций, требующих открытого соединения, можно повысить производительность приложения путем явного вызова метода `Open` объекта `Connection`, выполнения операций с источником данных и последующего вызова метода `Close` объекта `Connection`. Необходимо сохранять соединения с источником данных лишь на такое короткое время, насколько это возможно, освобождая ресурсы для использования другими клиентскими приложениями.  
  
## <a name="multiple-result-sets"></a>Несколько результирующих наборов  
 Если объект `DataAdapter` обнаруживает несколько результирующих наборов, то создает несколько таблиц в `DataSet`. Таблицы получают добавочное имя по умолчанию Table*N*, для Table0 начинающееся с «Table». Если имя таблицы передается в качестве аргумента методу `Fill` , то таблицы получают по умолчанию имя TableName*N*с последовательно увеличивающимся суффиксом, но начиная с «TableName», а не с TableName0.  
  
## <a name="populating-a-dataset-from-multiple-dataadapters"></a>Заполнение DataSet из нескольких адаптеров данных DataAdapter  
 Любое количество `DataAdapter` объекты, которые могут использоваться с `DataSet`. Каждый объект `DataAdapter` может использоваться для заполнения одного или более объектов `DataTable` и разрешения обновлений в соответствующем источнике данных. Объекты`DataRelation` и `Constraint` могут быть добавлены к `DataSet` локально, что позволяет связывать данные из разнородных источников данных. Например, `DataSet` может содержать данные из базы данных Microsoft SQL Server, из базы данных IBM DB2, доступ к которой предоставляется с помощью OLE DB, и источника данных, предназначенного для получения XML-данных в виде потока. Один или несколько объектов `DataAdapter` могут обрабатывать соединение с каждым источником данных.  
  
### <a name="example"></a>Пример  
 В следующем примере кода заполняется список клиентов из базы данных `Northwind` Microsoft SQL Server и список заказов из базы данных `Northwind` , который хранится в Microsoft Access 2000. Заполненные таблицы связываются с помощью `DataRelation`, и список клиентов отображает заказы данного клиента. Дополнительные сведения о `DataRelation` объектов, в разделе [Добавление отношений DataRelation](../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md) и [перехода отношений DataRelation](../../../../docs/framework/data/adonet/dataset-datatable-dataview/navigating-datarelations.md).  
  
```vb  
' Assumes that customerConnection is a valid SqlConnection object.  
' Assumes that orderConnection is a valid OleDbConnection object.  
Dim custAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM dbo.Customers", customerConnection)  
  
Dim ordAdapter As OleDbDataAdapter = New OleDbDataAdapter( _  
  "SELECT * FROM Orders", orderConnection)  
  
Dim customerOrders As DataSet = New DataSet()  
custAdapter.Fill(customerOrders, "Customers")  
ordAdapter.Fill(customerOrders, "Orders")  
  
Dim relation As DataRelation = _  
  customerOrders.Relations.Add("CustOrders", _  
  customerOrders.Tables("Customers").Columns("CustomerID"), _   
  customerOrders.Tables("Orders").Columns("CustomerID"))  
  
Dim pRow, cRow As DataRow  
For Each pRow In customerOrders.Tables("Customers").Rows  
  Console.WriteLine(pRow("CustomerID").ToString())  
  
  For Each cRow In pRow.GetChildRows(relation)  
    Console.WriteLine(vbTab & cRow("OrderID").ToString())  
  Next  
Next  
```  
  
```csharp  
// Assumes that customerConnection is a valid SqlConnection object.  
// Assumes that orderConnection is a valid OleDbConnection object.  
SqlDataAdapter custAdapter = new SqlDataAdapter(  
  "SELECT * FROM dbo.Customers", customerConnection);  
OleDbDataAdapter ordAdapter = new OleDbDataAdapter(  
  "SELECT * FROM Orders", orderConnection);  
  
DataSet customerOrders = new DataSet();  
  
custAdapter.Fill(customerOrders, "Customers");  
ordAdapter.Fill(customerOrders, "Orders");  
  
DataRelation relation = customerOrders.Relations.Add("CustOrders",  
  customerOrders.Tables["Customers"].Columns["CustomerID"],  
  customerOrders.Tables["Orders"].Columns["CustomerID"]);  
  
foreach (DataRow pRow in customerOrders.Tables["Customers"].Rows)  
{  
  Console.WriteLine(pRow["CustomerID"]);  
   foreach (DataRow cRow in pRow.GetChildRows(relation))  
    Console.WriteLine("\t" + cRow["OrderID"]);  
}  
```  
  
## <a name="sql-server-decimal-type"></a>Тип decimal SQL Server  
 По умолчанию `DataSet` сохраняет данные с помощью типов данных платформы [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] . Для большинства приложений благодаря этому появляется удобный способ представления сведений об источнике данных. Однако данное представление может вызвать проблему, если типом данных в источнике данных является применяемый в SQL Server тип decimal или numeric. Тип данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] `decimal` data type allows a maximum of 28 significant digits, whereas the SQL Server `decimal` data type allows 38 significant digits. Если во время операции `SqlDataAdapter` `Fill` определяет, что точность поля `decimal` SQL Server больше 28 символов, текущая строка не добавляется в `DataTable`. Вместо этого происходит событие `FillError` , которое позволяет определить, произойдет ли потеря точности, и предпринять соответствующие действия. Дополнительные сведения о `FillError` событий, в разделе [обработка событий DataAdapter](../../../../docs/framework/data/adonet/handling-dataadapter-events.md). Для получения значения типа `decimal` SQL Server можно также использовать объект <xref:System.Data.SqlClient.SqlDataReader> и вызывать метод <xref:System.Data.SqlClient.SqlDataReader.GetSqlDecimal%2A> .  
  
 В[!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] 2.0 появилась расширенная поддержка <xref:System.Data.SqlTypes> в `DataSet`. Дополнительные сведения см. в разделе [SqlTypes and the DataSet](../../../../docs/framework/data/adonet/sql/sqltypes-and-the-dataset.md).  
  
## <a name="ole-db-chapters"></a>Разделы OLE DB  
 Иерархические наборы строк, или разделы (тип `DBTYPE_HCHAPTER` в OLE DB, тип `adChapter` в ADO), могут использоваться для заполнения содержимого `DataSet`. Когда <xref:System.Data.OleDb.OleDbDataAdapter> во время операции `Fill` обнаруживает столбец, разбитый на разделы, для этого столбца создается `DataTable` , данная таблица заполняется столбцами и строками из раздела. Таблице, созданной для разбитого на разделы столбца, присваивается имя, состоящее из имени родительской таблицы и имени разбитого на разделы столбца, в форме «*ParentTableNameChapteredColumnName*». Если в наборе данных `DataSet` уже содержится таблица, имя которой согласуется с именем разбитого на разделы столбца, то данными раздела заполняется текущая таблица. Если в существующей таблице нет столбца, совпадающего со столбцом, содержащимся в разделе, то добавляется новый столбец.  
  
 Перед заполнением таблиц в `DataSet` данными, содержащимися в разбитых на разделы столбцах, между родительской и дочерней таблицами иерархического набора строк создается связь путем добавления целочисленного столбца к родительской и дочерней таблицам, установки родительского столбца на автоприращение и создания `DataRelation` с помощью добавленных из обеих таблиц столбцов. Добавленной связи присваивается имя с использованием имен родительской таблицы и разбитого на разделы столбца в виде «*ParentTableNameChapterColumnName*».  
  
 Обратите внимание, что связанный столбец существует только в `DataSet`. Дальнейшее заполнение из источника данных может вызвать добавление к таблицам новых строк вместо внесения изменений в существующие строки.  
  
 Обратите внимание, что при использовании перегруженного метода `DataAdapter.Fill` , который принимает `DataTable`в качестве аргумента, заполняется только эта таблица. Целочисленный столбец с автоприращением все еще можно добавить в таблицу, но нельзя создать или заполнить дочернюю таблицу, а также нельзя создать связь.  
  
 В следующем примере используется поставщик MSDataShape для создания разбитого на разделы столбца для каждого клиента из списка клиентов. После этого `DataSet` заполняется данными.  
  
```vb  
Using connection As OleDbConnection = New OleDbConnection( _  
  "Provider=MSDataShape;Data Provider=SQLOLEDB;" & _  
  "Data Source=(local);Integrated " & _  
  "Security=SSPI;Initial Catalog=northwind")  
  
Dim adapter As OleDbDataAdapter = New OleDbDataAdapter( _  
  "SHAPE {SELECT CustomerID, CompanyName FROM Customers} " & _  
  "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS Orders " & _  
  "RELATE CustomerID TO CustomerID)", connection)  
  
Dim customers As DataSet = New DataSet()  
  
adapter.Fill(customers, "Customers")  
End Using  
```  
  
```csharp  
using (OleDbConnection connection = new OleDbConnection("Provider=MSDataShape;Data Provider=SQLOLEDB;" +  
  "Data Source=(local);Integrated Security=SSPI;Initial Catalog=northwind"))  
{  
OleDbDataAdapter adapter = new OleDbDataAdapter("SHAPE {SELECT CustomerID, CompanyName FROM Customers} " +  
  "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS Orders " +  
  "RELATE CustomerID TO CustomerID)", connection);  
  
DataSet customers = new DataSet();  
adapter.Fill(customers, "Customers");  
}  
```  
  
 Когда операция `Fill` завершена, набор данных `DataSet` содержит две таблицы: `Customers` и `CustomersOrders`, в которых `CustomersOrders` представляет столбец, разбитый на разделы. Дополнительный столбец с именем `Orders` добавляется к таблице `Customers` , а дополнительный столбец с именем `CustomersOrders` добавляется к таблице `CustomersOrders` . Столбец `Orders` в таблице `Customers` устанавливается на автоприращение. `DataRelation`, `CustomersOrders`, создается с помощью столбцов, которые были добавлены к таблицам с `Customers` в виде дочерней таблицы. Следующие таблицы показывают некоторые образцы результатов.  
  
### <a name="tablename-customers"></a>TableName: Customers  
  
|CustomerID|CompanyName|Orders|  
|----------------|-----------------|------------|  
|ALFKI|Alfreds Futterkiste|0|  
|ANATR|Ana Trujillo Emparedados y helados|1|  
  
### <a name="tablename-customersorders"></a>TableName: CustomersOrders  
  
|CustomerID|OrderID|CustomersOrders|  
|----------------|-------------|---------------------|  
|ALFKI|10643|0|  
|ALFKI|10692|0|  
|ANATR|10308|1|  
|ANATR|10625|1|  
  
## <a name="see-also"></a>См. также  
 [Объекты DataAdapter и DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [Сопоставления типов данных в ADO.NET](../../../../docs/framework/data/adonet/data-type-mappings-in-ado-net.md)  
 [Изменение данных с помощью DbDataAdapter](../../../../docs/framework/data/adonet/modifying-data-with-a-dbdataadapter.md)  
 [Несколько активных результирующих наборов (MARS)](../../../../docs/framework/data/adonet/sql/multiple-active-result-sets-mars.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
