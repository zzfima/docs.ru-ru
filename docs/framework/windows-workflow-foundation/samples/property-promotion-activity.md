---
title: Действие Property Promotion
ms.date: 03/30/2017
ms.assetid: 802196b7-1159-4c05-b41b-d3bfdfcc88d9
ms.openlocfilehash: 6e059a0d344e6c62833feaa890c459c141a49673
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43747058"
---
# <a name="property-promotion-activity"></a><span data-ttu-id="1d23b-102">Действие Property Promotion</span><span class="sxs-lookup"><span data-stu-id="1d23b-102">Property Promotion Activity</span></span>
<span data-ttu-id="1d23b-103">Этот образец представляет собой законченное решение, в котором средства повышения уровня <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> встраиваются непосредственно в среду разработки рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="1d23b-103">This sample provides an end-to-end solution that integrates the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> Promotion feature directly into the workflow authoring experience.</span></span> <span data-ttu-id="1d23b-104">Предоставляется коллекция элементов конфигурации, действий рабочего процесса и расширений рабочих процессов, которая позволяет упростить использование средства повышения уровня.</span><span class="sxs-lookup"><span data-stu-id="1d23b-104">A collection of configuration elements, workflow activities, and workflow extensions that simplify the use of the Promotion feature are provided.</span></span> <span data-ttu-id="1d23b-105">Кроме того, этот образец включает простой рабочий процесс, в котором демонстрируется использование этой коллекции.</span><span class="sxs-lookup"><span data-stu-id="1d23b-105">Additionally, the sample contains a simple workflow that demonstrates how to use this collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1d23b-106">Образцы предназначены только для обучения.</span><span class="sxs-lookup"><span data-stu-id="1d23b-106">Samples are provided for educational purposes only.</span></span> <span data-ttu-id="1d23b-107">Они не предназначены для производственной среды и не были проверены в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="1d23b-107">They are not intended for a production environment, and have not been tested in a production environment.</span></span> <span data-ttu-id="1d23b-108">Корпорация Майкрософт не предоставляет техническую поддержку для этих образцов.</span><span class="sxs-lookup"><span data-stu-id="1d23b-108">Microsoft does not provide technical support for these samples.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1d23b-109">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="1d23b-109">Prerequisites</span></span>  
  
-   <span data-ttu-id="1d23b-110">Инициализированная база данных <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore></span><span class="sxs-lookup"><span data-stu-id="1d23b-110">An initialized <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> database</span></span>  
  
-   [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]  
  
## <a name="sample-projects"></a><span data-ttu-id="1d23b-111">Образцы проектов</span><span class="sxs-lookup"><span data-stu-id="1d23b-111">Sample Projects</span></span>  
  
-   <span data-ttu-id="1d23b-112">**PropertyPromotionActivity** проект содержит файлы, относящиеся к элементы конфигурации для повышения роли, действия рабочего процесса и расширения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="1d23b-112">The **PropertyPromotionActivity** project contains files pertaining to the promotion-specific configuration elements, workflow activities, and workflow extensions.</span></span>  
  
-   <span data-ttu-id="1d23b-113">**CounterServiceApplication** проект содержит образец рабочего процесса, использующего **SqlWorkflowInstanceStorePromotion** проекта.</span><span class="sxs-lookup"><span data-stu-id="1d23b-113">The **CounterServiceApplication** project contains a sample workflow that uses the **SqlWorkflowInstanceStorePromotion** project.</span></span>  
  
-   <span data-ttu-id="1d23b-114">Скрипт SQL (PropertyPromotionActivitySQLSample.sql), который должен быть запущен применительно к базе данных <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>.</span><span class="sxs-lookup"><span data-stu-id="1d23b-114">A SQL script (PropertyPromotionActivitySQLSample.sql) that must be run against the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> database.</span></span>  
  
-   <span data-ttu-id="1d23b-115">Файл решения, который связывает два проекта [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] (`PropertyPromotionActivity.sln`)</span><span class="sxs-lookup"><span data-stu-id="1d23b-115">A solution file that links the two [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] projects (`PropertyPromotionActivity.sln`)</span></span>  
  
## <a name="to-set-up-and-run-the-sample"></a><span data-ttu-id="1d23b-116">Установка и запуск образца</span><span class="sxs-lookup"><span data-stu-id="1d23b-116">To set up and run the sample</span></span>  
  
