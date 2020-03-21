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
# <a name="datatable-constraints"></a><span data-ttu-id="1450a-102">Ограничения таблиц данных</span><span class="sxs-lookup"><span data-stu-id="1450a-102">DataTable Constraints</span></span>
<span data-ttu-id="1450a-103">Ограничения позволяют принудительно поддерживать целостность данных <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="1450a-103">You can use constraints to enforce restrictions on the data in a <xref:System.Data.DataTable>, in order to maintain the integrity of the data.</span></span> <span data-ttu-id="1450a-104">Ограничение представляет собой автоматическое правило, применяемое к столбцу или связанным столбцам и определяющее порядок действий при каком-либо изменении содержимого строки.</span><span class="sxs-lookup"><span data-stu-id="1450a-104">A constraint is an automatic rule, applied to a column or related columns, that determines the course of action when the value of a row is somehow altered.</span></span> <span data-ttu-id="1450a-105">Ограничения применяются, `System.Data.DataSet.EnforceConstraints` когда свойство <xref:System.Data.DataSet> **истинен.**</span><span class="sxs-lookup"><span data-stu-id="1450a-105">Constraints are enforced when the `System.Data.DataSet.EnforceConstraints` property of the <xref:System.Data.DataSet> is **true**.</span></span> <span data-ttu-id="1450a-106">Пример кода, показывающий, как установить свойство `EnforceConstraints`, см. в разделе справки <xref:System.Data.DataSet.EnforceConstraints%2A>.</span><span class="sxs-lookup"><span data-stu-id="1450a-106">For a code example that shows how to set the `EnforceConstraints` property, see the <xref:System.Data.DataSet.EnforceConstraints%2A> reference topic.</span></span>  
  
 <span data-ttu-id="1450a-107">В ADO.NET имеется два типа ограничений: <xref:System.Data.ForeignKeyConstraint> и <xref:System.Data.UniqueConstraint>.</span><span class="sxs-lookup"><span data-stu-id="1450a-107">There are two kinds of constraints in ADO.NET: the <xref:System.Data.ForeignKeyConstraint> and the <xref:System.Data.UniqueConstraint>.</span></span> <span data-ttu-id="1450a-108">По умолчанию оба ограничения создаются автоматически при создании связи между <xref:System.Data.DataRelation> двумя или более таблицами путем добавления **в DataSet.**</span><span class="sxs-lookup"><span data-stu-id="1450a-108">By default, both constraints are created automatically when you create a relationship between two or more tables by adding a <xref:System.Data.DataRelation> to the **DataSet**.</span></span> <span data-ttu-id="1450a-109">Однако можно отключить это поведение, указав **ложные createConstraints** = **при** создании отношения.</span><span class="sxs-lookup"><span data-stu-id="1450a-109">However, you can disable this behavior by specifying **createConstraints** = **false** when creating the relation.</span></span>  
  
## <a name="foreignkeyconstraint"></a><span data-ttu-id="1450a-110">Ограничение ForeignKeyConstraint</span><span class="sxs-lookup"><span data-stu-id="1450a-110">ForeignKeyConstraint</span></span>  
 <span data-ttu-id="1450a-111">**ForeignKeyConstraint** применяет правила о том, как распространяются обновления и удаления в связанных таблицах.</span><span class="sxs-lookup"><span data-stu-id="1450a-111">A **ForeignKeyConstraint** enforces rules about how updates and deletes to related tables are propagated.</span></span> <span data-ttu-id="1450a-112">Например, если значение в строке одной таблицы обновляется или удаляется, и это же значение также используется в одной или нескольких связанных таблицах, **ForeignKeyConstraint** определяет, что происходит в связанных таблицах.</span><span class="sxs-lookup"><span data-stu-id="1450a-112">For example, if a value in a row of one table is updated or deleted, and that same value is also used in one or more related tables, a **ForeignKeyConstraint** determines what happens in the related tables.</span></span>  
  
 <span data-ttu-id="1450a-113"><xref:System.Data.ForeignKeyConstraint.UpdateRule%2A> Свойства <xref:System.Data.ForeignKeyConstraint.DeleteRule%2A> **Идентифицированный Ключ** определяют действие, необходимое для удаления или обновления строки в соответствующей таблице.</span><span class="sxs-lookup"><span data-stu-id="1450a-113">The <xref:System.Data.ForeignKeyConstraint.DeleteRule%2A> and <xref:System.Data.ForeignKeyConstraint.UpdateRule%2A> properties of the **ForeignKeyConstraint** define the action to be taken when the user attempts to delete or update a row in a related table.</span></span> <span data-ttu-id="1450a-114">В следующей таблице описаны различные параметры, доступные для свойств **DeleteRule** и **UpdateRule** of the **ForeignKeyConstraint.**</span><span class="sxs-lookup"><span data-stu-id="1450a-114">The following table describes the different settings available for the **DeleteRule** and **UpdateRule** properties of the **ForeignKeyConstraint**.</span></span>  
  
