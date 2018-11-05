---
title: Начало работы с хранилищем BLOB-объектов Azure, с помощью F#
description: Store неструктурированных данных в облаке в хранилище BLOB-объектов Azure.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: ea9dc334ec9c2bcd4a80cc501d4b6634da5f64e4
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/02/2018
ms.locfileid: "44037286"
---
# <a name="get-started-with-azure-blob-storage-using-f"></a><span data-ttu-id="6487c-103">Начало работы с хранилищем BLOB-объектов Azure, с помощью F#</span><span class="sxs-lookup"><span data-stu-id="6487c-103">Get started with Azure Blob storage using F#</span></span> #

<span data-ttu-id="6487c-104">Хранилище BLOB-объектов Azure — это служба, которая сохраняет неструктурированные данные в облаке в виде BLOB-объектов.</span><span class="sxs-lookup"><span data-stu-id="6487c-104">Azure Blob storage is a service that stores unstructured data in the cloud as objects/blobs.</span></span> <span data-ttu-id="6487c-105">В хранилище BLOB-объектов можно хранить любые типы текстовых или двоичных данных, таких как документы, файлы мультимедиа или установщики приложений.</span><span class="sxs-lookup"><span data-stu-id="6487c-105">Blob storage can store any type of text or binary data, such as a document, media file, or application installer.</span></span> <span data-ttu-id="6487c-106">Хранилище BLOB-объектов также называют хранилищем объектов.</span><span class="sxs-lookup"><span data-stu-id="6487c-106">Blob storage is also referred to as object storage.</span></span>

<span data-ttu-id="6487c-107">В этой статье показано, как выполнять типовые задачи с помощью хранилища BLOB-объектов.</span><span class="sxs-lookup"><span data-stu-id="6487c-107">This article shows you how to perform common tasks using Blob storage.</span></span> <span data-ttu-id="6487c-108">Примеры написаны с помощью F# с помощью клиентской библиотеки хранилища Azure для .NET.</span><span class="sxs-lookup"><span data-stu-id="6487c-108">The samples are written using F# using the Azure Storage Client Library for .NET.</span></span> <span data-ttu-id="6487c-109">Задачи, описанные включают как отправка, список, скачивание и удаление больших двоичных объектов.</span><span class="sxs-lookup"><span data-stu-id="6487c-109">The tasks covered include how to upload, list, download, and delete blobs.</span></span>

<span data-ttu-id="6487c-110">Общие сведения о хранилище BLOB-объектов, см. в разделе [руководство по .NET для хранилища BLOB-объектов](/azure/storage/storage-dotnet-how-to-use-blobs).</span><span class="sxs-lookup"><span data-stu-id="6487c-110">For a conceptual overview of blob storage, see [the .NET guide for blob storage](/azure/storage/storage-dotnet-how-to-use-blobs).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6487c-111">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="6487c-111">Prerequisites</span></span>

<span data-ttu-id="6487c-112">Чтобы использовать это руководство, необходимо сначала [создать учетную запись хранения](/azure/storage/storage-create-storage-account).</span><span class="sxs-lookup"><span data-stu-id="6487c-112">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span> <span data-ttu-id="6487c-113">Вам также потребуется ключ доступа к хранилищу для этой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="6487c-113">You also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="6487c-114">Создать скрипт F# и начала F#, интерактивный</span><span class="sxs-lookup"><span data-stu-id="6487c-114">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="6487c-115">Примеры в этой статье можно использовать в F# приложение или скрипт F#.</span><span class="sxs-lookup"><span data-stu-id="6487c-115">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="6487c-116">Чтобы создать скрипт F#, создайте файл с `.fsx` расширение, например `blobs.fsx`, в среде разработки F#.</span><span class="sxs-lookup"><span data-stu-id="6487c-116">To create an F# script, create a file with the `.fsx` extension, for example `blobs.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="6487c-117">Затем используйте [диспетчера пакетов](package-management.md) например [Paket](https://fsprojects.github.io/Paket/) или [NuGet](https://www.nuget.org/) установка `WindowsAzure.Storage` и `Microsoft.WindowsAzure.ConfigurationManager` пакетов и справочник по `WindowsAzure.Storage.dll` и `Microsoft.WindowsAzure.Configuration.dll` в скрипт с помощью `#r` директива.</span><span class="sxs-lookup"><span data-stu-id="6487c-117">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` and `Microsoft.WindowsAzure.ConfigurationManager` packages and reference `WindowsAzure.Storage.dll` and `Microsoft.WindowsAzure.Configuration.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="6487c-118">Добавьте объявления пространств имен</span><span class="sxs-lookup"><span data-stu-id="6487c-118">Add namespace declarations</span></span>

<span data-ttu-id="6487c-119">Добавьте следующий `open` операторы в верхнюю часть `blobs.fsx` файла:</span><span class="sxs-lookup"><span data-stu-id="6487c-119">Add the following `open` statements to the top of the `blobs.fsx` file:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a><span data-ttu-id="6487c-120">Получить строку подключения</span><span class="sxs-lookup"><span data-stu-id="6487c-120">Get your connection string</span></span>

