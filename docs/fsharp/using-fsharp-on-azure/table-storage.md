---
title: 'Начало работы с хранилищем таблиц Azure, с помощью F #'
description: Хранения структурированных данных в облаке с использованием хранилища таблиц Azure или Azure Cosmos DB.
keywords: 'Visual f #, f #, функционального программирования, .NET, .NET Core, Azure'
author: sylvanc
ms.author: phcart
ms.date: 03/26/2018
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 9e5d6cea-a98c-461e-a5cc-75f1d154eafd
ms.openlocfilehash: 6d40211e13e8d213aa5a40d585dd384abf49ddfa
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="get-started-with-azure-table-storage-and-the-azure-cosmos-db-table-api-using-f"></a><span data-ttu-id="492cc-104">Начало работы с хранилищем таблиц Azure и Azure DB Cosmos таблицы, в API с помощью F #</span><span class="sxs-lookup"><span data-stu-id="492cc-104">Get started with Azure Table storage and the Azure Cosmos DB Table API using F#</span></span> # 

<span data-ttu-id="492cc-105">Хранилище таблиц Azure — это служба, для сохранения структурированных данных NoSQL в облаке.</span><span class="sxs-lookup"><span data-stu-id="492cc-105">Azure Table storage is a service that stores structured NoSQL data in the cloud.</span></span> <span data-ttu-id="492cc-106">Хранилище ключей или атрибут с schemaless конструктора будет хранилище таблиц.</span><span class="sxs-lookup"><span data-stu-id="492cc-106">Table storage is a key/attribute store with a schemaless design.</span></span> <span data-ttu-id="492cc-107">Так как хранилище таблиц schemaless, можно легко адаптировать данных в соответствии с потребностями вашего приложения evolve.</span><span class="sxs-lookup"><span data-stu-id="492cc-107">Because Table storage is schemaless, it's easy to adapt your data as the needs of your application evolve.</span></span> <span data-ttu-id="492cc-108">Доступ к данным — это быстрый и экономичный для всех типов приложений.</span><span class="sxs-lookup"><span data-stu-id="492cc-108">Access to data is fast and cost-effective for all kinds of applications.</span></span> <span data-ttu-id="492cc-109">Хранилище таблиц, обычно значительно меньше стоимости традиционные SQL аналогичные объемами данных.</span><span class="sxs-lookup"><span data-stu-id="492cc-109">Table storage is typically significantly lower in cost than traditional SQL for similar volumes of data.</span></span>

<span data-ttu-id="492cc-110">Хранилище таблиц можно использовать для хранения гибкие наборов данных, таких как данные пользователя для веб-приложений, адресные книги, сведения об устройстве и любого другого типа метаданных, необходимых службе.</span><span class="sxs-lookup"><span data-stu-id="492cc-110">You can use Table storage to store flexible datasets, such as user data for web applications, address books, device information, and any other type of metadata that your service requires.</span></span> <span data-ttu-id="492cc-111">Можно хранить любое число сущностей в таблице, и учетную запись хранилища может содержать любое количество таблиц, вплоть до предела емкости учетной записи хранения.</span><span class="sxs-lookup"><span data-stu-id="492cc-111">You can store any number of entities in a table, and a storage account may contain any number of tables, up to the capacity limit of the storage account.</span></span>

<span data-ttu-id="492cc-112">Azure Cosmos DB предоставляет API-Интерфейс таблиц для приложения, написанные для табличного хранилища Azure и требующих возможностям расширенного выпуска:</span><span class="sxs-lookup"><span data-stu-id="492cc-112">Azure Cosmos DB provides the Table API for applications that are written for Azure Table storage and that require premium capabilities such as:</span></span>

