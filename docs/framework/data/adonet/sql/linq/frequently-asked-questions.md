---
title: Вопросы и ответы
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 252ed666-0679-4eea-b71b-2f14117ef443
ms.openlocfilehash: 3cc879e97438138554f1d39cf588e01bfbba28a6
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634707"
---
# <a name="frequently-asked-questions"></a><span data-ttu-id="b6a47-102">Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="b6a47-102">Frequently Asked Questions</span></span>

<span data-ttu-id="b6a47-103">В следующих разделах содержатся ответы на некоторые распространенные проблемы, которые могут возникнуть при реализации LINQ.</span><span class="sxs-lookup"><span data-stu-id="b6a47-103">The following sections answer some common issues that you might encounter when you implement LINQ.</span></span>

<span data-ttu-id="b6a47-104">Дополнительные проблемы описаны в [статье Устранение неполадок](troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="b6a47-104">Additional issues are addressed in [Troubleshooting](troubleshooting.md).</span></span>

## <a name="cannot-connect"></a><span data-ttu-id="b6a47-105">Не удается подключиться</span><span class="sxs-lookup"><span data-stu-id="b6a47-105">Cannot Connect</span></span>

<span data-ttu-id="b6a47-106">Вопрос.</span><span class="sxs-lookup"><span data-stu-id="b6a47-106">Q.</span></span> <span data-ttu-id="b6a47-107">Не удается соединиться с базой данных.</span><span class="sxs-lookup"><span data-stu-id="b6a47-107">I cannot connect to my database.</span></span>

<span data-ttu-id="b6a47-108">А.</span><span class="sxs-lookup"><span data-stu-id="b6a47-108">A.</span></span> <span data-ttu-id="b6a47-109">Убедитесь в правильности строки подключения и в том, что экземпляр SQL Server работает.</span><span class="sxs-lookup"><span data-stu-id="b6a47-109">Make sure your connection string is correct and that your SQL Server instance is running.</span></span> <span data-ttu-id="b6a47-110">Обратите внимание, что для [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] требуется включенный протокол именованных каналов.</span><span class="sxs-lookup"><span data-stu-id="b6a47-110">Note also that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] requires the Named Pipes protocol to be enabled.</span></span> <span data-ttu-id="b6a47-111">Дополнительные сведения см. [в разделе обучение по пошаговым руководствам](learning-by-walkthroughs.md).</span><span class="sxs-lookup"><span data-stu-id="b6a47-111">For more information, see [Learning by Walkthroughs](learning-by-walkthroughs.md).</span></span>

## <a name="changes-to-database-lost"></a><span data-ttu-id="b6a47-112">Потеряны изменения, внесенные в базу данных</span><span class="sxs-lookup"><span data-stu-id="b6a47-112">Changes to Database Lost</span></span>

<span data-ttu-id="b6a47-113">Вопрос.</span><span class="sxs-lookup"><span data-stu-id="b6a47-113">Q.</span></span> <span data-ttu-id="b6a47-114">В базу данных были внесены изменения, однако при повторном запуске приложения их там не оказалось.</span><span class="sxs-lookup"><span data-stu-id="b6a47-114">I made a change to data in the database, but when I reran my application, the change was no longer there.</span></span>

<span data-ttu-id="b6a47-115">А.</span><span class="sxs-lookup"><span data-stu-id="b6a47-115">A.</span></span> <span data-ttu-id="b6a47-116">Проверьте, что для сохранения результатов в базе данных был вызван метод <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span><span class="sxs-lookup"><span data-stu-id="b6a47-116">Make sure that you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> to save results to the database.</span></span>

## <a name="database-connection-open-how-long"></a><span data-ttu-id="b6a47-117">Как долго сохраняется открытым соединение с базой данных?</span><span class="sxs-lookup"><span data-stu-id="b6a47-117">Database Connection: Open How Long?</span></span>

<span data-ttu-id="b6a47-118">Вопрос.</span><span class="sxs-lookup"><span data-stu-id="b6a47-118">Q.</span></span> <span data-ttu-id="b6a47-119">Как долго соединение с базой данных будет оставаться открытым?</span><span class="sxs-lookup"><span data-stu-id="b6a47-119">How long does my database connection remain open?</span></span>

