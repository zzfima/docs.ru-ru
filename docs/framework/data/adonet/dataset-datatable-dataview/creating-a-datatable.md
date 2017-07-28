---
title: "Создание DataTable | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: eecf9d78-60e3-4fdc-8de0-e56c13a89414
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Создание DataTable
Объект <xref:System.Data.DataTable>, который представляет одну таблицу находящихся в памяти реляционных данных, может создаваться и использоваться независимо или использоваться другими объектами .NET Framework, чаще всего как член <xref:System.Data.DataSet>.  
  
 Объект **DataTable** можно создать, используя соответствующий конструктор для **DataTable**.  Этот объект можно добавить в **DataSet** при помощи метода **Add**, чтобы добавить его в коллекцию **Tables** объекта **DataTable**.  
  
 Можно также создать объекты **DataTable** в **DataSet** при помощи методов **Fill** или **FillSchema** объекта **DataAdapter** либо из стандартной или выводимой схемы XML с использованием методов **ReadXml**, **ReadXmlSchema** или **InferXmlSchema** объекта **DataSet**.  Следует отметить, что после добавления объекта **DataTable** как члена коллекции **Tables** объекта **DataSet** его нельзя добавить в коллекцию таблиц какого\-либо другого объекта **DataSet**.  
  
 При первом создании объекта **DataTable** у него нет схемы \(т. е. структуры\).  Для определения схемы таблицы необходимо создать и добавить объекты <xref:System.Data.DataColumn> в коллекцию **Columns** таблицы.  Можно также определить столбец первичного ключа для таблицы, а также создать и добавить объекты **Constraint** в коллекцию **Constraints** таблицы.  После определения схемы для таблицы **DataTable** можно добавить в таблицу строки данных, добавив объекты **DataRow** в коллекцию **Rows** таблицы.  
  
 Не требуется предоставлять значение для свойства <xref:System.Data.DataTable.TableName%2A> при создании объекта **DataTable**; свойство можно задать в любое время либо оставить его пустым.  Однако при добавлении таблицы без значения **TableName** в объект **DataSet** таблице присваивается имя по умолчанию Table*N* с увеличивающимся каждый раз значением N на единицу, начиная с имени «Table» для Table0.  
  
> [!NOTE]
>  Мы рекомендуем избегать такого соглашения об именах, как «Table*N*» при предоставлении значения **TableName**, т. к. предоставляемое имя может вступать в конфликт с именем по умолчанию существующей таблицы в объекте **DataSet**.  Если указанное имя уже существует, вызывается исключение.  
  
 В следующем примере создается экземпляр объекта **DataTable**, которому присваивается имя «Customers».  
  
```vb  
Dim workTable as DataTable = New DataTable("Customers")  
  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
```  
  
 В следующем примере создается экземпляр таблицы **DataTable** добавлением его в коллекцию **Tables** объекта **DataSet**.  
  
```vb  
Dim customers As DataSet = New DataSet  
Dim customersTable As DataTable = _  
   customers.Tables.Add("CustomersTable")  
  
```  
  
```csharp  
DataSet customers = new DataSet();  
DataTable customersTable = customers.Tables.Add("CustomersTable");  
```  
  
## См. также  
 <xref:System.Data.DataTable>   
 <xref:System.Data.DataTableCollection>   
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)   
 [Заполнение набора данных с помощью адаптера данных DataAdapter](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)   
 [Загрузка DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)   
 [Загрузка сведений о схеме DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)