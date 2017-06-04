---
title: "Удаление DataRow | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c34f531d-4b9b-4071-b2d7-342c402aa586
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# Удаление DataRow
Для удаления объекта <xref:System.Data.DataRow> из объекта <xref:System.Data.DataTable> служат два метода: метод **Remove** объекта <xref:System.Data.DataRowCollection> и метод <xref:System.Data.DataRow.Delete%2A> объекта **DataRow**.  Метод <xref:System.Data.DataRowCollection.Remove%2A> удаляет объект **DataRow** из коллекции **DataRowCollection**, тогда как метод <xref:System.Data.DataRow.Delete%2A> только помечает строку для удаления.  Фактическое удаление происходит, когда в приложении вызывается метод **AcceptChanges**.  Использование метода <xref:System.Data.DataRow.Delete%2A> позволяет программно проверять, какие строки помечены для удаления, перед их фактическим удалением.  Когда строка отмечена для удаления, ее свойство <xref:System.Data.DataRow.RowState%2A> имеет значение <xref:System.Data.DataRow.Delete%2A>.  
  
 Ни <xref:System.Data.DataRow.Delete%2A>, ни <xref:System.Data.DataRowCollection.Remove%2A> не должны вызываться в цикле foreach во время итерации по объекту <xref:System.Data.DataRowCollection>.  Ни <xref:System.Data.DataRow.Delete%2A>, ни <xref:System.Data.DataRowCollection.Remove%2A> не изменяет состояние коллекции.  
  
 При использовании <xref:System.Data.DataSet> или **DataTable** в сочетании с **DataAdapter** и реляционным источником данных для удаления строки используйте метод **Delete** объекта **DataRow**.  Метод **Delete** помечает строку как **Deleted** в наборе в **DataSet** или таблице **DataTable**, но не удаляет ее.  Вместо этого, когда объект **DataAdapter** обнаруживает строку, помеченную как **Deleted**, он выполняет свой метод **DeleteCommand**, чтобы удалить строку в источнике данных.  Затем строку можно окончательно удалить с помощью метода **AcceptChanges**.  При использовании метода **Remove** для удаления строки она полностью удаляется из таблицы, однако объект **DataAdapter** не удаляет строку в источнике данных.  
  
 Метод **Remove** объекта **DataRowCollection** получает объект **DataRow** в качестве аргумента и удаляет его из коллекции, как показано в следующем примере.  
  
```vb  
workTable.Rows.Remove(workRow)  
  
```  
  
```csharp  
workTable.Rows.Remove(workRow);  
```  
  
 В отличие от этого, в следующем примере показано, как вызывать метод **Delete** объекта **DataRow**, чтобы изменить состояние строки **RowState** в значение **Deleted**.  
  
```vb  
workRow.Delete  
  
```  
  
```csharp  
workRow.Delete();  
```  
  
 Если строка помечена для удаления и вызывается метод **AcceptChanges** объекта **DataTable**, то строка удаляется из таблицы **DataTable**.  Напротив, если вызвать метод **RejectChanges**, то состояние **RowState** строки возвращается к тому значению, которое оно имело до того, как строка была помечена как **Deleted**.  
  
> [!NOTE]
>  Если состояние **RowState** объекта **DataRow** имеет значение **Added**, означающее, что она недавно была добавлена в таблицу, и затем она помечается как **Deleted**, то строка удаляется из таблицы.  
  
## См. также  
 <xref:System.Data.DataRow>   
 <xref:System.Data.DataRowCollection>   
 <xref:System.Data.DataTable>   
 [Обработка данных в DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)