<span data-ttu-id="b6a47-120">А.</span><span class="sxs-lookup"><span data-stu-id="b6a47-120">A.</span></span> <span data-ttu-id="b6a47-121">Как правило, подключение остается открытым до тех пор, пока не будут использованы результаты запроса.</span><span class="sxs-lookup"><span data-stu-id="b6a47-121">A connection typically remains open until you consume the query results.</span></span> <span data-ttu-id="b6a47-122">Если планируется выделить время для обработки и кэширования всех результатов, к запросу следует применить <xref:System.Linq.Enumerable.ToList%2A>.</span><span class="sxs-lookup"><span data-stu-id="b6a47-122">If you expect to take time to process all the results and are not opposed to caching the results, apply <xref:System.Linq.Enumerable.ToList%2A> to the query.</span></span> <span data-ttu-id="b6a47-123">В типичных сценариях, где каждый объект обрабатывается только один раз, потоковая модель является предпочтительной в `DataReader` и [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6a47-123">In common scenarios where each object is processed only one time, the streaming model is superior in both `DataReader` and [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>

<span data-ttu-id="b6a47-124">Точные сведения об использовании подключения зависят от следующих моментов.</span><span class="sxs-lookup"><span data-stu-id="b6a47-124">The exact details of connection usage depend on the following:</span></span>

- <span data-ttu-id="b6a47-125">Состояние подключения, если <xref:System.Data.Linq.DataContext> создан с помощью объекта подключения.</span><span class="sxs-lookup"><span data-stu-id="b6a47-125">Connection status if the <xref:System.Data.Linq.DataContext> is constructed with a connection object.</span></span>

- <span data-ttu-id="b6a47-126">Параметры строки подключения (например, включение режима MARS).</span><span class="sxs-lookup"><span data-stu-id="b6a47-126">Connection string settings (for example, enabling Multiple Active Result Sets (MARS).</span></span> <span data-ttu-id="b6a47-127">Дополнительные сведения см. в разделе [Несколько активных результирующих наборов (MARS)](../multiple-active-result-sets-mars.md).</span><span class="sxs-lookup"><span data-stu-id="b6a47-127">For more information, see [Multiple Active Result Sets (MARS)](../multiple-active-result-sets-mars.md).</span></span>

## <a name="updating-without-querying"></a><span data-ttu-id="b6a47-128">Обновление без выполнения запросов</span><span class="sxs-lookup"><span data-stu-id="b6a47-128">Updating Without Querying</span></span>

<span data-ttu-id="b6a47-129">Вопрос.</span><span class="sxs-lookup"><span data-stu-id="b6a47-129">Q.</span></span> <span data-ttu-id="b6a47-130">Можно ли обновить данные таблицы, не отправляя запрос в базу данных?</span><span class="sxs-lookup"><span data-stu-id="b6a47-130">Can I update table data without first querying the database?</span></span>

<span data-ttu-id="b6a47-131">А.</span><span class="sxs-lookup"><span data-stu-id="b6a47-131">A.</span></span> <span data-ttu-id="b6a47-132">Хотя в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] отсутствуют команды обновления на основе наборов, для обновления без выполнения запроса можно воспользоваться любым из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="b6a47-132">Although [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] does not have set-based update commands, you can use either of the following techniques to update without first querying:</span></span>

- <span data-ttu-id="b6a47-133">Чтобы отправить код SQL, используйте <xref:System.Data.Linq.DataContext.ExecuteCommand%2A>.</span><span class="sxs-lookup"><span data-stu-id="b6a47-133">Use <xref:System.Data.Linq.DataContext.ExecuteCommand%2A> to send SQL code.</span></span>

- <span data-ttu-id="b6a47-134">Создайте новый экземпляр объекта и инициализируйте все текущие значения (поля), влияющие на обновление.</span><span class="sxs-lookup"><span data-stu-id="b6a47-134">Create a new instance of the object and initialize all the current values (fields) that affect the update.</span></span> <span data-ttu-id="b6a47-135">Затем прикрепите объект к <xref:System.Data.Linq.DataContext> с помощью <xref:System.Data.Linq.Table%601.Attach%2A> и отредактируйте поле, которое нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="b6a47-135">Then attach the object to the <xref:System.Data.Linq.DataContext> by using <xref:System.Data.Linq.Table%601.Attach%2A> and modify the field you want to change.</span></span>

## <a name="unexpected-query-results"></a><span data-ttu-id="b6a47-136">Неожиданные результаты запроса</span><span class="sxs-lookup"><span data-stu-id="b6a47-136">Unexpected Query Results</span></span>

<span data-ttu-id="b6a47-137">Вопрос.</span><span class="sxs-lookup"><span data-stu-id="b6a47-137">Q.</span></span> <span data-ttu-id="b6a47-138">Запрос возвращает непредвиденные результаты.</span><span class="sxs-lookup"><span data-stu-id="b6a47-138">My query is returning unexpected results.</span></span> <span data-ttu-id="b6a47-139">Как узнать, что случилось?</span><span class="sxs-lookup"><span data-stu-id="b6a47-139">How can I inspect what is occurring?</span></span>

<span data-ttu-id="b6a47-140">А.</span><span class="sxs-lookup"><span data-stu-id="b6a47-140">A.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="b6a47-141">предусматривает несколько средств для проверки создаваемого кода SQL.</span><span class="sxs-lookup"><span data-stu-id="b6a47-141">provides several tools for inspecting the SQL code it generates.</span></span> <span data-ttu-id="b6a47-142">Одним из наиболее важных <xref:System.Data.Linq.DataContext.Log%2A>.</span><span class="sxs-lookup"><span data-stu-id="b6a47-142">One of the most important is <xref:System.Data.Linq.DataContext.Log%2A>.</span></span> <span data-ttu-id="b6a47-143">Дополнительные сведения см. в разделе [Поддержка отладки](debugging-support.md).</span><span class="sxs-lookup"><span data-stu-id="b6a47-143">For more information, see [Debugging Support](debugging-support.md).</span></span>

## <a name="unexpected-stored-procedure-results"></a><span data-ttu-id="b6a47-144">Неожиданные результаты хранимой процедуры</span><span class="sxs-lookup"><span data-stu-id="b6a47-144">Unexpected Stored Procedure Results</span></span>

<span data-ttu-id="b6a47-145">Вопрос.</span><span class="sxs-lookup"><span data-stu-id="b6a47-145">Q.</span></span> <span data-ttu-id="b6a47-146">Имеется хранимая процедура, возвращаемое значение которой вычислено с помощью функции `MAX()`.</span><span class="sxs-lookup"><span data-stu-id="b6a47-146">I have a stored procedure whose return value is calculated by `MAX()`.</span></span> <span data-ttu-id="b6a47-147">При перетаскивании хранимой процедуры в область конструктора O/R возвращаемое значение неверно.</span><span class="sxs-lookup"><span data-stu-id="b6a47-147">When I drag the stored procedure to the O/R Designer surface, the return value is not correct.</span></span>

<span data-ttu-id="b6a47-148">А.</span><span class="sxs-lookup"><span data-stu-id="b6a47-148">A.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="b6a47-149">обеспечивает два способа возврата значений, сформированных в базе данных, с помощью хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="b6a47-149">provides two ways to return database-generated values by way of stored procedures:</span></span>

- <span data-ttu-id="b6a47-150">Путем именования выходного результата.</span><span class="sxs-lookup"><span data-stu-id="b6a47-150">By naming the output result.</span></span>

- <span data-ttu-id="b6a47-151">Путем явного указания выходного параметра.</span><span class="sxs-lookup"><span data-stu-id="b6a47-151">By explicitly specifying an output parameter.</span></span>

<span data-ttu-id="b6a47-152">Ниже представлен пример неверных выходных данных.</span><span class="sxs-lookup"><span data-stu-id="b6a47-152">The following is an example of incorrect output.</span></span> <span data-ttu-id="b6a47-153">Поскольку [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] не может сопоставить результаты, он всегда возвращает 0.</span><span class="sxs-lookup"><span data-stu-id="b6a47-153">Because [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] cannot map the results, it always returns 0:</span></span>

```sql
create procedure proc2

as

begin

select max(i) from t where name like 'hello'

end
```

<span data-ttu-id="b6a47-154">Ниже представлен пример правильных выходных данных с использованием выходного параметра.</span><span class="sxs-lookup"><span data-stu-id="b6a47-154">The following is an example of correct output by using an output parameter:</span></span>

```sql
create procedure proc2

@result int OUTPUT

as

select @result = MAX(i) from t where name like 'hello'

go
```

<span data-ttu-id="b6a47-155">Ниже представлен пример правильных выходных данных с именованием выходного результата.</span><span class="sxs-lookup"><span data-stu-id="b6a47-155">The following is an example of correct output by naming the output result:</span></span>

```sql
create procedure proc2

as

begin

select nax(i) AS MaxResult from t where name like 'hello'

end
```

<span data-ttu-id="b6a47-156">Дополнительные сведения см. в разделе [Настройка операций с помощью хранимых процедур](customizing-operations-by-using-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="b6a47-156">For more information, see [Customizing Operations By Using Stored Procedures](customizing-operations-by-using-stored-procedures.md).</span></span>

## <a name="serialization-errors"></a><span data-ttu-id="b6a47-157">Ошибки сериализации</span><span class="sxs-lookup"><span data-stu-id="b6a47-157">Serialization Errors</span></span>

<span data-ttu-id="b6a47-158">Вопрос.</span><span class="sxs-lookup"><span data-stu-id="b6a47-158">Q.</span></span> <span data-ttu-id="b6a47-159">При попытке сериализации возникает следующая ошибка: "тип" System. Data. LINQ. ChangeTracker + Стандардчанжетраккер "... не помечен как сериализуемый.</span><span class="sxs-lookup"><span data-stu-id="b6a47-159">When I try to serialize, I get the following error: "Type 'System.Data.Linq.ChangeTracker+StandardChangeTracker' ... is not marked as serializable."</span></span>

<span data-ttu-id="b6a47-160">А.</span><span class="sxs-lookup"><span data-stu-id="b6a47-160">A.</span></span> <span data-ttu-id="b6a47-161">Формирование кода в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] поддерживает сериализацию <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="b6a47-161">Code generation in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] supports <xref:System.Runtime.Serialization.DataContractSerializer> serialization.</span></span> <span data-ttu-id="b6a47-162">Оно не поддерживает <xref:System.Xml.Serialization.XmlSerializer> или <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>.</span><span class="sxs-lookup"><span data-stu-id="b6a47-162">It does not support <xref:System.Xml.Serialization.XmlSerializer> or <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>.</span></span> <span data-ttu-id="b6a47-163">Дополнительные сведения см. в разделе [Сериализация](serialization.md).</span><span class="sxs-lookup"><span data-stu-id="b6a47-163">For more information, see [Serialization](serialization.md).</span></span>

