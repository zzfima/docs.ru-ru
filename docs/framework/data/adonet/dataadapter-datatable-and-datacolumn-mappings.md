---
title: "Сопоставления DataAdapter, DataTable и DataColumn | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d023260a-a66a-4c39-b8f4-090cd130e730
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Сопоставления DataAdapter, DataTable и DataColumn
Сопоставление **DataAdapter** содержит коллекцию, имеющую от нуля или больше объектов <xref:System.Data.Common.DataTableMapping>, в своем свойстве **TableMappings**.  Класс **DataTableMapping** предоставляет главное сопоставление между данными, возвращенными запросом к источнику данных, и <xref:System.Data.DataTable>.  Имя **DataTableMapping** может быть передано вместо имени **DataTable** в метод **Fill** сопоставления **DataAdapter**.  В следующем примере создается экземпляр класса **DataTableMapping** с именем **AuthorsMapping** для таблицы **Authors**.  
  
```vb  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors")  
```  
  
```csharp  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors");  
```  
  
 Класс **DataTableMapping** позволяет использовать имена столбцов в объекте **DataTable**, отличные от таковых в базе данных.  В сопоставлении **DataAdapter** это сопоставление используется для согласования столбцов при обновлении таблицы.  
  
 Если не указан объект **TableName** или имя **DataTableMapping** при вызове метода **Fill** или **Update** объекта **DataAdapter**, то в объекте **DataAdapter** выполняется поиск экземпляра **DataTableMapping** с именем «Table».  Если имя **DataTableMapping** не существует, то значением **TableName** для объекта **DataTable** является «Table».  Можно указать применяемый по умолчанию класс **DataTableMapping** при создании объекта **DataTableMapping** с именем «Table».  
  
 В следующем примере кода создается экземпляр **DataTableMapping** \(из пространства имен <xref:System.Data.Common>\) и задается в качестве применяемого по умолчанию отображения для указанного объекта **DataAdapter** путем присваивания ему имени «Table».  Затем в этом примере столбцы из первой таблицы в результатах запроса \(таблицы **Customers** базы данных **Northwind**\) сопоставляются с набором понятных для пользователя имен в таблице **Northwind Customers** в <xref:System.Data.DataSet>.  Для столбцов, к которым не применяется сопоставление, используются имена столбцов из источника данных.  
  
```vb  
Dim mapping As DataTableMapping = _  
  adapter.TableMappings.Add("Table", "NorthwindCustomers")  
mapping.ColumnMappings.Add("CompanyName", "Company")  
mapping.ColumnMappings.Add("ContactName", "Contact")  
mapping.ColumnMappings.Add("PostalCode", "ZIPCode")  
  
adapter.Fill(custDS)  
  
```  
  
```csharp  
DataTableMapping mapping =   
  adapter.TableMappings.Add("Table", "NorthwindCustomers");  
mapping.ColumnMappings.Add("CompanyName", "Company");  
mapping.ColumnMappings.Add("ContactName", "Contact");  
mapping.ColumnMappings.Add("PostalCode", "ZIPCode");  
  
adapter.Fill(custDS);  
```  
  
 В более сложных ситуациях может быть принято решение, что один и тот же экземпляр **DataAdapter** должен поддерживать загрузку разных таблиц с различными сопоставлениями.  Чтобы обеспечить реализацию такого решения, достаточно просто ввести дополнительные объекты **DataTableMapping**.  
  
 Если методу **Fill** передается экземпляр **DataSet** и имя **DataTableMapping**, то при наличии сопоставления с этим именем используется это сопоставление; в противном случае используется объект **DataTable** с этим именем.  
  
 В следующих примерах создается экземпляр **DataTableMapping** с именем **Customers** и именем объекта **DataTable**, равным **BizTalkSchema**.  Затем в этом примере строки, возвращаемые инструкцией SELECT, сопоставляются с объектом **DataTable**, имеющим имя **BizTalkSchema**.  
  
```vb  
Dim mapping As ITableMapping = _  
  adapter.TableMappings.Add("Customers", "BizTalkSchema")  
mapping.ColumnMappings.Add("CustomerID", "ClientID")  
mapping.ColumnMappings.Add("CompanyName", "ClientName")  
mapping.ColumnMappings.Add("ContactName", "Contact")  
mapping.ColumnMappings.Add("PostalCode", "ZIP")  
  
adapter.Fill(custDS, "Customers")  
  
```  
  
```csharp  
ITableMapping mapping =   
  adapter.TableMappings.Add("Customers", "BizTalkSchema");  
mapping.ColumnMappings.Add("CustomerID", "ClientID");  
mapping.ColumnMappings.Add("CompanyName", "ClientName");  
mapping.ColumnMappings.Add("ContactName", "Contact");  
mapping.ColumnMappings.Add("PostalCode", "ZIP");  
  
adapter.Fill(custDS, "Customers");  
```  
  
> [!NOTE]
>  Если имя исходного столбца не задано для сопоставления столбцов, или имя исходной таблицы не задано для сопоставления таблиц, то автоматически создаются имена, применяемые по умолчанию.  Если ни один исходный столбец не предоставлен для сопоставления столбцов, то сопоставлению столбцов присваивается предусмотренное по умолчанию имя **ИсходныйСтолбец** *N* с автоматически увеличивающимся суффиксом, начиная с **ИсходныйСтолбец1**.  Если ни одно имя исходной таблицы не предоставлено для сопоставления таблиц, то сопоставлению таблиц присваивается предусмотренное по умолчанию имя **ИсходнаяТаблица** *N* с автоматически увеличивающимся суффиксом, начиная с **ИсходнаяТаблица1**.  
  
> [!NOTE]
>  Рекомендуется избегать использования соглашения об именах **ИсходныйСтолбец** *N* для сопоставления столбцов или **ИсходнаяТаблица** *N* для сопоставления таблиц, поскольку заданное имя может конфликтовать с существующим именем заданного по умолчанию сопоставления столбцов в коллекции **ColumnMappingCollection** или с именем сопоставления таблиц в коллекции **DataTableMappingCollection**.  Если указанное имя уже существует, возникает исключение.  
  
## Обработка нескольких результирующих наборов  
 Если команда **SelectCommand** возвращает несколько таблиц, то в методе **Fill** для таблиц в объекте **DataSet** автоматически формируются имена, которые в качестве суффиксов имеют автоматически увеличивающиеся значения. Значения начинаются с указанного имени таблицы и увеличиваются в форме **ИмяТаблицы** *N*, причем первым значением является **ИмяТаблицы1**.  Можно использовать сопоставления таблиц для сопоставления автоматически создаваемого имени таблицы с тем именем, которое требуется задать для таблицы в объекте **DataSet**.  Например, для к команды **SelectCommand**, которая возвращает две таблицы, **Customers** и **Orders**, можно выполнить следующий вызов метода **Fill**.  
  
```  
adapter.Fill(customersDataSet, "Customers")  
```  
  
 В объекте **DataSet** будут созданы две таблицы: **Customers** и **Customers1**.  Можно использовать сопоставления таблиц для обеспечения того, чтобы вторая таблица получила имя **Orders** вместо **Customers1**.  Для этого необходимо сопоставить исходную таблицу **Customers1** с таблицей **Orders** из **DataSet**, как показано в следующем примере.  
  
```  
adapter.TableMappings.Add("Customers1", "Orders")  
adapter.Fill(customersDataSet, "Customers")  
```  
  
## См. также  
 [Объекты DataAdapter и DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)   
 [Получение и изменение данных в ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)