- <span data-ttu-id="492cc-113">Готовое к использованию глобального распространения.</span><span class="sxs-lookup"><span data-stu-id="492cc-113">Turnkey global distribution.</span></span>
- <span data-ttu-id="492cc-114">Выделенный пропускная способность по всему миру.</span><span class="sxs-lookup"><span data-stu-id="492cc-114">Dedicated throughput worldwide.</span></span>
- <span data-ttu-id="492cc-115">Миллисекунды десяти задержки процентиля 99.</span><span class="sxs-lookup"><span data-stu-id="492cc-115">Single-digit millisecond latencies at the 99th percentile.</span></span>
- <span data-ttu-id="492cc-116">Гарантируется, что высокий уровень доступности.</span><span class="sxs-lookup"><span data-stu-id="492cc-116">Guaranteed high availability.</span></span>
- <span data-ttu-id="492cc-117">Автоматическое получателей индексирование.</span><span class="sxs-lookup"><span data-stu-id="492cc-117">Automatic secondary indexing.</span></span>

<span data-ttu-id="492cc-118">Приложения, написанные для табличного хранилища Azure можно перенести на Azure Cosmos DB с помощью API таблицы без изменений кода и воспользоваться преимуществами premium.</span><span class="sxs-lookup"><span data-stu-id="492cc-118">Applications written for Azure Table storage can migrate to Azure Cosmos DB by using the Table API with no code changes and take advantage of premium capabilities.</span></span> <span data-ttu-id="492cc-119">API таблицы содержит клиентские пакеты SDK для .NET, Java, Python и Node.js.</span><span class="sxs-lookup"><span data-stu-id="492cc-119">The Table API has client SDKs available for .NET, Java, Python, and Node.js.</span></span>

<span data-ttu-id="492cc-120">Дополнительные сведения см. в разделе [введение в Azure Cosmos DB таблицы API](https://docs.microsoft.com/azure/cosmos-db/table-introduction).</span><span class="sxs-lookup"><span data-stu-id="492cc-120">For more information, see [Introduction to Azure Cosmos DB Table API](https://docs.microsoft.com/azure/cosmos-db/table-introduction).</span></span>

## <a name="about-this-tutorial"></a><span data-ttu-id="492cc-121">О этого учебника</span><span class="sxs-lookup"><span data-stu-id="492cc-121">About this tutorial</span></span>

<span data-ttu-id="492cc-122">Этот учебник показывает способы написания кода F # для выполнения общих задач с помощью хранилища Azure таблицы или таблицы API DB Cosmos Azure, включая создание и удаление таблицы и вставка, обновление, удаление и запрос данных таблицы.</span><span class="sxs-lookup"><span data-stu-id="492cc-122">This tutorial shows how to write F# code to do some common tasks using Azure Table storage or the Azure Cosmos DB Table API, including creating and deleting a table and inserting, updating, deleting, and querying table data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="492cc-123">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="492cc-123">Prerequisites</span></span>

<span data-ttu-id="492cc-124">Чтобы использовать это руководство, необходимо сначала [создать учетную запись хранилища Azure](/azure/storage/storage-create-storage-account) или [учетная запись Azure Cosmos DB](https://azure.microsoft.com/try/cosmosdb/).</span><span class="sxs-lookup"><span data-stu-id="492cc-124">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account) or [Azure Cosmos DB account](https://azure.microsoft.com/try/cosmosdb/).</span></span>


## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="492cc-125">Создание скрипта F # и начала F #, интерактивный</span><span class="sxs-lookup"><span data-stu-id="492cc-125">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="492cc-126">Примеры в этой статье используется в F # приложения или скрипта F #.</span><span class="sxs-lookup"><span data-stu-id="492cc-126">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="492cc-127">Чтобы создать скрипт F #, создайте файл с `.fsx` расширение, например `tables.fsx`, в среде разработки F #.</span><span class="sxs-lookup"><span data-stu-id="492cc-127">To create an F# script, create a file with the `.fsx` extension, for example `tables.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="492cc-128">Затем используйте [диспетчера пакетов](package-management.md) такие как [Paket](https://fsprojects.github.io/Paket/) или [NuGet](https://www.nuget.org/) установка `WindowsAzure.Storage` пакета и ссылка `WindowsAzure.Storage.dll` в скрипте с помощью `#r`директивы.</span><span class="sxs-lookup"><span data-stu-id="492cc-128">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span> <span data-ttu-id="492cc-129">Сделать его снова, `Microsoft.WindowsAzure.ConfigurationManager` для получения имен Microsoft.Azure.</span><span class="sxs-lookup"><span data-stu-id="492cc-129">Do it again for `Microsoft.WindowsAzure.ConfigurationManager` in order to get the Microsoft.Azure namespace.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="492cc-130">Добавьте объявления пространств имен</span><span class="sxs-lookup"><span data-stu-id="492cc-130">Add namespace declarations</span></span>

<span data-ttu-id="492cc-131">Добавьте следующие `open` инструкции в начало `tables.fsx` файла:</span><span class="sxs-lookup"><span data-stu-id="492cc-131">Add the following `open` statements to the top of the `tables.fsx` file:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L1-L5)]

