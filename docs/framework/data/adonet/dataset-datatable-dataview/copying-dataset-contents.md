---
title: Копирование содержимого набора данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cb846617-2b1a-44ff-bd7f-5835f5ea37fa
ms.openlocfilehash: f60ef817773b6234b19856bfc0727eedb67e113e
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2019
ms.locfileid: "70205171"
---
# <a name="copying-dataset-contents"></a>Копирование содержимого набора данных
Можно создать копию, <xref:System.Data.DataSet> чтобы можно было работать с данными, не затрагивая исходные данные, или работать с подмножеством данных из **набора**данных. При копировании **набора данных**можно выполнить следующие действия.  
  
- Создайте точную копию **набора данных**, включая схему, данные, сведения о состоянии строки и версии строк.  
  
- Создайте **набор данных** , содержащий схему существующего **набора данных**, но только измененные строки. Можно вернуть все измененные строки или указать конкретный **датаровстате**. Дополнительные сведения о состояниях строк см. в разделе [состояния строк и версии строк](row-states-and-row-versions.md).  
  
- Скопируйте схему или реляционную структуру только **набора данных** без копирования каких бы то ни было строк. Строки могут быть импортированы в существующий объект <xref:System.Data.DataTable> с использованием <xref:System.Data.DataTable.ImportRow%2A>.  
  
 Чтобы создать точную копию **набора данных** , включающего как схему, так и данные, используйте <xref:System.Data.DataSet.Copy%2A> метод **набора данных**. В следующем примере кода показано, как создать точную копию **набора данных**.  
  
```vb  
Dim copyDataSet As DataSet = customerDataSet.Copy()  
```  
  
```csharp  
DataSet copyDataSet = customerDataSet.Copy();  
```  
  
 Чтобы создать копию **набора данных** , включающего схему, и только данные, представляющие **добавленные**, **измененные**или **Удаленные** строки, <xref:System.Data.DataSet.GetChanges%2A> используйте метод **набора данных**. Можно также использовать функции GetRows, чтобы возвратить только строки с указанным состоянием строки, передав значение **датаровстате** при вызовеметода GetRows. В следующем примере кода показано, как передать **датаровстате** при вызове методаического **изменения**.  
  
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
  
 Чтобы создать копию **набора данных** , включающего только схему, используйте <xref:System.Data.DataSet.Clone%2A> метод **набора данных**. Можно также добавить существующие строки в клонированный **набор данных** с помощью метода **импортров** объекта **DataTable**. **Импортров** добавляет данные, состояние строки и сведения о версии строки в указанную таблицу. Значения столбца добавляются только в тех случаях, если имена столбцов согласуются, а типы данных являются совместимыми.  
  
 В следующем примере кода создается клон **набора данных** , а затем строки из исходного **набора данных** добавляются в таблицу **Customers** в клоне **набора данных** для клиентов, где столбец **страна** имеет значение "Германия ".  
  
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
  
## <a name="see-also"></a>См. также

- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [Наборы данных, таблицы данных и объекты DataView](index.md)
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
