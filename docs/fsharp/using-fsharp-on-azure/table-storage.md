---
title: 'Начало работы с хранилищем таблиц Azure, с помощью F #'
description: Хранения структурированных данных в облаке с использованием хранилища таблиц Azure или Azure Cosmos DB.
author: sylvanc
ms.author: phcart
ms.date: 03/26/2018
ms.topic: conceptual
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 50721ca44bbae5c52984b08a30bc87507fbf063d
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="get-started-with-azure-table-storage-and-the-azure-cosmos-db-table-api-using-f"></a><span data-ttu-id="6a560-103">Начало работы с хранилищем таблиц Azure и Azure DB Cosmos таблицы, в API с помощью F #</span><span class="sxs-lookup"><span data-stu-id="6a560-103">Get started with Azure Table storage and the Azure Cosmos DB Table API using F#</span></span> # 

<span data-ttu-id="6a560-104">Хранилище таблиц Azure — это служба, для сохранения структурированных данных NoSQL в облаке.</span><span class="sxs-lookup"><span data-stu-id="6a560-104">Azure Table storage is a service that stores structured NoSQL data in the cloud.</span></span> <span data-ttu-id="6a560-105">Хранилище ключей или атрибут с schemaless конструктора будет хранилище таблиц.</span><span class="sxs-lookup"><span data-stu-id="6a560-105">Table storage is a key/attribute store with a schemaless design.</span></span> <span data-ttu-id="6a560-106">Так как хранилище таблиц schemaless, можно легко адаптировать данных в соответствии с потребностями вашего приложения evolve.</span><span class="sxs-lookup"><span data-stu-id="6a560-106">Because Table storage is schemaless, it's easy to adapt your data as the needs of your application evolve.</span></span> <span data-ttu-id="6a560-107">Доступ к данным — это быстрый и экономичный для всех типов приложений.</span><span class="sxs-lookup"><span data-stu-id="6a560-107">Access to data is fast and cost-effective for all kinds of applications.</span></span> <span data-ttu-id="6a560-108">Хранилище таблиц, обычно значительно меньше стоимости традиционные SQL аналогичные объемами данных.</span><span class="sxs-lookup"><span data-stu-id="6a560-108">Table storage is typically significantly lower in cost than traditional SQL for similar volumes of data.</span></span>

<span data-ttu-id="6a560-109">Хранилище таблиц можно использовать для хранения гибкие наборов данных, таких как данные пользователя для веб-приложений, адресные книги, сведения об устройстве и любого другого типа метаданных, необходимых службе.</span><span class="sxs-lookup"><span data-stu-id="6a560-109">You can use Table storage to store flexible datasets, such as user data for web applications, address books, device information, and any other type of metadata that your service requires.</span></span> <span data-ttu-id="6a560-110">Можно хранить любое число сущностей в таблице, и учетную запись хранилища может содержать любое количество таблиц, вплоть до предела емкости учетной записи хранения.</span><span class="sxs-lookup"><span data-stu-id="6a560-110">You can store any number of entities in a table, and a storage account may contain any number of tables, up to the capacity limit of the storage account.</span></span>

<span data-ttu-id="6a560-111">Azure Cosmos DB предоставляет API-Интерфейс таблиц для приложения, написанные для табличного хранилища Azure и требующих возможностям расширенного выпуска:</span><span class="sxs-lookup"><span data-stu-id="6a560-111">Azure Cosmos DB provides the Table API for applications that are written for Azure Table storage and that require premium capabilities such as:</span></span>

