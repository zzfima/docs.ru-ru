---
title: "поиск строк | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5da300e2-74c0-4d13-9202-fc20ed8212d8
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# поиск строк
При помощи методов <xref:System.Data.DataView.Find%2A> и <xref:System.Data.DataView.FindRows%2A> объекта <xref:System.Data.DataView> можно производить поиск строк по значениям их ключей сортировки.  Учет регистра значений для поиска в методах **Find** и **FindRows** определяется свойством **CaseSensitive** базового объекта <xref:System.Data.DataTable>.  Чтобы был возвращен результат, значения для поиска должны полностью совпадать со значениями ключей сортировки.  
  
 Метод **Find** возвращает целое значение с индексом объекта <xref:System.Data.DataRowView>, который соответствует критериям поиска.  Если критериям поиска соответствуют несколько строк, возвращается только индекс первого совпадающего объекта **DataRowView**.  Если совпадений не обнаружено, метод **Find** возвращает \-1.  
  
 Чтобы возвращать результаты поиска, в которых выводятся несколько совпадающих строк, используйте метод **FindRows**.  Метод **FindRows** работает так же, как метод **Find**, за исключением того, что он возвращает массив объектов **DataRowView**, который ссылается на все совпадающие строки в объекте **DataView**.  Если совпадений не обнаружено, массив **DataRowView** будет пустым.  
  
 Чтобы использовать метод **Find** или **FindRows**, необходимо указать порядок сортировки либо путем задания свойству **ApplyDefaultSort** значения **true**, либо при помощи свойства **Sort**.  Если никакого порядка сортировки не задано, то формируется исключение.  
  
 Методы **Find** и **FindRows** принимают массив значений в качестве ввода, длина которого соответствует числу столбцов в порядке сортировки.  В случае сортировки в одном столбце можно передавать одно значение.  Массив объектов передается для порядков сортировки, содержащих несколько столбцов.  Отметим, что для сортировки нескольких столбцов значения в массиве объектов должны соответствовать порядку столбцов, указанному в свойстве **Sort** объекта **DataView**.  
  
 В следующем примере кода показывается вызов метода **Find** для объекта **DataView** с порядком сортировки из одного столбца.  
  
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
  
 Если в свойстве **Sort** задано несколько столбцов, необходимо передавать массив объектов со значениями для поиска для каждого столбца в порядке, заданном свойством **Sort**, как показано в следующем примере кода.  
  
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
  
## См. также  
 <xref:System.Data.DataTable>   
 <xref:System.Data.DataView>   
 [Объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)