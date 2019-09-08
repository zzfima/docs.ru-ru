---
title: AcceptChanges и RejectChanges
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e2d1a6fe-31f9-4b83-9728-06c406a3394e
ms.openlocfilehash: c537fa808fc6ba4c740e71bfd70fe9cd1f3bd31a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785574"
---
# <a name="acceptchanges-and-rejectchanges"></a>AcceptChanges и RejectChanges
После проверки точности изменений <xref:System.Data.DataTable>, внесенных в данные в, можно принять изменения <xref:System.Data.DataRow> <xref:System.Data.DataRow.AcceptChanges%2A> с помощью метода, <xref:System.Data.DataTable>или <xref:System.Data.DataSet>, который будет устанавливать **текущие** значения строк в значение  **Исходные** значения и задаст свойству **RowState** значение **без изменений**. При принятии или отклонении изменений удаляется любая **роверрор** информация, а свойству **HasErrors** присваивается **значение false**. Принятие или отклонение изменений также может затрагивать обновление данных в источнике данных. Дополнительные сведения см. в разделе [Обновление источников данных с помощью DataAdapter](../updating-data-sources-with-dataadapters.md).  
  
 Если в **DataTable**существуют ограничения внешнего ключа, изменения, принятые или Отклоненные с помощью **AcceptChanges** и **RejectChanges** , распространяются на дочерние строки **DataRow** в соответствии **с ForeignKeyConstraint. Акцептрежектруле**. Дополнительные сведения см. в разделе [ограничения DataTable](datatable-constraints.md).  
  
 В следующем примере происходит проверка на наличие строк с ошибками, по возможности устраняются ошибки и отклоняются строки, в которых ошибка не может быть устранена. Обратите внимание, что для разрешенных ошибок значение **роверрор** сбрасывается в пустую строку, в результате чего свойство **HasErrors** устанавливается в значение **false**. Если все строки с ошибками были разрешены или отклонены, вызывается метод **AcceptChanges** , чтобы принять все изменения для всей **таблицы DataTable**.  
  
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
  
## <a name="see-also"></a>См. также

- <xref:System.Data.DataRow>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [Управление данными в DataTable](manipulating-data-in-a-datatable.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