- <span data-ttu-id="6a560-112">Готовое к использованию глобального распространения.</span><span class="sxs-lookup"><span data-stu-id="6a560-112">Turnkey global distribution.</span></span>
- <span data-ttu-id="6a560-113">Выделенный пропускная способность по всему миру.</span><span class="sxs-lookup"><span data-stu-id="6a560-113">Dedicated throughput worldwide.</span></span>
- <span data-ttu-id="6a560-114">Миллисекунды десяти задержки процентиля 99.</span><span class="sxs-lookup"><span data-stu-id="6a560-114">Single-digit millisecond latencies at the 99th percentile.</span></span>
- <span data-ttu-id="6a560-115">Гарантируется, что высокий уровень доступности.</span><span class="sxs-lookup"><span data-stu-id="6a560-115">Guaranteed high availability.</span></span>
- <span data-ttu-id="6a560-116">Автоматическое получателей индексирование.</span><span class="sxs-lookup"><span data-stu-id="6a560-116">Automatic secondary indexing.</span></span>

<span data-ttu-id="6a560-117">Приложения, написанные для табличного хранилища Azure можно перенести на Azure Cosmos DB с помощью API таблицы без изменений кода и воспользоваться преимуществами premium.</span><span class="sxs-lookup"><span data-stu-id="6a560-117">Applications written for Azure Table storage can migrate to Azure Cosmos DB by using the Table API with no code changes and take advantage of premium capabilities.</span></span> <span data-ttu-id="6a560-118">API таблицы содержит клиентские пакеты SDK для .NET, Java, Python и Node.js.</span><span class="sxs-lookup"><span data-stu-id="6a560-118">The Table API has client SDKs available for .NET, Java, Python, and Node.js.</span></span>

<span data-ttu-id="6a560-119">Дополнительные сведения см. в разделе [введение в Azure Cosmos DB таблицы API](https://docs.microsoft.com/azure/cosmos-db/table-introduction).</span><span class="sxs-lookup"><span data-stu-id="6a560-119">For more information, see [Introduction to Azure Cosmos DB Table API](https://docs.microsoft.com/azure/cosmos-db/table-introduction).</span></span>

## <a name="about-this-tutorial"></a><span data-ttu-id="6a560-120">О этого учебника</span><span class="sxs-lookup"><span data-stu-id="6a560-120">About this tutorial</span></span>

<span data-ttu-id="6a560-121">Этот учебник показывает способы написания кода F # для выполнения общих задач с помощью хранилища Azure таблицы или таблицы API DB Cosmos Azure, включая создание и удаление таблицы и вставка, обновление, удаление и запрос данных таблицы.</span><span class="sxs-lookup"><span data-stu-id="6a560-121">This tutorial shows how to write F# code to do some common tasks using Azure Table storage or the Azure Cosmos DB Table API, including creating and deleting a table and inserting, updating, deleting, and querying table data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6a560-122">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="6a560-122">Prerequisites</span></span>

<span data-ttu-id="6a560-123">Чтобы использовать это руководство, необходимо сначала [создать учетную запись хранилища Azure](/azure/storage/storage-create-storage-account) или [учетная запись Azure Cosmos DB](https://azure.microsoft.com/try/cosmosdb/).</span><span class="sxs-lookup"><span data-stu-id="6a560-123">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account) or [Azure Cosmos DB account](https://azure.microsoft.com/try/cosmosdb/).</span></span>


## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="6a560-124">Создание скрипта F # и начала F #, интерактивный</span><span class="sxs-lookup"><span data-stu-id="6a560-124">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="6a560-125">Примеры в этой статье используется в F # приложения или скрипта F #.</span><span class="sxs-lookup"><span data-stu-id="6a560-125">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="6a560-126">Чтобы создать скрипт F #, создайте файл с `.fsx` расширение, например `tables.fsx`, в среде разработки F #.</span><span class="sxs-lookup"><span data-stu-id="6a560-126">To create an F# script, create a file with the `.fsx` extension, for example `tables.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="6a560-127">Затем используйте [диспетчера пакетов](package-management.md) такие как [Paket](https://fsprojects.github.io/Paket/) или [NuGet](https://www.nuget.org/) установка `WindowsAzure.Storage` пакета и ссылка `WindowsAzure.Storage.dll` в скрипте с помощью `#r`директивы.</span><span class="sxs-lookup"><span data-stu-id="6a560-127">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span> <span data-ttu-id="6a560-128">Сделать его снова, `Microsoft.WindowsAzure.ConfigurationManager` для получения имен Microsoft.Azure.</span><span class="sxs-lookup"><span data-stu-id="6a560-128">Do it again for `Microsoft.WindowsAzure.ConfigurationManager` in order to get the Microsoft.Azure namespace.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="6a560-129">Добавьте объявления пространств имен</span><span class="sxs-lookup"><span data-stu-id="6a560-129">Add namespace declarations</span></span>

<span data-ttu-id="6a560-130">Добавьте следующие `open` инструкции в начало `tables.fsx` файла:</span><span class="sxs-lookup"><span data-stu-id="6a560-130">Add the following `open` statements to the top of the `tables.fsx` file:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L1-L5)]