### <a name="get-your-azure-storage-connection-string"></a><span data-ttu-id="492cc-132">Получение строки подключения хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="492cc-132">Get your Azure Storage connection string</span></span>

<span data-ttu-id="492cc-133">При подключении к службе таблиц хранилища Azure, вам потребуется строки подключения для этого учебника.</span><span class="sxs-lookup"><span data-stu-id="492cc-133">If you're connecting to Azure Storage Table service, you'll need your connection string for this tutorial.</span></span> <span data-ttu-id="492cc-134">Можно скопировать строку подключения на портале Azure.</span><span class="sxs-lookup"><span data-stu-id="492cc-134">You can copy your connection string from the Azure portal.</span></span> <span data-ttu-id="492cc-135">Дополнительные сведения о строках соединения см. в разделе [Настройка строки подключения хранилища](/azure/storage/storage-configure-connection-string).</span><span class="sxs-lookup"><span data-stu-id="492cc-135">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

### <a name="get-your-azure-cosmos-db-connection-string"></a><span data-ttu-id="492cc-136">Получить строку подключения к базе данных Azure Cosmos</span><span class="sxs-lookup"><span data-stu-id="492cc-136">Get your Azure Cosmos DB connection string</span></span>

<span data-ttu-id="492cc-137">При подключении к базе данных Azure Cosmos, вам потребуется строки подключения для этого учебника.</span><span class="sxs-lookup"><span data-stu-id="492cc-137">If you're connecting to Azure Cosmos DB, you'll need your connection string for this tutorial.</span></span> <span data-ttu-id="492cc-138">Можно скопировать строку подключения на портале Azure.</span><span class="sxs-lookup"><span data-stu-id="492cc-138">You can copy your connection string from the Azure portal.</span></span> <span data-ttu-id="492cc-139">На портале Azure в учетной записи Cosmos DB перейдите к **параметры** > **строка подключения**и нажмите кнопку **копирования** кнопку, чтобы скопировать первичный подключение Строка.</span><span class="sxs-lookup"><span data-stu-id="492cc-139">In the Azure portal, in your Cosmos DB account, go to **Settings** > **Connection String**, and click the **Copy** button to copy your Primary Connection String.</span></span> 

<span data-ttu-id="492cc-140">В учебнике введите строку подключения в скрипте, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="492cc-140">For the tutorial, enter your connection string in your script, like the following example:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L11-L11)]

<span data-ttu-id="492cc-141">Однако это **не рекомендуется** для реальных проектах.</span><span class="sxs-lookup"><span data-stu-id="492cc-141">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="492cc-142">Ключ учетной записи хранилища аналогична корневой пароль для учетной записи хранилища.</span><span class="sxs-lookup"><span data-stu-id="492cc-142">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="492cc-143">Всегда будьте внимательны защитить ключ учетной записи хранилища.</span><span class="sxs-lookup"><span data-stu-id="492cc-143">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="492cc-144">Избегайте распространением их другим пользователям, жестко запрограммированные ее или сохранить в текстовый файл, доступный другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="492cc-144">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="492cc-145">Можно повторно создать ключ с помощью портала Azure, если вы считаете, что он был скомпрометирован.</span><span class="sxs-lookup"><span data-stu-id="492cc-145">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="492cc-146">Для реальных приложений для сохранения строки подключения хранилища рекомендуется в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="492cc-146">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="492cc-147">Чтобы получить строку подключения из файла конфигурации, это можно сделать:</span><span class="sxs-lookup"><span data-stu-id="492cc-147">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L13-L15)]

