---
title: Начало работы с хранилищем таблиц Azure с использованиемF#
description: Store структурированных данных в облаке, используя хранилище таблиц Azure или Azure Cosmos DB.
author: sylvanc
ms.date: 03/26/2018
ms.openlocfilehash: 2b74a33023065ea809c2d7eb6202b1a254018422
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56966012"
---
# <a name="get-started-with-azure-table-storage-and-the-azure-cosmos-db-table-api-using-f"></a><span data-ttu-id="5da00-103">Начало работы с хранилищем таблиц Azure и API таблицы Azure Cosmos DB с помощью языка F\#</span><span class="sxs-lookup"><span data-stu-id="5da00-103">Get started with Azure Table storage and the Azure Cosmos DB Table API using F\#</span></span>

<span data-ttu-id="5da00-104">Хранилище таблиц Azure — это служба, которая хранит структурированные данные NoSQL в облаке.</span><span class="sxs-lookup"><span data-stu-id="5da00-104">Azure Table storage is a service that stores structured NoSQL data in the cloud.</span></span> <span data-ttu-id="5da00-105">Хранилище таблиц — это хранилище ключей и атрибутов с бессхемной конструкцией.</span><span class="sxs-lookup"><span data-stu-id="5da00-105">Table storage is a key/attribute store with a schemaless design.</span></span> <span data-ttu-id="5da00-106">Поскольку табличное хранилище является бессхемным, можно легко адаптировать данные по мере расширения приложения.</span><span class="sxs-lookup"><span data-stu-id="5da00-106">Because Table storage is schemaless, it's easy to adapt your data as the needs of your application evolve.</span></span> <span data-ttu-id="5da00-107">Доступ к данным — быстрое и экономичное для всех типов приложений.</span><span class="sxs-lookup"><span data-stu-id="5da00-107">Access to data is fast and cost-effective for all kinds of applications.</span></span> <span data-ttu-id="5da00-108">Табличное хранилище обычно значительно дешевле, чем традиционные SQL для похожих объемов данных.</span><span class="sxs-lookup"><span data-stu-id="5da00-108">Table storage is typically significantly lower in cost than traditional SQL for similar volumes of data.</span></span>

<span data-ttu-id="5da00-109">Хранилище таблиц можно использовать для хранения гибких наборов данных, таких как данные пользователя для веб-приложений, адресных книг, сведений об устройстве и любого другого типа метаданных, которые требуются вашей службе.</span><span class="sxs-lookup"><span data-stu-id="5da00-109">You can use Table storage to store flexible datasets, such as user data for web applications, address books, device information, and any other type of metadata that your service requires.</span></span> <span data-ttu-id="5da00-110">Можно хранить любое число сущностей в таблице, и учетную запись хранения может содержать любое количество таблиц в пределах емкости учетной записи хранения.</span><span class="sxs-lookup"><span data-stu-id="5da00-110">You can store any number of entities in a table, and a storage account may contain any number of tables, up to the capacity limit of the storage account.</span></span>

<span data-ttu-id="5da00-111">Azure Cosmos DB предоставляет API таблицы для приложений, написанные для хранилища таблиц Azure и которым требуется первоклассные возможности, такие как:</span><span class="sxs-lookup"><span data-stu-id="5da00-111">Azure Cosmos DB provides the Table API for applications that are written for Azure Table storage and that require premium capabilities such as:</span></span>

- <span data-ttu-id="5da00-112">Комплексные возможности глобального распределения.</span><span class="sxs-lookup"><span data-stu-id="5da00-112">Turnkey global distribution.</span></span>
- <span data-ttu-id="5da00-113">Выделенная пропускная способность по всему миру.</span><span class="sxs-lookup"><span data-stu-id="5da00-113">Dedicated throughput worldwide.</span></span>
- <span data-ttu-id="5da00-114">Миллисекунд задержки на 99-го процентиля.</span><span class="sxs-lookup"><span data-stu-id="5da00-114">Single-digit millisecond latencies at the 99th percentile.</span></span>
- <span data-ttu-id="5da00-115">Гарантированно высокий уровень доступности.</span><span class="sxs-lookup"><span data-stu-id="5da00-115">Guaranteed high availability.</span></span>
- <span data-ttu-id="5da00-116">Автоматическое вторичное индексирование.</span><span class="sxs-lookup"><span data-stu-id="5da00-116">Automatic secondary indexing.</span></span>

