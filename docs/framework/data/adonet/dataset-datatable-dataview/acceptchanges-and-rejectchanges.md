---
title: AcceptChanges и RejectChanges
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e2d1a6fe-31f9-4b83-9728-06c406a3394e
ms.openlocfilehash: a8589b157bc2579a03d856b73802abc9a4b42855
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204074"
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
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
