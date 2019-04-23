---
title: AcceptChanges и RejectChanges
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e2d1a6fe-31f9-4b83-9728-06c406a3394e
ms.openlocfilehash: bbcc666b99c2bade479e5ee51750b043c820845d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59172904"
---
# <a name="acceptchanges-and-rejectchanges"></a><span data-ttu-id="f4b4e-102">AcceptChanges и RejectChanges</span><span class="sxs-lookup"><span data-stu-id="f4b4e-102">AcceptChanges and RejectChanges</span></span>
<span data-ttu-id="f4b4e-103">После проверки точности изменения, внесенные в данные в <xref:System.Data.DataTable>, вы можете принять изменения с помощью <xref:System.Data.DataRow.AcceptChanges%2A> метод <xref:System.Data.DataRow>, <xref:System.Data.DataTable>, или <xref:System.Data.DataSet>, задающий **текущей** строки значения были **исходного** значения и задаст **RowState** свойства **Unchanged**.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-103">After verifying the accuracy of changes made to data in a <xref:System.Data.DataTable>, you can accept the changes using the <xref:System.Data.DataRow.AcceptChanges%2A> method of the <xref:System.Data.DataRow>, <xref:System.Data.DataTable>, or <xref:System.Data.DataSet>, which will set the **Current** row values to be the **Original** values and will set the **RowState** property to **Unchanged**.</span></span> <span data-ttu-id="f4b4e-104">Принятие или отклонение изменений удаление всех **RowError** и свойству **HasErrors** свойства **false**.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-104">Accepting or rejecting changes clears out any **RowError** information and sets the **HasErrors** property to **false**.</span></span> <span data-ttu-id="f4b4e-105">Принятие или отклонение изменений также может затрагивать обновление данных в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-105">Accepting or rejecting changes can also affect updating data in the data source.</span></span> <span data-ttu-id="f4b4e-106">Дополнительные сведения см. в разделе [обновление источников данных с объектами DataAdapter](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md).</span><span class="sxs-lookup"><span data-stu-id="f4b4e-106">For more information, see [Updating Data Sources with DataAdapters](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md).</span></span>  
  
 <span data-ttu-id="f4b4e-107">Если существуют ограничения внешнего ключа на **DataTable**, изменения, принятые или отклоненные с помощью **AcceptChanges** и **RejectChanges** распространяются на дочерние строки объекта  **DataRow** согласно **ForeignKeyConstraint.AcceptRejectRule**.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-107">If foreign key constraints exist on the **DataTable**, changes accepted or rejected using **AcceptChanges** and **RejectChanges** are propagated to child rows of the **DataRow** according to the **ForeignKeyConstraint.AcceptRejectRule**.</span></span> <span data-ttu-id="f4b4e-108">Дополнительные сведения см. в разделе [ограничения таблиц данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="f4b4e-108">For more information, see [DataTable Constraints](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).</span></span>  
  
 <span data-ttu-id="f4b4e-109">В следующем примере происходит проверка на наличие строк с ошибками, по возможности устраняются ошибки и отклоняются строки, в которых ошибка не может быть устранена.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-109">The following example checks for rows with errors, resolves the errors where applicable, and rejects the rows where the error cannot be resolved.</span></span> <span data-ttu-id="f4b4e-110">Обратите внимание, что применительно к устраненным ошибкам **RowError** значение сбрасывается на пустую строку, вызывая **HasErrors** свойству будет присвоено **false**.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-110">Note that, for resolved errors, the **RowError** value is reset to an empty string, causing the **HasErrors** property to be set to **false**.</span></span> <span data-ttu-id="f4b4e-111">Когда все строки с ошибками после устранения ошибок или отклонения **AcceptChanges** вызывается для принятия всех изменений для всего **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="f4b4e-111">When all the rows with errors have been resolved or rejected, **AcceptChanges** is called to accept all changes for the entire **DataTable**.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f4b4e-112">См. также</span><span class="sxs-lookup"><span data-stu-id="f4b4e-112">See also</span></span>

- <xref:System.Data.DataRow>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="f4b4e-113">Управление данными в DataTable</span><span class="sxs-lookup"><span data-stu-id="f4b4e-113">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="f4b4e-114">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f4b4e-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
