---
title: Сопоставления DataAdapter DataTable и DataColumn
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d023260a-a66a-4c39-b8f4-090cd130e730
ms.openlocfilehash: a9c81c8554c0fb393c10ed69f84c8b2d936ec1e6
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040126"
---
# <a name="dataadapter-datatable-and-datacolumn-mappings"></a>Сопоставления DataAdapter DataTable и DataColumn
Объект **DataAdapter** содержит коллекцию из нуля или более <xref:System.Data.Common.DataTableMapping> объектов в своем свойстве **TableMappings** . **Экземпляр DataTableMapping** предоставляет основное сопоставление данных, возвращенных запросом к источнику данных, и <xref:System.Data.DataTable>. Имя **экземпляр DataTableMapping** может быть передано вместо имени **DataTable** в метод **Fill** объекта **DataAdapter**. В следующем примере создается **экземпляр DataTableMapping** с именем **Аусорсмаппинг** для таблицы **authors** .  
  
```vb  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors")  
```  
  
```csharp  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors");  
```  
  
 **Экземпляр DataTableMapping** позволяет использовать имена столбцов в **DataTable** , которые отличаются от имен в базе данных. Объект **DataAdapter** использует сопоставление для сопоставления столбцов при обновлении таблицы.  
  
 Если не указать имя **TableName** или **экземпляр DataTableMapping** при вызове метода **Fill** или **Update** объекта **DataAdapter**, то **DataAdapter** ищет **экземпляр DataTableMapping** с именем Table. Если этот **экземпляр DataTableMapping** не существует, то **TableName** объекта **DataTable** имеет значение Table. Можно указать **экземпляр DataTableMapping** по умолчанию, создав **экземпляр DataTableMapping** с именем "Table".  
  
 Следующий пример кода создает **экземпляр DataTableMapping** (из пространства имен <xref:System.Data.Common>) и делает его сопоставлением по умолчанию для указанного **объекта DataAdapter** , присваивая ему имя "Table". Затем в примере сопоставляются столбцы из первой таблицы в результатах запроса (таблица **Customers** базы данных **Northwind** ) с набором более понятных имен пользователей в таблице **"Customers"** в <xref:System.Data.DataSet>. Для столбцов, к которым не применяется сопоставление, используются имена столбцов из источника данных.  
  
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
  
 В более сложных ситуациях может потребоваться, чтобы один и тот же **DataAdapter** поддерживал загрузку различных таблиц с разными сопоставлениями. Для этого просто добавьте дополнительные объекты **экземпляр DataTableMapping** .  
  
 Если методу **Fill** передается экземпляр **набора данных** и имя **экземпляр DataTableMapping** , если сопоставление с таким именем существует, оно используется; в противном случае используется **Таблица** данных с таким именем.  
  
 В следующих примерах создается **экземпляр DataTableMapping** с именем **Customers** и **DataTable** с именем **бизталксчема**. Затем в примере сопоставляются строки, возвращенные инструкцией SELECT, с **таблицей**данных **бизталксчема** .  
  
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
> Если имя исходного столбца не задано для сопоставления столбцов, или имя исходной таблицы не задано для сопоставления таблиц, то автоматически создаются имена, применяемые по умолчанию. Если для сопоставления столбцов не указан исходный столбец, сопоставлению столбцов присваивается добавочное имя по умолчанию **SourceColumn** *N,* начиная с **SourceColumn1**. Если для сопоставления таблицы не указано имя исходной таблицы, сопоставлению таблицы присваивается добавочное имя по умолчанию **SourceTable** *N*, начиная с **SourceTable1**.  
  
> [!NOTE]
> Мы рекомендуем не использовать соглашение об именовании **SourceColumn** *N* для сопоставления столбцов или **SourceTable** *N* для сопоставления таблиц, так как указываемое имя может конфликтовать с существующим именем сопоставления столбцов по умолчанию в  **Колумнмаппингколлектион** или имя сопоставления таблицы в **дататаблемаппингколлектион**. Если указанное имя уже существует, возникает исключение.  
  
## <a name="handling-multiple-result-sets"></a>Обработка нескольких результирующих наборов  
 Если **SelectCommand** возвращает несколько таблиц, функция **Fill** автоматически создает имена таблиц с добавочными значениями для таблиц в **наборе данных**, начиная с указанного имени таблицы и продолжая в форме **TableName** . *N*, начиная с **TableName1**. Сопоставления таблиц можно использовать для сопоставления автоматически создаваемого имени таблицы с именем, которое необходимо указать для таблицы в **наборе данных**. Например, для **SelectCommand** , возвращающего две таблицы, **Customers** и **Orders**, выполните следующий вызов функции **Fill**.  
  
```vb  
adapter.Fill(customersDataSet, "Customers")  
```  

```csharp  
adapter.Fill(customersDataSet, "Customers");  
```  

 В **наборе данных**создаются две таблицы: **Customers** и **Customers1**. Можно использовать сопоставления таблиц, чтобы гарантировать, что вторая таблица будет называться **Orders** вместо **Customers1**. Для этого сопоставьте исходную таблицу **Customers1** со столбцами таблицы **набора данных** ,как показано в следующем примере.  
  
```vb  
adapter.TableMappings.Add("Customers1", "Orders")  
adapter.Fill(customersDataSet, "Customers")  
```  

```csharp  
adapter.TableMappings.Add("Customers1", "Orders");  
adapter.Fill(customersDataSet, "Customers");  
```
  
## <a name="see-also"></a>См. также

- [Объекты DataAdapter и DataReader](dataadapters-and-datareaders.md)
- [Извлечение и изменение данных в ADO.NET](retrieving-and-modifying-data.md)
- [Общие сведения об ADO.NET](ado-net-overview.md)
