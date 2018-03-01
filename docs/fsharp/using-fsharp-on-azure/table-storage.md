---
title: "Начало работы с хранилищем таблиц Azure, с помощью F #"
description: "Хранения структурированных данных в облаке, с помощью хранилища таблиц Azure, хранилище данных NoSQL."
keywords: "Visual f #, f #, функционального программирования, .NET, .NET Core, Azure"
author: sylvanc
ms.author: phcart
ms.date: 09/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 9e5d6cea-a98c-461e-a5cc-75f1d154eafd
ms.openlocfilehash: 905374a60261b0c2a863edb956943d41ae80f04d
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2018
---
# <a name="get-started-with-azure-table-storage-using-f"></a><span data-ttu-id="cfb5c-104">Начало работы с хранилищем таблиц Azure, с помощью F #</span><span class="sxs-lookup"><span data-stu-id="cfb5c-104">Get started with Azure Table storage using F#</span></span> #

<span data-ttu-id="cfb5c-105">Хранилище таблиц Azure — это служба, для сохранения структурированных данных NoSQL в облаке.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-105">Azure Table storage is a service that stores structured NoSQL data in the cloud.</span></span> <span data-ttu-id="cfb5c-106">Хранилище ключей или атрибут с schemaless конструктора будет хранилище таблиц.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-106">Table storage is a key/attribute store with a schemaless design.</span></span> <span data-ttu-id="cfb5c-107">Так как хранилище таблиц schemaless, можно легко адаптировать данных в соответствии с потребностями вашего приложения evolve.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-107">Because Table storage is schemaless, it's easy to adapt your data as the needs of your application evolve.</span></span> <span data-ttu-id="cfb5c-108">Доступ к данным — это быстрый и экономичный для всех типов приложений.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-108">Access to data is fast and cost-effective for all kinds of applications.</span></span> <span data-ttu-id="cfb5c-109">Хранилище таблиц, обычно значительно меньше стоимости традиционные SQL аналогичные объемами данных.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-109">Table storage is typically significantly lower in cost than traditional SQL for similar volumes of data.</span></span>

<span data-ttu-id="cfb5c-110">Хранилище таблиц можно использовать для хранения гибкие наборов данных, таких как данные пользователя для веб-приложений, адресные книги, сведения об устройстве и любого другого типа метаданных, необходимых службе.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-110">You can use Table storage to store flexible datasets, such as user data for web applications, address books, device information, and any other type of metadata that your service requires.</span></span> <span data-ttu-id="cfb5c-111">Можно хранить любое число сущностей в таблице, и учетную запись хранилища может содержать любое количество таблиц, вплоть до предела емкости учетной записи хранения.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-111">You can store any number of entities in a table, and a storage account may contain any number of tables, up to the capacity limit of the storage account.</span></span>

### <a name="about-this-tutorial"></a><span data-ttu-id="cfb5c-112">О этого учебника</span><span class="sxs-lookup"><span data-stu-id="cfb5c-112">About this tutorial</span></span>

<span data-ttu-id="cfb5c-113">Этот учебник показывает способы написания кода F # для выполнения общих задач с помощью хранилища таблиц Azure, включая создание и удаление таблицы и вставка, обновление, удаление и запрос данных таблицы.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-113">This tutorial shows how to write F# code to do some common tasks using Azure Table storage, including creating and deleting a table and inserting, updating, deleting, and querying table data.</span></span>

<span data-ttu-id="cfb5c-114">Концептуальный обзор хранилища таблиц, см. в разделе [руководство по .NET для хранилища таблиц](/azure/storage/storage-dotnet-how-to-use-tables)</span><span class="sxs-lookup"><span data-stu-id="cfb5c-114">For a conceptual overview of table storage, please see [the .NET guide for table storage](/azure/storage/storage-dotnet-how-to-use-tables)</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cfb5c-115">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="cfb5c-115">Prerequisites</span></span>