## <a name="multiple-dbml-files"></a><span data-ttu-id="b6a47-164">Несколько DBML-файлов</span><span class="sxs-lookup"><span data-stu-id="b6a47-164">Multiple DBML Files</span></span>

<span data-ttu-id="b6a47-165">Вопрос.</span><span class="sxs-lookup"><span data-stu-id="b6a47-165">Q.</span></span> <span data-ttu-id="b6a47-166">При работе с несколькими DBML-файлами, использующими общие таблицы, возникает ошибка компилятора.</span><span class="sxs-lookup"><span data-stu-id="b6a47-166">When I have multiple DBML files that share some tables in common, I get a compiler error.</span></span>

<span data-ttu-id="b6a47-167">А.</span><span class="sxs-lookup"><span data-stu-id="b6a47-167">A.</span></span> <span data-ttu-id="b6a47-168">Задайте для свойств **пространства имен контекста** и **пространства имен сущности** реляционный конструктор объектов различные значения для каждого DBML-файла.</span><span class="sxs-lookup"><span data-stu-id="b6a47-168">Set the **Context Namespace** and **Entity Namespace** properties from the Object Relational Designer to a distinct value for each DBML file.</span></span> <span data-ttu-id="b6a47-169">Это способ исключает конфликты имен/пространств имен.</span><span class="sxs-lookup"><span data-stu-id="b6a47-169">This approach eliminates the name/namespace collision.</span></span>