<span data-ttu-id="492cc-148">С помощью диспетчера конфигурации Azure является необязательным.</span><span class="sxs-lookup"><span data-stu-id="492cc-148">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="492cc-149">Можно также использовать интерфейс API, например .NET Framework `ConfigurationManager` типа.</span><span class="sxs-lookup"><span data-stu-id="492cc-149">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="492cc-150">Синтаксический анализ строки соединения</span><span class="sxs-lookup"><span data-stu-id="492cc-150">Parse the connection string</span></span>

<span data-ttu-id="492cc-151">Чтобы обработать строку подключения, используйте:</span><span class="sxs-lookup"><span data-stu-id="492cc-151">To parse the connection string, use:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L21-L22)]

<span data-ttu-id="492cc-152">Возвращает `CloudStorageAccount`.</span><span class="sxs-lookup"><span data-stu-id="492cc-152">This returns a `CloudStorageAccount`.</span></span>

### <a name="create-the-table-service-client"></a><span data-ttu-id="492cc-153">Создание клиента службы таблиц</span><span class="sxs-lookup"><span data-stu-id="492cc-153">Create the Table service client</span></span>

<span data-ttu-id="492cc-154">`CloudTableClient` Позволяет получить таблицы и сущности в хранилище таблиц.</span><span class="sxs-lookup"><span data-stu-id="492cc-154">The `CloudTableClient` class enables you to retrieve tables and entities in Table storage.</span></span> <span data-ttu-id="492cc-155">Вот один из способов создания клиента службы.</span><span class="sxs-lookup"><span data-stu-id="492cc-155">Here's one way to create the service client:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L28-L29)]

<span data-ttu-id="492cc-156">Теперь вы готовы написать код, который считывает и записывает данные в хранилище таблиц.</span><span class="sxs-lookup"><span data-stu-id="492cc-156">Now you are ready to write code that reads data from and writes data to Table storage.</span></span>

### <a name="create-a-table"></a><span data-ttu-id="492cc-157">Создание таблицы</span><span class="sxs-lookup"><span data-stu-id="492cc-157">Create a table</span></span>

<span data-ttu-id="492cc-158">В этом примере показано, как создать таблицу, если он еще не существует:</span><span class="sxs-lookup"><span data-stu-id="492cc-158">This example shows how to create a table if it does not already exist:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L35-L39)]

### <a name="add-an-entity-to-a-table"></a><span data-ttu-id="492cc-159">Добавление сущности в таблицу</span><span class="sxs-lookup"><span data-stu-id="492cc-159">Add an entity to a table</span></span>

<span data-ttu-id="492cc-160">Сущность должна иметь тип, который наследует от `TableEntity`.</span><span class="sxs-lookup"><span data-stu-id="492cc-160">An entity has to have a type that inherits from `TableEntity`.</span></span> <span data-ttu-id="492cc-161">Вы можете расширить `TableEntity` в усмотрению, но ваш тип *должен* иметь конструктор без параметров.</span><span class="sxs-lookup"><span data-stu-id="492cc-161">You can extend `TableEntity` in any way you like, but your type *must* have a parameter-less constructor.</span></span> <span data-ttu-id="492cc-162">Только свойства, имеющие и `get` и `set` хранятся в таблице Azure.</span><span class="sxs-lookup"><span data-stu-id="492cc-162">Only properties that have both `get` and `set` are stored in your Azure Table.</span></span>