<span data-ttu-id="cfb5c-116">Чтобы использовать это руководство, необходимо сначала [создать учетную запись хранилища Azure](/azure/storage/storage-create-storage-account).</span><span class="sxs-lookup"><span data-stu-id="cfb5c-116">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span>
<span data-ttu-id="cfb5c-117">Кроме того, потребуется ключ доступа хранилища для этой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-117">You'll also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="cfb5c-118">Создание скрипта F # и начала F #, интерактивный</span><span class="sxs-lookup"><span data-stu-id="cfb5c-118">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="cfb5c-119">Примеры в этой статье используется в F # приложения или скрипта F #.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-119">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="cfb5c-120">Чтобы создать скрипт F #, создайте файл с `.fsx` расширение, например `tables.fsx`, в среде разработки F #.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-120">To create an F# script, create a file with the `.fsx` extension, for example `tables.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="cfb5c-121">Затем используйте [диспетчера пакетов](package-management.md) такие как [Paket](https://fsprojects.github.io/Paket/) или [NuGet](https://www.nuget.org/) установка `WindowsAzure.Storage` пакета и ссылка `WindowsAzure.Storage.dll` в скрипте с помощью `#r`директивы.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-121">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span> <span data-ttu-id="cfb5c-122">Выполните ее повторное «Microsoft.WindowsAzure.ConfigurationManager», чтобы получить Microsoft.Azure пространства имен.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-122">Do it again for \`Microsoft.WindowsAzure.ConfigurationManager' in order to get the Microsoft.Azure namespace.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="cfb5c-123">Добавьте объявления пространств имен</span><span class="sxs-lookup"><span data-stu-id="cfb5c-123">Add namespace declarations</span></span>

<span data-ttu-id="cfb5c-124">Добавьте следующие `open` инструкции в начало `tables.fsx` файла:</span><span class="sxs-lookup"><span data-stu-id="cfb5c-124">Add the following `open` statements to the top of the `tables.fsx` file:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a><span data-ttu-id="cfb5c-125">Получение строки подключения</span><span class="sxs-lookup"><span data-stu-id="cfb5c-125">Get your connection string</span></span>

<span data-ttu-id="cfb5c-126">Для этого учебника потребуется строку подключения хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-126">You'll need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="cfb5c-127">Дополнительные сведения о строках соединения см. в разделе [Настройка строки подключения хранилища](/azure/storage/storage-configure-connection-string).</span><span class="sxs-lookup"><span data-stu-id="cfb5c-127">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="cfb5c-128">Учебник вы введете строки подключения в скрипте, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="cfb5c-128">For the tutorial, you'll enter your connection string in your script, like this:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L11-L11)]

<span data-ttu-id="cfb5c-129">Однако это **не рекомендуется** для реальных проектах.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-129">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="cfb5c-130">Ключ учетной записи хранилища аналогична корневой пароль для учетной записи хранилища.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-130">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="cfb5c-131">Всегда будьте внимательны защитить ключ учетной записи хранилища.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-131">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="cfb5c-132">Избегайте распространением их другим пользователям, жестко запрограммированные ее или сохранить в текстовый файл, доступный другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-132">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="cfb5c-133">Можно повторно создать ключ с помощью портала Azure, если вы считаете, что он был скомпрометирован.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-133">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="cfb5c-134">Для реальных приложений для сохранения строки подключения хранилища рекомендуется в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-134">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="cfb5c-135">Чтобы получить строку подключения из файла конфигурации, это можно сделать:</span><span class="sxs-lookup"><span data-stu-id="cfb5c-135">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L13-L15)]

<span data-ttu-id="cfb5c-136">С помощью диспетчера конфигурации Azure является необязательным.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-136">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="cfb5c-137">Можно также использовать интерфейс API, например .NET Framework `ConfigurationManager` типа.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-137">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="cfb5c-138">Синтаксический анализ строки соединения</span><span class="sxs-lookup"><span data-stu-id="cfb5c-138">Parse the connection string</span></span>

<span data-ttu-id="cfb5c-139">Чтобы обработать строку подключения, используйте:</span><span class="sxs-lookup"><span data-stu-id="cfb5c-139">To parse the connection string, use:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L21-L22)]