|<span data-ttu-id="1450a-115">Установка правил</span><span class="sxs-lookup"><span data-stu-id="1450a-115">Rule setting</span></span>|<span data-ttu-id="1450a-116">Описание</span><span class="sxs-lookup"><span data-stu-id="1450a-116">Description</span></span>|  
|------------------|-----------------|  
|<span data-ttu-id="1450a-117">**Каскад**</span><span class="sxs-lookup"><span data-stu-id="1450a-117">**Cascade**</span></span>|<span data-ttu-id="1450a-118">Удалить или обновить связанные строки.</span><span class="sxs-lookup"><span data-stu-id="1450a-118">Delete or update related rows.</span></span>|  
|<span data-ttu-id="1450a-119">**SetNull**</span><span class="sxs-lookup"><span data-stu-id="1450a-119">**SetNull**</span></span>|<span data-ttu-id="1450a-120">Установите значения в связанных строках на **DBNull.**</span><span class="sxs-lookup"><span data-stu-id="1450a-120">Set values in related rows to **DBNull**.</span></span>|  
|<span data-ttu-id="1450a-121">**SetDefault**</span><span class="sxs-lookup"><span data-stu-id="1450a-121">**SetDefault**</span></span>|<span data-ttu-id="1450a-122">Присвоить столбцам в связанных строках значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1450a-122">Set values in related rows to the default value.</span></span>|  
|<span data-ttu-id="1450a-123">**Нет**</span><span class="sxs-lookup"><span data-stu-id="1450a-123">**None**</span></span>|<span data-ttu-id="1450a-124">Не выполнять никаких действий в связанных строках.</span><span class="sxs-lookup"><span data-stu-id="1450a-124">Take no action on related rows.</span></span> <span data-ttu-id="1450a-125">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1450a-125">This is the default.</span></span>|  
  
 <span data-ttu-id="1450a-126">**ForeignKeyConstraint** может ограничивать, а также распространять сяочливую изменения в связанные столбцы.</span><span class="sxs-lookup"><span data-stu-id="1450a-126">A **ForeignKeyConstraint** can restrict, as well as propagate, changes to related columns.</span></span> <span data-ttu-id="1450a-127">В зависимости от свойств, установленных для **ForeignKeyConstraint** столбца, если свойство **EnforceConstraints** **DataSet** **верно,** выполнение определенных операций на родительской строке приведет к исключению.</span><span class="sxs-lookup"><span data-stu-id="1450a-127">Depending on the properties set for the **ForeignKeyConstraint** of a column, if the **EnforceConstraints** property of the **DataSet** is **true**, performing certain operations on the parent row will result in an exception.</span></span> <span data-ttu-id="1450a-128">Например, если свойство **DeleteRule** **Of The ForeignKeyConstraint** **не**состоит из того, что родительский ряд не может быть удален, если в нем есть строки для детей.</span><span class="sxs-lookup"><span data-stu-id="1450a-128">For example, if the **DeleteRule** property of the **ForeignKeyConstraint** is **None**, a parent row cannot be deleted if it has any child rows.</span></span>  
  
 <span data-ttu-id="1450a-129">Можно создать иностранное ограничение ключа между отдельными столбиками или между массивом столбцов с помощью конструктора **ForeignKeyConstraint.**</span><span class="sxs-lookup"><span data-stu-id="1450a-129">You can create a foreign key constraint between single columns or between an array of columns by using the **ForeignKeyConstraint** constructor.</span></span> <span data-ttu-id="1450a-130">Передайте полученный объект **ForeignKeyConstraint** **методу** добавления свойства **ограничений** таблицы, который является **constraintCollection.**</span><span class="sxs-lookup"><span data-stu-id="1450a-130">Pass the resulting **ForeignKeyConstraint** object to the **Add** method of the table's **Constraints** property, which is a **ConstraintCollection**.</span></span> <span data-ttu-id="1450a-131">Вы также можете передать аргументы конструктора нескольким перегрузам метода **Добавления** **ConstraintCollection** для создания **ForeignKeyConstraint.**</span><span class="sxs-lookup"><span data-stu-id="1450a-131">You can also pass constructor arguments to several overloads of the **Add** method of a **ConstraintCollection** to create a **ForeignKeyConstraint**.</span></span>  
  
 <span data-ttu-id="1450a-132">При создании **ForeignKeyConstraint**вы можете передать значения **DeleteRule** и **UpdateRule** конструктору в качестве аргументов или установить их в качестве свойств, как в следующем примере (где значение **DeleteRule** установлено **в None).**</span><span class="sxs-lookup"><span data-stu-id="1450a-132">When creating a **ForeignKeyConstraint**, you can pass the **DeleteRule** and **UpdateRule** values to the constructor as arguments, or you can set them as properties as in the following example (where the **DeleteRule** value is set to **None**).</span></span>  
  
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
  