### <a name="get-your-azure-storage-connection-string"></a><span data-ttu-id="6a560-131">Получение строки подключения хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="6a560-131">Get your Azure Storage connection string</span></span>

<span data-ttu-id="6a560-132">При подключении к службе таблиц хранилища Azure, вам потребуется строки подключения для этого учебника.</span><span class="sxs-lookup"><span data-stu-id="6a560-132">If you're connecting to Azure Storage Table service, you'll need your connection string for this tutorial.</span></span> <span data-ttu-id="6a560-133">Можно скопировать строку подключения на портале Azure.</span><span class="sxs-lookup"><span data-stu-id="6a560-133">You can copy your connection string from the Azure portal.</span></span> <span data-ttu-id="6a560-134">Дополнительные сведения о строках соединения см. в разделе [Настройка строки подключения хранилища](/azure/storage/storage-configure-connection-string).</span><span class="sxs-lookup"><span data-stu-id="6a560-134">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

### <a name="get-your-azure-cosmos-db-connection-string"></a><span data-ttu-id="6a560-135">Получить строку подключения к базе данных Azure Cosmos</span><span class="sxs-lookup"><span data-stu-id="6a560-135">Get your Azure Cosmos DB connection string</span></span>

<span data-ttu-id="6a560-136">При подключении к базе данных Azure Cosmos, вам потребуется строки подключения для этого учебника.</span><span class="sxs-lookup"><span data-stu-id="6a560-136">If you're connecting to Azure Cosmos DB, you'll need your connection string for this tutorial.</span></span> <span data-ttu-id="6a560-137">Можно скопировать строку подключения на портале Azure.</span><span class="sxs-lookup"><span data-stu-id="6a560-137">You can copy your connection string from the Azure portal.</span></span> <span data-ttu-id="6a560-138">На портале Azure в учетной записи Cosmos DB перейдите к **параметры** > **строка подключения**и нажмите кнопку **копирования** кнопку, чтобы скопировать первичный подключение Строка.</span><span class="sxs-lookup"><span data-stu-id="6a560-138">In the Azure portal, in your Cosmos DB account, go to **Settings** > **Connection String**, and click the **Copy** button to copy your Primary Connection String.</span></span> 

<span data-ttu-id="6a560-139">В учебнике введите строку подключения в скрипте, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="6a560-139">For the tutorial, enter your connection string in your script, like the following example:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L11-L11)]

<span data-ttu-id="6a560-140">Однако это **не рекомендуется** для реальных проектах.</span><span class="sxs-lookup"><span data-stu-id="6a560-140">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="6a560-141">Ключ учетной записи хранилища аналогична корневой пароль для учетной записи хранилища.</span><span class="sxs-lookup"><span data-stu-id="6a560-141">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="6a560-142">Всегда будьте внимательны защитить ключ учетной записи хранилища.</span><span class="sxs-lookup"><span data-stu-id="6a560-142">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="6a560-143">Избегайте распространением их другим пользователям, жестко запрограммированные ее или сохранить в текстовый файл, доступный другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="6a560-143">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="6a560-144">Можно повторно создать ключ с помощью портала Azure, если вы считаете, что он был скомпрометирован.</span><span class="sxs-lookup"><span data-stu-id="6a560-144">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="6a560-145">Для реальных приложений для сохранения строки подключения хранилища рекомендуется в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="6a560-145">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="6a560-146">Чтобы получить строку подключения из файла конфигурации, это можно сделать:</span><span class="sxs-lookup"><span data-stu-id="6a560-146">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L13-L15)]

