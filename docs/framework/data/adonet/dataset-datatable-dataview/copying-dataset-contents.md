---
title: Копирование содержимого набора данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cb846617-2b1a-44ff-bd7f-5835f5ea37fa
ms.openlocfilehash: de13e07eb5c19b8beffa724fec4a128c418a4fed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151368"
---
# <a name="copying-dataset-contents"></a>Копирование содержимого набора данных
Можно создать копию, <xref:System.Data.DataSet> чтобы работать с данными, не влияя на исходные данные, или работать с подмножеством данных из **DataSet.** При копировании **набора данных**можно:  
  
- Создайте точную копию **DataSet,** включая схему, данные, сведения о состоянии строк и версии строк.  
  
- Создайте **DataSet,** содержащий схему существующего **DataSet,** но только строки, которые были изменены. Вы можете вернуть все строки, которые были изменены, или указать конкретные **DataRowState.** Для получения дополнительной информации [Row States and Row Versions](row-states-and-row-versions.md)о состояниях строк см.  
  
- Копируйте схему, или реляционную структуру, только **DataSet,** не копируя строки. Строки могут быть импортированы в существующий объект <xref:System.Data.DataTable> с использованием <xref:System.Data.DataTable.ImportRow%2A>.  
  
 Чтобы создать точную копию **DataSet,** которая включает в <xref:System.Data.DataSet.Copy%2A> себя как схему, так и данные, используйте метод **DataSet.** Следующий пример кода показывает, как создать точную копию **DataSet.**  
  
```vb  
Dim copyDataSet As DataSet = customerDataSet.Copy()  
```  
  
```csharp  
DataSet copyDataSet = customerDataSet.Copy();  
```  
  
 Для создания копии **DataSet,** включающей схему и только данные, представляющие **добавленные,** **измененные**или **удаленные** строки, используйте <xref:System.Data.DataSet.GetChanges%2A> метод **DataSet.** Вы также можете использовать **GetChanges** для возврата только строк с указанным состоянием строки, передавая значение **DataRowState** при вызове **GetChanges.** Следующий пример кода показывает, как пройти **DataRowState** при вызове **GetChanges.**  
  
```vb  
' Copy all changes.  
Dim changeDataSet As DataSet = customerDataSet.GetChanges()  
' Copy only new rows.  
Dim addedDataSetAs DataSet = _  
    customerDataSet.GetChanges(DataRowState.Added)  
```  
  
```csharp  
// Copy all changes.  
DataSet changeDataSet = customerDataSet.GetChanges();  
// Copy only new rows.  
DataSet addedDataSet= customerDataSet.GetChanges(DataRowState.Added);  
```  
  
 Чтобы создать копию **DataSet,** которая включает только <xref:System.Data.DataSet.Clone%2A> схему, используйте метод **DataSet.** Можно также добавить существующие строки в клонированный **DataSet** с помощью метода **ImportRow** **DataTable.** **ImportRow** добавляет данные, состояние строки и информацию о строке версии в указанную таблицу. Значения столбца добавляются только в тех случаях, если имена столбцов согласуются, а типы данных являются совместимыми.  
  
 Следующий пример кода создает клон **DataSet,** а затем добавляет строки из исходного **Набора данных** в таблицу **клиентов** в клоне **DataSet** для клиентов, где столбец **CountryRegion** имеет значение "Германия".  
  
```vb  
Dim customerDataSet As New DataSet  
        customerDataSet.Tables.Add(New DataTable("Customers"))  
        customerDataSet.Tables("Customers").Columns.Add("Name", GetType(String))  
        customerDataSet.Tables("Customers").Columns.Add("CountryRegion", GetType(String))  
        customerDataSet.Tables("Customers").Rows.Add("Juan", "Spain")  
        customerDataSet.Tables("Customers").Rows.Add("Johann", "Germany")  
        customerDataSet.Tables("Customers").Rows.Add("John", "UK")  
  
Dim germanyCustomers As DataSet = customerDataSet.Clone()  
  
Dim copyRows() As DataRow = _  
  customerDataSet.Tables("Customers").Select("CountryRegion = 'Germany'")  
  
Dim customerTable As DataTable = germanyCustomers.Tables("Customers")  
Dim copyRow As DataRow  
  
For Each copyRow In copyRows  
  customerTable.ImportRow(copyRow)  
Next  
```  
  
```csharp  
DataSet customerDataSet = new DataSet();  
customerDataSet.Tables.Add(new DataTable("Customers"));  
customerDataSet.Tables["Customers"].Columns.Add("Name", typeof(string));  
customerDataSet.Tables["Customers"].Columns.Add("CountryRegion", typeof(string));  
customerDataSet.Tables["Customers"].Rows.Add("Juan", "Spain");  
customerDataSet.Tables["Customers"].Rows.Add("Johann", "Germany");  
customerDataSet.Tables["Customers"].Rows.Add("John", "UK");  
  
DataSet germanyCustomers = customerDataSet.Clone();  
  
DataRow[] copyRows =
  customerDataSet.Tables["Customers"].Select("CountryRegion = 'Germany'");  
  
DataTable customerTable = germanyCustomers.Tables["Customers"];  
  
foreach (DataRow copyRow in copyRows)  
  customerTable.ImportRow(copyRow);  
```  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [Наборы данных, таблицы данных и объекты DataView](index.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