## <a name="avoiding-explicit-setting-of-database-generated-values-on-insert-or-update"></a><span data-ttu-id="b6a47-170">Предупреждение явного задания значений, созданных базой данных, в Insert или Update</span><span class="sxs-lookup"><span data-stu-id="b6a47-170">Avoiding Explicit Setting of Database-Generated Values on Insert or Update</span></span>

<span data-ttu-id="b6a47-171">Вопрос.</span><span class="sxs-lookup"><span data-stu-id="b6a47-171">Q.</span></span> <span data-ttu-id="b6a47-172">В базе данных имеется таблица со столбцом `DateCreated`, в качестве значения по умолчанию которой указана функция SQL `Getdate()`.</span><span class="sxs-lookup"><span data-stu-id="b6a47-172">I have a database table with a `DateCreated` column that defaults to SQL `Getdate()`.</span></span> <span data-ttu-id="b6a47-173">При попытке вставить новую запись с помощью [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] возвращается значение `NULL`.</span><span class="sxs-lookup"><span data-stu-id="b6a47-173">When I try to insert a new record by using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the value gets set to `NULL`.</span></span> <span data-ttu-id="b6a47-174">Хотя ожидается заданное по умолчанию значение базы данных.</span><span class="sxs-lookup"><span data-stu-id="b6a47-174">I would expect it to be set to the database default.</span></span>

<span data-ttu-id="b6a47-175">А.</span><span class="sxs-lookup"><span data-stu-id="b6a47-175">A.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="b6a47-176">автоматически обрабатывает данную ситуацию для столбцов identity (автоувеличение), rowguidcol (формируемые базой данных идентификаторы GUID) и timestamp.</span><span class="sxs-lookup"><span data-stu-id="b6a47-176">handles this situation automatically for identity (auto-increment) and rowguidcol (database-generated GUID) and timestamp columns.</span></span> <span data-ttu-id="b6a47-177">В других случаях следует вручную задать <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>=`true` и <xref:System.Data.Linq.Mapping.ColumnAttribute.AutoSync%2A>=<xref:System.Data.Linq.Mapping.AutoSync.Always>/<xref:System.Data.Linq.Mapping.AutoSync.OnInsert>/<xref:System.Data.Linq.Mapping.AutoSync.OnUpdate> свойства.</span><span class="sxs-lookup"><span data-stu-id="b6a47-177">In other cases, you should manually set <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>=`true` and <xref:System.Data.Linq.Mapping.ColumnAttribute.AutoSync%2A>=<xref:System.Data.Linq.Mapping.AutoSync.Always>/<xref:System.Data.Linq.Mapping.AutoSync.OnInsert>/<xref:System.Data.Linq.Mapping.AutoSync.OnUpdate> properties.</span></span>

## <a name="multiple-dataloadoptions"></a><span data-ttu-id="b6a47-178">Несколько параметров DataLoadOptions</span><span class="sxs-lookup"><span data-stu-id="b6a47-178">Multiple DataLoadOptions</span></span>

<span data-ttu-id="b6a47-179">Вопрос.</span><span class="sxs-lookup"><span data-stu-id="b6a47-179">Q.</span></span> <span data-ttu-id="b6a47-180">Можно ли задать дополнительные параметры загрузки, не переопределяя исходные?</span><span class="sxs-lookup"><span data-stu-id="b6a47-180">Can I specify additional load options without overwriting the first?</span></span>

<span data-ttu-id="b6a47-181">А.</span><span class="sxs-lookup"><span data-stu-id="b6a47-181">A.</span></span> <span data-ttu-id="b6a47-182">Да,</span><span class="sxs-lookup"><span data-stu-id="b6a47-182">Yes.</span></span> <span data-ttu-id="b6a47-183">Исходные параметры не переопределяются, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="b6a47-183">The first is not overwritten, as in the following example:</span></span>

```vb
Dim dlo As New DataLoadOptions()
dlo.LoadWith(Of Order)(Function(o As Order) o.Customer)
dlo.LoadWith(Of Order)(Function(o As Order) o.OrderDetails)
```