<span data-ttu-id="6a560-147">С помощью диспетчера конфигурации Azure является необязательным.</span><span class="sxs-lookup"><span data-stu-id="6a560-147">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="6a560-148">Можно также использовать интерфейс API, например .NET Framework `ConfigurationManager` типа.</span><span class="sxs-lookup"><span data-stu-id="6a560-148">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="6a560-149">Синтаксический анализ строки соединения</span><span class="sxs-lookup"><span data-stu-id="6a560-149">Parse the connection string</span></span>

<span data-ttu-id="6a560-150">Чтобы обработать строку подключения, используйте:</span><span class="sxs-lookup"><span data-stu-id="6a560-150">To parse the connection string, use:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L21-L22)]

<span data-ttu-id="6a560-151">Возвращает `CloudStorageAccount`.</span><span class="sxs-lookup"><span data-stu-id="6a560-151">This returns a `CloudStorageAccount`.</span></span>

### <a name="create-the-table-service-client"></a><span data-ttu-id="6a560-152">Создание клиента службы таблиц</span><span class="sxs-lookup"><span data-stu-id="6a560-152">Create the Table service client</span></span>

<span data-ttu-id="6a560-153">`CloudTableClient` Позволяет получить таблицы и сущности в хранилище таблиц.</span><span class="sxs-lookup"><span data-stu-id="6a560-153">The `CloudTableClient` class enables you to retrieve tables and entities in Table storage.</span></span> <span data-ttu-id="6a560-154">Вот один из способов создания клиента службы.</span><span class="sxs-lookup"><span data-stu-id="6a560-154">Here's one way to create the service client:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L28-L29)]

<span data-ttu-id="6a560-155">Теперь вы готовы написать код, который считывает и записывает данные в хранилище таблиц.</span><span class="sxs-lookup"><span data-stu-id="6a560-155">Now you are ready to write code that reads data from and writes data to Table storage.</span></span>

### <a name="create-a-table"></a><span data-ttu-id="6a560-156">Создание таблицы</span><span class="sxs-lookup"><span data-stu-id="6a560-156">Create a table</span></span>

<span data-ttu-id="6a560-157">В этом примере показано, как создать таблицу, если он еще не существует:</span><span class="sxs-lookup"><span data-stu-id="6a560-157">This example shows how to create a table if it does not already exist:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L35-L39)]

### <a name="add-an-entity-to-a-table"></a><span data-ttu-id="6a560-158">Добавление сущности в таблицу</span><span class="sxs-lookup"><span data-stu-id="6a560-158">Add an entity to a table</span></span>

<span data-ttu-id="6a560-159">Сущность должна иметь тип, который наследует от `TableEntity`.</span><span class="sxs-lookup"><span data-stu-id="6a560-159">An entity has to have a type that inherits from `TableEntity`.</span></span> <span data-ttu-id="6a560-160">Вы можете расширить `TableEntity` в усмотрению, но ваш тип *должен* иметь конструктор без параметров.</span><span class="sxs-lookup"><span data-stu-id="6a560-160">You can extend `TableEntity` in any way you like, but your type *must* have a parameter-less constructor.</span></span> <span data-ttu-id="6a560-161">Только свойства, имеющие и `get` и `set` хранятся в таблице Azure.</span><span class="sxs-lookup"><span data-stu-id="6a560-161">Only properties that have both `get` and `set` are stored in your Azure Table.</span></span>