<span data-ttu-id="492cc-163">Секции и ключом строки однозначно определяют сущность в таблице.</span><span class="sxs-lookup"><span data-stu-id="492cc-163">An entity's partition and row key uniquely identify the entity in the table.</span></span> <span data-ttu-id="492cc-164">Сущности с одинаковым ключом секции могут выполняться быстрее, чем с разными ключами секционирования, но с помощью различных разделов обеспечивает улучшенную масштабируемость параллельных операций.</span><span class="sxs-lookup"><span data-stu-id="492cc-164">Entities with the same partition key can be queried faster than those with different partition keys, but using diverse partition keys allows for greater scalability of parallel operations.</span></span>

<span data-ttu-id="492cc-165">Ниже приведен пример `Customer` , использующий `lastName` в качестве ключа секции и `firstName` как ключ строки.</span><span class="sxs-lookup"><span data-stu-id="492cc-165">Here's an example of a `Customer` that uses the `lastName` as the partition key and the `firstName` as the row key.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L45-L52)]

<span data-ttu-id="492cc-166">Теперь добавьте `Customer` в таблицу.</span><span class="sxs-lookup"><span data-stu-id="492cc-166">Now add `Customer` to the table.</span></span> <span data-ttu-id="492cc-167">Чтобы сделать это, создайте `TableOperation` , выполняемый в таблице.</span><span class="sxs-lookup"><span data-stu-id="492cc-167">To do so, create a `TableOperation` that executes on the table.</span></span> <span data-ttu-id="492cc-168">В этом случае вы создаете `Insert` операции.</span><span class="sxs-lookup"><span data-stu-id="492cc-168">In this case, you create an `Insert` operation.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L54-L55)]

### <a name="insert-a-batch-of-entities"></a><span data-ttu-id="492cc-169">Вставка пакета сущностей</span><span class="sxs-lookup"><span data-stu-id="492cc-169">Insert a batch of entities</span></span>

<span data-ttu-id="492cc-170">Пакет сущностей можно вставить в таблицу с помощью одиночную операцию записи.</span><span class="sxs-lookup"><span data-stu-id="492cc-170">You can insert a batch of entities into a table using a single write operation.</span></span> <span data-ttu-id="492cc-171">Пакетные операции позволяют объединить операций в за одно выполнение, но они имеют некоторые ограничения:</span><span class="sxs-lookup"><span data-stu-id="492cc-171">Batch operations allow you to combine operations into a single execution, but they have some restrictions:</span></span>

- <span data-ttu-id="492cc-172">Можно выполнять операции обновления, удаляет и вставляет в одной пакетной операции.</span><span class="sxs-lookup"><span data-stu-id="492cc-172">You can perform updates, deletes, and inserts in the same batch operation.</span></span>
- <span data-ttu-id="492cc-173">Пакетная операция может содержать до 100 сущностей.</span><span class="sxs-lookup"><span data-stu-id="492cc-173">A batch operation can include up to 100 entities.</span></span>
- <span data-ttu-id="492cc-174">Все сущности в пакетной операции должен иметь тот же ключ секционирования.</span><span class="sxs-lookup"><span data-stu-id="492cc-174">All entities in a batch operation must have the same partition key.</span></span>
- <span data-ttu-id="492cc-175">Хотя можно выполнить запрос в пакетной операции, он должен быть только операции в пакете.</span><span class="sxs-lookup"><span data-stu-id="492cc-175">While it is possible to perform a query in a batch operation, it must be the only operation in the batch.</span></span>

<span data-ttu-id="492cc-176">Вот код, который объединяет два вставок в пакетной операции.</span><span class="sxs-lookup"><span data-stu-id="492cc-176">Here's some code that combines two inserts into a batch operation:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L62-L71)]

### <a name="retrieve-all-entities-in-a-partition"></a><span data-ttu-id="492cc-177">Получение всех сущностей в секции</span><span class="sxs-lookup"><span data-stu-id="492cc-177">Retrieve all entities in a partition</span></span>