<span data-ttu-id="6487c-121">В этом руководстве необходимо строки подключения к службе хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="6487c-121">You need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="6487c-122">Дополнительные сведения о строках подключения см. в разделе [Настройка строк подключения службы хранилища](/azure/storage/storage-configure-connection-string).</span><span class="sxs-lookup"><span data-stu-id="6487c-122">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="6487c-123">Для этого руководства введите строку подключения в скрипте, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="6487c-123">For the tutorial, you enter your connection string in your script, like this:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L11-L11)]

<span data-ttu-id="6487c-124">Однако это **не рекомендуется** реальных проектов.</span><span class="sxs-lookup"><span data-stu-id="6487c-124">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="6487c-125">Ключ учетной записи хранения похож на корневой пароль для учетной записи хранения.</span><span class="sxs-lookup"><span data-stu-id="6487c-125">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="6487c-126">Не забудьте защитить ключ учетной записи хранения.</span><span class="sxs-lookup"><span data-stu-id="6487c-126">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="6487c-127">Избегайте распределения его другим пользователям, в коде, или сохранить его в текстовом файле, доступном другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="6487c-127">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="6487c-128">Можно повторно создать ключ с помощью портала Azure, если вы считаете, что он мог быть скомпрометирован.</span><span class="sxs-lookup"><span data-stu-id="6487c-128">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="6487c-129">Для реальных приложений, чтобы сохранить строку подключения хранилища рекомендуется в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="6487c-129">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="6487c-130">Чтобы получить строку подключения из файла конфигурации, это можно сделать:</span><span class="sxs-lookup"><span data-stu-id="6487c-130">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L13-L15)]

<span data-ttu-id="6487c-131">Использование диспетчера конфигураций Azure не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="6487c-131">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="6487c-132">Можно также использовать API, например .NET Framework `ConfigurationManager` типа.</span><span class="sxs-lookup"><span data-stu-id="6487c-132">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="6487c-133">Проанализировать строку подключения</span><span class="sxs-lookup"><span data-stu-id="6487c-133">Parse the connection string</span></span>

<span data-ttu-id="6487c-134">Чтобы проанализировать строку подключения, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="6487c-134">To parse the connection string, use:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L21-L22)]

<span data-ttu-id="6487c-135">Эта команда возвращает `CloudStorageAccount`.</span><span class="sxs-lookup"><span data-stu-id="6487c-135">This returns a `CloudStorageAccount`.</span></span>

### <a name="create-some-local-dummy-data"></a><span data-ttu-id="6487c-136">Создание локального фиктивный данных</span><span class="sxs-lookup"><span data-stu-id="6487c-136">Create some local dummy data</span></span>

<span data-ttu-id="6487c-137">Прежде чем начать, создайте некоторые фиктивные локальных данных в каталоге нашего сценария.</span><span class="sxs-lookup"><span data-stu-id="6487c-137">Before you begin, create some dummy local data in the directory of our script.</span></span> <span data-ttu-id="6487c-138">Затем можно загрузить эти данные.</span><span class="sxs-lookup"><span data-stu-id="6487c-138">Later you upload this data.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L28-L30)]

### <a name="create-the-blob-service-client"></a><span data-ttu-id="6487c-139">Создание клиента службы BLOB-объектов</span><span class="sxs-lookup"><span data-stu-id="6487c-139">Create the Blob service client</span></span>

<span data-ttu-id="6487c-140">`CloudBlobClient` Тип позволяет извлекать контейнеры и большие двоичные объекты, хранящиеся в хранилище BLOB-объектов.</span><span class="sxs-lookup"><span data-stu-id="6487c-140">The `CloudBlobClient` type enables you to retrieve containers and blobs stored in Blob storage.</span></span> <span data-ttu-id="6487c-141">Вот один из способов создания клиента службы:</span><span class="sxs-lookup"><span data-stu-id="6487c-141">Here's one way to create the service client:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L36-L36)]

<span data-ttu-id="6487c-142">Теперь вы готовы написать код, который считывает и записывает данные в хранилище BLOB-объектов.</span><span class="sxs-lookup"><span data-stu-id="6487c-142">Now you are ready to write code that reads data from and writes data to Blob storage.</span></span>

## <a name="create-a-container"></a><span data-ttu-id="6487c-143">Создание контейнера</span><span class="sxs-lookup"><span data-stu-id="6487c-143">Create a container</span></span>

<span data-ttu-id="6487c-144">В этом примере показано, как создать контейнер, если он еще не существует:</span><span class="sxs-lookup"><span data-stu-id="6487c-144">This example shows how to create a container if it does not already exist:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L42-L46)]

<span data-ttu-id="6487c-145">По умолчанию новый контейнер является закрытым. Это значит, что необходимо указать ключ доступа к хранилищу, чтобы скачать большие двоичные объекты из этого контейнера.</span><span class="sxs-lookup"><span data-stu-id="6487c-145">By default, the new container is private, meaning that you must specify your storage access key to download blobs from this container.</span></span> <span data-ttu-id="6487c-146">Если вы хотите сделать файлы в контейнере доступными для всех пользователей, можно разместить контейнер открытым, используя следующий код:</span><span class="sxs-lookup"><span data-stu-id="6487c-146">If you want to make the files within the container available to everyone, you can set the container to be public using the following code:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L48-L49)]