<span data-ttu-id="6a560-162">Секции и ключом строки однозначно определяют сущность в таблице.</span><span class="sxs-lookup"><span data-stu-id="6a560-162">An entity's partition and row key uniquely identify the entity in the table.</span></span> <span data-ttu-id="6a560-163">Сущности с одинаковым ключом секции могут выполняться быстрее, чем с разными ключами секционирования, но с помощью различных разделов обеспечивает улучшенную масштабируемость параллельных операций.</span><span class="sxs-lookup"><span data-stu-id="6a560-163">Entities with the same partition key can be queried faster than those with different partition keys, but using diverse partition keys allows for greater scalability of parallel operations.</span></span>

<span data-ttu-id="6a560-164">Ниже приведен пример `Customer` , использующий `lastName` в качестве ключа секции и `firstName` как ключ строки.</span><span class="sxs-lookup"><span data-stu-id="6a560-164">Here's an example of a `Customer` that uses the `lastName` as the partition key and the `firstName` as the row key.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L45-L52)]

<span data-ttu-id="6a560-165">Теперь добавьте `Customer` в таблицу.</span><span class="sxs-lookup"><span data-stu-id="6a560-165">Now add `Customer` to the table.</span></span> <span data-ttu-id="6a560-166">Чтобы сделать это, создайте `TableOperation` , выполняемый в таблице.</span><span class="sxs-lookup"><span data-stu-id="6a560-166">To do so, create a `TableOperation` that executes on the table.</span></span> <span data-ttu-id="6a560-167">В этом случае вы создаете `Insert` операции.</span><span class="sxs-lookup"><span data-stu-id="6a560-167">In this case, you create an `Insert` operation.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L54-L55)]

### <a name="insert-a-batch-of-entities"></a><span data-ttu-id="6a560-168">Вставка пакета сущностей</span><span class="sxs-lookup"><span data-stu-id="6a560-168">Insert a batch of entities</span></span>

<span data-ttu-id="6a560-169">Пакет сущностей можно вставить в таблицу с помощью одиночную операцию записи.</span><span class="sxs-lookup"><span data-stu-id="6a560-169">You can insert a batch of entities into a table using a single write operation.</span></span> <span data-ttu-id="6a560-170">Пакетные операции позволяют объединить операций в за одно выполнение, но они имеют некоторые ограничения:</span><span class="sxs-lookup"><span data-stu-id="6a560-170">Batch operations allow you to combine operations into a single execution, but they have some restrictions:</span></span>

- <span data-ttu-id="6a560-171">Можно выполнять операции обновления, удаляет и вставляет в одной пакетной операции.</span><span class="sxs-lookup"><span data-stu-id="6a560-171">You can perform updates, deletes, and inserts in the same batch operation.</span></span>
- <span data-ttu-id="6a560-172">Пакетная операция может содержать до 100 сущностей.</span><span class="sxs-lookup"><span data-stu-id="6a560-172">A batch operation can include up to 100 entities.</span></span>
- <span data-ttu-id="6a560-173">Все сущности в пакетной операции должен иметь тот же ключ секционирования.</span><span class="sxs-lookup"><span data-stu-id="6a560-173">All entities in a batch operation must have the same partition key.</span></span>
- <span data-ttu-id="6a560-174">Хотя можно выполнить запрос в пакетной операции, он должен быть только операции в пакете.</span><span class="sxs-lookup"><span data-stu-id="6a560-174">While it is possible to perform a query in a batch operation, it must be the only operation in the batch.</span></span>

<span data-ttu-id="6a560-175">Вот код, который объединяет два вставок в пакетной операции.</span><span class="sxs-lookup"><span data-stu-id="6a560-175">Here's some code that combines two inserts into a batch operation:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L62-L71)]

### <a name="retrieve-all-entities-in-a-partition"></a><span data-ttu-id="6a560-176">Получение всех сущностей в секции</span><span class="sxs-lookup"><span data-stu-id="6a560-176">Retrieve all entities in a partition</span></span>

