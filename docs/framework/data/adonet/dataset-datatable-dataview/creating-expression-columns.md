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
ms.openlocfilehash: 315944262136e5db453ea01eae64fff6cb0d534d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="creating-expression-columns"></a><span data-ttu-id="4fd22-102">Создание столбцов выражений</span><span class="sxs-lookup"><span data-stu-id="4fd22-102">Creating Expression Columns</span></span>
<span data-ttu-id="4fd22-103">Можно определить выражение для столбца, позволяя тем самым хранить в нем значение, вычисляемое из значений других столбцов той же строки или из значений столбцов нескольких строк таблицы.</span><span class="sxs-lookup"><span data-stu-id="4fd22-103">You can define an expression for a column, enabling it to contain a value calculated from other column values in the same row or from the column values of multiple rows in the table.</span></span> <span data-ttu-id="4fd22-104">Для определения вычисляемого выражения используется свойство <xref:System.Data.DataColumn.Expression%2A> целевого столбца, свойство <xref:System.Data.DataColumn.ColumnName%2A> - для ссылки на другие столбцы в выражении.</span><span class="sxs-lookup"><span data-stu-id="4fd22-104">To define the expression to be evaluated, use the <xref:System.Data.DataColumn.Expression%2A> property of the target column, and use the <xref:System.Data.DataColumn.ColumnName%2A> property to refer to other columns in the expression.</span></span> <span data-ttu-id="4fd22-105">Тип данных <xref:System.Data.DataColumn.DataType%2A> столбца выражения должен соответствовать типу данных значения, возвращаемого выражением.</span><span class="sxs-lookup"><span data-stu-id="4fd22-105">The <xref:System.Data.DataColumn.DataType%2A> for the expression column must be appropriate for the value that the expression returns.</span></span>  
  
 <span data-ttu-id="4fd22-106">В следующей таблице приведен список возможного использования столбцов выражений в таблице.</span><span class="sxs-lookup"><span data-stu-id="4fd22-106">The following table lists several possible uses for expression columns in a table.</span></span>  
  
|<span data-ttu-id="4fd22-107">Тип выражения</span><span class="sxs-lookup"><span data-stu-id="4fd22-107">Expression type</span></span>|<span data-ttu-id="4fd22-108">Пример</span><span class="sxs-lookup"><span data-stu-id="4fd22-108">Example</span></span>|  
|---------------------|-------------|  
|<span data-ttu-id="4fd22-109">Сравнение</span><span class="sxs-lookup"><span data-stu-id="4fd22-109">Comparison</span></span>|<span data-ttu-id="4fd22-110">"Total >= 500"</span><span class="sxs-lookup"><span data-stu-id="4fd22-110">"Total >= 500"</span></span>|  
|<span data-ttu-id="4fd22-111">Вычисление</span><span class="sxs-lookup"><span data-stu-id="4fd22-111">Computation</span></span>|<span data-ttu-id="4fd22-112">"UnitPrice * Quantity"</span><span class="sxs-lookup"><span data-stu-id="4fd22-112">"UnitPrice * Quantity"</span></span>|  
|<span data-ttu-id="4fd22-113">Статистическая обработка</span><span class="sxs-lookup"><span data-stu-id="4fd22-113">Aggregation</span></span>|<span data-ttu-id="4fd22-114">Sum(Price)</span><span class="sxs-lookup"><span data-stu-id="4fd22-114">Sum(Price)</span></span>|  
  
 <span data-ttu-id="4fd22-115">Можно задать **выражение** в существующем **DataColumn** объекта, или включить это свойство в качестве третьего аргумента, передаваемого <xref:System.Data.DataColumn> конструктора, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="4fd22-115">You can set the **Expression** property on an existing **DataColumn** object, or you can include the property as the third argument passed to the <xref:System.Data.DataColumn> constructor, as shown in the following example.</span></span>  
  
```vb  
workTable.Columns.Add("Total",Type.GetType("System.Double"))  
workTable.Columns.Add("SalesTax", Type.GetType("System.Double"), _  
  "Total * 0.086")  
```  
  
```csharp  
workTable.Columns.Add("Total", typeof(Double));  
workTable.Columns.Add("SalesTax", typeof(Double), "Total * 0.086");  
```  
  
 <span data-ttu-id="4fd22-116">Выражение может содержать ссылки на другие столбцы выражений, но циклическая ссылка, при которой два выражения ссылаются друг на друга, вызовет исключение.</span><span class="sxs-lookup"><span data-stu-id="4fd22-116">Expressions can reference other expression columns; however, a circular reference, in which two expressions reference each other, will generate an exception.</span></span> <span data-ttu-id="4fd22-117">Правила написания выражений см <xref:System.Data.DataColumn.Expression%2A> свойство **DataColumn** класса.</span><span class="sxs-lookup"><span data-stu-id="4fd22-117">For rules about writing expressions, see the <xref:System.Data.DataColumn.Expression%2A> property of the **DataColumn** class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fd22-118">См. также</span><span class="sxs-lookup"><span data-stu-id="4fd22-118">See Also</span></span>  
 <xref:System.Data.DataColumn>  
 <xref:System.Data.DataSet>  
 <xref:System.Data.DataTable>  
 [<span data-ttu-id="4fd22-119">Определение схемы таблицы данных</span><span class="sxs-lookup"><span data-stu-id="4fd22-119">DataTable Schema Definition</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 [<span data-ttu-id="4fd22-120">DataTables</span><span class="sxs-lookup"><span data-stu-id="4fd22-120">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [<span data-ttu-id="4fd22-121">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="4fd22-121">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