<span data-ttu-id="6487c-147">Любой пользователь в Интернете может видеть большие двоичные объекты в общедоступном контейнере, но можно изменить или удалить их только в том случае, если у вас есть ключа доступа или подписанный URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="6487c-147">Anyone on the Internet can see blobs in a public container, but you can modify or delete them only if you have the appropriate account access key or a shared access signature.</span></span>

## <a name="upload-a-blob-into-a-container"></a><span data-ttu-id="6487c-148">Отправка большого двоичного объекта в контейнер</span><span class="sxs-lookup"><span data-stu-id="6487c-148">Upload a blob into a container</span></span>

<span data-ttu-id="6487c-149">Хранилище BLOB-объектов поддерживает блочные и страничные.</span><span class="sxs-lookup"><span data-stu-id="6487c-149">Azure Blob Storage supports block blobs and page blobs.</span></span> <span data-ttu-id="6487c-150">В большинстве случаев большой двоичный объект является типом, рекомендуемые для использования.</span><span class="sxs-lookup"><span data-stu-id="6487c-150">In most cases, a block blob is the recommended type to use.</span></span>

<span data-ttu-id="6487c-151">Для отправки файла в блочный большой двоичный объект, получите ссылку на контейнер и используйте ее для получения ссылку на большой двоичный объект блока.</span><span class="sxs-lookup"><span data-stu-id="6487c-151">To upload a file to a block blob, get a container reference and use it to get a block blob reference.</span></span> <span data-ttu-id="6487c-152">Получив ссылку на BLOB-объектов, можно отправить любой поток данных к нему путем вызова `UploadFromFile` метод.</span><span class="sxs-lookup"><span data-stu-id="6487c-152">Once you have a blob reference, you can upload any stream of data to it by calling the `UploadFromFile` method.</span></span> <span data-ttu-id="6487c-153">Эта операция создает большой двоичный объект, если он не был ранее существует, или заменяет его, если он существует.</span><span class="sxs-lookup"><span data-stu-id="6487c-153">This operation creates the blob if it didn't previously exist, or overwrite it if it does exist.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L55-L59)]

## <a name="list-the-blobs-in-a-container"></a><span data-ttu-id="6487c-154">Перечисление больших двоичных объектов в контейнере</span><span class="sxs-lookup"><span data-stu-id="6487c-154">List the blobs in a container</span></span>

<span data-ttu-id="6487c-155">Чтобы получить список больших двоичных объектов в контейнере, сначала нужно получите ссылку на контейнер.</span><span class="sxs-lookup"><span data-stu-id="6487c-155">To list the blobs in a container, first get a container reference.</span></span> <span data-ttu-id="6487c-156">Затем можно использовать контейнер `ListBlobs` метод для извлечения больших двоичных объектов и (или) каталогов внутри него.</span><span class="sxs-lookup"><span data-stu-id="6487c-156">You can then use the container's `ListBlobs` method to retrieve the blobs and/or directories within it.</span></span> <span data-ttu-id="6487c-157">Чтобы получить доступ к широкому набору свойств и методов возвращаемого `IListBlobItem`, необходимо преобразовать его в `CloudBlockBlob`, `CloudPageBlob`, или `CloudBlobDirectory` объекта.</span><span class="sxs-lookup"><span data-stu-id="6487c-157">To access the rich set of properties and methods for a returned `IListBlobItem`, you must cast it to a `CloudBlockBlob`, `CloudPageBlob`, or `CloudBlobDirectory` object.</span></span> <span data-ttu-id="6487c-158">Если тип неизвестен, можно использовать проверку типов, чтобы определить, какие для приведения.</span><span class="sxs-lookup"><span data-stu-id="6487c-158">If the type is unknown, you can use a type check to determine which to cast it to.</span></span> <span data-ttu-id="6487c-159">Следующий код показывает, как получить и вывести URI каждого элемента в `mydata` контейнера:</span><span class="sxs-lookup"><span data-stu-id="6487c-159">The following code demonstrates how to retrieve and output the URI of each item in the `mydata` container:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L67-L80)]

<span data-ttu-id="6487c-160">Вы также можете имя BLOB-объектов с информацией о пути в их именах.</span><span class="sxs-lookup"><span data-stu-id="6487c-160">You can also name blobs with path information in their names.</span></span> <span data-ttu-id="6487c-161">Это создает структуры виртуальных каталогов, которые можно упорядочивать и просматривать, как и традиционную файловую систему.</span><span class="sxs-lookup"><span data-stu-id="6487c-161">This creates a virtual directory structure that you can organize and traverse as you would a traditional file system.</span></span> <span data-ttu-id="6487c-162">Обратите внимание, что структура каталогов является виртуальным только - только ресурсы, доступные в хранилище BLOB-объектов, контейнеров и больших двоичных объектов.</span><span class="sxs-lookup"><span data-stu-id="6487c-162">Note that the directory structure is virtual only - the only resources available in Blob storage are containers and blobs.</span></span> <span data-ttu-id="6487c-163">Однако клиентская библиотека хранилища предоставляет `CloudBlobDirectory` объекта к виртуальному каталогу и упростить процесс работы с большими двоичными объектами, которые упорядочены таким образом.</span><span class="sxs-lookup"><span data-stu-id="6487c-163">However, the storage client library offers a `CloudBlobDirectory` object to refer to a virtual directory and simplify the process of working with blobs that are organized in this way.</span></span>

