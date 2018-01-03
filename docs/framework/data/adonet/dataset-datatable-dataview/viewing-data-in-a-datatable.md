---
title: "Просмотр данных в таблице данных"
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
ms.assetid: 1d26e0fb-f6e0-4afa-9a9c-b8d55b8f20dc
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: ab7a60b4195f3d8976a61e3909682b3748e30341
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="viewing-data-in-a-datatable"></a>Просмотр данных в таблице данных
Можно получить содержимое из <xref:System.Data.DataTable> с помощью **строк** и **столбцы** коллекции **DataTable**. Можно также использовать <xref:System.Data.DataTable.Select%2A> метод для возврата подмножества данных в **DataTable** в соответствии с условиями поиска, порядок сортировки и состоянием строк. Кроме того, можно использовать <xref:System.Data.DataRowCollection.Find%2A> метод **DataRowCollection** при поиске конкретной строки, используя значение первичного ключа.  
  
 **Выберите** метод **DataTable** объект возвращает набор <xref:System.Data.DataRow> объектов, соответствующих указанным критериям. **Выберите** принимает необязательные аргументы критерия фильтра, выражения сортировки и **DataViewRowState**. Критерий фильтра определяет возвращаемые на основе строки **DataColumn** значения, например `LastName = 'Smith'`. Выражение сортировки следует стандартным соглашениям SQL об упорядочивании столбцов, например по `LastName ASC, FirstName ASC`. Правила написания выражений см <xref:System.Data.DataColumn.Expression%2A> свойство **DataColumn** класса.  
  
> [!TIP]
>  При выполнении количество вызовов **выберите** метод **DataTable**, можно повысить производительность, создав вначале <xref:System.Data.DataView> для **DataTable**. Создание **DataView** индексируются строки таблицы. **Выберите** метод, а затем использует этот индекс, значительно сокращает время формирования результата. Дополнительные сведения о создании **DataView** для **DataTable**, в разделе [объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md).  
  
 **Выберите** метод определяет, какие версии строк для просмотра и управления на основе <xref:System.Data.DataViewRowState>. В следующей таблице описаны возможные **DataViewRowState** значений перечисления.  
  
|Значение DataViewRowState|Описание:|  
|----------------------------|-----------------|  
|**CurrentRows**|Текущие строки, включая не изменившиеся, добавленные и измененные.|  
|**Удален**|Удаленная строка.|  
|**ModifiedCurrent**|Текущая версия, которая является измененной версией исходных данных. (См. **ModifiedOriginal**.)|  
|**ModifiedOriginal**|Исходная версия всех измененных строк. Текущая версия — доступны с помощью **ModifiedCurrent**.|  
|**Добавить**|Новая строка.|  
|**None**|Отсутствует.|  
|**OriginalRows**|Исходные строки, включая неизменившиеся и удаленные.|  
|**Без изменений**|Неизменившаяся строка.|  
  
 В следующем примере **DataSet** объекта является отфильтрованы, поэтому необходимо работать только со строками, **DataViewRowState** равно **CurrentRows**.  
  
```vb  
Dim column As DataColumn  
Dim row As DataRow  
  
Dim currentRows() As DataRow = _  
    workTable.Select(Nothing, Nothing, DataViewRowState.CurrentRows)  
  
If (currentRows.Length < 1 ) Then  
  Console.WriteLine("No Current Rows Found")  
Else  
  For Each column in workTable.Columns  
    Console.Write(vbTab & column.ColumnName)  
  Next  
  
  Console.WriteLine(vbTab & "RowState")  
  
  For Each row In currentRows  
    For Each column In workTable.Columns  
      Console.Write(vbTab & row(column).ToString())  
    Next  
  
    Dim rowState As String = _  
        System.Enum.GetName(row.RowState.GetType(), row.RowState)  
    Console.WriteLine(vbTab & rowState)  
  Next  
End If  
```  
  
```csharp  
DataRow[] currentRows = workTable.Select(  
    null, null, DataViewRowState.CurrentRows);  
  
if (currentRows.Length < 1 )  
  Console.WriteLine("No Current Rows Found");  
else  
{  
  foreach (DataColumn column in workTable.Columns)  
    Console.Write("\t{0}", column.ColumnName);  
  
  Console.WriteLine("\tRowState");  
  
  foreach (DataRow row in currentRows)  
  {  
    foreach (DataColumn column in workTable.Columns)  
      Console.Write("\t{0}", row[column]);  
  
    Console.WriteLine("\t" + row.RowState);  
  }  
}  
```  
  
 **Выберите** метод может использоваться для возвращения строк с разными значениями **RowState** или значениями полей. В следующем примере возвращается **DataRow** массив, который ссылается на все строки, которые были удалены и возвращает другой **DataRow** массив, который ссылается на все строки, упорядоченные по **CustLName**, где **CustID** столбца больше 5. Сведения о том, как просмотреть сведения в **Deleted** строк см. в разделе [состояния строк и версии строк](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).  
  
```vb  
' Retrieve all deleted rows.  
Dim deletedRows() As DataRow = workTable.Select(Nothing, Nothing, DataViewRowState.Deleted)  
  
' Retrieve rows where CustID > 5, and order by CustLName.  
Dim custRows() As DataRow = workTable.Select( _  
    "CustID > 5", "CustLName ASC")  
```  
  
```csharp  
// Retrieve all deleted rows.  
DataRow[] deletedRows = workTable.Select(  
    null, null, DataViewRowState.Deleted);  
  
// Retrieve rows where CustID > 5, and order by CustLName.  
DataRow[] custRows = workTable.Select("CustID > 5", "CustLName ASC");  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataSet>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataViewRowState>  
 [Управление данными в DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [Состояния и версии строк](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
