---
title: Сопоставления DataAdapter DataTable и DataColumn
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d023260a-a66a-4c39-b8f4-090cd130e730
ms.openlocfilehash: 6380dd0512bd7834f50b87f90f445cb01b7a8b95
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151563"
---
# <a name="dataadapter-datatable-and-datacolumn-mappings"></a>Сопоставления DataAdapter DataTable и DataColumn
**DataAdapter** содержит коллекцию объектов <xref:System.Data.Common.DataTableMapping> с нулевым или большим количеством объектов в **свойстве TableMappings.** **DataTableMapping** предоставляет мастер-картографирование между данными, возвращенными из <xref:System.Data.DataTable>запроса, против источника данных и . Имя **DataTableMapping** может быть передано вместо имени **DataTable** методу **заполнения** **DataAdapter.** Следующий пример создает **таблицу DataTableMapping** под названием **AuthorsMapping** для **авторов** таблицы.  
  
```vb  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors")  
```  
  
```csharp  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors");  
```  
  
 **DataTableMapping** позволяет использовать имена столбцов в **DataTable,** которые отличаются от тех, которые находятся в базе данных. **DataAdapter** использует отображение для соответствия столбцов при обновлении таблицы.  
  
 Если при вызове метода **Заполнения** или **обновления** **DataAdapter**вы не указали **имя TableName** или **имя DataTableMapping,** **DataAdapter** ищет **DataTableMapping** под названием "Таблица". Если этого **DataTableMapping** не существует, **таблицаНазвание** **dataTable** — это «Таблица». Можно указать **данные** по умолчанию, создав **DataTableMapping** с именем "Таблица".  
  
 Следующий пример кода создает **DataTableMapping** (из пространства <xref:System.Data.Common> имен) и делает его отображением по умолчанию для указанного **DataAdapter,** назвав его "Таблица". Затем в примере отображается столбцы из первой таблицы в результате запроса (таблица **клиентов** базы данных **Northwind)** <xref:System.Data.DataSet>с набором более удобных имен в таблице **клиентов Northwind** в таблице . Для столбцов, к которым не применяется сопоставление, используются имена столбцов из источника данных.  
  
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
  
 В более продвинутых ситуациях вы можете решить, что вам нужно, чтобы тот же **DataAdapter** поддерживал загрузку различных таблиц с различными отображениями. Для этого просто добавьте дополнительные объекты **DataTableMapping.**  
  
 При переводе метода **заполнения** **экземплярА DataSet** и имени **DataTableMapping,** если существует отображение с этим именем, оно используется; в противном случае используется **DataTable** с таким именем.  
  
 Следующие примеры создают **DataTableMapping** с именем **Клиентов** и именем **DataTable** **BizTalkSchema**. Пример затем отображает строки, возвращенные выпиской SELECT, в **BizTalkSchema** **DataTable.**  
  
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
> Если имя исходного столбца не задано для сопоставления столбцов, или имя исходной таблицы не задано для сопоставления таблиц, то автоматически создаются имена, применяемые по умолчанию. Если столбец исходного кода не поставляется для отображения столбца, отображению столбца дается дополнительное имя по умолчанию **SourceColumn** *N,* начиная с **SourceColumn1.** Если имя исходной таблицы не поставляется для отображения таблицы, отображение таблицы получает дополнительное значение значения по умолчанию **SourceTable** *N,* начиная с **SourceTable1.**  
  
> [!NOTE]
> Мы рекомендуем вам избегать именования конвенции **SourceColumn** *N* для отображения столбцов или **SourceTable** *N* для отображения таблицы, поскольку имя, которое вы поставляете, может противоречить существующему имени столбца по умолчанию в названии **columnMappingCollection** или имя отображения таблицы в **DataTableMappingCollection.** Если указанное имя уже существует, возникает исключение.  
  
## <a name="handling-multiple-result-sets"></a>Обработка нескольких результирующих наборов  
 Если **SelectCommand** возвращает несколько таблиц, **Fill** автоматически генерирует имена таблиц с дополнительными значениями для таблиц в **DataSet,** начиная с указанного имени таблицы и продолжая в форме **TableName** *N,* начиная с **TableName1.** Можно использовать таблицы для отображения автоматически генерируемого имени таблицы с именем, которое вы хотите указать для таблицы **DataSet.** Например, для **SelectCommand,** который возвращает две таблицы, **Клиенты** и **Заказы,** выдать следующий вызов **для заполнения.**  
  
```vb  
adapter.Fill(customersDataSet, "Customers")  
```  

```csharp  
adapter.Fill(customersDataSet, "Customers");  
```  

 В **DataSet**создаются две таблицы: **Клиенты** и **клиенты1**. Можно использовать таблицы для картирования, чтобы убедиться, что вторая таблица называется **Заказы** вместо **Customers1.** Для этого нанесите карту исходной таблицы **Customers1** в таблицу **DataSet** **Orders,** как показано в следующем примере.  
  
```vb  
adapter.TableMappings.Add("Customers1", "Orders")  
adapter.Fill(customersDataSet, "Customers")  
```  

```csharp  
adapter.TableMappings.Add("Customers1", "Orders");  
adapter.Fill(customersDataSet, "Customers");  
```
  
## <a name="see-also"></a>См. также раздел

- [Объекты DataAdapter и DataReader](dataadapters-and-datareaders.md)
- [Извлечение и изменение данных в ADO.NET](retrieving-and-modifying-data.md)
- [Общие сведения об ADO.NET](ado-net-overview.md)
