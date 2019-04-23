---
title: Поиск строк
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5da300e2-74c0-4d13-9202-fc20ed8212d8
ms.openlocfilehash: 72af4b049153ce647cc1ceb2d40c3b17cc7ed988
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59206555"
---
# <a name="finding-rows"></a><span data-ttu-id="80c66-102">Поиск строк</span><span class="sxs-lookup"><span data-stu-id="80c66-102">Finding Rows</span></span>
<span data-ttu-id="80c66-103">При помощи методов <xref:System.Data.DataView.Find%2A> и <xref:System.Data.DataView.FindRows%2A> объекта <xref:System.Data.DataView> можно производить поиск строк по значениям их ключей сортировки.</span><span class="sxs-lookup"><span data-stu-id="80c66-103">You can search for rows according to their sort key values by using the <xref:System.Data.DataView.Find%2A> and <xref:System.Data.DataView.FindRows%2A> methods of the <xref:System.Data.DataView>.</span></span> <span data-ttu-id="80c66-104">Учет регистра поиск значений в **найти** и **FindRows** методы определяется **CaseSensitive** базового объекта <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="80c66-104">The case sensitivity of search values in the **Find** and **FindRows** methods is determined by the **CaseSensitive** property of the underlying <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="80c66-105">Чтобы был возвращен результат, значения для поиска должны полностью совпадать со значениями ключей сортировки.</span><span class="sxs-lookup"><span data-stu-id="80c66-105">Search values must match existing sort key values in their entirety in order to return a result.</span></span>  
  
 <span data-ttu-id="80c66-106">**Найти** метод возвращает целое число с индексом <xref:System.Data.DataRowView> , соответствующий критериям поиска.</span><span class="sxs-lookup"><span data-stu-id="80c66-106">The **Find** method returns an integer with the index of the <xref:System.Data.DataRowView> that matches the search criteria.</span></span> <span data-ttu-id="80c66-107">Если более одной строки результатов поиска, только индекс первого совпадающего **DataRowView** возвращается.</span><span class="sxs-lookup"><span data-stu-id="80c66-107">If more than one row matches the search criteria, only the index of the first matching **DataRowView** is returned.</span></span> <span data-ttu-id="80c66-108">Если соответствий не найдено, **найти** возвращает -1.</span><span class="sxs-lookup"><span data-stu-id="80c66-108">If no matches are found, **Find** returns -1.</span></span>  
  
 <span data-ttu-id="80c66-109">Чтобы вернуть результаты поиска, которые соответствуют несколько строк, используйте **FindRows** метод.</span><span class="sxs-lookup"><span data-stu-id="80c66-109">To return search results that match multiple rows, use the **FindRows** method.</span></span> <span data-ttu-id="80c66-110">**FindRows** работает аналогично **найти** за тем исключением, что он возвращает **DataRowView** массив, который ссылается на все совпадающие строки в **DataView**.</span><span class="sxs-lookup"><span data-stu-id="80c66-110">**FindRows** works just like the **Find** method, except that it returns a **DataRowView** array that references all matching rows in the **DataView**.</span></span> <span data-ttu-id="80c66-111">Если соответствий не найдено, **DataRowView** возвращается пустой массив.</span><span class="sxs-lookup"><span data-stu-id="80c66-111">If no matches are found, the **DataRowView** array will be empty.</span></span>  
  
 <span data-ttu-id="80c66-112">Для использования **найти** или **FindRows** методы, необходимо указать порядок сортировки order, либо задав **ApplyDefaultSort** для **true** или с помощью **Сортировки** свойство.</span><span class="sxs-lookup"><span data-stu-id="80c66-112">To use the **Find** or **FindRows** methods you must specify a sort order either by setting **ApplyDefaultSort** to **true** or by using the **Sort** property.</span></span> <span data-ttu-id="80c66-113">Если никакого порядка сортировки не задано, то формируется исключение.</span><span class="sxs-lookup"><span data-stu-id="80c66-113">If no sort order is specified, an exception is thrown.</span></span>  
  
 <span data-ttu-id="80c66-114">**Найти** и **FindRows** методы принимают массив значений в качестве входных данных, длина которого совпадает с количеством столбцов в порядке сортировки.</span><span class="sxs-lookup"><span data-stu-id="80c66-114">The **Find** and **FindRows** methods take an array of values as input whose length matches the number of columns in the sort order.</span></span> <span data-ttu-id="80c66-115">В случае сортировки в одном столбце можно передавать одно значение.</span><span class="sxs-lookup"><span data-stu-id="80c66-115">In the case of a sort on a single column, you can pass a single value.</span></span> <span data-ttu-id="80c66-116">Массив объектов передается для порядков сортировки, содержащих несколько столбцов.</span><span class="sxs-lookup"><span data-stu-id="80c66-116">For sort orders containing multiple columns, you pass an array of objects.</span></span> <span data-ttu-id="80c66-117">Обратите внимание, что для сортировки нескольких столбцов, значения в массиве объектов должен соответствовать порядку столбцов, указанных в **сортировки** свойство **DataView**.</span><span class="sxs-lookup"><span data-stu-id="80c66-117">Note that for a sort on multiple columns, the values in the object array must match the order of the columns specified in the **Sort** property of the **DataView**.</span></span>  
  
 <span data-ttu-id="80c66-118">В следующем коде показано в примере **найти** от вызываемого метода **DataView** с порядком сортировки один столбец.</span><span class="sxs-lookup"><span data-stu-id="80c66-118">The following code example shows the **Find** method being called against a **DataView** with a single column sort order.</span></span>  
  
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
  
 <span data-ttu-id="80c66-119">Если ваш **сортировки** задано несколько столбцов, необходимо передать массив объектов со значениями для поиска для каждого столбца в порядке, указанном **сортировки** свойства, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="80c66-119">If your **Sort** property specifies multiple columns, you must pass an object array with the search values for each column in the order specified by the **Sort** property, as in the following code example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="80c66-120">См. также</span><span class="sxs-lookup"><span data-stu-id="80c66-120">See also</span></span>

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [<span data-ttu-id="80c66-121">Объекты DataView</span><span class="sxs-lookup"><span data-stu-id="80c66-121">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)
- [<span data-ttu-id="80c66-122">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="80c66-122">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