<span data-ttu-id="5da00-117">Приложения, написанные для хранилища таблиц Azure можно перенести в Azure Cosmos DB с помощью API таблицы без изменения кода и воспользоваться возможностями уровня "премиум".</span><span class="sxs-lookup"><span data-stu-id="5da00-117">Applications written for Azure Table storage can migrate to Azure Cosmos DB by using the Table API with no code changes and take advantage of premium capabilities.</span></span> <span data-ttu-id="5da00-118">API таблицы включает клиентские пакеты SDK для .NET, Java, Python и Node.js.</span><span class="sxs-lookup"><span data-stu-id="5da00-118">The Table API has client SDKs available for .NET, Java, Python, and Node.js.</span></span>

<span data-ttu-id="5da00-119">Дополнительные сведения см. в разделе [введение в API таблицы Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/table-introduction).</span><span class="sxs-lookup"><span data-stu-id="5da00-119">For more information, see [Introduction to Azure Cosmos DB Table API](https://docs.microsoft.com/azure/cosmos-db/table-introduction).</span></span>

## <a name="about-this-tutorial"></a><span data-ttu-id="5da00-120">Сведения об этом руководстве</span><span class="sxs-lookup"><span data-stu-id="5da00-120">About this tutorial</span></span>

<span data-ttu-id="5da00-121">Этот учебник демонстрирует запись F# код для выполнения некоторых общих задач, используя хранилище таблиц Azure или Azure Cosmos DB API таблиц, включая создание и удаление таблицы и вставки, обновления, удаления и запроса данных таблицы.</span><span class="sxs-lookup"><span data-stu-id="5da00-121">This tutorial shows how to write F# code to do some common tasks using Azure Table storage or the Azure Cosmos DB Table API, including creating and deleting a table and inserting, updating, deleting, and querying table data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5da00-122">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="5da00-122">Prerequisites</span></span>

<span data-ttu-id="5da00-123">Чтобы использовать это руководство, необходимо сначала [создать учетную запись хранения](/azure/storage/storage-create-storage-account) или [учетной записи Azure Cosmos DB](https://azure.microsoft.com/try/cosmosdb/).</span><span class="sxs-lookup"><span data-stu-id="5da00-123">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account) or [Azure Cosmos DB account](https://azure.microsoft.com/try/cosmosdb/).</span></span>


## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="5da00-124">Создание F# сценариев и запустить F# интерактивный</span><span class="sxs-lookup"><span data-stu-id="5da00-124">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="5da00-125">Примеры в этой статье можно использовать в любом F# приложения или F# скрипта.</span><span class="sxs-lookup"><span data-stu-id="5da00-125">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="5da00-126">Чтобы создать F# скрипт, создайте файл с `.fsx` расширение, например `tables.fsx`в вашей F# среды разработки.</span><span class="sxs-lookup"><span data-stu-id="5da00-126">To create an F# script, create a file with the `.fsx` extension, for example `tables.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="5da00-127">Затем используйте [диспетчера пакетов](package-management.md) например [Paket](https://fsprojects.github.io/Paket/) или [NuGet](https://www.nuget.org/) для установки `WindowsAzure.Storage` пакета и ссылка `WindowsAzure.Storage.dll` в скрипте, с помощью `#r`директива.</span><span class="sxs-lookup"><span data-stu-id="5da00-127">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span> <span data-ttu-id="5da00-128">Сделать это за `Microsoft.WindowsAzure.ConfigurationManager` для получения Microsoft.Azure пространства имен.</span><span class="sxs-lookup"><span data-stu-id="5da00-128">Do it again for `Microsoft.WindowsAzure.ConfigurationManager` in order to get the Microsoft.Azure namespace.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="5da00-129">Добавьте объявления пространств имен</span><span class="sxs-lookup"><span data-stu-id="5da00-129">Add namespace declarations</span></span>

<span data-ttu-id="5da00-130">Добавьте следующий `open` операторы в верхнюю часть `tables.fsx` файла:</span><span class="sxs-lookup"><span data-stu-id="5da00-130">Add the following `open` statements to the top of the `tables.fsx` file:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L1-L5)]