<span data-ttu-id="492cc-178">Для запроса к таблице для всех сущностей в секции, использовать `TableQuery` объекта.</span><span class="sxs-lookup"><span data-stu-id="492cc-178">To query a table for all entities in a partition, use a `TableQuery` object.</span></span> <span data-ttu-id="492cc-179">Здесь можно отфильтровать для сущностей, где ключ раздела «Smith».</span><span class="sxs-lookup"><span data-stu-id="492cc-179">Here, you filter for entities where "Smith" is the partition key.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L77-L82)]

<span data-ttu-id="492cc-180">Теперь можно распечатать результаты:</span><span class="sxs-lookup"><span data-stu-id="492cc-180">You now print the results:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L84-L85)]


### <a name="retrieve-a-range-of-entities-in-a-partition"></a><span data-ttu-id="492cc-181">Извлечь диапазон сущностей из секции</span><span class="sxs-lookup"><span data-stu-id="492cc-181">Retrieve a range of entities in a partition</span></span>

<span data-ttu-id="492cc-182">Если вы не хотите запросить все сущности в секции, можно указать диапазон, объединяя фильтр ключа секции с фильтром ключа строк.</span><span class="sxs-lookup"><span data-stu-id="492cc-182">If you don't want to query all the entities in a partition, you can specify a range by combining the partition key filter with a row key filter.</span></span> <span data-ttu-id="492cc-183">Здесь используется два фильтра для получения всех сущностей в раздел «Smith» где ключ строки (имя) начинается с буквы, более ранних, чем «M» в алфавите.</span><span class="sxs-lookup"><span data-stu-id="492cc-183">Here, you use two filters to get all entities in the "Smith" partition where the row key (first name) starts with a letter earlier than "M" in the alphabet.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L91-L100)]

<span data-ttu-id="492cc-184">Теперь можно распечатать результаты:</span><span class="sxs-lookup"><span data-stu-id="492cc-184">You now print the results:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L102-L103)]

### <a name="retrieve-a-single-entity"></a><span data-ttu-id="492cc-185">Извлечение отдельной сущности</span><span class="sxs-lookup"><span data-stu-id="492cc-185">Retrieve a single entity</span></span>

<span data-ttu-id="492cc-186">Можно написать запрос, чтобы получить конкретную сущность.</span><span class="sxs-lookup"><span data-stu-id="492cc-186">You can write a query to retrieve a single, specific entity.</span></span> <span data-ttu-id="492cc-187">Здесь используется `TableOperation` для указания клиентов «Ben Smith».</span><span class="sxs-lookup"><span data-stu-id="492cc-187">Here, you use a `TableOperation` to specify the customer "Ben Smith".</span></span> <span data-ttu-id="492cc-188">Вместо коллекции, будет возвращена `Customer`.</span><span class="sxs-lookup"><span data-stu-id="492cc-188">Instead of a collection, you get back a `Customer`.</span></span> <span data-ttu-id="492cc-189">Указание ключа секции и ключ строки в запросе является самым быстрым способом извлечения одной сущности из таблицы службы.</span><span class="sxs-lookup"><span data-stu-id="492cc-189">Specifying both the partition key and the row key in a query is the fastest way to retrieve a single entity from the Table service.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L109-L111)]

<span data-ttu-id="492cc-190">Теперь можно распечатать результаты:</span><span class="sxs-lookup"><span data-stu-id="492cc-190">You now print the results:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L113-L115)]


### <a name="replace-an-entity"></a><span data-ttu-id="492cc-191">Замените сущности</span><span class="sxs-lookup"><span data-stu-id="492cc-191">Replace an entity</span></span>