<span data-ttu-id="6487c-164">Например, рассмотрим следующий набор блочных BLOB-объектов в контейнере с именем `photos`:</span><span class="sxs-lookup"><span data-stu-id="6487c-164">For example, consider the following set of block blobs in a container named `photos`:</span></span>

<span data-ttu-id="6487c-165">*photo1.jpg*
*2015/architecture/description.txt*
*2015/architecture/photo3.jpg*
*2015 / Архитектура/photo4.jpg*
*2016/architecture/photo5.jpg*
*2016/architecture/photo6.jpg* 
 *2016/architecture/description.txt*
*2016/photo7.jpg*</span><span class="sxs-lookup"><span data-stu-id="6487c-165">*photo1.jpg*
*2015/architecture/description.txt*
*2015/architecture/photo3.jpg*
*2015/architecture/photo4.jpg*
*2016/architecture/photo5.jpg*
*2016/architecture/photo6.jpg*
*2016/architecture/description.txt*
*2016/photo7.jpg*</span></span>

<span data-ttu-id="6487c-166">При вызове `ListBlobs` в контейнере (как в примере выше) возвращается иерархический список.</span><span class="sxs-lookup"><span data-stu-id="6487c-166">When you call `ListBlobs` on a container (as in the above sample), a hierarchical listing is returned.</span></span> <span data-ttu-id="6487c-167">Если он содержит оба `CloudBlobDirectory` и `CloudBlockBlob` объекты, представляющие каталоги и большие двоичные объекты в контейнере, соответственно, а затем полученный результат выглядит примерно так:</span><span class="sxs-lookup"><span data-stu-id="6487c-167">If it contains both `CloudBlobDirectory` and `CloudBlockBlob` objects, representing the directories and blobs in the container, respectively, then the resulting output looks similar to this:</span></span>

```console
Directory: https://<accountname>.blob.core.windows.net/photos/2015/
Directory: https://<accountname>.blob.core.windows.net/photos/2016/
Block blob of length 505623: https://<accountname>.blob.core.windows.net/photos/photo1.jpg
```

<span data-ttu-id="6487c-168">При необходимости можно задать `UseFlatBlobListing` параметр `ListBlobs` метод `true`.</span><span class="sxs-lookup"><span data-stu-id="6487c-168">Optionally, you can set the `UseFlatBlobListing` parameter of the `ListBlobs` method to `true`.</span></span> <span data-ttu-id="6487c-169">В этом случае каждый большой двоичный объект в контейнере возвращается в виде `CloudBlockBlob` объекта.</span><span class="sxs-lookup"><span data-stu-id="6487c-169">In this case, every blob in the container is returned as a `CloudBlockBlob` object.</span></span> <span data-ttu-id="6487c-170">Вызов `ListBlobs` для возврата неструктурированного списка выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="6487c-170">The call to `ListBlobs` to return a flat listing looks like this:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L82-L89)]

<span data-ttu-id="6487c-171">и, в зависимости от текущего содержимого контейнера, результаты будут выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="6487c-171">and, depending on the current contents of your container, the results look like this:</span></span>

```console
Block blob of length 4: https://<accountname>.blob.core.windows.net/photos/2015/architecture/description.txt
Block blob of length 314618: https://<accountname>.blob.core.windows.net/photos/2015/architecture/photo3.jpg
Block blob of length 522713: https://<accountname>.blob.core.windows.net/photos/2015/architecture/photo4.jpg
Block blob of length 4: https://<accountname>.blob.core.windows.net/photos/2016/architecture/description.txt
Block blob of length 419048: https://<accountname>.blob.core.windows.net/photos/2016/architecture/photo5.jpg
Block blob of length 506388: https://<accountname>.blob.core.windows.net/photos/2016/architecture/photo6.jpg
Block blob of length 399751: https://<accountname>.blob.core.windows.net/photos/2016/photo7.jpg
Block blob of length 505623: https://<accountname>.blob.core.windows.net/photos/photo1.jpg
```

## <a name="download-blobs"></a><span data-ttu-id="6487c-172">Скачивание больших двоичных объектов</span><span class="sxs-lookup"><span data-stu-id="6487c-172">Download blobs</span></span>