### <a name="get-your-azure-storage-connection-string"></a><span data-ttu-id="5da00-131">Получить строку подключения хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="5da00-131">Get your Azure Storage connection string</span></span>

<span data-ttu-id="5da00-132">Если вы подключаетесь к таблиц службы хранилища Azure, нужно будет строки подключения в этом руководстве.</span><span class="sxs-lookup"><span data-stu-id="5da00-132">If you're connecting to Azure Storage Table service, you'll need your connection string for this tutorial.</span></span> <span data-ttu-id="5da00-133">Можно скопировать строку подключения на портале Azure.</span><span class="sxs-lookup"><span data-stu-id="5da00-133">You can copy your connection string from the Azure portal.</span></span> <span data-ttu-id="5da00-134">Дополнительные сведения о строках подключения см. в разделе [Настройка строк подключения службы хранилища](/azure/storage/storage-configure-connection-string).</span><span class="sxs-lookup"><span data-stu-id="5da00-134">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

### <a name="get-your-azure-cosmos-db-connection-string"></a><span data-ttu-id="5da00-135">Получить строку подключения к Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="5da00-135">Get your Azure Cosmos DB connection string</span></span>

<span data-ttu-id="5da00-136">Если вы подключаетесь к Azure Cosmos DB, нужно будет строки подключения в этом руководстве.</span><span class="sxs-lookup"><span data-stu-id="5da00-136">If you're connecting to Azure Cosmos DB, you'll need your connection string for this tutorial.</span></span> <span data-ttu-id="5da00-137">Можно скопировать строку подключения на портале Azure.</span><span class="sxs-lookup"><span data-stu-id="5da00-137">You can copy your connection string from the Azure portal.</span></span> <span data-ttu-id="5da00-138">На портале Azure в учетной записи Cosmos DB, перейдите к **параметры** > **строку подключения**и нажмите кнопку **копирования** кнопку, чтобы скопировать первичный подключения Строка.</span><span class="sxs-lookup"><span data-stu-id="5da00-138">In the Azure portal, in your Cosmos DB account, go to **Settings** > **Connection String**, and click the **Copy** button to copy your Primary Connection String.</span></span> 

<span data-ttu-id="5da00-139">Для этого руководства введите строку подключения в скрипте, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="5da00-139">For the tutorial, enter your connection string in your script, like the following example:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L11-L11)]

<span data-ttu-id="5da00-140">Однако это **не рекомендуется** реальных проектов.</span><span class="sxs-lookup"><span data-stu-id="5da00-140">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="5da00-141">Ключ учетной записи хранения похож на корневой пароль для учетной записи хранения.</span><span class="sxs-lookup"><span data-stu-id="5da00-141">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="5da00-142">Не забудьте защитить ключ учетной записи хранения.</span><span class="sxs-lookup"><span data-stu-id="5da00-142">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="5da00-143">Избегайте распределения его другим пользователям, в коде, или сохранить его в текстовом файле, доступном другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="5da00-143">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="5da00-144">Можно повторно создать ключ с помощью портала Azure, если вы считаете, что он мог быть скомпрометирован.</span><span class="sxs-lookup"><span data-stu-id="5da00-144">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="5da00-145">Для реальных приложений, чтобы сохранить строку подключения хранилища рекомендуется в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="5da00-145">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="5da00-146">Чтобы получить строку подключения из файла конфигурации, это можно сделать:</span><span class="sxs-lookup"><span data-stu-id="5da00-146">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L13-L15)]