<span data-ttu-id="cfb5c-140">Будет возвращен `CloudStorageAccount`.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-140">This will return a `CloudStorageAccount`.</span></span>

### <a name="create-the-table-service-client"></a><span data-ttu-id="cfb5c-141">Создание клиента службы таблиц</span><span class="sxs-lookup"><span data-stu-id="cfb5c-141">Create the Table service client</span></span>

<span data-ttu-id="cfb5c-142">`CloudTableClient` Позволяет получить таблиц и сущностей, хранящихся в хранилище таблиц.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-142">The `CloudTableClient` class enables you to retrieve tables and entities stored in Table storage.</span></span> <span data-ttu-id="cfb5c-143">Вот один из способов создания клиента службы.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-143">Here's one way to create the service client:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L28-L29)]

<span data-ttu-id="cfb5c-144">Теперь вы готовы написать код, который считывает и записывает данные в хранилище таблиц.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-144">Now you are ready to write code that reads data from and writes data to Table storage.</span></span>

## <a name="create-a-table"></a><span data-ttu-id="cfb5c-145">Создание таблицы</span><span class="sxs-lookup"><span data-stu-id="cfb5c-145">Create a table</span></span>

<span data-ttu-id="cfb5c-146">В этом примере показано, как создать таблицу, если он еще не существует:</span><span class="sxs-lookup"><span data-stu-id="cfb5c-146">This example shows how to create a table if it does not already exist:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L35-L39)]

## <a name="add-an-entity-to-a-table"></a><span data-ttu-id="cfb5c-147">Добавление сущности в таблицу</span><span class="sxs-lookup"><span data-stu-id="cfb5c-147">Add an entity to a table</span></span>

<span data-ttu-id="cfb5c-148">Сущность должна иметь тип, который наследует от `TableEntity`.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-148">An entity has to have a type that inherits from `TableEntity`.</span></span> <span data-ttu-id="cfb5c-149">Вы можете расширить `TableEntity` в усмотрению, но ваш тип *должен* иметь конструктор без параметров.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-149">You can extend `TableEntity` in any way you like, but your type *must* have a parameter-less constructor.</span></span> <span data-ttu-id="cfb5c-150">Только свойства, имеющие и `get` и `set` будут храниться в таблице Azure.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-150">Only properties that have both `get` and `set` will be stored in your Azure Table.</span></span>

<span data-ttu-id="cfb5c-151">Секции и ключом строки однозначно определяют сущность в таблице.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-151">An entity's partition and row key uniquely identify the entity in the table.</span></span> <span data-ttu-id="cfb5c-152">Сущности с одинаковым ключом секции могут выполняться быстрее, чем с разными ключами секционирования, но с помощью различных разделов обеспечивает улучшенную масштабируемость параллельных операций.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-152">Entities with the same partition key can be queried faster than those with different partition keys, but using diverse partition keys allows for greater scalability of parallel operations.</span></span>

<span data-ttu-id="cfb5c-153">Ниже приведен пример `Customer` , использующий `lastName` в качестве ключа секции и `firstName` как ключ строки.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-153">Here's an example of a `Customer` that uses the `lastName` as the partition key and the `firstName` as the row key.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L45-L52)]

<span data-ttu-id="cfb5c-154">Теперь мы добавим наш `Customer` в таблицу.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-154">Now we'll add our `Customer` to the table.</span></span> <span data-ttu-id="cfb5c-155">Чтобы сделать это, создайте `TableOperation` , будет выполняться в таблице.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-155">To do so, you create a `TableOperation` that will execute on the table.</span></span> <span data-ttu-id="cfb5c-156">В этом случае вы создаете `Insert` операции.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-156">In this case, you create an `Insert` operation.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L54-L55)]

## <a name="insert-a-batch-of-entities"></a><span data-ttu-id="cfb5c-157">Вставка пакета сущностей</span><span class="sxs-lookup"><span data-stu-id="cfb5c-157">Insert a batch of entities</span></span>