<span data-ttu-id="6487c-173">Чтобы скачать большие двоичные объекты, сначала нужно получить ссылку на BLOB-объектов, а затем вызовите `DownloadToStream` метод.</span><span class="sxs-lookup"><span data-stu-id="6487c-173">To download blobs, first retrieve a blob reference and then call the `DownloadToStream` method.</span></span> <span data-ttu-id="6487c-174">В следующем примере используется `DownloadToStream` метод для переноса содержимого большого двоичного объекта в объект потока, который затем можно сохранить в локальном файле.</span><span class="sxs-lookup"><span data-stu-id="6487c-174">The following example uses the `DownloadToStream` method to transfer the blob contents to a stream object that you can then persist to a local file.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L95-L101)]

<span data-ttu-id="6487c-175">Можно также использовать `DownloadToStream` метод для загрузки содержимого большого двоичного объекта в виде текстовой строки.</span><span class="sxs-lookup"><span data-stu-id="6487c-175">You can also use the `DownloadToStream` method to download the contents of a blob as a text string.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L103-L106)]

## <a name="delete-blobs"></a><span data-ttu-id="6487c-176">Удаление больших двоичных объектов</span><span class="sxs-lookup"><span data-stu-id="6487c-176">Delete blobs</span></span>

<span data-ttu-id="6487c-177">Чтобы удалить большой двоичный объект, сначала получите ссылку на BLOB-объектов, а затем вызовите `Delete` для него метода.</span><span class="sxs-lookup"><span data-stu-id="6487c-177">To delete a blob, first get a blob reference and then call the `Delete` method on it.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L112-L116)]

## <a name="list-blobs-in-pages-asynchronously"></a><span data-ttu-id="6487c-178">Асинхронно больших двоичных объектов в страницы</span><span class="sxs-lookup"><span data-stu-id="6487c-178">List blobs in pages asynchronously</span></span>

<span data-ttu-id="6487c-179">Если вы хотите контролировать количество результатов, возвращаемых в одной операцией получения листинга расположить большое количество больших двоичных объектов, можно больших двоичных объектов в страницы результатов.</span><span class="sxs-lookup"><span data-stu-id="6487c-179">If you are listing a large number of blobs, or you want to control the number of results you return in one listing operation, you can list blobs in pages of results.</span></span> <span data-ttu-id="6487c-180">В этом примере показано, как асинхронно возвращать результаты для того, чтобы не блокировать выполнение ожиданием большого объема возвращаемых результатов.</span><span class="sxs-lookup"><span data-stu-id="6487c-180">This example shows how to return results in pages asynchronously, so that execution is not blocked while waiting to return a large set of results.</span></span>

<span data-ttu-id="6487c-181">В этом примере показано плоского списка больших двоичных объектов, но можно также выполнить иерархический список, задав `useFlatBlobListing` параметр `ListBlobsSegmentedAsync` метод `false`.</span><span class="sxs-lookup"><span data-stu-id="6487c-181">This example shows a flat blob listing, but you can also perform a hierarchical listing, by setting the `useFlatBlobListing` parameter of the `ListBlobsSegmentedAsync` method to `false`.</span></span>

<span data-ttu-id="6487c-182">Образец определяет асинхронный метод, с помощью `async` блока.</span><span class="sxs-lookup"><span data-stu-id="6487c-182">The sample defines an asynchronous method, using an `async` block.</span></span> <span data-ttu-id="6487c-183">``let!`` Ключевое слово приостанавливает выполнение примера метода, до завершения задачи в список.</span><span class="sxs-lookup"><span data-stu-id="6487c-183">The ``let!`` keyword suspends execution of the sample method until the listing task completes.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L122-L160)]

<span data-ttu-id="6487c-184">Теперь мы можем использовать этот асинхронные подпрограммы следующим образом.</span><span class="sxs-lookup"><span data-stu-id="6487c-184">We can now use this asynchronous routine as follows.</span></span> <span data-ttu-id="6487c-185">Сначала вам необходимо отправить некоторые фиктивные данные (с помощью локальный файл, созданный ранее в этом руководстве).</span><span class="sxs-lookup"><span data-stu-id="6487c-185">First you upload some dummy data (using the local file created earlier in this tutorial).</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L162-L166)]

<span data-ttu-id="6487c-186">Теперь вызовите процедуру.</span><span class="sxs-lookup"><span data-stu-id="6487c-186">Now, call the routine.</span></span> <span data-ttu-id="6487c-187">Использовании `Async.RunSynchronously` для принудительного выполнения асинхронной операции.</span><span class="sxs-lookup"><span data-stu-id="6487c-187">You use `Async.RunSynchronously` to force the execution of the asynchronous operation.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L168-L168)]

## <a name="writing-to-an-append-blob"></a><span data-ttu-id="6487c-188">Запись в добавочный BLOB-объект</span><span class="sxs-lookup"><span data-stu-id="6487c-188">Writing to an append blob</span></span>

