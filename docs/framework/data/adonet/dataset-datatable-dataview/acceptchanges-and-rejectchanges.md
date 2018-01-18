---
title: "AcceptChanges и RejectChanges"
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
ms.assetid: e2d1a6fe-31f9-4b83-9728-06c406a3394e
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 4c7d86aed61957d15d9c37f494bf80088b164dea
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="acceptchanges-and-rejectchanges"></a><span data-ttu-id="c0f34-102">AcceptChanges и RejectChanges</span><span class="sxs-lookup"><span data-stu-id="c0f34-102">AcceptChanges and RejectChanges</span></span>
<span data-ttu-id="c0f34-103">После проверки изменений, внесенных в данные в точности <xref:System.Data.DataTable>, можно принять изменения с помощью <xref:System.Data.DataRow.AcceptChanges%2A> метод <xref:System.Data.DataRow>, <xref:System.Data.DataTable>, или <xref:System.Data.DataSet>, задающий **текущей** строки значения были **исходного** значения и задаст **RowState** свойства **Unchanged**.</span><span class="sxs-lookup"><span data-stu-id="c0f34-103">After verifying the accuracy of changes made to data in a <xref:System.Data.DataTable>, you can accept the changes using the <xref:System.Data.DataRow.AcceptChanges%2A> method of the <xref:System.Data.DataRow>, <xref:System.Data.DataTable>, or <xref:System.Data.DataSet>, which will set the **Current** row values to be the **Original** values and will set the **RowState** property to **Unchanged**.</span></span> <span data-ttu-id="c0f34-104">Принятие или отклонение изменений удаление всех **RowError** сведения и наборы **HasErrors** свойства **false**.</span><span class="sxs-lookup"><span data-stu-id="c0f34-104">Accepting or rejecting changes clears out any **RowError** information and sets the **HasErrors** property to **false**.</span></span> <span data-ttu-id="c0f34-105">Принятие или отклонение изменений также может затрагивать обновление данных в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="c0f34-105">Accepting or rejecting changes can also affect updating data in the data source.</span></span> <span data-ttu-id="c0f34-106">Дополнительные сведения см. в разделе [обновление источников данных с помощью DataAdapter](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md).</span><span class="sxs-lookup"><span data-stu-id="c0f34-106">For more information, see [Updating Data Sources with DataAdapters](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md).</span></span>  
  
 <span data-ttu-id="c0f34-107">Если существуют ограничения внешнего ключа на **DataTable**, изменения, принятые или отклоненные с помощью **AcceptChanges** и **RejectChanges** распространяются на дочерние строки объекта  **DataRow** согласно **ForeignKeyConstraint.AcceptRejectRule**.</span><span class="sxs-lookup"><span data-stu-id="c0f34-107">If foreign key constraints exist on the **DataTable**, changes accepted or rejected using **AcceptChanges** and **RejectChanges** are propagated to child rows of the **DataRow** according to the **ForeignKeyConstraint.AcceptRejectRule**.</span></span> <span data-ttu-id="c0f34-108">Дополнительные сведения см. в разделе [ограничения таблиц данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="c0f34-108">For more information, see [DataTable Constraints](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).</span></span>  
  
 <span data-ttu-id="c0f34-109">В следующем примере происходит проверка на наличие строк с ошибками, по возможности устраняются ошибки и отклоняются строки, в которых ошибка не может быть устранена.</span><span class="sxs-lookup"><span data-stu-id="c0f34-109">The following example checks for rows with errors, resolves the errors where applicable, and rejects the rows where the error cannot be resolved.</span></span> <span data-ttu-id="c0f34-110">Обратите внимание, что для разрешения ошибок, **RowError** значение сбрасывается на пустую строку, вызывая **HasErrors** свойству будет присвоено **false**.</span><span class="sxs-lookup"><span data-stu-id="c0f34-110">Note that, for resolved errors, the **RowError** value is reset to an empty string, causing the **HasErrors** property to be set to **false**.</span></span> <span data-ttu-id="c0f34-111">Когда все строки с ошибками после устранения ошибок или отклонения **AcceptChanges** вызывается для принятия всех изменений для всего **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="c0f34-111">When all the rows with errors have been resolved or rejected, **AcceptChanges** is called to accept all changes for the entire **DataTable**.</span></span>  
  
```vb  
If workTable.HasErrors Then  
  Dim errRow As DataRow  
  
  For Each errRow in workTable.GetErrors()  
  
    If errRow.RowError = "Total cannot exceed 1000." Then  
      errRow("Total") = 1000  
      errRow.RowError = ""    ' Clear the error.  
    Else  
      errRow.RejectChanges()  
    End If  
  Next  
End If  
  
workTable.AcceptChanges()  
```  
  
```csharp  
if (workTable.HasErrors)  
{  
  
  foreach (DataRow errRow in workTable.GetErrors())  
  {  
    if (errRow.RowError == "Total cannot exceed 1000.")  
    {  
      errRow["Total"] = 1000;  
      errRow.RowError = "";    // Clear the error.  
    }  
    else  
      errRow.RejectChanges();  
  }  
}  
  
workTable.AcceptChanges();  
```  
  
## <a name="see-also"></a><span data-ttu-id="c0f34-112">См. также</span><span class="sxs-lookup"><span data-stu-id="c0f34-112">See Also</span></span>  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataSet>  
 <xref:System.Data.DataTable>  
 [<span data-ttu-id="c0f34-113">Управление данными в DataTable</span><span class="sxs-lookup"><span data-stu-id="c0f34-113">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [<span data-ttu-id="c0f34-114">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c0f34-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
