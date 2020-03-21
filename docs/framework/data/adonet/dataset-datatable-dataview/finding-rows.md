---
title: Поиск строк
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5da300e2-74c0-4d13-9202-fc20ed8212d8
ms.openlocfilehash: cfd4587f0dde7687ecf88bf6b31c44b90a2287ca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151147"
---
# <a name="finding-rows"></a>Поиск строк
При помощи методов <xref:System.Data.DataView.Find%2A> и <xref:System.Data.DataView.FindRows%2A> объекта <xref:System.Data.DataView> можно производить поиск строк по значениям их ключей сортировки. Чувствительность к случаям значений поиска в методах **Find** and **FindRows** определяется <xref:System.Data.DataTable>свойством **CaseSensitive** основного значения. Чтобы был возвращен результат, значения для поиска должны полностью совпадать со значениями ключей сортировки.  
  
 Метод **Поиска** возвращает стычку с <xref:System.Data.DataRowView> индексом, который соответствует критериям поиска. Если более одной строки соответствуют критериям поиска, возвращается только индекс первого соответствующего **DataRowView.** Если совпадений не найдено, **найти** возвращается -1.  
  
 Чтобы вернуть результаты поиска, которые соответствуют нескольким строкам, используйте метод **FindRows.** **FindRows** работает так же, как метод **поиска,** за исключением того, что он возвращает массив **DataRowView,** который ссылается на все соответствующие строки в **DataView.** Если совпадения не найдены, массив **DataRowView** будет пуст.  
  
 Для использования методов **Поиска** или **FindRows** необходимо указать заказ на сортировку либо путем установки **ApplyDefaultSort** на **истину,** либо с помощью свойства **Sort.** Если никакого порядка сортировки не задано, то формируется исключение.  
  
 Методы **Поиска** и **Поиска Строки** берут массив значений в качестве ввода, длина которых соответствует количеству столбцов в порядке сортировки. В случае сортировки в одном столбце можно передавать одно значение. Массив объектов передается для порядков сортировки, содержащих несколько столбцов. Обратите внимание, что для сортировки на нескольких столбцах значения в массиве объектов должны соответствовать порядку столбцов, указанным в свойстве **Sort** of the **DataView.**  
  
 Следующий пример кода показывает метод **Поиска,** который вызывается против **DataView** с одним порядком сортировки столбца.  
  
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
  
 Если свойство **Sort** определяет несколько столбцов, необходимо передать массив объектов с значениями поиска для каждой колонки в порядке, указанном свойством **Sort,** как в следующем примере кода.  
  
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
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [Объекты DataView](dataviews.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
