---
title: "Ограничения DataTable | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 27c9f2fd-f64d-4b4e-bbf6-1d24f47067cb
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Ограничения DataTable
Ограничения позволяют принудительно поддерживать целостность данных <xref:System.Data.DataTable>.  Ограничение представляет собой автоматическое правило, применяемое к столбцу или связанным столбцам и определяющее порядок действий при каком\-либо изменении содержимого строки.  Ограничения применяются, если свойство  `System.Data.DataSet.EnforceConstraints` коллекции <xref:System.Data.DataSet> имеет значение **true**.  Пример кода, показывающий, как установить свойство `EnforceConstraints`, см. в разделе справки <xref:System.Data.DataSet.EnforceConstraints%2A>.  
  
 В ADO.NET имеется два типа ограничений: <xref:System.Data.ForeignKeyConstraint> и <xref:System.Data.UniqueConstraint>.  По умолчанию оба ограничения создаются автоматически при установке связи между двумя или несколькими таблицами путем добавления отношения <xref:System.Data.DataRelation> к коллекции **DataSet**.  Однако такое поведение можно отменить, указав параметр **createConstraints** \= **false** при создании связи.  
  
## Ограничение ForeignKeyConstraint  
 Ограничение **ForeignKeyConstraint** применяет правила распространения обновлений и удалений в связанных таблицах.  Например, если обновлено или удалено значение строки одной таблицы, и то же самое значение используется в одной или нескольких связанных таблицах, **ForeignKeyConstraint** определяет, что произойдет в связанных таблицах.  
  
 Свойства <xref:System.Data.ForeignKeyConstraint.DeleteRule%2A> и <xref:System.Data.ForeignKeyConstraint.UpdateRule%2A> ограничения **ForeignKeyConstraint** задают действие, которое должно быть выполнено, когда пользователь пытается удалить или обновить строку в связанной таблице.  В следующей таблице приведены настройки, доступные для свойств **DeleteRule** и **UpdateRule** ограничения **ForeignKeyConstraint**.  
  
|Установка правил|Описание|  
|----------------------|--------------|  
|**Cascade**|Удалить или обновить связанные строки.|  
|**SetNull**|Присвоить столбцам в связанных строках значение **DBNull**.|  
|**SetDefault**|Присвоить столбцам в связанных строках значение по умолчанию.|  
|**Нет**|Не выполнять никаких действий в связанных строках.  Это значение по умолчанию.|  
  
 **ForeignKeyConstraint** может ограничивать или распространять изменения на связанные столбцы.  В зависимости от свойств, заданных для ограничения **ForeignKeyConstraint** столбца, при значении свойства **EnforceConstraints** для **DataSet**, равном **true**, определенные операции в родительских строках приведут к возникновению исключения.  Например, если свойство **DeleteRule** ограничения **ForeignKeyConstraint** имеет значение **None**, родительскую строку нельзя удалять, если у нее имеются дочерние строки.  
  
 Можно создать ограничение внешнего ключа между отдельными столбцами или массивом столбцов с помощью конструктора **ForeignKeyConstraint**.  Передайте объект **ForeignKeyConstraint** методу **Add** свойства таблицы **Constraints**, которое представляет собой объект **ConstraintCollection**.  Для создания ограничения **ForeignKeyConstraint** можно также передать аргументы конструктора одному из нескольких перегруженных методов **Add** коллекции **ConstraintCollection**.  
  
 При создании ограничения **ForeignKeyConstraint** можно передать конструктору значения **DeleteRule** и **UpdateRule** в качестве аргументов или задать их в виде свойств, как показано в следующем примере \(где значение **DeleteRule** равно **None**\).  
  
```vb  
Dim custOrderFK As ForeignKeyConstraint = New ForeignKeyConstraint("CustOrderFK", _  
  custDS.Tables("CustTable").Columns("CustomerID"), _  
  custDS.Tables("OrdersTable").Columns("CustomerID"))  
custOrderFK.DeleteRule = Rule.None    
' Cannot delete a customer value that has associated existing orders.  
custDS.Tables("OrdersTable").Constraints.Add(custOrderFK)  
  
```  
  