<span data-ttu-id="6a560-177">Для запроса к таблице для всех сущностей в секции, использовать `TableQuery` объекта.</span><span class="sxs-lookup"><span data-stu-id="6a560-177">To query a table for all entities in a partition, use a `TableQuery` object.</span></span> <span data-ttu-id="6a560-178">Здесь можно отфильтровать для сущностей, где ключ раздела «Smith».</span><span class="sxs-lookup"><span data-stu-id="6a560-178">Here, you filter for entities where "Smith" is the partition key.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L77-L82)]

<span data-ttu-id="6a560-179">Теперь можно распечатать результаты:</span><span class="sxs-lookup"><span data-stu-id="6a560-179">You now print the results:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L84-L85)]


### <a name="retrieve-a-range-of-entities-in-a-partition"></a><span data-ttu-id="6a560-180">Извлечь диапазон сущностей из секции</span><span class="sxs-lookup"><span data-stu-id="6a560-180">Retrieve a range of entities in a partition</span></span>

<span data-ttu-id="6a560-181">Если вы не хотите запросить все сущности в секции, можно указать диапазон, объединяя фильтр ключа секции с фильтром ключа строк.</span><span class="sxs-lookup"><span data-stu-id="6a560-181">If you don't want to query all the entities in a partition, you can specify a range by combining the partition key filter with a row key filter.</span></span> <span data-ttu-id="6a560-182">Здесь используется два фильтра для получения всех сущностей в раздел «Smith» где ключ строки (имя) начинается с буквы, более ранних, чем «M» в алфавите.</span><span class="sxs-lookup"><span data-stu-id="6a560-182">Here, you use two filters to get all entities in the "Smith" partition where the row key (first name) starts with a letter earlier than "M" in the alphabet.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L91-L100)]

<span data-ttu-id="6a560-183">Теперь можно распечатать результаты:</span><span class="sxs-lookup"><span data-stu-id="6a560-183">You now print the results:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L102-L103)]

### <a name="retrieve-a-single-entity"></a><span data-ttu-id="6a560-184">Извлечение отдельной сущности</span><span class="sxs-lookup"><span data-stu-id="6a560-184">Retrieve a single entity</span></span>

<span data-ttu-id="6a560-185">Можно написать запрос, чтобы получить конкретную сущность.</span><span class="sxs-lookup"><span data-stu-id="6a560-185">You can write a query to retrieve a single, specific entity.</span></span> <span data-ttu-id="6a560-186">Здесь используется `TableOperation` для указания клиентов «Ben Smith».</span><span class="sxs-lookup"><span data-stu-id="6a560-186">Here, you use a `TableOperation` to specify the customer "Ben Smith".</span></span> <span data-ttu-id="6a560-187">Вместо коллекции, будет возвращена `Customer`.</span><span class="sxs-lookup"><span data-stu-id="6a560-187">Instead of a collection, you get back a `Customer`.</span></span> <span data-ttu-id="6a560-188">Указание ключа секции и ключ строки в запросе является самым быстрым способом извлечения одной сущности из таблицы службы.</span><span class="sxs-lookup"><span data-stu-id="6a560-188">Specifying both the partition key and the row key in a query is the fastest way to retrieve a single entity from the Table service.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L109-L111)]

<span data-ttu-id="6a560-189">Теперь можно распечатать результаты:</span><span class="sxs-lookup"><span data-stu-id="6a560-189">You now print the results:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L113-L115)]


### <a name="replace-an-entity"></a><span data-ttu-id="6a560-190">Замените сущности</span><span class="sxs-lookup"><span data-stu-id="6a560-190">Replace an entity</span></span>

