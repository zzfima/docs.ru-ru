---
title: "Просмотр данных в DataTable | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1d26e0fb-f6e0-4afa-9a9c-b8d55b8f20dc
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Просмотр данных в DataTable
Доступ к содержимому <xref:System.Data.DataTable> можно получить с помощью коллекций **Rows** и **Columns** объекта **DataTable**.  Для возвращения подмножества данных в **DataTable** в соответствии с условиями поиска, порядком сортировки и состоянием строк можно также использовать метод <xref:System.Data.DataTable.Select%2A>.  Кроме того, при поиске конкретной строки по значению первичного ключа можно использовать метод <xref:System.Data.DataRowCollection.Find%2A> класса **DataRowCollection**.  
  
 Метод **Select** объекта **DataTable** возвращает набор объектов <xref:System.Data.DataRow>, соответствующих заданным критериям.  Метод **Select** принимает необязательные аргументы критерия фильтра, выражения сортировки и **DataViewRowState**.  Критерий фильтра определяет возвращаемые строки на основе значений **DataColumn**, например `LastName = 'Smith'`.  Выражение сортировки следует стандартным соглашениям SQL об упорядочивании столбцов, например по `LastName ASC, FirstName ASC`.  Правила написания выражений см. в свойстве <xref:System.Data.DataColumn.Expression%2A> класса **DataColumn**.  
  
> [!TIP]
>  Если выполняется несколько вызовов метода **Select** объекта **DataTable**, можно повысить производительность, создав вначале представление <xref:System.Data.DataView> для таблицы **DataTable**.  При создании **DataView** индексируются строки таблицы.  Метод **Select** использует этот индекс, что значительно сокращает время формирования результата.  Сведения о создании представления **DataView** для таблицы **DataTable** см. в разделе [Объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md).  
  
 Метод **Select** определяет, какую версию строк нужно просмотреть или обработать, на основе <xref:System.Data.DataViewRowState>.  В следующей таблице показаны возможные значения перечисления **DataViewRowState**.  
  
|Значение DataViewRowState|Описание|  
|-------------------------------|--------------|  
|**CurrentRows**|Текущие строки, включая не изменившиеся, добавленные и измененные.|  
|**Deleted**|Удаленная строка.|  
|**ModifiedCurrent**|Текущая версия, которая является измененной версией исходных данных.  \(См. **ModifiedOriginal**.\)|  
|**ModifiedOriginal**|Исходная версия всех измененных строк.  Текущая версия доступна при использовании параметра **ModifiedCurrent**.|  
|**Added**|Новая строка.|  
|**Нет**|Отсутствует.|  
|**OriginalRows**|Исходные строки, включая неизменившиеся и удаленные.|  
|**Unchanged**|Неизменившаяся строка.|  
  
 В следующем примере объект **DataSet** фильтруется таким образом, что возвращаются только строки, параметр **DataViewRowState** для которых имеет значение **CurrentRows**.  
  
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
  
 Метод **Select** может использоваться для возвращения строк с разными значениями **RowState** или значениями полей.  Следующий пример возвращает массив строк **DataRow**, который ссылается на все удаленные строки и возвращает другой массив **DataRow**, ссылающийся на строки, упорядоченные по **CustLName**, в которых столбец **CustID** больше 5.  Сведения о просмотре данных в строке **Deleted** см. в разделе [Состояния и версии строк](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).  
  
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
  
## См. также  
 <xref:System.Data.DataRow>   
 <xref:System.Data.DataSet>   
 <xref:System.Data.DataTable>   
 <xref:System.Data.DataViewRowState>   
 [Обработка данных в DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)   
 [Состояния и версии строк](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)