<span data-ttu-id="cfb5c-158">Пакет сущностей можно вставить в таблицу с помощью одиночную операцию записи.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-158">You can insert a batch of entities into a table using a single write operation.</span></span> <span data-ttu-id="cfb5c-159">Пакетные операции позволяют объединить операций в за одно выполнение, но они имеют некоторые ограничения:</span><span class="sxs-lookup"><span data-stu-id="cfb5c-159">Batch operations allow you to combine operations into a single execution, but they have some restrictions:</span></span>

- <span data-ttu-id="cfb5c-160">Можно выполнять операции обновления, удаляет и вставляет в одной пакетной операции.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-160">You can perform updates, deletes, and inserts in the same batch operation.</span></span>
- <span data-ttu-id="cfb5c-161">Пакетная операция может содержать до 100 сущностей.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-161">A batch operation can include up to 100 entities.</span></span>
- <span data-ttu-id="cfb5c-162">Все сущности в пакетной операции должен иметь тот же ключ секционирования.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-162">All entities in a batch operation must have the same partition key.</span></span>
- <span data-ttu-id="cfb5c-163">Хотя можно выполнить запрос в пакетной операции, он должен быть только операции в пакете.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-163">While it is possible to perform a query in a batch operation, it must be the only operation in the batch.</span></span>

<span data-ttu-id="cfb5c-164">Вот код, который объединяет два вставок в пакетной операции.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-164">Here's some code that combines two inserts into a batch operation:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L62-L71)]

## <a name="retrieve-all-entities-in-a-partition"></a><span data-ttu-id="cfb5c-165">Получение всех сущностей в секции</span><span class="sxs-lookup"><span data-stu-id="cfb5c-165">Retrieve all entities in a partition</span></span>

<span data-ttu-id="cfb5c-166">Для запроса к таблице для всех сущностей в секции, использовать `TableQuery` объекта.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-166">To query a table for all entities in a partition, use a `TableQuery` object.</span></span> <span data-ttu-id="cfb5c-167">Здесь можно отфильтровать для сущностей, где ключ раздела «Buster».</span><span class="sxs-lookup"><span data-stu-id="cfb5c-167">Here, you filter for entities where "Buster" is the partition key.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L77-L80)]

<span data-ttu-id="cfb5c-168">Теперь можно распечатать результаты:</span><span class="sxs-lookup"><span data-stu-id="cfb5c-168">You now print the results:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L84-L85)]


## <a name="retrieve-a-range-of-entities-in-a-partition"></a><span data-ttu-id="cfb5c-169">Извлечь диапазон сущностей из секции</span><span class="sxs-lookup"><span data-stu-id="cfb5c-169">Retrieve a range of entities in a partition</span></span>

<span data-ttu-id="cfb5c-170">Если вы не хотите запросить все сущности в секции, можно указать диапазон, объединяя фильтр ключа секции с фильтром ключа строк.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-170">If you don't want to query all the entities in a partition, you can specify a range by combining the partition key filter with a row key filter.</span></span> <span data-ttu-id="cfb5c-171">Здесь используется два фильтра для получения всех сущностей в раздел «Buster» которых ключ строки (имя) начинается с буквы, более ранних, чем «M» в алфавите.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-171">Here, you use two filters to get all entities in the "Buster" partition where the row key (first name) starts with a letter earlier than "M" in the alphabet.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L91-L100)]

<span data-ttu-id="cfb5c-172">Теперь можно распечатать результаты:</span><span class="sxs-lookup"><span data-stu-id="cfb5c-172">You now print the results:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L102-L103)]

## <a name="retrieve-a-single-entity"></a><span data-ttu-id="cfb5c-173">Извлечение отдельной сущности</span><span class="sxs-lookup"><span data-stu-id="cfb5c-173">Retrieve a single entity</span></span>