### <a name="acceptrejectrule"></a><span data-ttu-id="1450a-133">Свойство AcceptRejectRule</span><span class="sxs-lookup"><span data-stu-id="1450a-133">AcceptRejectRule</span></span>  
 <span data-ttu-id="1450a-134">Изменения в строках могут быть приняты с помощью метода **AcceptChanges** или отменены с помощью метода **RejectChanges** **DataSet,** **DataTable**или **DataRow.**</span><span class="sxs-lookup"><span data-stu-id="1450a-134">Changes to rows can be accepted using the **AcceptChanges** method or canceled using the **RejectChanges** method of the **DataSet**, **DataTable**, or **DataRow**.</span></span> <span data-ttu-id="1450a-135">Когда **DataSet** содержит **ForeignKeyConstraints,** ссылаясь на методы **AcceptChanges** или **RejectChanges,** применяет **сядек AcceptRejectRule.**</span><span class="sxs-lookup"><span data-stu-id="1450a-135">When a **DataSet** contains **ForeignKeyConstraints**, invoking the **AcceptChanges** or **RejectChanges** methods enforces the **AcceptRejectRule**.</span></span> <span data-ttu-id="1450a-136">Свойство **AcceptRejectRule** of the **ForeignKeyConstraint** определяет, какие действия будут приняты в строках ребенка, когда **AcceptChanges** или **RejectChanges** вызывается на родительской строке.</span><span class="sxs-lookup"><span data-stu-id="1450a-136">The **AcceptRejectRule** property of the **ForeignKeyConstraint** determines which action will be taken on the child rows when **AcceptChanges** or **RejectChanges** is called on the parent row.</span></span>  
  
 <span data-ttu-id="1450a-137">В следующей таблице перечислены доступные настройки для **AcceptRejectRule**.</span><span class="sxs-lookup"><span data-stu-id="1450a-137">The following table lists the available settings for the **AcceptRejectRule**.</span></span>  
  
|<span data-ttu-id="1450a-138">Установка правил</span><span class="sxs-lookup"><span data-stu-id="1450a-138">Rule setting</span></span>|<span data-ttu-id="1450a-139">Описание</span><span class="sxs-lookup"><span data-stu-id="1450a-139">Description</span></span>|  
|------------------|-----------------|  
|<span data-ttu-id="1450a-140">**Каскад**</span><span class="sxs-lookup"><span data-stu-id="1450a-140">**Cascade**</span></span>|<span data-ttu-id="1450a-141">Принять или отклонить изменения в дочерних строках.</span><span class="sxs-lookup"><span data-stu-id="1450a-141">Accept or reject changes to child rows.</span></span>|  
|<span data-ttu-id="1450a-142">**Нет**</span><span class="sxs-lookup"><span data-stu-id="1450a-142">**None**</span></span>|<span data-ttu-id="1450a-143">Не выполнять никаких действий в дочерних строках.</span><span class="sxs-lookup"><span data-stu-id="1450a-143">Take no action on child rows.</span></span> <span data-ttu-id="1450a-144">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1450a-144">This is the default.</span></span>|  
  