<span data-ttu-id="5da00-147">Использование диспетчера конфигураций Azure не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="5da00-147">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="5da00-148">Можно также использовать API, например .NET Framework `ConfigurationManager` типа.</span><span class="sxs-lookup"><span data-stu-id="5da00-148">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="5da00-149">Проанализировать строку подключения</span><span class="sxs-lookup"><span data-stu-id="5da00-149">Parse the connection string</span></span>

<span data-ttu-id="5da00-150">Чтобы проанализировать строку подключения, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5da00-150">To parse the connection string, use:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L21-L22)]

<span data-ttu-id="5da00-151">Эта команда возвращает `CloudStorageAccount`.</span><span class="sxs-lookup"><span data-stu-id="5da00-151">This returns a `CloudStorageAccount`.</span></span>

### <a name="create-the-table-service-client"></a><span data-ttu-id="5da00-152">Создание клиента службы таблиц</span><span class="sxs-lookup"><span data-stu-id="5da00-152">Create the Table service client</span></span>

<span data-ttu-id="5da00-153">`CloudTableClient` Класс позволяет получать таблицы и сущности в хранилище таблиц.</span><span class="sxs-lookup"><span data-stu-id="5da00-153">The `CloudTableClient` class enables you to retrieve tables and entities in Table storage.</span></span> <span data-ttu-id="5da00-154">Вот один из способов создания клиента службы:</span><span class="sxs-lookup"><span data-stu-id="5da00-154">Here's one way to create the service client:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L28-L29)]

<span data-ttu-id="5da00-155">Теперь вы готовы написать код, который считывает и записывает данные в хранилище таблиц.</span><span class="sxs-lookup"><span data-stu-id="5da00-155">Now you are ready to write code that reads data from and writes data to Table storage.</span></span>

### <a name="create-a-table"></a><span data-ttu-id="5da00-156">Создание таблицы</span><span class="sxs-lookup"><span data-stu-id="5da00-156">Create a table</span></span>

<span data-ttu-id="5da00-157">В этом примере показано, как создать таблицу, если он еще не существует:</span><span class="sxs-lookup"><span data-stu-id="5da00-157">This example shows how to create a table if it does not already exist:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L35-L39)]

### <a name="add-an-entity-to-a-table"></a><span data-ttu-id="5da00-158">Добавление сущности в таблицу</span><span class="sxs-lookup"><span data-stu-id="5da00-158">Add an entity to a table</span></span>

<span data-ttu-id="5da00-159">Сущность должна иметь тип, наследующий от `TableEntity`.</span><span class="sxs-lookup"><span data-stu-id="5da00-159">An entity has to have a type that inherits from `TableEntity`.</span></span> <span data-ttu-id="5da00-160">Вы можете расширить `TableEntity` по своему усмотрению, но ваш тип *необходимо* иметь конструктор без параметров.</span><span class="sxs-lookup"><span data-stu-id="5da00-160">You can extend `TableEntity` in any way you like, but your type *must* have a parameter-less constructor.</span></span> <span data-ttu-id="5da00-161">Только свойства, имеющие и `get` и `set` хранятся в таблице Azure.</span><span class="sxs-lookup"><span data-stu-id="5da00-161">Only properties that have both `get` and `set` are stored in your Azure Table.</span></span>