<span data-ttu-id="6a560-191">Чтобы обновить сущность, получить его из службы таблиц, изменять объект сущности, а затем сохраните изменения к службе таблиц через `Replace` операции.</span><span class="sxs-lookup"><span data-stu-id="6a560-191">To update an entity, retrieve it from the Table service, modify the entity object, and then save the changes back to the Table service using a `Replace` operation.</span></span> <span data-ttu-id="6a560-192">В этом случае сущность, которая полностью заменить на сервере, пока не изменят сущностей на сервере, так как он был извлечен, в этом случае операция завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="6a560-192">This causes the entity to be fully replaced on the server, unless the entity on the server has changed since it was retrieved, in which case the operation fails.</span></span> <span data-ttu-id="6a560-193">Эта ошибка является приложения будет случайно перезаписать изменения из других источников.</span><span class="sxs-lookup"><span data-stu-id="6a560-193">This failure is to prevent your application from inadvertently overwriting changes from other sources.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L121-L128)]

### <a name="insert-or-replace-an-entity"></a><span data-ttu-id="6a560-194">INSERT или замены сущности</span><span class="sxs-lookup"><span data-stu-id="6a560-194">Insert-or-replace an entity</span></span>

<span data-ttu-id="6a560-195">В некоторых случаях вы не знаете, существует ли сущность в таблице.</span><span class="sxs-lookup"><span data-stu-id="6a560-195">Sometimes, you don't know whether an entity exists in the table.</span></span> <span data-ttu-id="6a560-196">И если да, текущие значения, хранящиеся в нем больше не нужны.</span><span class="sxs-lookup"><span data-stu-id="6a560-196">And if it does, the current values stored in it are no longer needed.</span></span> <span data-ttu-id="6a560-197">Можно использовать `InsertOrReplace` для создания сущности или заменить его, если он существует, независимо от их состояния.</span><span class="sxs-lookup"><span data-stu-id="6a560-197">You can use `InsertOrReplace` to create the entity, or replace it if it exists, regardless of its state.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L134-L141)]

### <a name="query-a-subset-of-entity-properties"></a><span data-ttu-id="6a560-198">Запрос подмножества свойств сущности</span><span class="sxs-lookup"><span data-stu-id="6a560-198">Query a subset of entity properties</span></span>

<span data-ttu-id="6a560-199">Запрос таблицы можно получить только несколько свойств с сущностью, а не все из них.</span><span class="sxs-lookup"><span data-stu-id="6a560-199">A table query can retrieve just a few properties from an entity instead of all of them.</span></span> <span data-ttu-id="6a560-200">Этот метод вызывается проекции, может повысить производительность запросов, особенно для больших объектов.</span><span class="sxs-lookup"><span data-stu-id="6a560-200">This technique, called projection, can improve query performance, especially for large entities.</span></span> <span data-ttu-id="6a560-201">Здесь, возвращают только по электронной почте адреса, используя `DynamicTableEntity` и `EntityResolver`.</span><span class="sxs-lookup"><span data-stu-id="6a560-201">Here, you return only email addresses using `DynamicTableEntity` and `EntityResolver`.</span></span> <span data-ttu-id="6a560-202">Обратите внимание, что проекции не поддерживается на эмулятор локального хранилища, поэтому этот код выполняется только в том случае, если вы используете учетную запись в службе таблиц.</span><span class="sxs-lookup"><span data-stu-id="6a560-202">Note that projection is not supported on the local storage emulator, so this code runs only when you're using an account on the Table service.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L147-L158)]

### <a name="retrieve-entities-in-pages-asynchronously"></a><span data-ttu-id="6a560-203">Получение сущностей на страницах асинхронно</span><span class="sxs-lookup"><span data-stu-id="6a560-203">Retrieve entities in pages asynchronously</span></span>

<span data-ttu-id="6a560-204">Если вы читаете большое количество сущностей, и вы хотите их обработка по мере их загрузки, а не ждать их все для возврата, можно использовать сегментированных запрос.</span><span class="sxs-lookup"><span data-stu-id="6a560-204">If you are reading a large number of entities, and you want to process them as they are retrieved rather than waiting for them all to return, you can use a segmented query.</span></span> <span data-ttu-id="6a560-205">Здесь возвращают результаты в страницы с помощью асинхронного рабочего процесса, чтобы выполнение не блокируется во время ожидания для большого набора результатов.</span><span class="sxs-lookup"><span data-stu-id="6a560-205">Here, you return results in pages by using an async workflow so that execution is not blocked while you're waiting for a large set of results to return.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L163-L178)]