### <a name="example"></a><span data-ttu-id="1450a-145">Пример</span><span class="sxs-lookup"><span data-stu-id="1450a-145">Example</span></span>  
 <span data-ttu-id="1450a-146">В следующем примере создается ограничение <xref:System.Data.ForeignKeyConstraint>, устанавливаются некоторые из его свойств, в том числе <xref:System.Data.ForeignKeyConstraint.AcceptRejectRule%2A>, а само ограничение добавляется в коллекцию <xref:System.Data.ConstraintCollection> объекта <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="1450a-146">The following example creates a <xref:System.Data.ForeignKeyConstraint>, sets several of its properties, including the <xref:System.Data.ForeignKeyConstraint.AcceptRejectRule%2A>, and adds it to the <xref:System.Data.ConstraintCollection> of a <xref:System.Data.DataTable> object.</span></span>  
  
 [!code-csharp[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/CS/source.cs#1)]
 [!code-vb[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/VB/source.vb#1)]  
  
## <a name="uniqueconstraint"></a><span data-ttu-id="1450a-147">Ограничение UniqueConstraint</span><span class="sxs-lookup"><span data-stu-id="1450a-147">UniqueConstraint</span></span>  
 <span data-ttu-id="1450a-148">Объект **UniqueConstraint,** который может быть назначен либо одному столбцу, либо массиву столбцов в **DataTable,** гарантирует, что все данные в указанном столбце или столбцах уникальны в строке.</span><span class="sxs-lookup"><span data-stu-id="1450a-148">The **UniqueConstraint** object, which can be assigned either to a single column or to an array of columns in a **DataTable**, ensures that all data in the specified column or columns is unique per row.</span></span> <span data-ttu-id="1450a-149">Можно создать уникальное ограничение для столбца или массива столбцов с помощью конструктора **UniqueConstraint.**</span><span class="sxs-lookup"><span data-stu-id="1450a-149">You can create a unique constraint for a column or array of columns by using the **UniqueConstraint** constructor.</span></span> <span data-ttu-id="1450a-150">Передайте полученный объект **UniqueConstraint** **методу** добавления свойства **ограничений** таблицы, который является **constraintCollection.**</span><span class="sxs-lookup"><span data-stu-id="1450a-150">Pass the resulting **UniqueConstraint** object to the **Add** method of the table's **Constraints** property, which is a **ConstraintCollection**.</span></span> <span data-ttu-id="1450a-151">Вы также можете передать аргументы конструктора нескольким перегрузам метода **Добавления** **ConstraintCollection** для создания **UniqueConstraint.**</span><span class="sxs-lookup"><span data-stu-id="1450a-151">You can also pass constructor arguments to several overloads of the **Add** method of a **ConstraintCollection** to create a **UniqueConstraint**.</span></span> <span data-ttu-id="1450a-152">При создании **UniqueConstraint** для столбцов или столбцов можно дополнительно указать, являются ли столбцы или столбцы основным ключом.</span><span class="sxs-lookup"><span data-stu-id="1450a-152">When creating a **UniqueConstraint** for a column or columns, you can optionally specify whether the column or columns are a primary key.</span></span>  
  
 <span data-ttu-id="1450a-153">Вы также можете создать уникальное ограничение для столбца, установив **уникальное** свойство столбца на **истину.**</span><span class="sxs-lookup"><span data-stu-id="1450a-153">You can also create a unique constraint for a column by setting the **Unique** property of the column to **true**.</span></span> <span data-ttu-id="1450a-154">Кроме того, установка **уникального** свойства одного столбца на **ложное** удаляет любые уникальные ограничения, которые могут существовать.</span><span class="sxs-lookup"><span data-stu-id="1450a-154">Alternatively, setting the **Unique** property of a single column to **false** removes any unique constraint that may exist.</span></span> <span data-ttu-id="1450a-155">При определении столбца или группы столбцов в качестве первичного ключа таблицы автоматически создается ограничение уникальности для заданного столбца или группы столбцов.</span><span class="sxs-lookup"><span data-stu-id="1450a-155">Defining a column or columns as the primary key for a table will automatically create a unique constraint for the specified column or columns.</span></span> <span data-ttu-id="1450a-156">При удалении столбца из свойства **PrimaryKey** **DataTable**удаляется **UniqueConstraint.**</span><span class="sxs-lookup"><span data-stu-id="1450a-156">If you remove a column from the **PrimaryKey** property of a **DataTable**, the **UniqueConstraint** is removed.</span></span>  
  
 <span data-ttu-id="1450a-157">Следующий пример создает **UniqueConstraint** для двух столбцов **DataTable.**</span><span class="sxs-lookup"><span data-stu-id="1450a-157">The following example creates a **UniqueConstraint** for two columns of a **DataTable**.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1450a-158">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1450a-158">See also</span></span>

- <xref:System.Data.DataRelation>
- <xref:System.Data.DataTable>
- <xref:System.Data.ForeignKeyConstraint>
- <xref:System.Data.UniqueConstraint>
- [<span data-ttu-id="1450a-159">Определение схемы таблицы данных</span><span class="sxs-lookup"><span data-stu-id="1450a-159">DataTable Schema Definition</span></span>](datatable-schema-definition.md)
- [<span data-ttu-id="1450a-160">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="1450a-160">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="1450a-161">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1450a-161">ADO.NET Overview</span></span>](../ado-net-overview.md)
