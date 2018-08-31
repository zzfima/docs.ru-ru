---
title: Ограничения таблиц данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 27c9f2fd-f64d-4b4e-bbf6-1d24f47067cb
ms.openlocfilehash: fa70af311d6b4fa4e17bb3ba6110e4cea420c34c
ms.sourcegitcommit: a368166a51e5204c0224fbf5e46476e3ed122817
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2018
ms.locfileid: "43332037"
---
# <a name="datatable-constraints"></a>Ограничения таблиц данных
Ограничения позволяют принудительно поддерживать целостность данных <xref:System.Data.DataTable>. Ограничение представляет собой автоматическое правило, применяемое к столбцу или связанным столбцам и определяющее порядок действий при каком-либо изменении содержимого строки. Ограничения применяются при `System.Data.DataSet.EnforceConstraints` свойство <xref:System.Data.DataSet> — **true**. Пример кода, показывающий, как установить свойство `EnforceConstraints`, см. в разделе справки <xref:System.Data.DataSet.EnforceConstraints%2A>.  
  
 В ADO.NET имеется два типа ограничений: <xref:System.Data.ForeignKeyConstraint> и <xref:System.Data.UniqueConstraint>. По умолчанию оба ограничения создаются автоматически при создании связи между двух или более таблиц, добавив <xref:System.Data.DataRelation> для **набора данных**. Тем не менее, это поведение можно отключить, указав **createConstraints** = **false** при создании связи.  
  
## <a name="foreignkeyconstraint"></a>Ограничение ForeignKeyConstraint  
 Объект **ForeignKeyConstraint** определяет порядок распространения обновлений и удалений в связанных таблицах. Например, если значение в строке одной таблицы обновляется или удаляется и то же самое значение также используется в одном или нескольких связанных таблицах **ForeignKeyConstraint** определяет, что произойдет в связанных таблицах.  
  
 <xref:System.Data.ForeignKeyConstraint.DeleteRule%2A> И <xref:System.Data.ForeignKeyConstraint.UpdateRule%2A> свойства **ForeignKeyConstraint** определить действие, выполняемое, когда пользователь пытается удалить или обновить строку в связанной таблице. В следующей таблице описаны различные доступные параметры для **DeleteRule** и **UpdateRule** свойства **ForeignKeyConstraint**.  
  
|Установка правил|Описание:|  
|------------------|-----------------|  
|**Cascade**|Удалить или обновить связанные строки.|  
|**SetNull**|Задайте значения в связанных строках **DBNull**.|  
|**SetDefault**|Присвоить столбцам в связанных строках значение по умолчанию.|  
|**None**|Не выполнять никаких действий в связанных строках. Это значение по умолчанию.|  
  
 Объект **ForeignKeyConstraint** может ограничивать или распространять, изменения на связанные столбцы. В зависимости от свойств, заданных для **ForeignKeyConstraint** столбца, если **EnforceConstraints** свойство **набора данных** является **true**, определенные операции в родительскую строку приведет к исключению. Например если **DeleteRule** свойство **ForeignKeyConstraint** — **None**, родительскую строку нельзя удалить, если он имеет дочерние строки.  
  
 Можно создать ограничение внешнего ключа между отдельными столбцами или массивом столбцов с помощью **ForeignKeyConstraint** конструктор. Передайте объект **ForeignKeyConstraint** объект **добавить** метод таблицы **ограничения** свойство, являющееся **ConstraintCollection**. Можно также передать аргументы конструктора из нескольких перегруженных **добавить** метод **ConstraintCollection** для создания **ForeignKeyConstraint**.  
  
 При создании **ForeignKeyConstraint**, вы можете передать **DeleteRule** и **UpdateRule** значения в конструктор как аргументы, или задать их в виде свойств, как показано на Следующий пример (где **DeleteRule** присваивается значение **None**).  
  
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
 Изменения в строках можно принять, используя **AcceptChanges** метода или отменить с помощью метода **RejectChanges** метод **набора данных**, **DataTable**, или **DataRow**. Когда **набора данных** содержит **ForeignKeyConstraints**, вызов **AcceptChanges** или **RejectChanges** методов обеспечивает  **AcceptRejectRule**. **AcceptRejectRule** свойство **ForeignKeyConstraint** определяет действие, которое будет предпринять в дочерних строках, если **AcceptChanges** или  **RejectChanges** вызывается в родительской строке.  
  
 В следующей таблице перечислены доступные параметры для **AcceptRejectRule**.  
  
|Установка правил|Описание:|  
|------------------|-----------------|  
|**Cascade**|Принять или отклонить изменения в дочерних строках.|  
|**None**|Не выполнять никаких действий в дочерних строках. Это значение по умолчанию.|  
  
### <a name="example"></a>Пример  
 В следующем примере создается ограничение <xref:System.Data.ForeignKeyConstraint>, устанавливаются некоторые из его свойств, в том числе <xref:System.Data.ForeignKeyConstraint.AcceptRejectRule%2A>, а само ограничение добавляется в коллекцию <xref:System.Data.ConstraintCollection> объекта <xref:System.Data.DataTable>.  
  
 [!code-csharp[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/CS/source.cs#1)]
 [!code-vb[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/VB/source.vb#1)]  
  
## <a name="uniqueconstraint"></a>Ограничение UniqueConstraint  
 **UniqueConstraint** объект, который можно назначить отдельным столбцом или массиву столбцов в **DataTable**, обеспечивает уникальность каждой строки все данные в указанном столбце или столбцах. Можно создать ограничение уникальности для столбца или массива столбцов с помощью **UniqueConstraint** конструктор. Передайте объект **UniqueConstraint** объект **добавить** метод таблицы **ограничения** свойство, являющееся **ConstraintCollection**. Можно также передать аргументы конструктора из нескольких перегруженных **добавить** метод **ConstraintCollection** для создания **UniqueConstraint**. При создании **UniqueConstraint** для столбца или столбцов, при необходимости можно указать, ли столбец или столбцы первичного ключа.  
  
 Можно также создать ограничение уникальности для столбца, задав **Unique** свойство столбца **true**. Кроме того, параметр **Unique** свойство из одного столбца для **false** удаляет любые ограничения уникальности, могут существовать. При определении столбца или группы столбцов в качестве первичного ключа таблицы автоматически создается ограничение уникальности для заданного столбца или группы столбцов. Если удалить столбец из **PrimaryKey** свойство **DataTable**, **UniqueConstraint** удаляется.  
  
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
 [Определение схемы DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 [Наборы данных, таблицы данных и объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