1.  <span data-ttu-id="1d23b-117">Инициализируйте базу данных сохраняемости рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="1d23b-117">Initialize a workflow persistence database.</span></span>  
  
    1.  <span data-ttu-id="1d23b-118">Перейдите в каталог образца (\WF\Basic\Persistence\PropertyPromotionActivity) и запустите пакет CreateInstanceStore.cmd.</span><span class="sxs-lookup"><span data-stu-id="1d23b-118">Navigate to the sample directory (\WF\Basic\Persistence\PropertyPromotionActivity) and run CreateInstanceStore.cmd.</span></span>  
  
    2.  <span data-ttu-id="1d23b-119">Если права администратора недоступны, создайте имя входа SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1d23b-119">If Administrator privileges are not available, create a SQL Server login.</span></span> <span data-ttu-id="1d23b-120">В SQL Server Management Studio перейдите в раздел **безопасности**, **имена входа**.</span><span class="sxs-lookup"><span data-stu-id="1d23b-120">In SQL Server Management Studio, go to **Security**, **Logins**.</span></span> <span data-ttu-id="1d23b-121">Щелкните правой кнопкой мыши **имена входа** и создайте новое имя входа.</span><span class="sxs-lookup"><span data-stu-id="1d23b-121">Right-click **Logins** and create a new login.</span></span> <span data-ttu-id="1d23b-122">Добавьте своего пользователя ACL к роли SQL, открыв **баз данных**, **InstanceStore**, **безопасности**.</span><span class="sxs-lookup"><span data-stu-id="1d23b-122">Add your ACL user to the SQL role by opening **Databases**, **InstanceStore**, **Security**.</span></span> <span data-ttu-id="1d23b-123">Щелкните правой кнопкой мыши **пользователей** и выберите **нового пользователя**.</span><span class="sxs-lookup"><span data-stu-id="1d23b-123">Right-click **Users** and select **New user**.</span></span> <span data-ttu-id="1d23b-124">Задайте **имя входа** к созданным выше пользователем.</span><span class="sxs-lookup"><span data-stu-id="1d23b-124">Set the **Login name** to the user created above.</span></span> <span data-ttu-id="1d23b-125">Добавьте пользователя к членам роли базы данных System.Activities.DurableInstancing.InstanceStoreUsers (и к другим ролям).</span><span class="sxs-lookup"><span data-stu-id="1d23b-125">Add the user to the Database role membership System.Activities.DurableInstancing.InstanceStoreUsers (and others).</span></span> <span data-ttu-id="1d23b-126">Обратите внимание, что пользователь может уже существовать (например, пользователь dbo).</span><span class="sxs-lookup"><span data-stu-id="1d23b-126">Note that the user might exist already (for example, user dbo).</span></span>  
  
