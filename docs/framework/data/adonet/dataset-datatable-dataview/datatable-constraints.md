---
title: "Ограничения таблиц данных"
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
ms.assetid: 27c9f2fd-f64d-4b4e-bbf6-1d24f47067cb
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: fb1fd2c7aa057fcc83c82ab9d72129db2cac680e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="datatable-constraints"></a>Ограничения таблиц данных
Ограничения позволяют принудительно поддерживать целостность данных <xref:System.Data.DataTable>. Ограничение представляет собой автоматическое правило, применяемое к столбцу или связанным столбцам и определяющее порядок действий при каком-либо изменении содержимого строки. Ограничения применяются при `System.Data.DataSet.EnforceConstraints` свойство <xref:System.Data.DataSet> — **true**. Пример кода, показывающий, как установить свойство `EnforceConstraints`, см. в разделе справки <xref:System.Data.DataSet.EnforceConstraints%2A>.  
  
 В ADO.NET имеется два типа ограничений: <xref:System.Data.ForeignKeyConstraint> и <xref:System.Data.UniqueConstraint>. По умолчанию оба ограничения создаются автоматически при создании связи между двух или более таблиц, добавив <xref:System.Data.DataRelation> для **набора данных**. Тем не менее, можно отключить это поведение, указав **createConstraints** = **false** при создании связи.  
  
## <a name="foreignkeyconstraint"></a>Ограничение ForeignKeyConstraint  
 Объект **ForeignKeyConstraint** применяет правила, определяющие порядок распространения обновлений и удалений в связанных таблицах. Например, если значение в строке одной таблицы обновляется или удаляется и то же самое значение также используется в одном или нескольких связанных таблицах **ForeignKeyConstraint** определяет, что произойдет в связанных таблицах.  
  
 <xref:System.Data.ForeignKeyConstraint.DeleteRule%2A> И <xref:System.Data.ForeignKeyConstraint.UpdateRule%2A> свойства **ForeignKeyConstraint** определить действие, выполняемое в случае, когда пользователь пытается удалить или обновить строку в связанной таблице. В следующей таблице описаны различные параметры, доступные для **DeleteRule** и **UpdateRule** свойства **ForeignKeyConstraint**.  
  
|Установка правил|Описание|  
|------------------|-----------------|  
|**CASCADE**|Удалить или обновить связанные строки.|  
|**SetNull**|Значения в связанных строках **DBNull**.|  
|**SetDefault**|Присвоить столбцам в связанных строках значение по умолчанию.|  
|**None**|Не выполнять никаких действий в связанных строках. Это значение по умолчанию.|  
  
 Объект **ForeignKeyConstraint** можно ограничить, распространять, изменения на связанные столбцы. В зависимости от свойств, заданных для **ForeignKeyConstraint** столбца, если **EnforceConstraints** свойство **DataSet** — **true**, определенные операции в родительских строках приведет к возникновению исключения. Например если **DeleteRule** свойство **ForeignKeyConstraint** — **нет**, родительскую строку нельзя удалить, если он имеет дочерние строки.  
  
 Можно создать ограничение внешнего ключа между отдельными столбцами или массивом столбцов с помощью **ForeignKeyConstraint** конструктор. Передайте объект **ForeignKeyConstraint** объект **добавить** свойства таблицы **ограничения** свойство, которое является **ConstraintCollection**. Можно также передать аргументы конструктора одному из нескольких перегруженных **добавить** метод **ConstraintCollection** для создания **ForeignKeyConstraint**.  
  
 При создании **ForeignKeyConstraint**, можно передать **DeleteRule** и **UpdateRule** значения в конструктор как аргументов или задать их в виде свойств, как и в Следующий пример (где **DeleteRule** имеет значение **нет**).  
  
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
  
### <a name="acceptrejectrule"></a>Свойство AcceptRejectRule  
 Изменения в строках могут быть получены с помощью **AcceptChanges** метода или отменить с помощью **RejectChanges** метод **DataSet**, **DataTable**, или **DataRow**. Когда **DataSet** содержит **ForeignKeyConstraints**, вызов **AcceptChanges** или **RejectChanges** методов обеспечивает  **AcceptRejectRule**. **AcceptRejectRule** свойство **ForeignKeyConstraint** определяет действие, которое следует предпринять в дочерних строках, если **AcceptChanges** или  **RejectChanges** вызывается в родительских строках.  
  
 В следующей таблице перечислены доступные параметры для **AcceptRejectRule**.  
  
|Установка правил|Описание|  
|------------------|-----------------|  
|**CASCADE**|Принять или отклонить изменения в дочерних строках.|  
|**None**|Не выполнять никаких действий в дочерних строках. Это значение по умолчанию.|  
  
### <a name="example"></a>Пример  
 В следующем примере создается ограничение <xref:System.Data.ForeignKeyConstraint>, устанавливаются некоторые из его свойств, в том числе <xref:System.Data.ForeignKeyConstraint.AcceptRejectRule%2A>, а само ограничение добавляется в коллекцию <xref:System.Data.ConstraintCollection> объекта <xref:System.Data.DataTable>.  
  
 [!code-csharp[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/CS/source.cs#1)]
 [!code-vb[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/VB/source.vb#1)]  
  
## <a name="uniqueconstraint"></a>Ограничение UniqueConstraint  
 **UniqueConstraint** объекта, которые могут быть назначены одному столбцу или к массиву столбцов в **DataTable**, обеспечивает уникальность каждой строки все данные для указанного столбца или столбцов. Можно создать ограничение уникальности для столбца или массива столбцов с помощью **UniqueConstraint** конструктор. Передайте объект **UniqueConstraint** объект **добавить** свойства таблицы **ограничения** свойство, которое является **ConstraintCollection**. Можно также передать аргументы конструктора одному из нескольких перегруженных **добавить** метод **ConstraintCollection** для создания **UniqueConstraint**. При создании **UniqueConstraint** для столбца или столбцов, можно указать, ли столбец или столбцы первичного ключа.  
  
 Можно также создать ограничение уникальности для столбца, присвоив **Unique** свойство столбца **true**. Кроме того, параметр **Unique** свойство из одного столбца для **false** удаляет уникальности, которые могут существовать. При определении столбца или группы столбцов в качестве первичного ключа таблицы автоматически создается ограничение уникальности для заданного столбца или группы столбцов. Если удалить столбец из **PrimaryKey** свойство **DataTable**, **UniqueConstraint** удаляется.  
  
 В следующем примере создается **UniqueConstraint** для двух столбцов **DataTable**.  
  
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
  
## <a name="see-also"></a>См. также  
 <xref:System.Data.DataRelation>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.ForeignKeyConstraint>  
 <xref:System.Data.UniqueConstraint>  
 [Определение схемы таблицы данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 [Наборы данных, таблицы данных и объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
