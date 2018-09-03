---
title: Создание столбцов выражений
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0af3bd64-92a2-4b47-ae62-f5df35f131a6
ms.openlocfilehash: 9c7a656e82198568c39b9bb58f8708f563d6caa2
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2018
ms.locfileid: "43482319"
---
# <a name="creating-expression-columns"></a><span data-ttu-id="2eb50-102">Создание столбцов выражений</span><span class="sxs-lookup"><span data-stu-id="2eb50-102">Creating Expression Columns</span></span>
<span data-ttu-id="2eb50-103">Можно определить выражение для столбца, позволяя тем самым хранить в нем значение, вычисляемое из значений других столбцов той же строки или из значений столбцов нескольких строк таблицы.</span><span class="sxs-lookup"><span data-stu-id="2eb50-103">You can define an expression for a column, enabling it to contain a value calculated from other column values in the same row or from the column values of multiple rows in the table.</span></span> <span data-ttu-id="2eb50-104">Для определения вычисляемого выражения используется свойство <xref:System.Data.DataColumn.Expression%2A> целевого столбца, свойство <xref:System.Data.DataColumn.ColumnName%2A> - для ссылки на другие столбцы в выражении.</span><span class="sxs-lookup"><span data-stu-id="2eb50-104">To define the expression to be evaluated, use the <xref:System.Data.DataColumn.Expression%2A> property of the target column, and use the <xref:System.Data.DataColumn.ColumnName%2A> property to refer to other columns in the expression.</span></span> <span data-ttu-id="2eb50-105">Тип данных <xref:System.Data.DataColumn.DataType%2A> столбца выражения должен соответствовать типу данных значения, возвращаемого выражением.</span><span class="sxs-lookup"><span data-stu-id="2eb50-105">The <xref:System.Data.DataColumn.DataType%2A> for the expression column must be appropriate for the value that the expression returns.</span></span>  
  
 <span data-ttu-id="2eb50-106">В следующей таблице приведен список возможного использования столбцов выражений в таблице.</span><span class="sxs-lookup"><span data-stu-id="2eb50-106">The following table lists several possible uses for expression columns in a table.</span></span>  
  
|<span data-ttu-id="2eb50-107">Тип выражения</span><span class="sxs-lookup"><span data-stu-id="2eb50-107">Expression type</span></span>|<span data-ttu-id="2eb50-108">Пример</span><span class="sxs-lookup"><span data-stu-id="2eb50-108">Example</span></span>|  
|---------------------|-------------|  
|<span data-ttu-id="2eb50-109">Сравнение</span><span class="sxs-lookup"><span data-stu-id="2eb50-109">Comparison</span></span>|<span data-ttu-id="2eb50-110">"Total >= 500"</span><span class="sxs-lookup"><span data-stu-id="2eb50-110">"Total >= 500"</span></span>|  
|<span data-ttu-id="2eb50-111">Вычисление</span><span class="sxs-lookup"><span data-stu-id="2eb50-111">Computation</span></span>|<span data-ttu-id="2eb50-112">"UnitPrice \* Quantity"</span><span class="sxs-lookup"><span data-stu-id="2eb50-112">"UnitPrice \* Quantity"</span></span>|  
|<span data-ttu-id="2eb50-113">Статистическая обработка</span><span class="sxs-lookup"><span data-stu-id="2eb50-113">Aggregation</span></span>|<span data-ttu-id="2eb50-114">Sum(Price)</span><span class="sxs-lookup"><span data-stu-id="2eb50-114">Sum(Price)</span></span>|  
  
 <span data-ttu-id="2eb50-115">Можно задать **выражение** свойство на существующем **DataColumn** объекта, или можно включить свойство как третий аргумент, передаваемый в <xref:System.Data.DataColumn> конструктора, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="2eb50-115">You can set the **Expression** property on an existing **DataColumn** object, or you can include the property as the third argument passed to the <xref:System.Data.DataColumn> constructor, as shown in the following example.</span></span>  
  
```vb  
workTable.Columns.Add("Total",Type.GetType("System.Double"))  
workTable.Columns.Add("SalesTax", Type.GetType("System.Double"), _  
  "Total * 0.086")  
```  
  
```csharp  
workTable.Columns.Add("Total", typeof(Double));  
workTable.Columns.Add("SalesTax", typeof(Double), "Total * 0.086");  
```  
  
 <span data-ttu-id="2eb50-116">Выражение может содержать ссылки на другие столбцы выражений, но циклическая ссылка, при которой два выражения ссылаются друг на друга, вызовет исключение.</span><span class="sxs-lookup"><span data-stu-id="2eb50-116">Expressions can reference other expression columns; however, a circular reference, in which two expressions reference each other, will generate an exception.</span></span> <span data-ttu-id="2eb50-117">Правила написания выражений, см. в разделе <xref:System.Data.DataColumn.Expression%2A> свойство **DataColumn** класса.</span><span class="sxs-lookup"><span data-stu-id="2eb50-117">For rules about writing expressions, see the <xref:System.Data.DataColumn.Expression%2A> property of the **DataColumn** class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2eb50-118">См. также</span><span class="sxs-lookup"><span data-stu-id="2eb50-118">See Also</span></span>  
 <xref:System.Data.DataColumn>  
 <xref:System.Data.DataSet>  
 <xref:System.Data.DataTable>  
 [<span data-ttu-id="2eb50-119">Определение схемы DataTable</span><span class="sxs-lookup"><span data-stu-id="2eb50-119">DataTable Schema Definition</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 [<span data-ttu-id="2eb50-120">DataTables</span><span class="sxs-lookup"><span data-stu-id="2eb50-120">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [<span data-ttu-id="2eb50-121">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2eb50-121">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