```csharp  
ForeignKeyConstraint custOrderFK = new ForeignKeyConstraint("CustOrderFK",  
  custDS.Tables["CustTable"].Columns["CustomerID"],   
  custDS.Tables["OrdersTable"].Columns["CustomerID"]);  
custOrderFK.DeleteRule = Rule.None;    
// Cannot delete a customer value that has associated existing orders.  
custDS.Tables["OrdersTable"].Constraints.Add(custOrderFK);  
```  
  
### Свойство AcceptRejectRule  
 Изменения строк можно принять, используя метод **AcceptChanges**, или отменить с помощью метода **RejectChanges** для **DataSet**, **DataTable** или **DataRow**.  Если **DataSet** содержит ограничение **ForeignKeyConstraints**, вызов методов **AcceptChanges** и **RejectChanges** применяет свойство **AcceptRejectRule**.  Свойство **AcceptRejectRule** ограничения **ForeignKeyConstraint** определяет, какие действия следует предпринять в дочерних строках, если в родительской строке вызывается метод **AcceptChanges** или **RejectChanges**.  
  
 В следующей таблице перечислены доступные настройки **AcceptRejectRule**.  
  
|Установка правил|Описание|  
|----------------------|--------------|  
|**Cascade**|Принять или отклонить изменения в дочерних строках.|  
|**Нет**|Не выполнять никаких действий в дочерних строках.  Это значение по умолчанию.|  
  
### Пример  
 В следующем примере создается ограничение <xref:System.Data.ForeignKeyConstraint>, устанавливаются некоторые из его свойств, в том числе <xref:System.Data.ForeignKeyConstraint.AcceptRejectRule%2A>, а само ограничение добавляется в коллекцию <xref:System.Data.ConstraintCollection> объекта <xref:System.Data.DataTable>.  
  
 [!code-csharp[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/CS/source.cs#1)]
 [!code-vb[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/VB/source.vb#1)]  
  
## Ограничение UniqueConstraint  
 Объект **UniqueConstraint**, назначаемый или отдельному столбцу, или массиву столбцов в наборе данных **DataTable**, обеспечивает уникальность всех данных заданного столбца или столбцов для одной строки.  Можно создать ограничение уникальности для столбца или массива столбцов с помощью конструктора **UniqueConstraint**.  Передайте объект **UniqueConstraint** методу **Add** свойства таблицы **Constraints**, которое представляет собой коллекцию **ConstraintCollection**.  Для создания ограничения **UniqueConstraint** можно также передать аргументы конструктора одному из нескольких перегруженных методов **Add** коллекции **ConstraintCollection**.  При создании ограничения **UniqueConstraint** для одного или нескольких столбцов можно по желанию указать, является ли этот столбец или группа столбцов первичным ключом.  
  
 Можно также создать ограничение уникальности для столбца, присвоив его свойству **Unique** значение **true**.  Либо, присвоив свойству **Unique** одного столбца значение **false**, можно удалить любое существующее ограничение уникальности.  При определении столбца или группы столбцов в качестве первичного ключа таблицы автоматически создается ограничение уникальности для заданного столбца или группы столбцов.  Если удалить столбец из свойства **PrimaryKey** для **DataTable**, ограничение **UniqueConstraint** удаляется.  
  
 В следующем примере создается ограничение **UniqueConstraint** для двух столбцов **DataTable**.  
  
```vb  
Dim custTable As DataTable = custDS.Tables("Customers")  
Dim custUnique As UniqueConstraint = _  
    New UniqueConstraint(New DataColumn()   {custTable.Columns("CustomerID"), _  
    custTable.Columns("CompanyName")})  
custDS.Tables("Customers").Constraints.Add(custUnique)  
  
```  
  
```csharp  
DataTable custTable = custDS.Tables["Customers"];  
UniqueConstraint custUnique = new UniqueConstraint(new DataColumn[]   
    {custTable.Columns["CustomerID"],   
    custTable.Columns["CompanyName"]});  
custDS.Tables["Customers"].Constraints.Add(custUnique);  
```  
  
## См. также  
 <xref:System.Data.DataRelation>   
 <xref:System.Data.DataTable>   
 <xref:System.Data.ForeignKeyConstraint>   
 <xref:System.Data.UniqueConstraint>   
 [Определение схемы DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)   
 [Объекты DataSet, DataTable и DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)