<span data-ttu-id="5da00-162">Сущности раздела и ключа строки однозначно идентифицировать сущность в таблице.</span><span class="sxs-lookup"><span data-stu-id="5da00-162">An entity's partition and row key uniquely identify the entity in the table.</span></span> <span data-ttu-id="5da00-163">Сущности с одинаковым ключом раздела можно запрашивать быстрее, чем с разными ключами раздела, но использование различных ключей разделов обеспечивает более высокую масштабируемость параллельных операций.</span><span class="sxs-lookup"><span data-stu-id="5da00-163">Entities with the same partition key can be queried faster than those with different partition keys, but using diverse partition keys allows for greater scalability of parallel operations.</span></span>

<span data-ttu-id="5da00-164">Ниже приведен пример `Customer` , использующий `lastName` как ключ раздела и `firstName` как ключ строки.</span><span class="sxs-lookup"><span data-stu-id="5da00-164">Here's an example of a `Customer` that uses the `lastName` as the partition key and the `firstName` as the row key.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L45-L52)]

<span data-ttu-id="5da00-165">Теперь добавьте `Customer` в таблицу.</span><span class="sxs-lookup"><span data-stu-id="5da00-165">Now add `Customer` to the table.</span></span> <span data-ttu-id="5da00-166">Чтобы сделать это, создайте `TableOperation` , выполняющийся в таблице.</span><span class="sxs-lookup"><span data-stu-id="5da00-166">To do so, create a `TableOperation` that executes on the table.</span></span> <span data-ttu-id="5da00-167">В этом случае создается `Insert` операции.</span><span class="sxs-lookup"><span data-stu-id="5da00-167">In this case, you create an `Insert` operation.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L54-L55)]

### <a name="insert-a-batch-of-entities"></a><span data-ttu-id="5da00-168">Вставка пакета сущностей</span><span class="sxs-lookup"><span data-stu-id="5da00-168">Insert a batch of entities</span></span>

<span data-ttu-id="5da00-169">Можете вставить пакет сущностей в таблицу с использованием одиночную операцию записи.</span><span class="sxs-lookup"><span data-stu-id="5da00-169">You can insert a batch of entities into a table using a single write operation.</span></span> <span data-ttu-id="5da00-170">Пакетные операции позволяют объединить операции в одно выполнение, но они имеют некоторые ограничения:</span><span class="sxs-lookup"><span data-stu-id="5da00-170">Batch operations allow you to combine operations into a single execution, but they have some restrictions:</span></span>

- <span data-ttu-id="5da00-171">Вы можете выполнять операции обновления, удаления и вставки в одной пакетной операции.</span><span class="sxs-lookup"><span data-stu-id="5da00-171">You can perform updates, deletes, and inserts in the same batch operation.</span></span>
- <span data-ttu-id="5da00-172">Пакетная операция может включать до 100 сущностей.</span><span class="sxs-lookup"><span data-stu-id="5da00-172">A batch operation can include up to 100 entities.</span></span>
- <span data-ttu-id="5da00-173">Все сущности в пакетной операции должен иметь один и тот же ключ секции.</span><span class="sxs-lookup"><span data-stu-id="5da00-173">All entities in a batch operation must have the same partition key.</span></span>
- <span data-ttu-id="5da00-174">Хотя можно выполнить запрос в пакетной операции, он должен быть единственной операцией в пакете.</span><span class="sxs-lookup"><span data-stu-id="5da00-174">While it is possible to perform a query in a batch operation, it must be the only operation in the batch.</span></span>

<span data-ttu-id="5da00-175">Ниже приведен код, который объединяет два вставок в пакетной операции.</span><span class="sxs-lookup"><span data-stu-id="5da00-175">Here's some code that combines two inserts into a batch operation:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L62-L71)]

### <a name="retrieve-all-entities-in-a-partition"></a><span data-ttu-id="5da00-176">Получение всех сущностей в разделе</span><span class="sxs-lookup"><span data-stu-id="5da00-176">Retrieve all entities in a partition</span></span>