<span data-ttu-id="6a560-206">Вы теперь можно выполнить это вычисление синхронно:</span><span class="sxs-lookup"><span data-stu-id="6a560-206">You now execute this computation synchronously:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L180-L180)]

### <a name="delete-an-entity"></a><span data-ttu-id="6a560-207">Удаление сущности</span><span class="sxs-lookup"><span data-stu-id="6a560-207">Delete an entity</span></span>

<span data-ttu-id="6a560-208">Сущность можно удалить после его получения.</span><span class="sxs-lookup"><span data-stu-id="6a560-208">You can delete an entity after you have retrieved it.</span></span> <span data-ttu-id="6a560-209">С обновлением сущности, это не выполняется, если сущность была изменена с момента его загрузки.</span><span class="sxs-lookup"><span data-stu-id="6a560-209">As with updating an entity, this fails if the entity has changed since you retrieved it.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L186-L187)]

### <a name="delete-a-table"></a><span data-ttu-id="6a560-210">Удаление таблицы</span><span class="sxs-lookup"><span data-stu-id="6a560-210">Delete a table</span></span>

<span data-ttu-id="6a560-211">Можно удалить таблицу из учетной записи хранилища.</span><span class="sxs-lookup"><span data-stu-id="6a560-211">You can delete a table from a storage account.</span></span> <span data-ttu-id="6a560-212">Таблицы, которая была удалена, будут недоступны для быть повторно созданы в течение заданного времени после удаления.</span><span class="sxs-lookup"><span data-stu-id="6a560-212">A table that has been deleted will be unavailable to be re-created for a period of time following the deletion.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L193-L193)]

## <a name="next-steps"></a><span data-ttu-id="6a560-213">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="6a560-213">Next steps</span></span>

<span data-ttu-id="6a560-214">Теперь, когда вы узнали основы хранилище таблиц, приведены по следующим ссылкам, Дополнительные сведения о более сложных задач хранилища и API-Интерфейс таблиц Azure Cosmos DB.</span><span class="sxs-lookup"><span data-stu-id="6a560-214">Now that you've learned the basics of Table storage, follow these links to learn about more complex storage tasks and the Azure Cosmos DB Table API.</span></span>

- [<span data-ttu-id="6a560-215">Введение в Azure Cosmos API DB таблиц</span><span class="sxs-lookup"><span data-stu-id="6a560-215">Introduction to Azure Cosmos DB Table API</span></span>](https://docs.microsoft.com/azure/cosmos-db/table-introduction)
- [<span data-ttu-id="6a560-216">Клиентская библиотека хранилища для Справочник по .NET</span><span class="sxs-lookup"><span data-stu-id="6a560-216">Storage Client Library for .NET reference</span></span>](https://docs.microsoft.com/dotnet/api/overview/azure/storage?view=azure-dotnet)
- [<span data-ttu-id="6a560-217">Тип поставщика хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="6a560-217">Azure Storage Type Provider</span></span>](http://fsprojects.github.io/AzureStorageTypeProvider/)
- [<span data-ttu-id="6a560-218">Блог группы разработчиков хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="6a560-218">Azure Storage Team Blog</span></span>](http://blogs.msdn.com/b/windowsazurestorage/)
- [<span data-ttu-id="6a560-219">Настройка строк подключения</span><span class="sxs-lookup"><span data-stu-id="6a560-219">Configuring Connection Strings</span></span>](https://docs.microsoft.com/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="6a560-220">Приступая к работе с хранилищем таблиц Azure в .NET</span><span class="sxs-lookup"><span data-stu-id="6a560-220">Getting Started with Azure Table Storage in .NET</span></span>](https://azure.microsoft.com/resources/samples/storage-table-dotnet-getting-started/)