<span data-ttu-id="cfb5c-174">Можно написать запрос, чтобы получить конкретную сущность.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-174">You can write a query to retrieve a single, specific entity.</span></span> <span data-ttu-id="cfb5c-175">Здесь используется `TableOperation` для указания клиентов «Ларри Buster».</span><span class="sxs-lookup"><span data-stu-id="cfb5c-175">Here, you use a `TableOperation` to specify the customer "Larry Buster".</span></span> <span data-ttu-id="cfb5c-176">Вместо коллекции, будет возвращена `Customer`.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-176">Instead of a collection, you get back a `Customer`.</span></span> <span data-ttu-id="cfb5c-177">Указание ключа секции и ключ строки в запросе является самым быстрым способом извлечения одной сущности из таблицы службы.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-177">Specifying both the partition key and the row key in a query is the fastest way to retrieve a single entity from the Table service.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L109-L111)]

<span data-ttu-id="cfb5c-178">Теперь можно распечатать результаты:</span><span class="sxs-lookup"><span data-stu-id="cfb5c-178">You now print the results:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L113-L115)]


## <a name="replace-an-entity"></a><span data-ttu-id="cfb5c-179">Замените сущности</span><span class="sxs-lookup"><span data-stu-id="cfb5c-179">Replace an entity</span></span>

<span data-ttu-id="cfb5c-180">Чтобы обновить сущность, получить его из службы таблиц, изменять объект сущности, а затем сохраните изменения к службе таблиц через `Replace` операции.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-180">To update an entity, retrieve it from the Table service, modify the entity object, and then save the changes back to the Table service using a `Replace` operation.</span></span> <span data-ttu-id="cfb5c-181">В этом случае сущность, которая полностью заменить на сервере, пока не изменят сущностей на сервере, так как он был извлечен, в этом случае операция завершится неудачей.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-181">This causes the entity to be fully replaced on the server, unless the entity on the server has changed since it was retrieved, in which case the operation will fail.</span></span> <span data-ttu-id="cfb5c-182">Эта ошибка является приложения будет случайно перезаписать изменения из других источников.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-182">This failure is to prevent your application from inadvertently overwriting changes from other sources.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L121-L128)]

## <a name="insert-or-replace-an-entity"></a><span data-ttu-id="cfb5c-183">INSERT или замены сущности</span><span class="sxs-lookup"><span data-stu-id="cfb5c-183">Insert-or-replace an entity</span></span>

<span data-ttu-id="cfb5c-184">В некоторых случаях вы не знаете, если сущность существует в таблице или нет.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-184">Sometimes, you don't know if the entity exists in the table or not.</span></span> <span data-ttu-id="cfb5c-185">И если да, текущие значения, хранящиеся в нем больше не нужны.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-185">And if it does, the current values stored in it are no longer needed.</span></span> <span data-ttu-id="cfb5c-186">Можно использовать `InsertOrReplace` для создания сущности или заменить его, если он существует, независимо от их состояния.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-186">You can use `InsertOrReplace` to create the entity, or replace it if it exists, regardless of its state.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L134-L140)]

## <a name="query-a-subset-of-entity-properties"></a><span data-ttu-id="cfb5c-187">Запрос подмножества свойств сущности</span><span class="sxs-lookup"><span data-stu-id="cfb5c-187">Query a subset of entity properties</span></span>

<span data-ttu-id="cfb5c-188">Запрос таблицы можно получить только несколько свойств с сущностью, а не все из них.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-188">A table query can retrieve just a few properties from an entity instead of all of them.</span></span> <span data-ttu-id="cfb5c-189">Этот метод вызывается проекции, может повысить производительность запросов, особенно для больших объектов.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-189">This technique, called projection, can improve query performance, especially for large entities.</span></span> <span data-ttu-id="cfb5c-190">Здесь, возвращают только по электронной почте адреса, используя `DynamicTableEntity` и `EntityResolver`.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-190">Here, you return only email addresses using `DynamicTableEntity` and `EntityResolver`.</span></span> <span data-ttu-id="cfb5c-191">Обратите внимание, что проекции не поддерживается на эмулятор локального хранилища, поэтому этот код выполняется только в том случае, если вы используете учетную запись в службе таблиц.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-191">Note that projection is not supported on the local storage emulator, so this code runs only when you're using an account on the Table service.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L146-L157)]

