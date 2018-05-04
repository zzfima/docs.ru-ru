---
title: Поиск строк
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5da300e2-74c0-4d13-9202-fc20ed8212d8
ms.openlocfilehash: 57ed6045ca0ea9f9579640839e8198716cf79fe0
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="finding-rows"></a>Поиск строк
При помощи методов <xref:System.Data.DataView.Find%2A> и <xref:System.Data.DataView.FindRows%2A> объекта <xref:System.Data.DataView> можно производить поиск строк по значениям их ключей сортировки. Чувствительность к регистру для поиска значений в **найти** и **FindRows** методы определяется **CaseSensitive** базового объекта <xref:System.Data.DataTable>. Чтобы был возвращен результат, значения для поиска должны полностью совпадать со значениями ключей сортировки.  
  
 **Найти** метод возвращает целое число с индексом <xref:System.Data.DataRowView> , соответствующие условиям поиска. Если более чем одной строке соответствует критерию поиска, а только индекс первого совпадающего **DataRowView** возвращается. Если соответствий не найдено, **найти** возвращает -1.  
  
 Чтобы вернуть результаты поиска, которые соответствуют несколько строк, используйте **FindRows** метод. **FindRows** работает аналогично **найти** за исключением того, что он возвращает **DataRowView** массив, который ссылается на все совпадающие строки в **DataView**. Если соответствий не найдено, **DataRowView** возвращается пустой массив.  
  
 Для использования **найти** или **FindRows** методы, необходимо указать порядок сортировки order, задав **ApplyDefaultSort** для **true** или с помощью **Сортировки** свойство. Если никакого порядка сортировки не задано, то формируется исключение.  
  
 **Найти** и **FindRows** методы принимают массив значений в качестве входных данных, длина которого совпадает с количеством столбцов в порядке сортировки. В случае сортировки в одном столбце можно передавать одно значение. Массив объектов передается для порядков сортировки, содержащих несколько столбцов. Обратите внимание, что для сортировки нескольких столбцов значения в массиве объектов должен соответствовать порядку столбцов, указанных в **сортировки** свойство **DataView**.  
  
 В следующем примере кода показан **найти** от вызываемого метода **DataView** с порядком сортировки из одного столбца.  
  
```vb  
Dim custView As DataView = _  
  New DataView(custDS.Tables("Customers"), "", _  
  "CompanyName", DataViewRowState.CurrentRows)  
  
Dim rowIndex As Integer = custView.Find("The Cracker Box")  
  
If rowIndex = -1 Then  
  Console.WriteLine("No match found.")  
Else  
  Console.WriteLine("{0}, {1}", _  
    custView(rowIndex)("CustomerID").ToString(), _  
    custView(rowIndex)("CompanyName").ToString())  
End If  
```  
  
```csharp  
DataView custView = new DataView(custDS.Tables["Customers"], "",   
  "CompanyName", DataViewRowState.CurrentRows);  
  
int rowIndex = custView.Find("The Cracker Box");  
  
if (rowIndex == -1)  
  Console.WriteLine("No match found.");  
else  
  Console.WriteLine("{0}, {1}",  
    custView[rowIndex]["CustomerID"].ToString(),  
    custView[rowIndex]["CompanyName"].ToString());  
```  
  
 Если ваш **сортировки** задано несколько столбцов, необходимо передавать массив объектов со значениями для поиска для каждого столбца в порядке, указанном **сортировки** свойства, как показано в следующем примере кода.  
  
```vb  
Dim custView As DataView = _  
  New DataView(custDS.Tables("Customers"), "", _  
  "CompanyName, ContactName", _  
  DataViewRowState.CurrentRows)  
  
Dim foundRows() As DataRowView = _  
  custView.FindRows(New object() {"The Cracker Box", "Liu Wong"})  
  
If foundRows.Length = 0 Then  
  Console.WriteLine("No match found.")  
Else  
  Dim myDRV As DataRowView  
  For Each myDRV In foundRows  
    Console.WriteLine("{0}, {1}", _  
      myDRV("CompanyName").ToString(), myDRV("ContactName").ToString())  
  Next  
End If  
```  
  
```csharp  
DataView custView = new DataView(custDS.Tables["Customers"], "",  
  "CompanyName, ContactName",  
  DataViewRowState.CurrentRows);  
  
DataRowView[] foundRows =   
  custView.FindRows(new object[] {"The Cracker Box", "Liu Wong"});  
  
if (foundRows.Length == 0)  
  Console.WriteLine("No match found.");  
else  
  foreach (DataRowView myDRV in foundRows)  
    Console.WriteLine("{0}, {1}", myDRV["CompanyName"].ToString(),   
      myDRV["ContactName"].ToString());  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataView>  
 [Объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