```csharp
DataLoadOptions dlo = new DataLoadOptions();
dlo.LoadWith<Order>(o => o.Customer);
dlo.LoadWith<Order>(o => o.OrderDetails);
```

## <a name="errors-using-sql-compact-35"></a><span data-ttu-id="b6a47-184">Ошибки при использовании SQL Compact 3.5</span><span class="sxs-lookup"><span data-stu-id="b6a47-184">Errors Using SQL Compact 3.5</span></span>

<span data-ttu-id="b6a47-185">Вопрос.</span><span class="sxs-lookup"><span data-stu-id="b6a47-185">Q.</span></span> <span data-ttu-id="b6a47-186">При перетаскивании таблиц из базы данных SQL Server Compact 3,5 возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="b6a47-186">I get an error when I drag tables out of a SQL Server Compact 3.5 database.</span></span>

<span data-ttu-id="b6a47-187">А.</span><span class="sxs-lookup"><span data-stu-id="b6a47-187">A.</span></span> <span data-ttu-id="b6a47-188">Реляционный конструктор объектов не поддерживает SQL Server Compact 3,5, хотя среда выполнения [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] делает.</span><span class="sxs-lookup"><span data-stu-id="b6a47-188">The Object Relational Designer does not support SQL Server Compact 3.5, although the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] runtime does.</span></span> <span data-ttu-id="b6a47-189">В этом случае необходимо создать собственные классы сущностей и добавить соответствующие атрибуты.</span><span class="sxs-lookup"><span data-stu-id="b6a47-189">In this situation, you must create your own entity classes and add the appropriate attributes.</span></span>

## <a name="errors-in-inheritance-relationships"></a><span data-ttu-id="b6a47-190">Ошибки в связях наследования</span><span class="sxs-lookup"><span data-stu-id="b6a47-190">Errors in Inheritance Relationships</span></span>

<span data-ttu-id="b6a47-191">Вопрос.</span><span class="sxs-lookup"><span data-stu-id="b6a47-191">Q.</span></span> <span data-ttu-id="b6a47-192">Я использовал фигуру наследования панели элементов в реляционный конструктор объектов для соединения двух сущностей, но выдает ошибки.</span><span class="sxs-lookup"><span data-stu-id="b6a47-192">I used the toolbox inheritance shape in the Object Relational Designer to connect two entities, but I get errors.</span></span>

<span data-ttu-id="b6a47-193">А.</span><span class="sxs-lookup"><span data-stu-id="b6a47-193">A.</span></span> <span data-ttu-id="b6a47-194">Простого создания связи недостаточно.</span><span class="sxs-lookup"><span data-stu-id="b6a47-194">Creating the relationship is not enough.</span></span> <span data-ttu-id="b6a47-195">Необходимо предоставить сведения, такие как столбец дискриминатора, значение дискриминатора базового класса и значение дискриминатора производного класса.</span><span class="sxs-lookup"><span data-stu-id="b6a47-195">You must provide information such as the discriminator column, base class discriminator value, and derived class discriminator value.</span></span>

## <a name="provider-model"></a><span data-ttu-id="b6a47-196">Модель поставщика</span><span class="sxs-lookup"><span data-stu-id="b6a47-196">Provider Model</span></span>

<span data-ttu-id="b6a47-197">Вопрос.</span><span class="sxs-lookup"><span data-stu-id="b6a47-197">Q.</span></span> <span data-ttu-id="b6a47-198">Доступна ли модель общего поставщика?</span><span class="sxs-lookup"><span data-stu-id="b6a47-198">Is a public provider model available?</span></span>

<span data-ttu-id="b6a47-199">А.</span><span class="sxs-lookup"><span data-stu-id="b6a47-199">A.</span></span> <span data-ttu-id="b6a47-200">Такая модель отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b6a47-200">No public provider model is available.</span></span> <span data-ttu-id="b6a47-201">В настоящее время [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] поддерживает только SQL Server и SQL Server Compact 3,5.</span><span class="sxs-lookup"><span data-stu-id="b6a47-201">At this time, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] supports SQL Server and SQL Server Compact 3.5 only.</span></span>

## <a name="sql-injection-attacks"></a><span data-ttu-id="b6a47-202">Атаки путем внедрения кода SQL</span><span class="sxs-lookup"><span data-stu-id="b6a47-202">SQL-Injection Attacks</span></span>

<span data-ttu-id="b6a47-203">Вопрос.</span><span class="sxs-lookup"><span data-stu-id="b6a47-203">Q.</span></span> <span data-ttu-id="b6a47-204">Каким образом [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] защищен от атак путем внедрения кода SQL?</span><span class="sxs-lookup"><span data-stu-id="b6a47-204">How is [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] protected from SQL-injection attacks?</span></span>

