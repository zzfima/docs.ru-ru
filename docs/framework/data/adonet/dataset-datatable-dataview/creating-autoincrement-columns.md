---
title: Создание столбцов AutoIncrement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cf09732a-ab54-4d98-89e2-4d0a1f28fbce
ms.openlocfilehash: 2548ad9382b406978dac0a3d366207626278f501
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2019
ms.locfileid: "70205130"
---
# <a name="creating-autoincrement-columns"></a><span data-ttu-id="21032-102">Создание столбцов AutoIncrement</span><span class="sxs-lookup"><span data-stu-id="21032-102">Creating AutoIncrement Columns</span></span>
<span data-ttu-id="21032-103">Чтобы обеспечить наличие в столбце уникальных значений, можно указать, что значения в столбце должны увеличиваться автоматически при добавлении новых строк к таблице.</span><span class="sxs-lookup"><span data-stu-id="21032-103">To ensure unique column values, you can set the column values to increment automatically when new rows are added to the table.</span></span> <span data-ttu-id="21032-104">Чтобы создать автоматическое приращение <xref:System.Data.DataColumn>, <xref:System.Data.DataColumn.AutoIncrement%2A> присвойте свойству столбца значение **true**.</span><span class="sxs-lookup"><span data-stu-id="21032-104">To create an auto-incrementing <xref:System.Data.DataColumn>, set the <xref:System.Data.DataColumn.AutoIncrement%2A> property of the column to **true**.</span></span> <span data-ttu-id="21032-105">Затем начинается со значения, определенного <xref:System.Data.DataColumn.AutoIncrementSeed%2A> в свойстве, и при добавлении каждой строки значение столбца **AutoIncrement** <xref:System.Data.DataColumn.AutoIncrementStep%2A> увеличивается на значение, определенное в свойстве столбца. <xref:System.Data.DataColumn></span><span class="sxs-lookup"><span data-stu-id="21032-105">The <xref:System.Data.DataColumn> then starts with the value defined in the <xref:System.Data.DataColumn.AutoIncrementSeed%2A> property, and with each row added the value of the **AutoIncrement** column increases by the value defined in the <xref:System.Data.DataColumn.AutoIncrementStep%2A> property of the column.</span></span>  
  
 <span data-ttu-id="21032-106">Для столбцов с автоувеличением рекомендуется, <xref:System.Data.DataColumn.ReadOnly%2A> чтобы свойство **DataColumn** было установлено в **значение true**.</span><span class="sxs-lookup"><span data-stu-id="21032-106">For **AutoIncrement** columns, we recommend that the <xref:System.Data.DataColumn.ReadOnly%2A> property of the **DataColumn** be set to **true**.</span></span>  
  
 <span data-ttu-id="21032-107">В следующем примере показано, как создать столбец, значения в котором начинаются с 200 и каждый раз увеличиваются с шагом 3.</span><span class="sxs-lookup"><span data-stu-id="21032-107">The following example demonstrates how to create a column that starts with a value of 200 and adds incrementally in steps of 3.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="21032-108">См. также</span><span class="sxs-lookup"><span data-stu-id="21032-108">See also</span></span>

- <xref:System.Data.DataColumn>
- [<span data-ttu-id="21032-109">Определение схемы DataTable</span><span class="sxs-lookup"><span data-stu-id="21032-109">DataTable Schema Definition</span></span>](datatable-schema-definition.md)
- [<span data-ttu-id="21032-110">DataTables</span><span class="sxs-lookup"><span data-stu-id="21032-110">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="21032-111">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="21032-111">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
