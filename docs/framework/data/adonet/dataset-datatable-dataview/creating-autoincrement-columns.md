---
title: Создание столбцов AutoIncrement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cf09732a-ab54-4d98-89e2-4d0a1f28fbce
ms.openlocfilehash: 5e4a36829107480a44980c7210b39c21231c67f4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786455"
---
# <a name="creating-autoincrement-columns"></a><span data-ttu-id="153b3-102">Создание столбцов AutoIncrement</span><span class="sxs-lookup"><span data-stu-id="153b3-102">Creating AutoIncrement Columns</span></span>
<span data-ttu-id="153b3-103">Чтобы обеспечить наличие в столбце уникальных значений, можно указать, что значения в столбце должны увеличиваться автоматически при добавлении новых строк к таблице.</span><span class="sxs-lookup"><span data-stu-id="153b3-103">To ensure unique column values, you can set the column values to increment automatically when new rows are added to the table.</span></span> <span data-ttu-id="153b3-104">Чтобы создать автоматическое приращение <xref:System.Data.DataColumn>, <xref:System.Data.DataColumn.AutoIncrement%2A> присвойте свойству столбца значение **true**.</span><span class="sxs-lookup"><span data-stu-id="153b3-104">To create an auto-incrementing <xref:System.Data.DataColumn>, set the <xref:System.Data.DataColumn.AutoIncrement%2A> property of the column to **true**.</span></span> <span data-ttu-id="153b3-105">Затем начинается со значения, определенного <xref:System.Data.DataColumn.AutoIncrementSeed%2A> в свойстве, и при добавлении каждой строки значение столбца **AutoIncrement** <xref:System.Data.DataColumn.AutoIncrementStep%2A> увеличивается на значение, определенное в свойстве столбца. <xref:System.Data.DataColumn></span><span class="sxs-lookup"><span data-stu-id="153b3-105">The <xref:System.Data.DataColumn> then starts with the value defined in the <xref:System.Data.DataColumn.AutoIncrementSeed%2A> property, and with each row added the value of the **AutoIncrement** column increases by the value defined in the <xref:System.Data.DataColumn.AutoIncrementStep%2A> property of the column.</span></span>  
  
 <span data-ttu-id="153b3-106">Для столбцов с **автоувеличением** рекомендуется, <xref:System.Data.DataColumn.ReadOnly%2A> чтобы свойство **DataColumn** было установлено в **значение true**.</span><span class="sxs-lookup"><span data-stu-id="153b3-106">For **AutoIncrement** columns, we recommend that the <xref:System.Data.DataColumn.ReadOnly%2A> property of the **DataColumn** be set to **true**.</span></span>  
  
 <span data-ttu-id="153b3-107">В следующем примере показано, как создать столбец, значения в котором начинаются с 200 и каждый раз увеличиваются с шагом 3.</span><span class="sxs-lookup"><span data-stu-id="153b3-107">The following example demonstrates how to create a column that starts with a value of 200 and adds incrementally in steps of 3.</span></span>  
  
```vb  
Dim workColumn As DataColumn = workTable.Columns.Add( _  
    "CustomerID", typeof(Int32))  
workColumn.AutoIncrement = true  
workColumn.AutoIncrementSeed = 200  
workColumn.AutoIncrementStep = 3  
```  
  
```csharp  
DataColumn workColumn = workTable.Columns.Add(  
    "CustomerID", typeof(Int32));  
workColumn.AutoIncrement = true;  
workColumn.AutoIncrementSeed = 200;  
workColumn.AutoIncrementStep = 3;  
```  
  
## <a name="see-also"></a><span data-ttu-id="153b3-108">См. также</span><span class="sxs-lookup"><span data-stu-id="153b3-108">See also</span></span>

- <xref:System.Data.DataColumn>
- [<span data-ttu-id="153b3-109">Определение схемы DataTable</span><span class="sxs-lookup"><span data-stu-id="153b3-109">DataTable Schema Definition</span></span>](datatable-schema-definition.md)
- [<span data-ttu-id="153b3-110">DataTables</span><span class="sxs-lookup"><span data-stu-id="153b3-110">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="153b3-111">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="153b3-111">ADO.NET Overview</span></span>](../ado-net-overview.md)