<span data-ttu-id="5da00-177">Чтобы запросить таблицу для всех сущностей в разделе, используйте `TableQuery` объекта.</span><span class="sxs-lookup"><span data-stu-id="5da00-177">To query a table for all entities in a partition, use a `TableQuery` object.</span></span> <span data-ttu-id="5da00-178">Здесь вы фильтрации для сущностей, где «Smith» является ключом секции.</span><span class="sxs-lookup"><span data-stu-id="5da00-178">Here, you filter for entities where "Smith" is the partition key.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L77-L82)]

<span data-ttu-id="5da00-179">Вы теперь выведите результаты:</span><span class="sxs-lookup"><span data-stu-id="5da00-179">You now print the results:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L84-L85)]


### <a name="retrieve-a-range-of-entities-in-a-partition"></a><span data-ttu-id="5da00-180">Получение диапазона сущностей в разделе</span><span class="sxs-lookup"><span data-stu-id="5da00-180">Retrieve a range of entities in a partition</span></span>

<span data-ttu-id="5da00-181">Если вы не хотите запрашивать все сущности в секции, можно указать диапазон, объединив фильтр ключа раздела с фильтром ключа строк.</span><span class="sxs-lookup"><span data-stu-id="5da00-181">If you don't want to query all the entities in a partition, you can specify a range by combining the partition key filter with a row key filter.</span></span> <span data-ttu-id="5da00-182">Здесь используется два фильтра для получения всех сущностей в разделе «Smith» где ключ строки (имя) начинается с буквы, более ранних, чем «M» в алфавите.</span><span class="sxs-lookup"><span data-stu-id="5da00-182">Here, you use two filters to get all entities in the "Smith" partition where the row key (first name) starts with a letter earlier than "M" in the alphabet.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L91-L100)]

<span data-ttu-id="5da00-183">Вы теперь выведите результаты:</span><span class="sxs-lookup"><span data-stu-id="5da00-183">You now print the results:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L102-L103)]

### <a name="retrieve-a-single-entity"></a><span data-ttu-id="5da00-184">Извлечение одной сущности</span><span class="sxs-lookup"><span data-stu-id="5da00-184">Retrieve a single entity</span></span>

<span data-ttu-id="5da00-185">Можно написать запрос для получения отдельной сущности.</span><span class="sxs-lookup"><span data-stu-id="5da00-185">You can write a query to retrieve a single, specific entity.</span></span> <span data-ttu-id="5da00-186">Здесь используется `TableOperation` для указания клиента «Ben Smith».</span><span class="sxs-lookup"><span data-stu-id="5da00-186">Here, you use a `TableOperation` to specify the customer "Ben Smith".</span></span> <span data-ttu-id="5da00-187">Вместо коллекции, вы получаете `Customer`.</span><span class="sxs-lookup"><span data-stu-id="5da00-187">Instead of a collection, you get back a `Customer`.</span></span> <span data-ttu-id="5da00-188">Указание ключа секции и ключа строки в запросе — это самый быстрый способ извлечь одну сущность из службы таблиц.</span><span class="sxs-lookup"><span data-stu-id="5da00-188">Specifying both the partition key and the row key in a query is the fastest way to retrieve a single entity from the Table service.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L109-L111)]

<span data-ttu-id="5da00-189">Вы теперь выведите результаты:</span><span class="sxs-lookup"><span data-stu-id="5da00-189">You now print the results:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L113-L115)]


### <a name="replace-an-entity"></a><span data-ttu-id="5da00-190">Замена сущности</span><span class="sxs-lookup"><span data-stu-id="5da00-190">Replace an entity</span></span>