<span data-ttu-id="b6a47-205">А.</span><span class="sxs-lookup"><span data-stu-id="b6a47-205">A.</span></span> <span data-ttu-id="b6a47-206">Внедрение SQL-кода представляло серьезную угрозу для традиционных SQL-запросов, создаваемых путем объединения данных, вводимых пользователем.</span><span class="sxs-lookup"><span data-stu-id="b6a47-206">SQL injection has been a significant risk for traditional SQL queries formed by concatenating user input.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="b6a47-207">предотвращает подобное внедрение за счет использования в запросах объектов <xref:System.Data.SqlClient.SqlParameter>.</span><span class="sxs-lookup"><span data-stu-id="b6a47-207">avoids such injection by using <xref:System.Data.SqlClient.SqlParameter> in queries.</span></span> <span data-ttu-id="b6a47-208">Вводимые данные преобразуются в значения параметров.</span><span class="sxs-lookup"><span data-stu-id="b6a47-208">User input is turned into parameter values.</span></span> <span data-ttu-id="b6a47-209">Этот способ исключает использование вредоносных команд из введенных данных.</span><span class="sxs-lookup"><span data-stu-id="b6a47-209">This approach prevents malicious commands from being used from customer input.</span></span>

## <a name="changing-read-only-flag-in-dbml-files"></a><span data-ttu-id="b6a47-210">Создание флага "Только чтение" в файлах DBML.</span><span class="sxs-lookup"><span data-stu-id="b6a47-210">Changing Read-only Flag in DBML Files</span></span>

<span data-ttu-id="b6a47-211">Вопрос.</span><span class="sxs-lookup"><span data-stu-id="b6a47-211">Q.</span></span> <span data-ttu-id="b6a47-212">Как можно избавиться от некоторых методов задания свойств при создании объектной модели из файла DBM?</span><span class="sxs-lookup"><span data-stu-id="b6a47-212">How do I eliminate setters from some properties when I create an object model from a DBML file?</span></span>

<span data-ttu-id="b6a47-213">А.</span><span class="sxs-lookup"><span data-stu-id="b6a47-213">A.</span></span> <span data-ttu-id="b6a47-214">Выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="b6a47-214">Take the following steps for this advanced scenario:</span></span>

1. <span data-ttu-id="b6a47-215">В файле DBML измените свойство, присвоив флагу <xref:System.Data.Linq.ITable.IsReadOnly%2A> значение `True`.</span><span class="sxs-lookup"><span data-stu-id="b6a47-215">In the .dbml file, modify the property by changing the <xref:System.Data.Linq.ITable.IsReadOnly%2A> flag to `True`.</span></span>

2. <span data-ttu-id="b6a47-216">Добавьте разделяемый класс.</span><span class="sxs-lookup"><span data-stu-id="b6a47-216">Add a partial class.</span></span> <span data-ttu-id="b6a47-217">Создайте конструктор с параметрами для членов, доступных только для чтения.</span><span class="sxs-lookup"><span data-stu-id="b6a47-217">Create a constructor with parameters for the read-only members.</span></span>

3. <span data-ttu-id="b6a47-218">Проверьте значение по умолчанию <xref:System.Data.Linq.Mapping.UpdateCheck> (<xref:System.Data.Linq.Mapping.UpdateCheck.Never>), чтобы определить, является ли оно правильным для приложения.</span><span class="sxs-lookup"><span data-stu-id="b6a47-218">Review the default <xref:System.Data.Linq.Mapping.UpdateCheck> value (<xref:System.Data.Linq.Mapping.UpdateCheck.Never>) to determine whether that is the correct value for your application.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="b6a47-219">Если вы используете реляционный конструктор объектов в Visual Studio, изменения могут быть перезаписаны.</span><span class="sxs-lookup"><span data-stu-id="b6a47-219">If you are using the Object Relational Designer in Visual Studio, your changes might be overwritten.</span></span>

## <a name="aptca"></a><span data-ttu-id="b6a47-220">APTCA</span><span class="sxs-lookup"><span data-stu-id="b6a47-220">APTCA</span></span>

<span data-ttu-id="b6a47-221">Вопрос.</span><span class="sxs-lookup"><span data-stu-id="b6a47-221">Q.</span></span> <span data-ttu-id="b6a47-222">Помечена ли сборка System.Data.Linq для использования кодом с частичным доверием?</span><span class="sxs-lookup"><span data-stu-id="b6a47-222">Is System.Data.Linq marked for use by partially trusted code?</span></span>

<span data-ttu-id="b6a47-223">А.</span><span class="sxs-lookup"><span data-stu-id="b6a47-223">A.</span></span> <span data-ttu-id="b6a47-224">Да, сборка System. Data. LINQ. dll состоит из .NET Framework сборок, помеченных атрибутом <xref:System.Security.AllowPartiallyTrustedCallersAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b6a47-224">Yes, the System.Data.Linq.dll assembly is among those .NET Framework assemblies marked with the <xref:System.Security.AllowPartiallyTrustedCallersAttribute> attribute.</span></span> <span data-ttu-id="b6a47-225">Без этой маркировки сборки в .NET Framework предназначены для использования только полностью доверенным кодом.</span><span class="sxs-lookup"><span data-stu-id="b6a47-225">Without this marking, assemblies in the .NET Framework are intended for use only by fully trusted code.</span></span>

<span data-ttu-id="b6a47-226">Основной сценарий в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] для разрешения частично доверенных вызывающих объектов заключается в том, чтобы обеспечить доступ к сборке [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] из веб-приложений, где конфигурация *доверия* является средней.</span><span class="sxs-lookup"><span data-stu-id="b6a47-226">The principal scenario in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] for allowing partially trusted callers is to enable the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] assembly to be accessed from Web applications, where the *trust* configuration is Medium.</span></span>

