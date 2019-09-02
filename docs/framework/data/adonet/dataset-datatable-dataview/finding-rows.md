---
title: Поиск строк
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5da300e2-74c0-4d13-9202-fc20ed8212d8
ms.openlocfilehash: 2ff2b6b6d00c854d07f36d37986268a388c7f31b
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203714"
---
# <a name="finding-rows"></a>Поиск строк
При помощи методов <xref:System.Data.DataView.Find%2A> и <xref:System.Data.DataView.FindRows%2A> объекта <xref:System.Data.DataView> можно производить поиск строк по значениям их ключей сортировки. Регистр значений поиска в методах **Find** и **FindRows** определяется свойством **CaseSensitive** базового <xref:System.Data.DataTable>класса. Чтобы был возвращен результат, значения для поиска должны полностью совпадать со значениями ключей сортировки.  
  
 Метод **Find** возвращает целое число с индексом <xref:System.Data.DataRowView> , который соответствует условиям поиска. Если критерию поиска соответствует более одной строки, возвращается только индекс первого соответствующего **DataRowView** . Если совпадений не найдено, функция **Find** возвращает значение-1.  
  
 Чтобы вернуть результаты поиска, соответствующие нескольким строкам, используйте метод **FindRows** . **FindRows** работает так же, как метод **Find** , за исключением того, что он возвращает массив **DataRowView** , который ссылается на все совпадающие строки в **объекте DataView**. Если совпадений не найдено, массив **DataRowView** будет пустым.  
  
 Чтобы использовать методы **Find** или **FindRows** , необходимо указать порядок сортировки, задав для **апплидефаултсорт** **значение true** или воспользовавшись свойством **Sort** . Если никакого порядка сортировки не задано, то формируется исключение.  
  
 Методы **Find** и **FindRows** принимают массив значений в качестве входных данных, длина которых совпадает с числом столбцов в порядке сортировки. В случае сортировки в одном столбце можно передавать одно значение. Массив объектов передается для порядков сортировки, содержащих несколько столбцов. Обратите внимание, что при сортировке по нескольким столбцам значения в массиве объектов должны соответствовать порядку столбцов, указанных в свойстве **Sort** объекта **DataView**.  
  
 В следующем примере кода показан метод **Find** , вызываемый для **DataView** с одним порядком сортировки столбца.  
  
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
  
 Если свойство **Sort** указывает несколько столбцов, необходимо передать массив объектов со значениями поиска для каждого столбца в порядке, указанном свойством **Sort** , как показано в следующем примере кода.  
  
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

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [Объекты DataView](dataviews.md)
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