<span data-ttu-id="5da00-191">Чтобы обновить сущность, извлеките ее из службы таблиц, измените объект сущности, а затем сохраните изменения обратно в службу таблиц с использованием `Replace` операции.</span><span class="sxs-lookup"><span data-stu-id="5da00-191">To update an entity, retrieve it from the Table service, modify the entity object, and then save the changes back to the Table service using a `Replace` operation.</span></span> <span data-ttu-id="5da00-192">Это приводит к сущность будет полностью заменена на сервере, если только сущность на сервере была изменена с момента ее получения, в этом случае операция завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="5da00-192">This causes the entity to be fully replaced on the server, unless the entity on the server has changed since it was retrieved, in which case the operation fails.</span></span> <span data-ttu-id="5da00-193">Причина заключается в том, чтобы предотвратить приложения от перезаписи изменений из других источников.</span><span class="sxs-lookup"><span data-stu-id="5da00-193">This failure is to prevent your application from inadvertently overwriting changes from other sources.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L121-L128)]

### <a name="insert-or-replace-an-entity"></a><span data-ttu-id="5da00-194">Вставка или замена сущности</span><span class="sxs-lookup"><span data-stu-id="5da00-194">Insert-or-replace an entity</span></span>

<span data-ttu-id="5da00-195">В некоторых случаях вы не знаете, существует ли сущность в таблице.</span><span class="sxs-lookup"><span data-stu-id="5da00-195">Sometimes, you don't know whether an entity exists in the table.</span></span> <span data-ttu-id="5da00-196">И если да, текущие значения, хранящиеся в ней больше не требуются.</span><span class="sxs-lookup"><span data-stu-id="5da00-196">And if it does, the current values stored in it are no longer needed.</span></span> <span data-ttu-id="5da00-197">Можно использовать `InsertOrReplace` для создания сущности или заменить его, если он существует, независимо от ее состояния.</span><span class="sxs-lookup"><span data-stu-id="5da00-197">You can use `InsertOrReplace` to create the entity, or replace it if it exists, regardless of its state.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L134-L141)]

### <a name="query-a-subset-of-entity-properties"></a><span data-ttu-id="5da00-198">Запрос подмножества свойств сущности</span><span class="sxs-lookup"><span data-stu-id="5da00-198">Query a subset of entity properties</span></span>

<span data-ttu-id="5da00-199">Табличный запрос может получить лишь несколько свойств сущности, а не все из них.</span><span class="sxs-lookup"><span data-stu-id="5da00-199">A table query can retrieve just a few properties from an entity instead of all of them.</span></span> <span data-ttu-id="5da00-200">Этот метод, который называется проекции, можно повысить производительность запросов, особенно для крупных сущностей.</span><span class="sxs-lookup"><span data-stu-id="5da00-200">This technique, called projection, can improve query performance, especially for large entities.</span></span> <span data-ttu-id="5da00-201">Здесь, возвращают только по электронной почте адреса, используя `DynamicTableEntity` и `EntityResolver`.</span><span class="sxs-lookup"><span data-stu-id="5da00-201">Here, you return only email addresses using `DynamicTableEntity` and `EntityResolver`.</span></span> <span data-ttu-id="5da00-202">Обратите внимание на то, что проекция не поддерживается в эмуляторе локального хранилища, поэтому этот код выполняется только в том случае, если вы используете учетную запись в службе таблиц.</span><span class="sxs-lookup"><span data-stu-id="5da00-202">Note that projection is not supported on the local storage emulator, so this code runs only when you're using an account on the Table service.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L147-L158)]

### <a name="retrieve-entities-in-pages-asynchronously"></a><span data-ttu-id="5da00-203">Асинхронного получения объектов со страниц</span><span class="sxs-lookup"><span data-stu-id="5da00-203">Retrieve entities in pages asynchronously</span></span>

<span data-ttu-id="5da00-204">Если вы читаете большое количество сущностей, и вы хотите их обработка по мере их загрузки, а не ждать их все для возврата, можно использовать Сегментированный запрос.</span><span class="sxs-lookup"><span data-stu-id="5da00-204">If you are reading a large number of entities, and you want to process them as they are retrieved rather than waiting for them all to return, you can use a segmented query.</span></span> <span data-ttu-id="5da00-205">Здесь возвращают результаты в страницы с помощью асинхронных рабочих процессов таким образом, чтобы не блокировать выполнение во время ожидания для большого набора результатов.</span><span class="sxs-lookup"><span data-stu-id="5da00-205">Here, you return results in pages by using an async workflow so that execution is not blocked while you're waiting for a large set of results to return.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L163-L178)]