2.  <span data-ttu-id="1d23b-127">Откройте файл решения PropertyPromotionActivity.sln в [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1d23b-127">Open the PropertyPromotionActivity.sln solution file in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
3.  <span data-ttu-id="1d23b-128">Если хранилище экземпляров создано в базе данных, отличной от локальной установки SQL Server Express, то необходимо обновить строку подключения базы данных.</span><span class="sxs-lookup"><span data-stu-id="1d23b-128">If you created the instance store in a database other than a local installation of SQL Server Express, then you must update the database connection string.</span></span> <span data-ttu-id="1d23b-129">Измените файл App.config в разделе **CounterServiceApplication** , задав значение `connectionString` атрибут `sqlWorkflowInstanceStorePromotion` узла, которое указывает базу данных сохраняемости, которая была инициализирована в шаге 1.</span><span class="sxs-lookup"><span data-stu-id="1d23b-129">Alter the App.config file under the **CounterServiceApplication** by setting the value of the `connectionString` attribute on the `sqlWorkflowInstanceStorePromotion` node so that it points to the persistence database that was initialized in step 1.</span></span>  
  
4.  <span data-ttu-id="1d23b-130">Постройте и запустите это решение.</span><span class="sxs-lookup"><span data-stu-id="1d23b-130">Build and run the solution.</span></span> <span data-ttu-id="1d23b-131">Это приведет к запуску службы счетчика WF и вызовет автоматический запуск экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="1d23b-131">This will start the Counter WF service and automatically start a workflow instance.</span></span>  
  
5.  <span data-ttu-id="1d23b-132">Быстро выделите все строки в представлении [dbo].[CounterService] в применяемой базе данных сохраняемости (это представление было добавлено в результате выполнения пакета CreateInstanceStore.cmd в шаге 1).</span><span class="sxs-lookup"><span data-stu-id="1d23b-132">Quickly select all the rows in the [dbo].[CounterService] view in your persistence database (this view was added by running CreateInstanceStore.cmd in step 1).</span></span> <span data-ttu-id="1d23b-133">Появится результирующий набор, аналогичный следующему:</span><span class="sxs-lookup"><span data-stu-id="1d23b-133">You will see a result set similar to the following:</span></span>  
  
    |<span data-ttu-id="1d23b-134">InstanceId</span><span class="sxs-lookup"><span data-stu-id="1d23b-134">InstanceId</span></span>|<span data-ttu-id="1d23b-135">CounterValue</span><span class="sxs-lookup"><span data-stu-id="1d23b-135">CounterValue</span></span>|<span data-ttu-id="1d23b-136">CounterValueLastUpdated</span><span class="sxs-lookup"><span data-stu-id="1d23b-136">CounterValueLastUpdated</span></span>|  
    |----------------|------------------|-----------------------------|  
    |<span data-ttu-id="1d23b-137">2FA2C302-929E-4C0D-8C25-768A3DA20CE5</span><span class="sxs-lookup"><span data-stu-id="1d23b-137">2FA2C302-929E-4C0D-8C25-768A3DA20CE5</span></span>|<span data-ttu-id="1d23b-138">12</span><span class="sxs-lookup"><span data-stu-id="1d23b-138">12</span></span>|<span data-ttu-id="1d23b-139">2010-02-18 22:48:01.740</span><span class="sxs-lookup"><span data-stu-id="1d23b-139">2010-02-18 22:48:01.740</span></span>|  
  
     <span data-ttu-id="1d23b-140">Продолжая обновлять это представление, обратите внимание, что значения CounterValue и CounterValueLastUpdated изменяются через каждые две секунды.</span><span class="sxs-lookup"><span data-stu-id="1d23b-140">As you keep refreshing the view, you will notice that CounterValue and CounterValueLastUpdated change every two seconds.</span></span> <span data-ttu-id="1d23b-141">Это интервал, в течение которого счетчик обновляет сам себя.</span><span class="sxs-lookup"><span data-stu-id="1d23b-141">This is the interval at which the counter updates itself.</span></span> <span data-ttu-id="1d23b-142">Значения CounterValue и CounterValueLastUpdated представляют свойства с повышенным уровнем для этого рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="1d23b-142">CounterValue and CounterValueLastUpdated represent promoted properties for this workflow.</span></span>  
  
## <a name="to-remove-the-sample"></a><span data-ttu-id="1d23b-143">Удаление образца</span><span class="sxs-lookup"><span data-stu-id="1d23b-143">To remove the sample</span></span>  
  
-   <span data-ttu-id="1d23b-144">Выполните пакет RemoveInstanceStore.cmd в каталоге образца (\WF\Basic\Persistence\PropertyPromotionActivity).</span><span class="sxs-lookup"><span data-stu-id="1d23b-144">Run RemoveInstanceStore.cmd in the sample directory (\WF\Basic\Persistence\PropertyPromotionActivity).</span></span>  
  
## <a name="understanding-this-sample"></a><span data-ttu-id="1d23b-145">Основные сведения об этом образце</span><span class="sxs-lookup"><span data-stu-id="1d23b-145">Understanding This Sample</span></span>  
 <span data-ttu-id="1d23b-146">Образец содержит два проекта и файл SQL:</span><span class="sxs-lookup"><span data-stu-id="1d23b-146">The sample contains two projects and an SQL file:</span></span>  
  
-   <span data-ttu-id="1d23b-147">**CounterServiceApplication** представляет собой консольное приложение, на котором размещается простая служба счетчика WF.</span><span class="sxs-lookup"><span data-stu-id="1d23b-147">**CounterServiceApplication** is a console application that hosts a simple Counter WF service.</span></span> <span data-ttu-id="1d23b-148">После получения одностороннего сообщения через конечную точку `Start` рабочий процесс производит отсчет от 0 до 29, увеличивая переменную счетчика через каждые две секунды.</span><span class="sxs-lookup"><span data-stu-id="1d23b-148">Upon receiving a one-way message through the `Start` endpoint, the workflow counts from 0 to 29, incrementing a counter variable every two seconds.</span></span> <span data-ttu-id="1d23b-149">После каждого приращения счетчика рабочий процесс сохраняется и свойства с повышенным уровнем обновляются в представлении [dbo].[CounterService].</span><span class="sxs-lookup"><span data-stu-id="1d23b-149">After every counter increment, the workflow persists, and the promoted properties are updated in the [dbo].[CounterService] view.</span></span> <span data-ttu-id="1d23b-150">После запуска консольного приложения это приложение размещает службу WF и отправляет сообщение в конечную точку `Start`, создавая экземпляр счетчика WF.</span><span class="sxs-lookup"><span data-stu-id="1d23b-150">When the console application is run, it hosts the WF service and sends a message to the `Start` endpoint, creating a Counter WF instance.</span></span>  
  
-   <span data-ttu-id="1d23b-151">**PropertyPromotionActivity** — это библиотека классов, который содержит элементы конфигурации, действия рабочего процесса и расширения рабочего процесса, **CounterServiceApplication** использует.</span><span class="sxs-lookup"><span data-stu-id="1d23b-151">**PropertyPromotionActivity** is a class library that contains the configuration elements, workflow activities, and workflow extensions that the **CounterServiceApplication** uses.</span></span>  
  
-   <span data-ttu-id="1d23b-152">**PropertyPromotionActivitySQLSample.sql** создает и добавляет представление [dbo]. [ CounterService] в базу данных.</span><span class="sxs-lookup"><span data-stu-id="1d23b-152">**PropertyPromotionActivitySQLSample.sql** creates and adds the view [dbo].[CounterService] to the database.</span></span>  
  
### <a name="counterserviceapplication"></a><span data-ttu-id="1d23b-153">CounterServiceApplication</span><span class="sxs-lookup"><span data-stu-id="1d23b-153">CounterServiceApplication</span></span>  
  
#### <a name="using-the-sqlworkflowinstancestorepromotion-configuration-element"></a><span data-ttu-id="1d23b-154">Использование элемента конфигурации SqlWorkflowInstanceStorePromotion</span><span class="sxs-lookup"><span data-stu-id="1d23b-154">Using the SqlWorkflowInstanceStorePromotion Configuration Element</span></span>  
 <span data-ttu-id="1d23b-155">Элемент конфигурации `SqlWorkflowInstanceStorePromotion` наследует от элемента конфигурации `SqlWorkflowInstanceStore`, но добавляет дополнительный элемент конфигурации с именем `promotionSets`.</span><span class="sxs-lookup"><span data-stu-id="1d23b-155">The `SqlWorkflowInstanceStorePromotion` configuration element inherits from the `SqlWorkflowInstanceStore` configuration element, but adds an additional configuration element called `promotionSets`.</span></span> <span data-ttu-id="1d23b-156">Элемент `promotionSets` позволяет пользователю задавать свойства с повышенным уровнем путем настройки.</span><span class="sxs-lookup"><span data-stu-id="1d23b-156">The `promotionSets` element enables the user to specify promoted properties through configuration.</span></span> <span data-ttu-id="1d23b-157">Это файл конфигурации, который используется образцом:</span><span class="sxs-lookup"><span data-stu-id="1d23b-157">This is the configuration file that is used by the sample:</span></span>  
  
```xml  
<sqlWorkflowInstanceStorePromotion connectionString ="Data Source=.;Initial Catalog=SqlWorkflowInstanceStoreTest;Integrated Security=True;">  
  <promotionSets>  
    <promotionSet name="CounterService">  
      <promotedValue propertyName="Count"/>  
      <promotedValue propertyName="LastIncrementedAt"/>  
    </promotionSet>  
  </promotionSets>  
</sqlWorkflowInstanceStorePromotion>  
```  
  
 <span data-ttu-id="1d23b-158">Изучите определение для представления [dbo].[CounterService].</span><span class="sxs-lookup"><span data-stu-id="1d23b-158">Examine the definition for the [dbo].[CounterService] view.</span></span>  
  
```sql  
create view [dbo].[CounterService] as  
      select [InstanceId],  
 [Value1] as [CounterValue],  
 [Value2] as [CounterValueLastUpdated]  
      from [System.Activities.DurableInstancing].[InstancePromotedProperties]  
      where [PromotionName] = 'CounterService'  
go  
```  
  
 <span data-ttu-id="1d23b-159">При сохранении экземпляра рабочего процесса происходит вставка в представление `InstancePromotedProperties` одной строки для каждого `PromotionSet`, определенного в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1d23b-159">When a workflow instance persists, a row is inserted into the `InstancePromotedProperties` view for each `PromotionSet` defined in the configuration.</span></span> <span data-ttu-id="1d23b-160">Эта строка содержит все свойства `PromotionSet` с повышенным уровнем (по одному свойству с повышенным уровнем на каждый столбец).</span><span class="sxs-lookup"><span data-stu-id="1d23b-160">This row contains all the promoted properties of the `PromotionSet` (one promoted property per column).</span></span> <span data-ttu-id="1d23b-161">Ключом для этого значения `PromotionSet` является кортеж `InstanceId, PromotionName`.</span><span class="sxs-lookup"><span data-stu-id="1d23b-161">This `PromotionSet` is keyed by the tuple: `InstanceId, PromotionName`.</span></span> <span data-ttu-id="1d23b-162">В этом образце в конфигурации был определен один объект `PromotionSet`, атрибутом имени которого является `CounterService`.</span><span class="sxs-lookup"><span data-stu-id="1d23b-162">In this sample, we have one `PromotionSet` defined in configuration whose name attribute is `CounterService`.</span></span> <span data-ttu-id="1d23b-163">Обратите внимание на то, что значение столбца `PromotionName` равно атрибуту имени элемента `PromotionSet`.</span><span class="sxs-lookup"><span data-stu-id="1d23b-163">Note how the `PromotionName` column value is equal to the name attribute of the `PromotionSet` element.</span></span>  
  
 <span data-ttu-id="1d23b-164">Порядок элементов `promotedValue` коррелирует с размещением свойств с повышенным уровнем в представлении `InstancePromotedProperties`.</span><span class="sxs-lookup"><span data-stu-id="1d23b-164">The order of the `promotedValue` elements correlates with the placement of the promoted properties in the `InstancePromotedProperties` view.</span></span> <span data-ttu-id="1d23b-165">`Count` - первый элемент `promotedValue`.</span><span class="sxs-lookup"><span data-stu-id="1d23b-165">`Count` is the first `promotedValue` element.</span></span> <span data-ttu-id="1d23b-166">В результате он сопоставляется со столбцом `Value1` в представлении `InstancePromotedProperties`.</span><span class="sxs-lookup"><span data-stu-id="1d23b-166">As a result, it is mapped to the `Value1` column in the `InstancePromotedProperties` view.</span></span> <span data-ttu-id="1d23b-167">`LastIncrementedAt` - второй элемент `promotedValue`.</span><span class="sxs-lookup"><span data-stu-id="1d23b-167">`LastIncrementedAt` is the second `promotedValue` element.</span></span> <span data-ttu-id="1d23b-168">В результате он сопоставляется со столбцом `Value2` в представлении `InstancePromotedProperties`.</span><span class="sxs-lookup"><span data-stu-id="1d23b-168">As a result, it is mapped to the `Value2` column in the `InstancePromotedProperties` view.</span></span>  
  
#### <a name="using-the-promotevalue-activity"></a><span data-ttu-id="1d23b-169">Использование действия PromoteValue</span><span class="sxs-lookup"><span data-stu-id="1d23b-169">Using the PromoteValue Activity</span></span>  
 <span data-ttu-id="1d23b-170">Изучите файл CounterService.xamlx в конструкторе Windows Workflow Foundation.</span><span class="sxs-lookup"><span data-stu-id="1d23b-170">Examine the CounterService.xamlx file in the Windows Workflow Foundation Designer.</span></span> <span data-ttu-id="1d23b-171">Обратите внимание, что в определении WF имеются два специальных действия - `PromoteValue<DateTime>` и `PromoteValue<Int32>`.</span><span class="sxs-lookup"><span data-stu-id="1d23b-171">Notice that there are two special activities in the WF definition: `PromoteValue<DateTime>` and `PromoteValue<Int32>`.</span></span>  
  
 <span data-ttu-id="1d23b-172">В действии `PromoteValue<Int32>` член `Name` определен как `Count`.</span><span class="sxs-lookup"><span data-stu-id="1d23b-172">The `PromoteValue<Int32>` activity has its `Name` member defined as `Count`.</span></span> <span data-ttu-id="1d23b-173">Этот объект согласуется с первым элементом `promotedValue` в конфигурации и имеет свое значение `Value`, определенное как переменная рабочего процесса `Counter`.</span><span class="sxs-lookup"><span data-stu-id="1d23b-173">This matches with the first `promotedValue` element in the configuration, and has its `Value` defined as the `Counter` workflow variable.</span></span> <span data-ttu-id="1d23b-174">При сохранении этого рабочего процесса переменная рабочего процесса `Counter` сохраняется как свойство с повышенным уровнем в столбце `Value1` представления `InstancePromotedProperties`.</span><span class="sxs-lookup"><span data-stu-id="1d23b-174">When the workflow persists, the `Counter` workflow variable is persisted as a promoted property into the `Value1` column of the `InstancePromotedProperties` view.</span></span>  
  
 <span data-ttu-id="1d23b-175">В действии `PromoteValue<DateTime>` член `Name` определен как `LastIncrementedAt`.</span><span class="sxs-lookup"><span data-stu-id="1d23b-175">The `PromoteValue<DateTime>` activity has its `Name` member defined as `LastIncrementedAt`.</span></span> <span data-ttu-id="1d23b-176">Этот объект согласуется со вторым элементом `promotedValue` в конфигурации и имеет свое значение `Value`, определенное как переменная рабочего процесса `TimeLastIncremented`.</span><span class="sxs-lookup"><span data-stu-id="1d23b-176">This matches with the second `promotedValue` element in the configuration, and has its `Value` defined as the `TimeLastIncremented` workflow variable.</span></span> <span data-ttu-id="1d23b-177">Это означает, что при сохранении этого рабочего процесса переменная рабочего процесса `TimeLastIncremented` сохраняется как свойство с повышенным уровнем в столбце `Value2` представления `InstancePromotedProperties`.</span><span class="sxs-lookup"><span data-stu-id="1d23b-177">This means that when the workflow persists, the value for the `TimeLastIncremented` workflow variable will be persisted as a promoted property into the `Value2` column of the `InstancePromotedProperties` view.</span></span>  
  
 <span data-ttu-id="1d23b-178">Следует отметить, что в действии `PromotedValue` имеется также член типа Boolean с именем `ClearExistingPromotedData`.</span><span class="sxs-lookup"><span data-stu-id="1d23b-178">Note that the `PromotedValue` activity also has a Boolean member called `ClearExistingPromotedData`.</span></span> <span data-ttu-id="1d23b-179">Если этот член задан равным `true`, происходит очистка всех значений свойств с повышенным уровнем вплоть до этой точки в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="1d23b-179">When this member is set to `true`, this clears all the promoted property values up to that point in the workflow.</span></span> <span data-ttu-id="1d23b-180">Например, допустим, что действие Sequence определено последовательно:</span><span class="sxs-lookup"><span data-stu-id="1d23b-180">For example, if a Sequence activity is defined as follows:</span></span>  
  
1.  <span data-ttu-id="1d23b-181">PromoteValue {Name = «Count», Value = 3}</span><span class="sxs-lookup"><span data-stu-id="1d23b-181">PromoteValue { Name = "Count", Value = 3}</span></span>  
  
2.  <span data-ttu-id="1d23b-182">PromoteValue {Name = «LastIncrementedAt», значение = 1-1-2000}</span><span class="sxs-lookup"><span data-stu-id="1d23b-182">PromoteValue {Name = "LastIncrementedAt", Value = 1-1-2000 }</span></span>  
  
3.  <span data-ttu-id="1d23b-183">Persist</span><span class="sxs-lookup"><span data-stu-id="1d23b-183">Persist</span></span>  
  
4.  <span data-ttu-id="1d23b-184">PromoteValue {Name = «Count», Value = 4, ClearExistingPromotedData = true}</span><span class="sxs-lookup"><span data-stu-id="1d23b-184">PromoteValue {Name = "Count", Value = 4, ClearExistingPromotedData = true}</span></span>  
  
5.  <span data-ttu-id="1d23b-185">Persist</span><span class="sxs-lookup"><span data-stu-id="1d23b-185">Persist</span></span>  
  
 <span data-ttu-id="1d23b-186">При втором сохранении значением с повышенным уровнем для `Count` будет 4.</span><span class="sxs-lookup"><span data-stu-id="1d23b-186">On the second persist, the promoted value for `Count` will be 4.</span></span> <span data-ttu-id="1d23b-187">Тем не менее значением с повышенным уровнем для `LastIncrementedAt` будет `NULL`.</span><span class="sxs-lookup"><span data-stu-id="1d23b-187">However, the promoted value for `LastIncrementedAt` will be `NULL`.</span></span> <span data-ttu-id="1d23b-188">Если `ClearExistingPromotedData` не задано равным `true` для шага 4, то после второго сохранения значением с повышенным уровнем для Count будет 4.</span><span class="sxs-lookup"><span data-stu-id="1d23b-188">If `ClearExistingPromotedData` was not set to `true` for step 4, then after the second persist, the promoted value for Count would be 4.</span></span> <span data-ttu-id="1d23b-189">В результате значение с повышенным уровнем для `LastIncrementedAt` все еще останется равным 1-1-2000.</span><span class="sxs-lookup"><span data-stu-id="1d23b-189">As a result, the promoted value for `LastIncrementedAt` would still be 1-1-2000.</span></span>  
  
### <a name="propertypromotionactivity"></a><span data-ttu-id="1d23b-190">PropertyPromotionActivity</span><span class="sxs-lookup"><span data-stu-id="1d23b-190">PropertyPromotionActivity</span></span>  
 <span data-ttu-id="1d23b-191">Эта библиотека классов содержит следующие общедоступные классы, позволяющие упростить использование средства повышения уровня <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>.</span><span class="sxs-lookup"><span data-stu-id="1d23b-191">This class library contains the following public classes to simplify use of the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> Promotion feature.</span></span>  
  
#### <a name="promotevalue-class"></a><span data-ttu-id="1d23b-192">Класс PromoteValue</span><span class="sxs-lookup"><span data-stu-id="1d23b-192">PromoteValue Class</span></span>  
 <span data-ttu-id="1d23b-193">Этот класс повышает уровень одного свойства.</span><span class="sxs-lookup"><span data-stu-id="1d23b-193">This class promotes one property.</span></span> <span data-ttu-id="1d23b-194">Имя свойства с повышенным уровнем должно соответствовать атрибуту name элемента `promotedValue` в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1d23b-194">The name of the promoted property should match a name attribute of a `promotedValue` element in the configuration.</span></span> <span data-ttu-id="1d23b-195">Это действие может использоваться в конструкторе рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="1d23b-195">This activity can be used in the Workflow Designer.</span></span> <span data-ttu-id="1d23b-196">Пример использования см. в описании CounterServiceApplication.</span><span class="sxs-lookup"><span data-stu-id="1d23b-196">See the CounterServiceApplication for an example usage.</span></span>  
  
```csharp  
public class PromoteValue<T> : CodeActivity  
{  
    public PromoteValue()  
    {  
    }  
  
    public bool ClearExistingPromotedData { get; set; }  
    public string Name { get; set; }  
    public InArgument<T> Value { get; set; }  
}  
```  
  
 <span data-ttu-id="1d23b-197">ClearExistingPromotedData (Bool)</span><span class="sxs-lookup"><span data-stu-id="1d23b-197">ClearExistingPromotedData (Bool)</span></span>  
 <span data-ttu-id="1d23b-198">Очищает все значения, уровень которых был повышен перед этим действием.</span><span class="sxs-lookup"><span data-stu-id="1d23b-198">Clears all values that were promoted before this activity.</span></span>  
  
 <span data-ttu-id="1d23b-199">Name (string)</span><span class="sxs-lookup"><span data-stu-id="1d23b-199">Name (string)</span></span>  
 <span data-ttu-id="1d23b-200">Имя, которое представляет данное свойство.</span><span class="sxs-lookup"><span data-stu-id="1d23b-200">The name that represents this property.</span></span> <span data-ttu-id="1d23b-201">Оно должно соответствовать имени атрибута \<promotedValue > элемент в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1d23b-201">This should match the name attribute of a \<promotedValue> element in the configuration.</span></span>  
  
 <span data-ttu-id="1d23b-202">Значение (InArgument\<T >)</span><span class="sxs-lookup"><span data-stu-id="1d23b-202">Value (InArgument\<T>)</span></span>  
 <span data-ttu-id="1d23b-203">Переменная и/или значение, которое необходимо сохранить в столбце.</span><span class="sxs-lookup"><span data-stu-id="1d23b-203">The variable / value that you want to store in the column.</span></span>  
  
#### <a name="promotevalues-class"></a><span data-ttu-id="1d23b-204">Класс PromoteValues</span><span class="sxs-lookup"><span data-stu-id="1d23b-204">PromoteValues Class</span></span>  
 <span data-ttu-id="1d23b-205">Повышает уровень нескольких свойств.</span><span class="sxs-lookup"><span data-stu-id="1d23b-205">Promotes multiple properties.</span></span> <span data-ttu-id="1d23b-206">Имена свойств с повышенным уровнем должны соответствовать всем атрибутам name в элементах `promotedValue` в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1d23b-206">The names of the promoted properties should match all name attributes in the `promotedValue` elements in the configuration.</span></span> <span data-ttu-id="1d23b-207">Применение аналогично применению в действии `PromoteValue`, за исключением того факта, что повышение уровня нескольких свойств может происходить одновременно.</span><span class="sxs-lookup"><span data-stu-id="1d23b-207">Usage is similar to the `PromoteValue` activity, except for the fact that multiple properties can be promoted at the same time.</span></span> <span data-ttu-id="1d23b-208">Это действие не может использоваться в конструкторе рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="1d23b-208">This activity cannot be used in the Workflow Designer.</span></span>  
  
```  
public class PromoteValues : CodeActivity  
{  
    public PromoteValues()  
    {  
        this.ValuesToPromote = new Dictionary<string, InArgument>();  
    }  
  
    public bool ClearExistingPromotedData { get; set; }  
    public IDictionary<string, InArgument> ValuesToPromote { get; set; }  
}  
```  
  
#### <a name="sqlworkflowinstancestorepromotionbehavior"></a><span data-ttu-id="1d23b-209">SqlWorkflowInstanceStorePromotionBehavior</span><span class="sxs-lookup"><span data-stu-id="1d23b-209">SqlWorkflowInstanceStorePromotionBehavior</span></span>  
 <span data-ttu-id="1d23b-210">Происходит от `SqlWorkflowInstanceStoreBehavior`.</span><span class="sxs-lookup"><span data-stu-id="1d23b-210">Derives from `SqlWorkflowInstanceStoreBehavior`.</span></span> <span data-ttu-id="1d23b-211">Этот производный класс добавляет участника настраиваемой сохраняемости (также в составе этой библиотеки) как расширение рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="1d23b-211">This derived class adds a custom persistence participant (also a part of this library) as a workflow extension.</span></span> <span data-ttu-id="1d23b-212">Реализация двух предыдущих действий рабочего процесса основана на этом участнике настраиваемой сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="1d23b-212">The implementation of the previous two workflow activities relies on this custom persistence participant.</span></span>  
  
```  
public class SqlWorkflowInstanceStorePromotionBehavior :  
             SqlWorkflowInstanceStoreBehavior, IServiceBehavior  
{  
        public void Promote(string name, IEnumerable<string> promoteAsSqlVariant,  
                            IEnumerable<string> promoteAsBinary)  
  
}  
```  
  
 <span data-ttu-id="1d23b-213">Эта библиотека классов содержит также реализацию `ConfigurationElement` для `SqlWorkflowInstanceStorePromotionElement` и участника настраиваемой сохраняемости, используемого предыдущими действиями по повышению уровня.</span><span class="sxs-lookup"><span data-stu-id="1d23b-213">This class library also contains the `ConfigurationElement` implementation for the `SqlWorkflowInstanceStorePromotionElement` and a custom persistence participant used by the previous promotion activities.</span></span>  
  
### <a name="propertypromotionactivitysqlsample"></a><span data-ttu-id="1d23b-214">PropertyPromotionActivitySQLSample</span><span class="sxs-lookup"><span data-stu-id="1d23b-214">PropertyPromotionActivitySQLSample</span></span>  
 <span data-ttu-id="1d23b-215">Этот файл SQL создает представление `[dbo].[CounterService]` в дополнение к представлению `[InstancePromotedProperties]` для формирования запросов ко всем экземплярам, в которых задано повышение уровня CounterService.</span><span class="sxs-lookup"><span data-stu-id="1d23b-215">This SQL file creates a `[dbo].[CounterService]` view in addition to the `[InstancePromotedProperties]` view for querying all instances that have a CounterService Promotion set.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1d23b-216">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="1d23b-216">The samples may already be installed on your computer.</span></span> <span data-ttu-id="1d23b-217">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="1d23b-217">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="1d23b-218">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="1d23b-218">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1d23b-219">Этот образец находится в следующем каталоге:</span><span class="sxs-lookup"><span data-stu-id="1d23b-219">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Persistence\PropertyPromotionActivity`  
  
## <a name="see-also"></a><span data-ttu-id="1d23b-220">См. также</span><span class="sxs-lookup"><span data-stu-id="1d23b-220">See Also</span></span>  
 [<span data-ttu-id="1d23b-221">Образцы размещения AppFabric и сохраняемости</span><span class="sxs-lookup"><span data-stu-id="1d23b-221">AppFabric Hosting and Persistence Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193961)