## <a name="mapping-data-from-multiple-tables"></a><span data-ttu-id="b6a47-227">Сопоставление данных из нескольких таблиц</span><span class="sxs-lookup"><span data-stu-id="b6a47-227">Mapping Data from Multiple Tables</span></span>

<span data-ttu-id="b6a47-228">Вопрос.</span><span class="sxs-lookup"><span data-stu-id="b6a47-228">Q.</span></span> <span data-ttu-id="b6a47-229">Данные в сущность поступают из нескольких таблиц.</span><span class="sxs-lookup"><span data-stu-id="b6a47-229">The data in my entity comes from multiple tables.</span></span> <span data-ttu-id="b6a47-230">Как их сопоставить?</span><span class="sxs-lookup"><span data-stu-id="b6a47-230">How do I map it?</span></span>

<span data-ttu-id="b6a47-231">А.</span><span class="sxs-lookup"><span data-stu-id="b6a47-231">A.</span></span> <span data-ttu-id="b6a47-232">В базе данных можно создать представление и сопоставить с ним сущность.</span><span class="sxs-lookup"><span data-stu-id="b6a47-232">You can create a view in a database and map the entity to the view.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="b6a47-233">создает одинаковый SQL-код для представлений и таблиц.</span><span class="sxs-lookup"><span data-stu-id="b6a47-233">generates the same SQL for views as it does for tables.</span></span>

> [!NOTE]
> <span data-ttu-id="b6a47-234">В данном сценарии использование представлений имеет ограничения.</span><span class="sxs-lookup"><span data-stu-id="b6a47-234">The use of views in this scenario has limitations.</span></span> <span data-ttu-id="b6a47-235">Способ работает с максимальной безопасностью, если операции, выполняемые в <xref:System.Data.Linq.Table%601>, поддерживаются базовым представлением.</span><span class="sxs-lookup"><span data-stu-id="b6a47-235">This approach works most safely when the operations performed on <xref:System.Data.Linq.Table%601> are supported by the underlying view.</span></span> <span data-ttu-id="b6a47-236">Операции, которые предполагается использовать, известны только вам.</span><span class="sxs-lookup"><span data-stu-id="b6a47-236">Only you know which operations are intended.</span></span> <span data-ttu-id="b6a47-237">Например, большинство приложений доступны только для чтения, а другой номер немалым выполняет `Create`/`Update`/`Delete` операций только с помощью хранимых процедур в представлениях.</span><span class="sxs-lookup"><span data-stu-id="b6a47-237">For example, most applications are read-only, and another sizeable number perform `Create`/`Update`/`Delete` operations only by using stored procedures against views.</span></span>

## <a name="connection-pooling"></a><span data-ttu-id="b6a47-238">Пулы подключений</span><span class="sxs-lookup"><span data-stu-id="b6a47-238">Connection Pooling</span></span>

<span data-ttu-id="b6a47-239">Вопрос.</span><span class="sxs-lookup"><span data-stu-id="b6a47-239">Q.</span></span> <span data-ttu-id="b6a47-240">Существует ли конструкция, которая поможет в организации пула объектов <xref:System.Data.Linq.DataContext>?</span><span class="sxs-lookup"><span data-stu-id="b6a47-240">Is there a construct that can help with <xref:System.Data.Linq.DataContext> pooling?</span></span>

<span data-ttu-id="b6a47-241">А.</span><span class="sxs-lookup"><span data-stu-id="b6a47-241">A.</span></span> <span data-ttu-id="b6a47-242">Не пытайтесь повторно использовать экземпляры <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="b6a47-242">Do not try to reuse instances of <xref:System.Data.Linq.DataContext>.</span></span> <span data-ttu-id="b6a47-243">Каждый <xref:System.Data.Linq.DataContext> сохраняет состояние (включая кэш идентификации) для одного определенного сеанса редактирования/запроса.</span><span class="sxs-lookup"><span data-stu-id="b6a47-243">Each <xref:System.Data.Linq.DataContext> maintains state (including an identity cache) for one particular edit/query session.</span></span> <span data-ttu-id="b6a47-244">Для получения новых экземпляров на основе текущего состояния базы данных используйте новый <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="b6a47-244">To obtain new instances based on the current state of the database, use a new <xref:System.Data.Linq.DataContext>.</span></span>

<span data-ttu-id="b6a47-245">Вы по-прежнему можете использовать базовые пулы соединений ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="b6a47-245">You can still use underlying ADO.NET connection pooling.</span></span> <span data-ttu-id="b6a47-246">Дополнительные сведения см. в разделе [Пулы подключений SQL Server (ADO.NET)](../../sql-server-connection-pooling.md).</span><span class="sxs-lookup"><span data-stu-id="b6a47-246">For more information, see [SQL Server Connection Pooling (ADO.NET)](../../sql-server-connection-pooling.md).</span></span>

## <a name="second-datacontext-is-not-updated"></a><span data-ttu-id="b6a47-247">Не выполняется обновление второго DataContext</span><span class="sxs-lookup"><span data-stu-id="b6a47-247">Second DataContext Is Not Updated</span></span>

