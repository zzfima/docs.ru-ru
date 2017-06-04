---
title: "AcceptChanges и RejectChanges | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e2d1a6fe-31f9-4b83-9728-06c406a3394e
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# AcceptChanges и RejectChanges
После проверки правильности изменений, внесенных в данные в объекте <xref:System.Data.DataTable>, эти изменения можно принять с помощью метода <xref:System.Data.DataRow.AcceptChanges%2A> объекта <xref:System.Data.DataRow>, <xref:System.Data.DataTable> или <xref:System.Data.DataSet>, который присваивает значениям строк **Current** значения **Original**, а свойству **RowState** \- значение **Unchanged**.  В результате принятия или отклонения изменений происходит удаление всех данных **RowError** и свойству **HasErrors** присваивается значение **false**.  Принятие или отклонение изменений также может затрагивать обновление данных в источнике данных.  Для получения дополнительной информации см. [Обновление источников данных с помощью объектов DataAdapter](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md).  
  
 Если для объекта **DataTable** существуют ограничения внешнего ключа, то изменения, принятые или отклоненные с помощью методов **AcceptChanges** или **RejectChanges**, распространяются на дочерние строки объекта **DataRow** в соответствии с правилами **ForeignKeyConstraint.AcceptRejectRule**.  Для получения дополнительной информации см. [Ограничения DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).  
  
 В следующем примере происходит проверка на наличие строк с ошибками, по возможности устраняются ошибки и отклоняются строки, в которых ошибка не может быть устранена.  Следует отметить, что применительно к устраненным ошибкам значение **RowError** переустанавливается в пустую строку, что приводит к присвоению свойству **HasErrors** значения **false**.  После устранения ошибок или отклонения всех строк с ошибками вызывается метод **AcceptChanges** для принятия всех изменений для всего объекта **DataTable**.  
  
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
  
## См. также  
 <xref:System.Data.DataRow>   
 <xref:System.Data.DataSet>   
 <xref:System.Data.DataTable>   
 [Обработка данных в DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)