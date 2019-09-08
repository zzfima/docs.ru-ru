---
title: Ограничения таблиц данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 27c9f2fd-f64d-4b4e-bbf6-1d24f47067cb
ms.openlocfilehash: 3f3055b11f0e682ae5a9578289e30dc2716343fe
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785404"
---
# <a name="datatable-constraints"></a>Ограничения таблиц данных
Ограничения позволяют принудительно поддерживать целостность данных <xref:System.Data.DataTable>. Ограничение представляет собой автоматическое правило, применяемое к столбцу или связанным столбцам и определяющее порядок действий при каком-либо изменении содержимого строки. Ограничения применяются, если `System.Data.DataSet.EnforceConstraints` свойство <xref:System.Data.DataSet> объекта имеет **значение true**. Пример кода, показывающий, как установить свойство `EnforceConstraints`, см. в разделе справки <xref:System.Data.DataSet.EnforceConstraints%2A>.  
  
 В ADO.NET имеется два типа ограничений: <xref:System.Data.ForeignKeyConstraint> и <xref:System.Data.UniqueConstraint>. По умолчанию оба ограничения создаются автоматически при создании связи между двумя или более таблицами путем добавления <xref:System.Data.DataRelation> в **набор данных**. Однако это поведение можно отключить, указав **креатеконстраинтс** = **false** при создании связи.  
  
## <a name="foreignkeyconstraint"></a>Ограничение ForeignKeyConstraint  
 **ForeignKeyConstraint** применяет правила, связанные с распространением обновлений и удалений в связанных таблицах. Например, если значение в строке одной таблицы Обновлено или удалено и это же значение также используется в одной или нескольких связанных таблицах, **ForeignKeyConstraint** определяет, что происходит в связанных таблицах.  
  
 Свойства <xref:System.Data.ForeignKeyConstraint.DeleteRule%2A> и <xref:System.Data.ForeignKeyConstraint.UpdateRule%2A> объекта **ForeignKeyConstraint** определяют действие, которое должно быть предпринято, когда пользователь пытается удалить или обновить строку в связанной таблице. В следующей таблице описаны различные параметры, доступные для свойств **DeleteRule** и **UpdateRule** объекта **ForeignKeyConstraint**.  
  
|Установка правил|Описание|  
|------------------|-----------------|  
|**Cascade**|Удалить или обновить связанные строки.|  
|**SetNull**|Задайте **DBNull**значения в связанных строках.|  
|**сетдефаулт**|Присвоить столбцам в связанных строках значение по умолчанию.|  
|**None**|Не выполнять никаких действий в связанных строках. Это значение по умолчанию.|  
  
 **ForeignKeyConstraint** может ограничивать, а также распространять изменения в связанных столбцах. В зависимости от свойств, заданных для объекта **ForeignKeyConstraint** столбца, если свойство **енфорцеконстраинтс** **набора данных** имеет **значение true**, выполнение определенных операций в родительской строке приведет к исключению. Например, **Если свойство объекта** **ForeignKeyConstraint** имеет значение **None**, то родительская строка не может быть удалена, если она содержит дочерние строки.  
  
 Ограничение внешнего ключа можно создать между отдельными столбцами или между массивами столбцов с помощью конструктора **ForeignKeyConstraint** . Передайте полученный объект **ForeignKeyConstraint** методу **Add** свойства Table **rechecks** , который является **констраинтколлектион**. Можно также передать аргументы конструктора в несколько перегрузок метода **Add** объекта **констраинтколлектион** , чтобы создать объект **ForeignKeyConstraint**.  
  
 При создании **ForeignKeyConstraint**можно передать значения **DeleteRule** и **UpdateRule** в конструктор в качестве аргументов или задать их в качестве свойств, как показано в следующем примере (где значение **DeleteRule** равно  **Нет**).  
  
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
 Изменения в строках могут быть приняты с помощью метода **AcceptChanges** или отменены с помощью метода **RejectChanges** **набора данных**, **DataTable**или **DataRow**. Если **набор данных** содержит **фореигнкэйконстраинтс**, вызов методов **AcceptChanges** или **RejectChanges** применяет **акцептрежектруле**. Свойство **акцептрежектруле** объекта **ForeignKeyConstraint** определяет, какое действие будет выполнено с дочерними строками при вызове **метода AcceptChanges** или **RejectChanges** в родительской строке.  
  
 В следующей таблице перечислены доступные параметры для **акцептрежектруле**.  
  
|Установка правил|Описание|  
|------------------|-----------------|  
|**Cascade**|Принять или отклонить изменения в дочерних строках.|  
|**None**|Не выполнять никаких действий в дочерних строках. Это значение по умолчанию.|  
  
### <a name="example"></a>Пример  
 В следующем примере создается ограничение <xref:System.Data.ForeignKeyConstraint>, устанавливаются некоторые из его свойств, в том числе <xref:System.Data.ForeignKeyConstraint.AcceptRejectRule%2A>, а само ограничение добавляется в коллекцию <xref:System.Data.ConstraintCollection> объекта <xref:System.Data.DataTable>.  
  
 [!code-csharp[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/CS/source.cs#1)]
 [!code-vb[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/VB/source.vb#1)]  
  
## <a name="uniqueconstraint"></a>Ограничение UniqueConstraint  
 Объект **UniqueConstraint** , который может быть назначен одному столбцу или массиву столбцов в **DataTable**, гарантирует, что все данные в указанном столбце или столбцах уникальны для каждой строки. Можно создать ограничение уникальности для столбца или массива столбцов с помощью конструктора **UniqueConstraint** . Передайте полученный объект **UniqueConstraint** в метод **Add** свойства **ограничения** таблицы, которое является **констраинтколлектион**. Можно также передать аргументы конструктора в несколько перегрузок метода **Add** объекта **констраинтколлектион** , чтобы создать **UniqueConstraint**. При создании **UniqueConstraint** для столбца или столбцов можно дополнительно указать, является ли столбец или столбцы первичным ключом.  
  
 Можно также создать ограничение уникальности для столбца, задав свойству **UNIQUE** столбца **значение true**. Кроме того, если задать для свойства **UNIQUE** одного столбца значение **false** , то все ограничения уникальности, которые могут существовать, будут удалены. При определении столбца или группы столбцов в качестве первичного ключа таблицы автоматически создается ограничение уникальности для заданного столбца или группы столбцов. Если удалить столбец из свойства **PrimaryKey** объекта **DataTable**, **UniqueConstraint** будет удален.  
  
 В следующем примере создается **UniqueConstraint** для двух столбцов **таблицы DataTable**.  
  
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

- <xref:System.Data.DataRelation>
- <xref:System.Data.DataTable>
- <xref:System.Data.ForeignKeyConstraint>
- <xref:System.Data.UniqueConstraint>
- [Определение схемы DataTable](datatable-schema-definition.md)
- [Наборы данных, таблицы данных и объекты DataView](index.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
