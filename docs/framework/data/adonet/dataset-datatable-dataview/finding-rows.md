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
# <a name="finding-rows"></a><span data-ttu-id="da03b-102">Поиск строк</span><span class="sxs-lookup"><span data-stu-id="da03b-102">Finding Rows</span></span>
<span data-ttu-id="da03b-103">При помощи методов <xref:System.Data.DataView.Find%2A> и <xref:System.Data.DataView.FindRows%2A> объекта <xref:System.Data.DataView> можно производить поиск строк по значениям их ключей сортировки.</span><span class="sxs-lookup"><span data-stu-id="da03b-103">You can search for rows according to their sort key values by using the <xref:System.Data.DataView.Find%2A> and <xref:System.Data.DataView.FindRows%2A> methods of the <xref:System.Data.DataView>.</span></span> <span data-ttu-id="da03b-104">Чувствительность к случаям значений поиска в методах **Find** and **FindRows** определяется <xref:System.Data.DataTable>свойством **CaseSensitive** основного значения.</span><span class="sxs-lookup"><span data-stu-id="da03b-104">The case sensitivity of search values in the **Find** and **FindRows** methods is determined by the **CaseSensitive** property of the underlying <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="da03b-105">Чтобы был возвращен результат, значения для поиска должны полностью совпадать со значениями ключей сортировки.</span><span class="sxs-lookup"><span data-stu-id="da03b-105">Search values must match existing sort key values in their entirety in order to return a result.</span></span>  
  
 <span data-ttu-id="da03b-106">Метод **Поиска** возвращает стычку с <xref:System.Data.DataRowView> индексом, который соответствует критериям поиска.</span><span class="sxs-lookup"><span data-stu-id="da03b-106">The **Find** method returns an integer with the index of the <xref:System.Data.DataRowView> that matches the search criteria.</span></span> <span data-ttu-id="da03b-107">Если более одной строки соответствуют критериям поиска, возвращается только индекс первого соответствующего **DataRowView.**</span><span class="sxs-lookup"><span data-stu-id="da03b-107">If more than one row matches the search criteria, only the index of the first matching **DataRowView** is returned.</span></span> <span data-ttu-id="da03b-108">Если совпадений не найдено, **найти** возвращается -1.</span><span class="sxs-lookup"><span data-stu-id="da03b-108">If no matches are found, **Find** returns -1.</span></span>  
  
 <span data-ttu-id="da03b-109">Чтобы вернуть результаты поиска, которые соответствуют нескольким строкам, используйте метод **FindRows.**</span><span class="sxs-lookup"><span data-stu-id="da03b-109">To return search results that match multiple rows, use the **FindRows** method.</span></span> <span data-ttu-id="da03b-110">**FindRows** работает так же, как метод **поиска,** за исключением того, что он возвращает массив **DataRowView,** который ссылается на все соответствующие строки в **DataView.**</span><span class="sxs-lookup"><span data-stu-id="da03b-110">**FindRows** works just like the **Find** method, except that it returns a **DataRowView** array that references all matching rows in the **DataView**.</span></span> <span data-ttu-id="da03b-111">Если совпадения не найдены, массив **DataRowView** будет пуст.</span><span class="sxs-lookup"><span data-stu-id="da03b-111">If no matches are found, the **DataRowView** array will be empty.</span></span>  
  
 <span data-ttu-id="da03b-112">Для использования методов **Поиска** или **FindRows** необходимо указать заказ на сортировку либо путем установки **ApplyDefaultSort** на **истину,** либо с помощью свойства **Sort.**</span><span class="sxs-lookup"><span data-stu-id="da03b-112">To use the **Find** or **FindRows** methods you must specify a sort order either by setting **ApplyDefaultSort** to **true** or by using the **Sort** property.</span></span> <span data-ttu-id="da03b-113">Если никакого порядка сортировки не задано, то формируется исключение.</span><span class="sxs-lookup"><span data-stu-id="da03b-113">If no sort order is specified, an exception is thrown.</span></span>  
  
 <span data-ttu-id="da03b-114">Методы **Поиска** и **Поиска Строки** берут массив значений в качестве ввода, длина которых соответствует количеству столбцов в порядке сортировки.</span><span class="sxs-lookup"><span data-stu-id="da03b-114">The **Find** and **FindRows** methods take an array of values as input whose length matches the number of columns in the sort order.</span></span> <span data-ttu-id="da03b-115">В случае сортировки в одном столбце можно передавать одно значение.</span><span class="sxs-lookup"><span data-stu-id="da03b-115">In the case of a sort on a single column, you can pass a single value.</span></span> <span data-ttu-id="da03b-116">Массив объектов передается для порядков сортировки, содержащих несколько столбцов.</span><span class="sxs-lookup"><span data-stu-id="da03b-116">For sort orders containing multiple columns, you pass an array of objects.</span></span> <span data-ttu-id="da03b-117">Обратите внимание, что для сортировки на нескольких столбцах значения в массиве объектов должны соответствовать порядку столбцов, указанным в свойстве **Sort** of the **DataView.**</span><span class="sxs-lookup"><span data-stu-id="da03b-117">Note that for a sort on multiple columns, the values in the object array must match the order of the columns specified in the **Sort** property of the **DataView**.</span></span>  
  
 <span data-ttu-id="da03b-118">Следующий пример кода показывает метод **Поиска,** который вызывается против **DataView** с одним порядком сортировки столбца.</span><span class="sxs-lookup"><span data-stu-id="da03b-118">The following code example shows the **Find** method being called against a **DataView** with a single column sort order.</span></span>  
  
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
  
 <span data-ttu-id="da03b-119">Если свойство **Sort** определяет несколько столбцов, необходимо передать массив объектов с значениями поиска для каждой колонки в порядке, указанном свойством **Sort,** как в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="da03b-119">If your **Sort** property specifies multiple columns, you must pass an object array with the search values for each column in the order specified by the **Sort** property, as in the following code example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="da03b-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="da03b-120">See also</span></span>

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [<span data-ttu-id="da03b-121">Объекты DataView</span><span class="sxs-lookup"><span data-stu-id="da03b-121">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="da03b-122">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="da03b-122">ADO.NET Overview</span></span>](../ado-net-overview.md)