<span data-ttu-id="492cc-192">Чтобы обновить сущность, получить его из службы таблиц, изменять объект сущности, а затем сохраните изменения к службе таблиц через `Replace` операции.</span><span class="sxs-lookup"><span data-stu-id="492cc-192">To update an entity, retrieve it from the Table service, modify the entity object, and then save the changes back to the Table service using a `Replace` operation.</span></span> <span data-ttu-id="492cc-193">В этом случае сущность, которая полностью заменить на сервере, пока не изменят сущностей на сервере, так как он был извлечен, в этом случае операция завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="492cc-193">This causes the entity to be fully replaced on the server, unless the entity on the server has changed since it was retrieved, in which case the operation fails.</span></span> <span data-ttu-id="492cc-194">Эта ошибка является приложения будет случайно перезаписать изменения из других источников.</span><span class="sxs-lookup"><span data-stu-id="492cc-194">This failure is to prevent your application from inadvertently overwriting changes from other sources.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L121-L128)]

### <a name="insert-or-replace-an-entity"></a><span data-ttu-id="492cc-195">INSERT или замены сущности</span><span class="sxs-lookup"><span data-stu-id="492cc-195">Insert-or-replace an entity</span></span>

<span data-ttu-id="492cc-196">В некоторых случаях вы не знаете, существует ли сущность в таблице.</span><span class="sxs-lookup"><span data-stu-id="492cc-196">Sometimes, you don't know whether an entity exists in the table.</span></span> <span data-ttu-id="492cc-197">И если да, текущие значения, хранящиеся в нем больше не нужны.</span><span class="sxs-lookup"><span data-stu-id="492cc-197">And if it does, the current values stored in it are no longer needed.</span></span> <span data-ttu-id="492cc-198">Можно использовать `InsertOrReplace` для создания сущности или заменить его, если он существует, независимо от их состояния.</span><span class="sxs-lookup"><span data-stu-id="492cc-198">You can use `InsertOrReplace` to create the entity, or replace it if it exists, regardless of its state.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L134-L141)]

### <a name="query-a-subset-of-entity-properties"></a><span data-ttu-id="492cc-199">Запрос подмножества свойств сущности</span><span class="sxs-lookup"><span data-stu-id="492cc-199">Query a subset of entity properties</span></span>

<span data-ttu-id="492cc-200">Запрос таблицы можно получить только несколько свойств с сущностью, а не все из них.</span><span class="sxs-lookup"><span data-stu-id="492cc-200">A table query can retrieve just a few properties from an entity instead of all of them.</span></span> <span data-ttu-id="492cc-201">Этот метод вызывается проекции, может повысить производительность запросов, особенно для больших объектов.</span><span class="sxs-lookup"><span data-stu-id="492cc-201">This technique, called projection, can improve query performance, especially for large entities.</span></span> <span data-ttu-id="492cc-202">Здесь, возвращают только по электронной почте адреса, используя `DynamicTableEntity` и `EntityResolver`.</span><span class="sxs-lookup"><span data-stu-id="492cc-202">Here, you return only email addresses using `DynamicTableEntity` and `EntityResolver`.</span></span> <span data-ttu-id="492cc-203">Обратите внимание, что проекции не поддерживается на эмулятор локального хранилища, поэтому этот код выполняется только в том случае, если вы используете учетную запись в службе таблиц.</span><span class="sxs-lookup"><span data-stu-id="492cc-203">Note that projection is not supported on the local storage emulator, so this code runs only when you're using an account on the Table service.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L147-L158)]

### <a name="retrieve-entities-in-pages-asynchronously"></a><span data-ttu-id="492cc-204">Получение сущностей на страницах асинхронно</span><span class="sxs-lookup"><span data-stu-id="492cc-204">Retrieve entities in pages asynchronously</span></span>

<span data-ttu-id="492cc-205">Если вы читаете большое количество сущностей, и вы хотите их обработка по мере их загрузки, а не ждать их все для возврата, можно использовать сегментированных запрос.</span><span class="sxs-lookup"><span data-stu-id="492cc-205">If you are reading a large number of entities, and you want to process them as they are retrieved rather than waiting for them all to return, you can use a segmented query.</span></span> <span data-ttu-id="492cc-206">Здесь возвращают результаты в страницы с помощью асинхронного рабочего процесса, чтобы выполнение не блокируется во время ожидания для большого набора результатов.</span><span class="sxs-lookup"><span data-stu-id="492cc-206">Here, you return results in pages by using an async workflow so that execution is not blocked while you're waiting for a large set of results to return.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L163-L178)]