## <a name="retrieve-entities-in-pages-asynchronously"></a><span data-ttu-id="cfb5c-192">Получение сущностей на страницах асинхронно</span><span class="sxs-lookup"><span data-stu-id="cfb5c-192">Retrieve entities in pages asynchronously</span></span>

<span data-ttu-id="cfb5c-193">Если вы читаете большое количество сущностей, и вы хотите их обработка по мере их загрузки, а не ждать их все для возврата, можно использовать сегментированных запрос.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-193">If you are reading a large number of entities, and you want to process them as they are retrieved rather than waiting for them all to return, you can use a segmented query.</span></span> <span data-ttu-id="cfb5c-194">Здесь возвращают результаты в страницы с помощью асинхронного рабочего процесса, чтобы выполнение не блокируется во время ожидания для большого набора результатов.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-194">Here, you return results in pages by using an async workflow so that execution is not blocked while you're waiting for a large set of results to return.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L163-L177)]

<span data-ttu-id="cfb5c-195">Вы теперь можно выполнить это вычисление синхронно:</span><span class="sxs-lookup"><span data-stu-id="cfb5c-195">You now execute this computation synchronously:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L179-L179)]

## <a name="delete-an-entity"></a><span data-ttu-id="cfb5c-196">Удаление сущности</span><span class="sxs-lookup"><span data-stu-id="cfb5c-196">Delete an entity</span></span>

<span data-ttu-id="cfb5c-197">Сущность можно удалить после его получения.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-197">You can delete an entity after you have retrieved it.</span></span> <span data-ttu-id="cfb5c-198">С обновлением сущности, если произойдет сущность была изменена с момента его загрузки.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-198">As with updating an entity, this will fail if the entity has changed since you retrieved it.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L185-L186)]

## <a name="delete-a-table"></a><span data-ttu-id="cfb5c-199">Удаление таблицы</span><span class="sxs-lookup"><span data-stu-id="cfb5c-199">Delete a table</span></span>

<span data-ttu-id="cfb5c-200">Можно удалить таблицу из учетной записи хранилища.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-200">You can delete a table from a storage account.</span></span> <span data-ttu-id="cfb5c-201">Таблицы, которая была удалена, будут недоступны для быть повторно созданы в течение заданного времени после удаления.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-201">A table that has been deleted will be unavailable to be re-created for a period of time following the deletion.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L192-L192)]

## <a name="next-steps"></a><span data-ttu-id="cfb5c-202">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="cfb5c-202">Next steps</span></span>

<span data-ttu-id="cfb5c-203">Теперь, когда вы узнали основы хранилище таблиц, выполните эти ссылки на дополнительные сведения о более сложных задач хранилища.</span><span class="sxs-lookup"><span data-stu-id="cfb5c-203">Now that you've learned the basics of Table storage, follow these links to learn about more complex storage tasks:</span></span>

- [<span data-ttu-id="cfb5c-204">API-интерфейсов хранилища Azure для .NET</span><span class="sxs-lookup"><span data-stu-id="cfb5c-204">Azure Storage APIs for .NET</span></span>](/dotnet/api/overview/azure/storage)
- [<span data-ttu-id="cfb5c-205">Тип поставщика хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="cfb5c-205">Azure Storage Type Provider</span></span>](https://fsprojects.github.io/AzureStorageTypeProvider/)
- [<span data-ttu-id="cfb5c-206">Блог группы разработчиков хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="cfb5c-206">Azure Storage Team Blog</span></span>](https://blogs.msdn.microsoft.com/b/windowsazurestorage/)
- [<span data-ttu-id="cfb5c-207">Настройка строки подключения хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="cfb5c-207">Configure Azure Storage connection strings</span></span>](/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="cfb5c-208">Приступая к работе с хранилищем таблиц Azure в .NET</span><span class="sxs-lookup"><span data-stu-id="cfb5c-208">Getting Started with Azure Table Storage in .NET</span></span>](https://azure.microsoft.com/documentation/samples/storage-table-dotnet-getting-started/)
