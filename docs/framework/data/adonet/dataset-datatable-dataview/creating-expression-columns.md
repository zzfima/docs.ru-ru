---
title: "Создание столбцов выражений"
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
ms.assetid: 0af3bd64-92a2-4b47-ae62-f5df35f131a6
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: c1b0b7be8be6bec0c5a8850029bd3336d107f0a0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="creating-expression-columns"></a><span data-ttu-id="e107a-102">Создание столбцов выражений</span><span class="sxs-lookup"><span data-stu-id="e107a-102">Creating Expression Columns</span></span>
<span data-ttu-id="e107a-103">Можно определить выражение для столбца, позволяя тем самым хранить в нем значение, вычисляемое из значений других столбцов той же строки или из значений столбцов нескольких строк таблицы.</span><span class="sxs-lookup"><span data-stu-id="e107a-103">You can define an expression for a column, enabling it to contain a value calculated from other column values in the same row or from the column values of multiple rows in the table.</span></span> <span data-ttu-id="e107a-104">Для определения вычисляемого выражения используется свойство <xref:System.Data.DataColumn.Expression%2A> целевого столбца, свойство <xref:System.Data.DataColumn.ColumnName%2A> - для ссылки на другие столбцы в выражении.</span><span class="sxs-lookup"><span data-stu-id="e107a-104">To define the expression to be evaluated, use the <xref:System.Data.DataColumn.Expression%2A> property of the target column, and use the <xref:System.Data.DataColumn.ColumnName%2A> property to refer to other columns in the expression.</span></span> <span data-ttu-id="e107a-105">Тип данных <xref:System.Data.DataColumn.DataType%2A> столбца выражения должен соответствовать типу данных значения, возвращаемого выражением.</span><span class="sxs-lookup"><span data-stu-id="e107a-105">The <xref:System.Data.DataColumn.DataType%2A> for the expression column must be appropriate for the value that the expression returns.</span></span>  
  
 <span data-ttu-id="e107a-106">В следующей таблице приведен список возможного использования столбцов выражений в таблице.</span><span class="sxs-lookup"><span data-stu-id="e107a-106">The following table lists several possible uses for expression columns in a table.</span></span>  
  
|<span data-ttu-id="e107a-107">Тип выражения</span><span class="sxs-lookup"><span data-stu-id="e107a-107">Expression type</span></span>|<span data-ttu-id="e107a-108">Пример</span><span class="sxs-lookup"><span data-stu-id="e107a-108">Example</span></span>|  
|---------------------|-------------|  
|<span data-ttu-id="e107a-109">Сравнение</span><span class="sxs-lookup"><span data-stu-id="e107a-109">Comparison</span></span>|<span data-ttu-id="e107a-110">"Total >= 500"</span><span class="sxs-lookup"><span data-stu-id="e107a-110">"Total >= 500"</span></span>|  
|<span data-ttu-id="e107a-111">Вычисление</span><span class="sxs-lookup"><span data-stu-id="e107a-111">Computation</span></span>|<span data-ttu-id="e107a-112">"UnitPrice * Quantity"</span><span class="sxs-lookup"><span data-stu-id="e107a-112">"UnitPrice * Quantity"</span></span>|  
|<span data-ttu-id="e107a-113">Статистическая обработка</span><span class="sxs-lookup"><span data-stu-id="e107a-113">Aggregation</span></span>|<span data-ttu-id="e107a-114">Sum(Price)</span><span class="sxs-lookup"><span data-stu-id="e107a-114">Sum(Price)</span></span>|  
  
 <span data-ttu-id="e107a-115">Можно задать **выражение** в существующем **DataColumn** объекта, или включить это свойство в качестве третьего аргумента, передаваемого <xref:System.Data.DataColumn> конструктора, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="e107a-115">You can set the **Expression** property on an existing **DataColumn** object, or you can include the property as the third argument passed to the <xref:System.Data.DataColumn> constructor, as shown in the following example.</span></span>  
  
```vb  
workTable.Columns.Add("Total",Type.GetType("System.Double"))  
workTable.Columns.Add("SalesTax", Type.GetType("System.Double"), _  
  "Total * 0.086")  
```  
  
```csharp  
workTable.Columns.Add("Total", typeof(Double));  
workTable.Columns.Add("SalesTax", typeof(Double), "Total * 0.086");  
```  
  
 <span data-ttu-id="e107a-116">Выражение может содержать ссылки на другие столбцы выражений, но циклическая ссылка, при которой два выражения ссылаются друг на друга, вызовет исключение.</span><span class="sxs-lookup"><span data-stu-id="e107a-116">Expressions can reference other expression columns; however, a circular reference, in which two expressions reference each other, will generate an exception.</span></span> <span data-ttu-id="e107a-117">Правила написания выражений см <xref:System.Data.DataColumn.Expression%2A> свойство **DataColumn** класса.</span><span class="sxs-lookup"><span data-stu-id="e107a-117">For rules about writing expressions, see the <xref:System.Data.DataColumn.Expression%2A> property of the **DataColumn** class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e107a-118">См. также</span><span class="sxs-lookup"><span data-stu-id="e107a-118">See Also</span></span>  
 <xref:System.Data.DataColumn>  
 <xref:System.Data.DataSet>  
 <xref:System.Data.DataTable>  
 [<span data-ttu-id="e107a-119">Определение схемы DataTable</span><span class="sxs-lookup"><span data-stu-id="e107a-119">DataTable Schema Definition</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 [<span data-ttu-id="e107a-120">DataTables</span><span class="sxs-lookup"><span data-stu-id="e107a-120">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [<span data-ttu-id="e107a-121">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e107a-121">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