<span data-ttu-id="492cc-207">Вы теперь можно выполнить это вычисление синхронно:</span><span class="sxs-lookup"><span data-stu-id="492cc-207">You now execute this computation synchronously:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L180-L180)]

### <a name="delete-an-entity"></a><span data-ttu-id="492cc-208">Удаление сущности</span><span class="sxs-lookup"><span data-stu-id="492cc-208">Delete an entity</span></span>

<span data-ttu-id="492cc-209">Сущность можно удалить после его получения.</span><span class="sxs-lookup"><span data-stu-id="492cc-209">You can delete an entity after you have retrieved it.</span></span> <span data-ttu-id="492cc-210">С обновлением сущности, это не выполняется, если сущность была изменена с момента его загрузки.</span><span class="sxs-lookup"><span data-stu-id="492cc-210">As with updating an entity, this fails if the entity has changed since you retrieved it.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L186-L187)]

### <a name="delete-a-table"></a><span data-ttu-id="492cc-211">Удаление таблицы</span><span class="sxs-lookup"><span data-stu-id="492cc-211">Delete a table</span></span>

<span data-ttu-id="492cc-212">Можно удалить таблицу из учетной записи хранилища.</span><span class="sxs-lookup"><span data-stu-id="492cc-212">You can delete a table from a storage account.</span></span> <span data-ttu-id="492cc-213">Таблицы, которая была удалена, будут недоступны для быть повторно созданы в течение заданного времени после удаления.</span><span class="sxs-lookup"><span data-stu-id="492cc-213">A table that has been deleted will be unavailable to be re-created for a period of time following the deletion.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L193-L193)]

## <a name="next-steps"></a><span data-ttu-id="492cc-214">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="492cc-214">Next steps</span></span>

<span data-ttu-id="492cc-215">Теперь, когда вы узнали основы хранилище таблиц, приведены по следующим ссылкам, Дополнительные сведения о более сложных задач хранилища и API-Интерфейс таблиц Azure Cosmos DB.</span><span class="sxs-lookup"><span data-stu-id="492cc-215">Now that you've learned the basics of Table storage, follow these links to learn about more complex storage tasks and the Azure Cosmos DB Table API.</span></span>

- [<span data-ttu-id="492cc-216">Введение в Azure Cosmos API DB таблиц</span><span class="sxs-lookup"><span data-stu-id="492cc-216">Introduction to Azure Cosmos DB Table API</span></span>](https://docs.microsoft.com/azure/cosmos-db/table-introduction)
- [<span data-ttu-id="492cc-217">Клиентская библиотека хранилища для Справочник по .NET</span><span class="sxs-lookup"><span data-stu-id="492cc-217">Storage Client Library for .NET reference</span></span>](https://docs.microsoft.com/dotnet/api/overview/azure/storage?view=azure-dotnet)
- [<span data-ttu-id="492cc-218">Тип поставщика хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="492cc-218">Azure Storage Type Provider</span></span>](http://fsprojects.github.io/AzureStorageTypeProvider/)
- [<span data-ttu-id="492cc-219">Блог группы разработчиков хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="492cc-219">Azure Storage Team Blog</span></span>](http://blogs.msdn.com/b/windowsazurestorage/)
- [<span data-ttu-id="492cc-220">Настройка строк подключения</span><span class="sxs-lookup"><span data-stu-id="492cc-220">Configuring Connection Strings</span></span>](https://docs.microsoft.com/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="492cc-221">Приступая к работе с хранилищем таблиц Azure в .NET</span><span class="sxs-lookup"><span data-stu-id="492cc-221">Getting Started with Azure Table Storage in .NET</span></span>](https://azure.microsoft.com/resources/samples/storage-table-dotnet-getting-started/)