<span data-ttu-id="b6a47-248">Вопрос.</span><span class="sxs-lookup"><span data-stu-id="b6a47-248">Q.</span></span> <span data-ttu-id="b6a47-249">Для хранения значения в базе данных использовался один экземпляр <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="b6a47-249">I used one instance of <xref:System.Data.Linq.DataContext> to store values in the database.</span></span> <span data-ttu-id="b6a47-250">Однако второй <xref:System.Data.Linq.DataContext> в той же базе данных не отражает обновленные значения.</span><span class="sxs-lookup"><span data-stu-id="b6a47-250">However, a second <xref:System.Data.Linq.DataContext> on the same database does not reflect the updated values.</span></span> <span data-ttu-id="b6a47-251">Второй экземпляр <xref:System.Data.Linq.DataContext>, вероятно, возвращает кэшированные значения.</span><span class="sxs-lookup"><span data-stu-id="b6a47-251">The second <xref:System.Data.Linq.DataContext> instance seems to return cached values.</span></span>

<span data-ttu-id="b6a47-252">А.</span><span class="sxs-lookup"><span data-stu-id="b6a47-252">A.</span></span> <span data-ttu-id="b6a47-253">Это сделано намеренно.</span><span class="sxs-lookup"><span data-stu-id="b6a47-253">This behavior is by design.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="b6a47-254">по-прежнему возвращает те же экземпляры и значения, которые отображались в первом экземпляре.</span><span class="sxs-lookup"><span data-stu-id="b6a47-254">continues to return the same instances/values that you saw in the first instance.</span></span> <span data-ttu-id="b6a47-255">При выполнении обновлений используется оптимистическая блокировка.</span><span class="sxs-lookup"><span data-stu-id="b6a47-255">When you make updates, you use optimistic concurrency.</span></span> <span data-ttu-id="b6a47-256">Для проверки текущего состояния базы данных используются исходные данные, которые подтверждают неизменность ее состояния.</span><span class="sxs-lookup"><span data-stu-id="b6a47-256">The original data is used to check against the current database state to assert that it is in fact still unchanged.</span></span> <span data-ttu-id="b6a47-257">Если состояние изменилось, возникает конфликт, который должен быть устранен приложением.</span><span class="sxs-lookup"><span data-stu-id="b6a47-257">If it has changed, a conflict occurs and your application must resolve it.</span></span> <span data-ttu-id="b6a47-258">Одним вариантом является сброс исходного состояния до текущего состояния базы данных и повторная попытка обновления.</span><span class="sxs-lookup"><span data-stu-id="b6a47-258">One option of your application is to reset the original state to the current database state and to try the update again.</span></span> <span data-ttu-id="b6a47-259">Дополнительные сведения см. [в разделе руководство. Управление конфликтами изменений](how-to-manage-change-conflicts.md).</span><span class="sxs-lookup"><span data-stu-id="b6a47-259">For more information, see [How to: Manage Change Conflicts](how-to-manage-change-conflicts.md).</span></span>

<span data-ttu-id="b6a47-260">Кроме того, <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> можно задать значение «false», которое отключает кэширование и отслеживание изменений.</span><span class="sxs-lookup"><span data-stu-id="b6a47-260">You can also set <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> to false, which turns off caching and change tracking.</span></span> <span data-ttu-id="b6a47-261">После этого самые последние значения можно будет извлекать при каждом запросе.</span><span class="sxs-lookup"><span data-stu-id="b6a47-261">You can then retrieve the latest values every time that you query.</span></span>

## <a name="cannot-call-submitchanges-in-read-only-mode"></a><span data-ttu-id="b6a47-262">Не удается вызвать метод SubmitChanges в режиме "только чтение"</span><span class="sxs-lookup"><span data-stu-id="b6a47-262">Cannot Call SubmitChanges in Read-only Mode</span></span>

<span data-ttu-id="b6a47-263">Вопрос.</span><span class="sxs-lookup"><span data-stu-id="b6a47-263">Q.</span></span> <span data-ttu-id="b6a47-264">При попытке вызова метода <xref:System.Data.Linq.DataContext.SubmitChanges%2A> в режиме только для чтения возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="b6a47-264">When I try to call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> in read-only mode, I get an error.</span></span>

<span data-ttu-id="b6a47-265">А.</span><span class="sxs-lookup"><span data-stu-id="b6a47-265">A.</span></span> <span data-ttu-id="b6a47-266">Режим только для чтения отключает для контекста возможность отслеживания изменений.</span><span class="sxs-lookup"><span data-stu-id="b6a47-266">Read-only mode turns off the ability of the context to track changes.</span></span>

## <a name="see-also"></a><span data-ttu-id="b6a47-267">См. также:</span><span class="sxs-lookup"><span data-stu-id="b6a47-267">See also</span></span>

- [<span data-ttu-id="b6a47-268">Ссылки</span><span class="sxs-lookup"><span data-stu-id="b6a47-268">Reference</span></span>](reference.md)
- [<span data-ttu-id="b6a47-269">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="b6a47-269">Troubleshooting</span></span>](troubleshooting.md)
- [<span data-ttu-id="b6a47-270">Безопасность в LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="b6a47-270">Security in LINQ to SQL</span></span>](security-in-linq-to-sql.md)