<span data-ttu-id="6487c-189">Добавочный большой двоичный объект оптимизирован для операций добавления, например ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="6487c-189">An append blob is optimized for append operations, such as logging.</span></span> <span data-ttu-id="6487c-190">Как и блочный BLOB-объект добавочный большой двоичный объект состоит из блоков, но при добавлении нового блока в добавочный большой двоичный объект, он всегда добавляется в конец большого двоичного объекта.</span><span class="sxs-lookup"><span data-stu-id="6487c-190">Like a block blob, an append blob is comprised of blocks, but when you add a new block to an append blob, it is always appended to the end of the blob.</span></span> <span data-ttu-id="6487c-191">Невозможно обновить или удалить существующий блок в добавочном большом двоичном объекте.</span><span class="sxs-lookup"><span data-stu-id="6487c-191">You cannot update or delete an existing block in an append blob.</span></span> <span data-ttu-id="6487c-192">Идентификаторы блоков в добавочном большом двоичном объекте не отображаются, как они предназначены для блочных BLOB-объектов.</span><span class="sxs-lookup"><span data-stu-id="6487c-192">The block IDs for an append blob are not exposed as they are for a block blob.</span></span>

<span data-ttu-id="6487c-193">Каждый блок в добавочном большом двоичном объекте может иметь разный размер, не более 4 МБ и добавочный большой двоичный объект может содержать не более 50 000 блоков.</span><span class="sxs-lookup"><span data-stu-id="6487c-193">Each block in an append blob can be a different size, up to a maximum of 4 MB, and an append blob can include a maximum of 50,000 blocks.</span></span> <span data-ttu-id="6487c-194">Таким образом, максимальный размер добавочный большой двоичный объект является немного более 195 ГБ (4 МБ X 50 000 блоков).</span><span class="sxs-lookup"><span data-stu-id="6487c-194">The maximum size of an append blob is therefore slightly more than 195 GB (4 MB X 50,000 blocks).</span></span>

<span data-ttu-id="6487c-195">Следующий пример создает новый добавочный большой двоичный объект и добавляет некоторые данные, имитируя простые операции ведение журнала.</span><span class="sxs-lookup"><span data-stu-id="6487c-195">The following example creates a new append blob and appends some data to it, simulating a simple logging operation.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L174-L203)]

