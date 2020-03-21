---
title: Ограничения таблиц данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 27c9f2fd-f64d-4b4e-bbf6-1d24f47067cb
ms.openlocfilehash: 4b7972c281786a4e36d0e9c1e455776a293423ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151290"
---
# <a name="datatable-constraints"></a>Ограничения таблиц данных
Ограничения позволяют принудительно поддерживать целостность данных <xref:System.Data.DataTable>. Ограничение представляет собой автоматическое правило, применяемое к столбцу или связанным столбцам и определяющее порядок действий при каком-либо изменении содержимого строки. Ограничения применяются, `System.Data.DataSet.EnforceConstraints` когда свойство <xref:System.Data.DataSet> **истинен.** Пример кода, показывающий, как установить свойство `EnforceConstraints`, см. в разделе справки <xref:System.Data.DataSet.EnforceConstraints%2A>.  
  
 В ADO.NET имеется два типа ограничений: <xref:System.Data.ForeignKeyConstraint> и <xref:System.Data.UniqueConstraint>. По умолчанию оба ограничения создаются автоматически при создании связи между <xref:System.Data.DataRelation> двумя или более таблицами путем добавления **в DataSet.** Однако можно отключить это поведение, указав **ложные createConstraints** = **при** создании отношения.  
  
## <a name="foreignkeyconstraint"></a>Ограничение ForeignKeyConstraint  
 **ForeignKeyConstraint** применяет правила о том, как распространяются обновления и удаления в связанных таблицах. Например, если значение в строке одной таблицы обновляется или удаляется, и это же значение также используется в одной или нескольких связанных таблицах, **ForeignKeyConstraint** определяет, что происходит в связанных таблицах.  
  
 <xref:System.Data.ForeignKeyConstraint.UpdateRule%2A> Свойства <xref:System.Data.ForeignKeyConstraint.DeleteRule%2A> **Идентифицированный Ключ** определяют действие, необходимое для удаления или обновления строки в соответствующей таблице. В следующей таблице описаны различные параметры, доступные для свойств **DeleteRule** и **UpdateRule** of the **ForeignKeyConstraint.**  
  
|Установка правил|Описание|  
|------------------|-----------------|  
|**Каскад**|Удалить или обновить связанные строки.|  
|**SetNull**|Установите значения в связанных строках на **DBNull.**|  
|**SetDefault**|Присвоить столбцам в связанных строках значение по умолчанию.|  
|**Нет**|Не выполнять никаких действий в связанных строках. Это значение по умолчанию.|  
  
 **ForeignKeyConstraint** может ограничивать, а также распространять сяочливую изменения в связанные столбцы. В зависимости от свойств, установленных для **ForeignKeyConstraint** столбца, если свойство **EnforceConstraints** **DataSet** **верно,** выполнение определенных операций на родительской строке приведет к исключению. Например, если свойство **DeleteRule** **Of The ForeignKeyConstraint** **не**состоит из того, что родительский ряд не может быть удален, если в нем есть строки для детей.  
  
 Можно создать иностранное ограничение ключа между отдельными столбиками или между массивом столбцов с помощью конструктора **ForeignKeyConstraint.** Передайте полученный объект **ForeignKeyConstraint** **методу** добавления свойства **ограничений** таблицы, который является **constraintCollection.** Вы также можете передать аргументы конструктора нескольким перегрузам метода **Добавления** **ConstraintCollection** для создания **ForeignKeyConstraint.**  
  
 При создании **ForeignKeyConstraint**вы можете передать значения **DeleteRule** и **UpdateRule** конструктору в качестве аргументов или установить их в качестве свойств, как в следующем примере (где значение **DeleteRule** установлено **в None).**  
  
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
 Изменения в строках могут быть приняты с помощью метода **AcceptChanges** или отменены с помощью метода **RejectChanges** **DataSet,** **DataTable**или **DataRow.** Когда **DataSet** содержит **ForeignKeyConstraints,** ссылаясь на методы **AcceptChanges** или **RejectChanges,** применяет **сядек AcceptRejectRule.** Свойство **AcceptRejectRule** of the **ForeignKeyConstraint** определяет, какие действия будут приняты в строках ребенка, когда **AcceptChanges** или **RejectChanges** вызывается на родительской строке.  
  
 В следующей таблице перечислены доступные настройки для **AcceptRejectRule**.  
  
|Установка правил|Описание|  
|------------------|-----------------|  
|**Каскад**|Принять или отклонить изменения в дочерних строках.|  
|**Нет**|Не выполнять никаких действий в дочерних строках. Это значение по умолчанию.|  
  
### <a name="example"></a>Пример  
 В следующем примере создается ограничение <xref:System.Data.ForeignKeyConstraint>, устанавливаются некоторые из его свойств, в том числе <xref:System.Data.ForeignKeyConstraint.AcceptRejectRule%2A>, а само ограничение добавляется в коллекцию <xref:System.Data.ConstraintCollection> объекта <xref:System.Data.DataTable>.  
  
 [!code-csharp[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/CS/source.cs#1)]
 [!code-vb[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/VB/source.vb#1)]  
  
## <a name="uniqueconstraint"></a>Ограничение UniqueConstraint  
 Объект **UniqueConstraint,** который может быть назначен либо одному столбцу, либо массиву столбцов в **DataTable,** гарантирует, что все данные в указанном столбце или столбцах уникальны в строке. Можно создать уникальное ограничение для столбца или массива столбцов с помощью конструктора **UniqueConstraint.** Передайте полученный объект **UniqueConstraint** **методу** добавления свойства **ограничений** таблицы, который является **constraintCollection.** Вы также можете передать аргументы конструктора нескольким перегрузам метода **Добавления** **ConstraintCollection** для создания **UniqueConstraint.** При создании **UniqueConstraint** для столбцов или столбцов можно дополнительно указать, являются ли столбцы или столбцы основным ключом.  
  
 Вы также можете создать уникальное ограничение для столбца, установив **уникальное** свойство столбца на **истину.** Кроме того, установка **уникального** свойства одного столбца на **ложное** удаляет любые уникальные ограничения, которые могут существовать. При определении столбца или группы столбцов в качестве первичного ключа таблицы автоматически создается ограничение уникальности для заданного столбца или группы столбцов. При удалении столбца из свойства **PrimaryKey** **DataTable**удаляется **UniqueConstraint.**  
  
 Следующий пример создает **UniqueConstraint** для двух столбцов **DataTable.**  
  
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
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Data.DataRelation>
- <xref:System.Data.DataTable>
- <xref:System.Data.ForeignKeyConstraint>
- <xref:System.Data.UniqueConstraint>
- [Определение схемы таблицы данных](datatable-schema-definition.md)
- [Наборы данных, таблицы данных и объекты DataView](index.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
