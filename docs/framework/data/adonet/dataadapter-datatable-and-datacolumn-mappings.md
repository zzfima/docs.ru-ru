---
title: Сопоставления DataAdapter DataTable и DataColumn
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d023260a-a66a-4c39-b8f4-090cd130e730
ms.openlocfilehash: 9f33ae085bef2b611d1ce95bed1b26f9101a10b9
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43385230"
---
# <a name="dataadapter-datatable-and-datacolumn-mappings"></a>Сопоставления DataAdapter DataTable и DataColumn
Объект **DataAdapter** содержит коллекцию из нуля или более <xref:System.Data.Common.DataTableMapping> объекты в его **TableMappings** свойство. Объект **DataTableMapping** предоставляет главное сопоставление между данными, возвращенные запросом в источнике данных и <xref:System.Data.DataTable>. **DataTableMapping** может быть передано вместо **DataTable** в **заполнения** метод **DataAdapter**. В следующем примере создается **DataTableMapping** с именем **AuthorsMapping** для **авторы** таблицы.  
  
```vb  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors")  
```  
  
```csharp  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors");  
```  
  
 Объект **DataTableMapping** позволяет использовать имена столбцов в **DataTable** , которые отличаются от тех, которые в базе данных. **DataAdapter** сопоставление используется для согласования столбцов при обновлении таблицы.  
  
 Если вы не укажете **TableName** или **DataTableMapping** при вызове **заполнения** или **обновление** метод  **DataAdapter**, **DataAdapter** ищет **DataTableMapping** с именем «Table». Если это **DataTableMapping** не существует, **TableName** из **DataTable** является «Table». Можно задать значение по умолчанию **DataTableMapping** путем создания **DataTableMapping** с именем «TABLE».  
  
 В следующем примере кода создается **DataTableMapping** (из <xref:System.Data.Common> пространства имен) и делает его сопоставление по умолчанию для указанного **DataAdapter** путем присваивания ему имени «Table». Пример затем сопоставляет столбцы из первой таблицы, в результате запроса ( **клиентов** таблицы **Northwind** базы данных) в набор более понятные имена в **Northwind Customers**  в таблицу <xref:System.Data.DataSet>. Для столбцов, к которым не применяется сопоставление, используются имена столбцов из источника данных.  
  
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
  
 В более сложных ситуациях можно решить, что требуется же **DataAdapter** должен поддерживать загрузку разных таблиц с различными сопоставлениями. Чтобы сделать это, просто добавьте дополнительные **DataTableMapping** объектов.  
  
 Когда **заполнения** методу передается экземпляр **набора данных** и **DataTableMapping** имя, если сопоставление с таким именем существует, он используется, в противном случае,  **DataTable** с, используется имя.  
  
 В следующих примерах создаются **DataTableMapping** с именем **клиентов** и **DataTable** имя **BizTalkSchema**. Пример затем сопоставляет строк, возвращаемых инструкцией SELECT для **BizTalkSchema** **DataTable**.  
  
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
>  Если имя исходного столбца не задано для сопоставления столбцов, или имя исходной таблицы не задано для сопоставления таблиц, то автоматически создаются имена, применяемые по умолчанию. Если ни один исходный столбец для отображения столбцов, сопоставлению столбцов присваивается предусмотренное по умолчанию имя **SourceColumn** *N,* начиная с **Исходныйстолбец1**. Если нет имя исходной таблицы для сопоставления таблиц, сопоставлению таблиц присваивается предусмотренное по умолчанию имя **SourceTable** *N*, начиная с **Исходнаятаблица1**.  
  
> [!NOTE]
>  Мы рекомендуем избегать именования **SourceColumn** *N* для сопоставления столбцов, или **SourceTable** *N* для таблицы сопоставление, так как к. предоставляемое имя может конфликтовать с существующим именем сопоставления столбцов по умолчанию в **ColumnMappingCollection** или имени таблицы сопоставления в **DataTableMappingCollection** . Если указанное имя уже существует, возникает исключение.  
  
## <a name="handling-multiple-result-sets"></a>Обработка нескольких результирующих наборов  
 Если ваш **SelectCommand** возвращает несколько таблиц, **заполнения** автоматически формирует имена таблиц с добавочные значения для таблиц в **набора данных**, начиная с указано имя таблицы и продолжая на в виде **TableName** *N*, начиная с **TableName1**. Можно использовать сопоставления таблиц для сопоставления автоматически создаваемого имени таблицы с именем, которое требуется задать для таблицы в **набора данных**. Например, для **SelectCommand** , возвращает две таблицы, **клиентов** и **заказы**, выполните следующий вызов в **заполнения**.  
  
```  
adapter.Fill(customersDataSet, "Customers")  
```  
  
 Будут созданы две таблицы в **набора данных**: **клиентов** и **Customers1**. Можно использовать сопоставления таблиц, чтобы убедиться, что во второй таблице называется **заказы** вместо **Customers1**. Чтобы сделать это, необходимо сопоставить исходную таблицу из **Customers1** для **набора данных** таблицы **заказы**, как показано в следующем примере.  
  
```  
adapter.TableMappings.Add("Customers1", "Orders")  
adapter.Fill(customersDataSet, "Customers")  
```  
  
## <a name="see-also"></a>См. также  
 [Объекты DataAdapter и DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [Извлечение и изменение данных в ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