<span data-ttu-id="6487c-196">См. в разделе [основные сведения о блочных, страничных и добавочных](https://msdn.microsoft.com/library/azure/ee691964.aspx) Дополнительные сведения о различиях между тремя типами больших двоичных объектов.</span><span class="sxs-lookup"><span data-stu-id="6487c-196">See [Understanding Block Blobs, Page Blobs, and Append Blobs](https://msdn.microsoft.com/library/azure/ee691964.aspx) for more information about the differences between the three types of blobs.</span></span>

## <a name="concurrent-access"></a><span data-ttu-id="6487c-197">Одновременный доступ</span><span class="sxs-lookup"><span data-stu-id="6487c-197">Concurrent access</span></span>

<span data-ttu-id="6487c-198">Для поддержки параллельного доступа к большому двоичному объекту из нескольких клиентов или экземпляров процесса, можно использовать **теги eTag** или **аренды**.</span><span class="sxs-lookup"><span data-stu-id="6487c-198">To support concurrent access to a blob from multiple clients or multiple process instances, you can use **ETags** or **leases**.</span></span>

* <span data-ttu-id="6487c-199">**ETag** -позволяет обнаружить, что большой двоичный объект или контейнер были изменены другим процессом</span><span class="sxs-lookup"><span data-stu-id="6487c-199">**Etag** - provides a way to detect that the blob or container has been modified by another process</span></span>

* <span data-ttu-id="6487c-200">**Аренда** -предоставляет способ получить монопольный обновляемый запись или удаление доступа к большому двоичному объекту в течение заданного времени</span><span class="sxs-lookup"><span data-stu-id="6487c-200">**Lease** - provides a way to obtain exclusive, renewable, write or delete access to a blob for a period of time</span></span>

<span data-ttu-id="6487c-201">Дополнительные сведения см. в разделе [управление параллелизмом в хранилище Microsoft Azure](https://azure.microsoft.com/blog/managing-concurrency-in-microsoft-azure-storage-2/).</span><span class="sxs-lookup"><span data-stu-id="6487c-201">For more information, see [Managing Concurrency in Microsoft Azure Storage](https://azure.microsoft.com/blog/managing-concurrency-in-microsoft-azure-storage-2/).</span></span>

## <a name="naming-containers"></a><span data-ttu-id="6487c-202">Контейнеры именования</span><span class="sxs-lookup"><span data-stu-id="6487c-202">Naming containers</span></span>

<span data-ttu-id="6487c-203">Каждый большой двоичный объект в службе хранилища Azure должны находиться в контейнере.</span><span class="sxs-lookup"><span data-stu-id="6487c-203">Every blob in Azure storage must reside in a container.</span></span> <span data-ttu-id="6487c-204">Контейнер составляет часть имени BLOB-объектов.</span><span class="sxs-lookup"><span data-stu-id="6487c-204">The container forms part of the blob name.</span></span> <span data-ttu-id="6487c-205">Например `mydata` имя контейнера в этих URI BLOB-образец объектов:</span><span class="sxs-lookup"><span data-stu-id="6487c-205">For example, `mydata` is the name of the container in these sample blob URIs:</span></span>

    https://storagesample.blob.core.windows.net/mydata/blob1.txt
    https://storagesample.blob.core.windows.net/mydata/photos/myphoto.jpg

<span data-ttu-id="6487c-206">Имя контейнера должно быть допустимым DNS-именем, удовлетворяющие следующим правилам именования:</span><span class="sxs-lookup"><span data-stu-id="6487c-206">A container name must be a valid DNS name, conforming to the following naming rules:</span></span>

1. <span data-ttu-id="6487c-207">Имена контейнеров должны начинаться с буквы или цифры и может содержать только буквы, цифры и дефис (-).</span><span class="sxs-lookup"><span data-stu-id="6487c-207">Container names must start with a letter or number, and can contain only letters, numbers, and the dash (-) character.</span></span>
1. <span data-ttu-id="6487c-208">Каждого символа дефиса (-) непосредственно перед и после него должны буква или цифра; последовательные дефисы не допускаются в именах контейнеров.</span><span class="sxs-lookup"><span data-stu-id="6487c-208">Every dash (-) character must be immediately preceded and followed by a letter or number; consecutive dashes are not permitted in container names.</span></span>
1. <span data-ttu-id="6487c-209">Все буквы в имени контейнера должны быть строчными.</span><span class="sxs-lookup"><span data-stu-id="6487c-209">All letters in a container name must be lowercase.</span></span>
1. <span data-ttu-id="6487c-210">Имени контейнера должна составлять от 3 до 63 символов.</span><span class="sxs-lookup"><span data-stu-id="6487c-210">Container names must be from 3 through 63 characters long.</span></span>

<span data-ttu-id="6487c-211">Обратите внимание на то, что имя контейнера всегда должен быть нижнего регистра.</span><span class="sxs-lookup"><span data-stu-id="6487c-211">Note that the name of a container must always be lowercase.</span></span> <span data-ttu-id="6487c-212">Если вы включите является буквой верхнего регистра в имени контейнера или другом нарушении правил именования контейнера, может появиться ошибку 400 (неправильный запрос).</span><span class="sxs-lookup"><span data-stu-id="6487c-212">If you include an upper-case letter in a container name, or otherwise violate the container naming rules, you may receive a 400 error (Bad Request).</span></span>

## <a name="managing-security-for-blobs"></a><span data-ttu-id="6487c-213">Управление безопасностью для больших двоичных объектов</span><span class="sxs-lookup"><span data-stu-id="6487c-213">Managing security for blobs</span></span>

<span data-ttu-id="6487c-214">По умолчанию службы хранилища Azure защищает ваши данные, ограничивая доступ к владелец учетной записи, у которого есть ключи доступа учетной записи.</span><span class="sxs-lookup"><span data-stu-id="6487c-214">By default, Azure Storage keeps your data secure by limiting access to the account owner, who is in possession of the account access keys.</span></span> <span data-ttu-id="6487c-215">Если вам нужно совместно использовать данные большого двоичного объекта в учетной записи хранения, очень важно сделать это без ущерба для безопасности ключей доступа учетной записи.</span><span class="sxs-lookup"><span data-stu-id="6487c-215">When you need to share blob data in your storage account, it is important to do so without compromising the security of your account access keys.</span></span> <span data-ttu-id="6487c-216">Кроме того можно зашифровать данные больших двоичных объектов, чтобы обеспечить безопасную отправку по сети и в службе хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="6487c-216">Additionally, you can encrypt blob data to ensure that it is secure going over the wire and in Azure Storage.</span></span>

### <a name="controlling-access-to-blob-data"></a><span data-ttu-id="6487c-217">Управление доступом к данным BLOB-объектов</span><span class="sxs-lookup"><span data-stu-id="6487c-217">Controlling access to blob data</span></span>

<span data-ttu-id="6487c-218">По умолчанию данные больших двоичных объектов в учетной записи хранения доступен только владельцу учетной записи хранения.</span><span class="sxs-lookup"><span data-stu-id="6487c-218">By default, the blob data in your storage account is accessible only to storage account owner.</span></span> <span data-ttu-id="6487c-219">Проверка подлинности запросов к хранилищу BLOB-объектов требуется ключ доступа учетной записи по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6487c-219">Authenticating requests against Blob storage requires the account access key by default.</span></span> <span data-ttu-id="6487c-220">Тем не менее может потребоваться сделать определенные данные больших двоичных объектов доступным другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="6487c-220">However, you might want to make certain blob data available to other users.</span></span>

<span data-ttu-id="6487c-221">Дополнительные сведения о том, как управлять доступом к хранилище BLOB-объектов см. в разделе [руководство по .NET для раздела хранилища BLOB-объектов используется управление доступом на](/azure/storage/storage-dotnet-how-to-use-blobs#controlling-access-to-blob-data).</span><span class="sxs-lookup"><span data-stu-id="6487c-221">For details on how to control access to blob storage, see [the .NET guide for blob storage section on access control](/azure/storage/storage-dotnet-how-to-use-blobs#controlling-access-to-blob-data).</span></span>


### <a name="encrypting-blob-data"></a><span data-ttu-id="6487c-222">Шифрование данных больших двоичных объектов</span><span class="sxs-lookup"><span data-stu-id="6487c-222">Encrypting blob data</span></span>

<span data-ttu-id="6487c-223">Служба хранилища Azure поддерживает шифрование данных больших двоичных объектов, как на стороне клиента, так и на сервере.</span><span class="sxs-lookup"><span data-stu-id="6487c-223">Azure Storage supports encrypting blob data both at the client and on the server.</span></span>

<span data-ttu-id="6487c-224">Сведения о шифровании данных больших двоичных объектов, см. в разделе [руководство по .NET для раздела хранилища BLOB-объектов на шифрование](/azure/storage/storage-dotnet-how-to-use-blobs#encrypting-blob-data).</span><span class="sxs-lookup"><span data-stu-id="6487c-224">For details on encrypting blob data, see [the .NET guide for blob storage section on encryption](/azure/storage/storage-dotnet-how-to-use-blobs#encrypting-blob-data).</span></span>

## <a name="next-steps"></a><span data-ttu-id="6487c-225">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="6487c-225">Next steps</span></span>

<span data-ttu-id="6487c-226">Теперь, когда вы узнали основные сведения о хранилище BLOB-объектов, используйте следующие ссылки для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="6487c-226">Now that you've learned the basics of Blob storage, follow these links to learn more.</span></span>

### <a name="tools"></a><span data-ttu-id="6487c-227">Инструменты</span><span class="sxs-lookup"><span data-stu-id="6487c-227">Tools</span></span>
- <span data-ttu-id="6487c-228">[F# AzureStorageTypeProvider](https://fsprojects.github.io/AzureStorageTypeProvider/) поставщик типов F#, который может использоваться для просмотра ресурсов BLOB-объектов, таблиц и хранилища очередей Azure и легко применить с ними операции CRUD.</span><span class="sxs-lookup"><span data-stu-id="6487c-228">[F# AzureStorageTypeProvider](https://fsprojects.github.io/AzureStorageTypeProvider/) An F# Type Provider which can be used to explore Blob, Table and Queue Azure Storage assets and easily apply CRUD operations on them.</span></span>
- <span data-ttu-id="6487c-229">[FSharp.Azure.Storage](https://github.com/fsprojects/FSharp.Azure.Storage) F# API для использования службы хранилища таблиц Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="6487c-229">[FSharp.Azure.Storage](https://github.com/fsprojects/FSharp.Azure.Storage) An F# API for using Microsoft Azure Table Storage service</span></span>
- <span data-ttu-id="6487c-230">[Обозреватель хранилищ Microsoft Azure (MASE)](/azure/vs-azure-tools-storage-manage-with-storage-explorer) — это бесплатное автономное приложение от корпорации Майкрософт, который позволяет визуально работать с данными из хранилища Azure в Windows, OS X и Linux.</span><span class="sxs-lookup"><span data-stu-id="6487c-230">[Microsoft Azure Storage Explorer (MASE)](/azure/vs-azure-tools-storage-manage-with-storage-explorer) is a free, standalone app from Microsoft that enables you to work visually with Azure Storage data on Windows, OS X, and Linux.</span></span>

### <a name="blob-storage-reference"></a><span data-ttu-id="6487c-231">Справочник по хранилища BLOB-объектов</span><span class="sxs-lookup"><span data-stu-id="6487c-231">Blob storage reference</span></span>

- [<span data-ttu-id="6487c-232">API службы хранилища Azure для .NET</span><span class="sxs-lookup"><span data-stu-id="6487c-232">Azure Storage APIs for .NET</span></span>](/dotnet/api/overview/azure/storage)
- [<span data-ttu-id="6487c-233">Справочник по API REST служб хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="6487c-233">Azure Storage Services REST API Reference</span></span>](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)

### <a name="related-guides"></a><span data-ttu-id="6487c-234">Связанные руководства</span><span class="sxs-lookup"><span data-stu-id="6487c-234">Related guides</span></span>

- [<span data-ttu-id="6487c-235">Приступая к работе с хранилищем BLOB-объектов Azure в C#</span><span class="sxs-lookup"><span data-stu-id="6487c-235">Getting Started with Azure Blob Storage in C#</span></span>](https://azure.microsoft.com/resources/samples/storage-blob-dotnet-getting-started/)
- [<span data-ttu-id="6487c-236">Перенос данных с помощью программы командной строки AzCopy для Windows</span><span class="sxs-lookup"><span data-stu-id="6487c-236">Transfer data with the AzCopy command-line utility on Windows</span></span>](/azure/storage/common/storage-use-azcopy)
- [<span data-ttu-id="6487c-237">Перенос данных с помощью служебной программы командной строки AzCopy для Linux</span><span class="sxs-lookup"><span data-stu-id="6487c-237">Transfer data with the AzCopy command-line utility on Linux</span></span>](/azure/storage/common/storage-use-azcopy-linux)
- [<span data-ttu-id="6487c-238">Настройка строк подключения службы хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="6487c-238">Configure Azure Storage connection strings</span></span>](/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="6487c-239">Блог группы разработчиков хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="6487c-239">Azure Storage Team Blog</span></span>](https://blogs.msdn.microsoft.com/windowsazurestorage/)