<span data-ttu-id="5da00-206">Теперь пользователь хранимую процедуру вычисления синхронно:</span><span class="sxs-lookup"><span data-stu-id="5da00-206">You now execute this computation synchronously:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L180-L180)]

### <a name="delete-an-entity"></a><span data-ttu-id="5da00-207">Удаление сущности</span><span class="sxs-lookup"><span data-stu-id="5da00-207">Delete an entity</span></span>

<span data-ttu-id="5da00-208">Сущность можно удалить после ее получения.</span><span class="sxs-lookup"><span data-stu-id="5da00-208">You can delete an entity after you have retrieved it.</span></span> <span data-ttu-id="5da00-209">Как и в обновление сущности, это не выполняется, если сущность не была изменена с момента ее получения.</span><span class="sxs-lookup"><span data-stu-id="5da00-209">As with updating an entity, this fails if the entity has changed since you retrieved it.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L186-L187)]

### <a name="delete-a-table"></a><span data-ttu-id="5da00-210">Удаление таблицы</span><span class="sxs-lookup"><span data-stu-id="5da00-210">Delete a table</span></span>

<span data-ttu-id="5da00-211">Можно удалить таблицу из учетной записи хранения.</span><span class="sxs-lookup"><span data-stu-id="5da00-211">You can delete a table from a storage account.</span></span> <span data-ttu-id="5da00-212">Таблица, которая была удалена, будет недоступен нельзя воссоздать в течение заданного времени после удаления.</span><span class="sxs-lookup"><span data-stu-id="5da00-212">A table that has been deleted will be unavailable to be re-created for a period of time following the deletion.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L193-L193)]

## <a name="next-steps"></a><span data-ttu-id="5da00-213">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="5da00-213">Next steps</span></span>

<span data-ttu-id="5da00-214">Теперь, когда ознакомились с основными понятиями хранилища таблиц, по следующим ссылкам, чтобы узнать о более сложных задачах хранилища и API таблицы Azure Cosmos DB.</span><span class="sxs-lookup"><span data-stu-id="5da00-214">Now that you've learned the basics of Table storage, follow these links to learn about more complex storage tasks and the Azure Cosmos DB Table API.</span></span>

- [<span data-ttu-id="5da00-215">Введение в Azure API таблиц Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="5da00-215">Introduction to Azure Cosmos DB Table API</span></span>](https://docs.microsoft.com/azure/cosmos-db/table-introduction)
- [<span data-ttu-id="5da00-216">Клиентская библиотека хранилища для .NET</span><span class="sxs-lookup"><span data-stu-id="5da00-216">Storage Client Library for .NET reference</span></span>](https://docs.microsoft.com/dotnet/api/overview/azure/storage?view=azure-dotnet)
- [<span data-ttu-id="5da00-217">Тип поставщика хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="5da00-217">Azure Storage Type Provider</span></span>](https://fsprojects.github.io/AzureStorageTypeProvider/)
- [<span data-ttu-id="5da00-218">Блог группы разработчиков хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="5da00-218">Azure Storage Team Blog</span></span>](https://blogs.msdn.com/b/windowsazurestorage/)
- [<span data-ttu-id="5da00-219">Настройка строк подключения</span><span class="sxs-lookup"><span data-stu-id="5da00-219">Configuring Connection Strings</span></span>](https://docs.microsoft.com/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="5da00-220">Приступая к работе с хранилищем таблиц Azure в .NET</span><span class="sxs-lookup"><span data-stu-id="5da00-220">Getting Started with Azure Table Storage in .NET</span></span>](https://azure.microsoft.com/resources/samples/storage-table-dotnet-getting-started/)
