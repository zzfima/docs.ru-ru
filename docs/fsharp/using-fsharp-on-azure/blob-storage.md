---
title: "Начало работы с хранилищем больших двоичных объектов Azure с помощью F #"
description: "Хранить неструктурированные данные в облако с помощью хранилища больших двоичных объектов Azure."
keywords: "Visual f #, f #, функционального программирования, .NET, .NET Core, Azure"
author: sylvanc
ms.author: phcart
ms.date: 09/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: c5b74a4f-dcd1-4849-930c-904b6c8a04e1
ms.openlocfilehash: 92e26aff605d3bed89e388dd3616a2a9a3a96081
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="get-started-with-azure-blob-storage-using-f"></a><span data-ttu-id="14a74-104">Начало работы с хранилищем больших двоичных объектов Azure с помощью F #</span><span class="sxs-lookup"><span data-stu-id="14a74-104">Get started with Azure Blob storage using F#</span></span> #

<span data-ttu-id="14a74-105">Хранилище BLOB-объектов Azure — это служба, которая сохраняет неструктурированные данные в облаке в виде BLOB-объектов.</span><span class="sxs-lookup"><span data-stu-id="14a74-105">Azure Blob storage is a service that stores unstructured data in the cloud as objects/blobs.</span></span> <span data-ttu-id="14a74-106">В хранилище BLOB-объектов можно хранить любые типы текстовых или двоичных данных, таких как документы, файлы мультимедиа или установщики приложений.</span><span class="sxs-lookup"><span data-stu-id="14a74-106">Blob storage can store any type of text or binary data, such as a document, media file, or application installer.</span></span> <span data-ttu-id="14a74-107">Хранилище BLOB-объектов также называют хранилищем объектов.</span><span class="sxs-lookup"><span data-stu-id="14a74-107">Blob storage is also referred to as object storage.</span></span>

<span data-ttu-id="14a74-108">В этой статье показано, как выполнять типовые задачи с помощью хранилища больших двоичных объектов.</span><span class="sxs-lookup"><span data-stu-id="14a74-108">This article shows you how to perform common tasks using Blob storage.</span></span> <span data-ttu-id="14a74-109">Образцы записываются с помощью F # с помощью клиентской библиотеки хранилища Azure для .NET.</span><span class="sxs-lookup"><span data-stu-id="14a74-109">The samples are written using F# using the Azure Storage Client Library for .NET.</span></span> <span data-ttu-id="14a74-110">Рассмотренные задачи включают как передача, список, загрузка и удаление больших двоичных объектов.</span><span class="sxs-lookup"><span data-stu-id="14a74-110">The tasks covered include how to upload, list, download, and delete blobs.</span></span>

<span data-ttu-id="14a74-111">Общие сведения о хранилище больших двоичных объектов, в разделе [руководство по .NET для хранилища BLOB-объектов](/azure/storage/storage-dotnet-how-to-use-blobs).</span><span class="sxs-lookup"><span data-stu-id="14a74-111">For a conceptual overview of blob storage, see [the .NET guide for blob storage](/azure/storage/storage-dotnet-how-to-use-blobs).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="14a74-112">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="14a74-112">Prerequisites</span></span>

<span data-ttu-id="14a74-113">Чтобы использовать это руководство, необходимо сначала [создать учетную запись хранилища Azure](/azure/storage/storage-create-storage-account).</span><span class="sxs-lookup"><span data-stu-id="14a74-113">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span> <span data-ttu-id="14a74-114">Необходимо также ключи доступа к хранилищу для этой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="14a74-114">You also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="14a74-115">Создание скрипта F # и начала F #, интерактивный</span><span class="sxs-lookup"><span data-stu-id="14a74-115">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="14a74-116">Примеры в этой статье используется в F # приложения или скрипта F #.</span><span class="sxs-lookup"><span data-stu-id="14a74-116">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="14a74-117">Чтобы создать скрипт F #, создайте файл с `.fsx` расширение, например `blobs.fsx`, в среде разработки F #.</span><span class="sxs-lookup"><span data-stu-id="14a74-117">To create an F# script, create a file with the `.fsx` extension, for example `blobs.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="14a74-118">Затем с помощью [диспетчера пакетов](package-management.md) например [Paket](https://fsprojects.github.io/Paket/) или [NuGet](https://www.nuget.org/) установка `WindowsAzure.Storage` и `Microsoft.WindowsAzure.ConfigurationManager` пакетов и ссылок `WindowsAzure.Storage.dll` и `Microsoft.WindowsAzure.Configuration.dll` в сценарий с помощью `#r` директивы.</span><span class="sxs-lookup"><span data-stu-id="14a74-118">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` and `Microsoft.WindowsAzure.ConfigurationManager` packages and reference `WindowsAzure.Storage.dll` and `Microsoft.WindowsAzure.Configuration.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="14a74-119">Добавьте объявления пространств имен</span><span class="sxs-lookup"><span data-stu-id="14a74-119">Add namespace declarations</span></span>

<span data-ttu-id="14a74-120">Добавьте следующие `open` инструкции в начало `blobs.fsx` файла:</span><span class="sxs-lookup"><span data-stu-id="14a74-120">Add the following `open` statements to the top of the `blobs.fsx` file:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a><span data-ttu-id="14a74-121">Получение строки подключения</span><span class="sxs-lookup"><span data-stu-id="14a74-121">Get your connection string</span></span>

<span data-ttu-id="14a74-122">В этом учебнике требуется строка подключения хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="14a74-122">You need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="14a74-123">Дополнительные сведения о строках соединения см. в разделе [Настройка строки подключения хранилища](/azure/storage/storage-configure-connection-string).</span><span class="sxs-lookup"><span data-stu-id="14a74-123">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="14a74-124">В учебнике введите строку подключения в скрипте, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="14a74-124">For the tutorial, you enter your connection string in your script, like this:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L11-L11)]

<span data-ttu-id="14a74-125">Однако это **не рекомендуется** для реальных проектах.</span><span class="sxs-lookup"><span data-stu-id="14a74-125">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="14a74-126">Ключ учетной записи хранилища аналогична корневой пароль для учетной записи хранилища.</span><span class="sxs-lookup"><span data-stu-id="14a74-126">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="14a74-127">Всегда будьте внимательны защитить ключ учетной записи хранилища.</span><span class="sxs-lookup"><span data-stu-id="14a74-127">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="14a74-128">Избегайте распространением их другим пользователям, жестко запрограммированные ее или сохранить в текстовый файл, доступный другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="14a74-128">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="14a74-129">Можно повторно создать ключ с помощью портала Azure, если вы считаете, что он был скомпрометирован.</span><span class="sxs-lookup"><span data-stu-id="14a74-129">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="14a74-130">Для реальных приложений для сохранения строки подключения хранилища рекомендуется в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="14a74-130">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="14a74-131">Чтобы получить строку подключения из файла конфигурации, это можно сделать:</span><span class="sxs-lookup"><span data-stu-id="14a74-131">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L13-L15)]

<span data-ttu-id="14a74-132">С помощью диспетчера конфигурации Azure является необязательным.</span><span class="sxs-lookup"><span data-stu-id="14a74-132">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="14a74-133">Можно также использовать интерфейс API, например .NET Framework `ConfigurationManager` типа.</span><span class="sxs-lookup"><span data-stu-id="14a74-133">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="14a74-134">Синтаксический анализ строки соединения</span><span class="sxs-lookup"><span data-stu-id="14a74-134">Parse the connection string</span></span>

<span data-ttu-id="14a74-135">Чтобы обработать строку подключения, используйте:</span><span class="sxs-lookup"><span data-stu-id="14a74-135">To parse the connection string, use:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L21-L22)]

<span data-ttu-id="14a74-136">Возвращает `CloudStorageAccount`.</span><span class="sxs-lookup"><span data-stu-id="14a74-136">This returns a `CloudStorageAccount`.</span></span>

### <a name="create-some-local-dummy-data"></a><span data-ttu-id="14a74-137">Создать некоторые локальные фиктивные данные</span><span class="sxs-lookup"><span data-stu-id="14a74-137">Create some local dummy data</span></span>

<span data-ttu-id="14a74-138">Прежде чем начать, создайте некоторые фиктивный локальных данных в каталоге наш сценарий.</span><span class="sxs-lookup"><span data-stu-id="14a74-138">Before you begin, create some dummy local data in the directory of our script.</span></span> <span data-ttu-id="14a74-139">Затем можно загрузить эти данные.</span><span class="sxs-lookup"><span data-stu-id="14a74-139">Later you upload this data.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L28-L30)]

### <a name="create-the-blob-service-client"></a><span data-ttu-id="14a74-140">Создание клиента службы BLOB-объектов</span><span class="sxs-lookup"><span data-stu-id="14a74-140">Create the Blob service client</span></span>

<span data-ttu-id="14a74-141">`CloudBlobClient` Тип позволяет получить контейнеры и большие двоичные объекты, хранящиеся в хранилище больших двоичных объектов.</span><span class="sxs-lookup"><span data-stu-id="14a74-141">The `CloudBlobClient` type enables you to retrieve containers and blobs stored in Blob storage.</span></span> <span data-ttu-id="14a74-142">Вот один из способов создания клиента службы.</span><span class="sxs-lookup"><span data-stu-id="14a74-142">Here's one way to create the service client:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L36-L36)]

<span data-ttu-id="14a74-143">Теперь вы готовы написать код, который считывает и записывает данные в хранилище больших двоичных объектов.</span><span class="sxs-lookup"><span data-stu-id="14a74-143">Now you are ready to write code that reads data from and writes data to Blob storage.</span></span>

## <a name="create-a-container"></a><span data-ttu-id="14a74-144">Создание контейнера</span><span class="sxs-lookup"><span data-stu-id="14a74-144">Create a container</span></span>

<span data-ttu-id="14a74-145">В этом примере показано, как создать контейнер, если он еще не существует:</span><span class="sxs-lookup"><span data-stu-id="14a74-145">This example shows how to create a container if it does not already exist:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L42-L46)]

<span data-ttu-id="14a74-146">По умолчанию новый контейнер является закрытым, это означает, что необходимо указать ключи доступа к хранилищу для загрузки больших двоичных объектов из этого контейнера.</span><span class="sxs-lookup"><span data-stu-id="14a74-146">By default, the new container is private, meaning that you must specify your storage access key to download blobs from this container.</span></span> <span data-ttu-id="14a74-147">Если вы хотите сделать файлы в контейнере общедоступной, можно задать контейнер должен быть открытым, используя следующий код:</span><span class="sxs-lookup"><span data-stu-id="14a74-147">If you want to make the files within the container available to everyone, you can set the container to be public using the following code:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L48-L49)]

<span data-ttu-id="14a74-148">Содержимое в Интернете могут видеть большие двоичные объекты в общедоступном контейнере, но можно изменить или удалить их только в том случае, если у вас есть ключ соответствующую учетную запись доступа или подписанный URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="14a74-148">Anyone on the Internet can see blobs in a public container, but you can modify or delete them only if you have the appropriate account access key or a shared access signature.</span></span>

## <a name="upload-a-blob-into-a-container"></a><span data-ttu-id="14a74-149">Отправить большой двоичный объект в контейнер</span><span class="sxs-lookup"><span data-stu-id="14a74-149">Upload a blob into a container</span></span>

<span data-ttu-id="14a74-150">Хранилище больших двоичных объектов Azure поддерживает блочных и страничных больших двоичных объектов.</span><span class="sxs-lookup"><span data-stu-id="14a74-150">Azure Blob Storage supports block blobs and page blobs.</span></span> <span data-ttu-id="14a74-151">В большинстве случаев блочного BLOB-объекта — это рекомендуемый тип для использования.</span><span class="sxs-lookup"><span data-stu-id="14a74-151">In most cases, a block blob is the recommended type to use.</span></span>

<span data-ttu-id="14a74-152">Чтобы отправить файл в большой двоичный объект блока, получить ссылку на контейнер и использовать его для получения ссылки блок больших двоичных объектов.</span><span class="sxs-lookup"><span data-stu-id="14a74-152">To upload a file to a block blob, get a container reference and use it to get a block blob reference.</span></span> <span data-ttu-id="14a74-153">Получив ссылку на большой двоичный объект можно передать любой поток данных в его путем вызова `UploadFromFile` метод.</span><span class="sxs-lookup"><span data-stu-id="14a74-153">Once you have a blob reference, you can upload any stream of data to it by calling the `UploadFromFile` method.</span></span> <span data-ttu-id="14a74-154">Эта операция создает большой двоичный объект, если он не существует, или ранее перезаписать его, если он существует.</span><span class="sxs-lookup"><span data-stu-id="14a74-154">This operation creates the blob if it didn't previously exist, or overwrite it if it does exist.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L55-L59)]

## <a name="list-the-blobs-in-a-container"></a><span data-ttu-id="14a74-155">Перечисление BLOB-объектов в контейнере</span><span class="sxs-lookup"><span data-stu-id="14a74-155">List the blobs in a container</span></span>

<span data-ttu-id="14a74-156">Перечисление BLOB-объектов в контейнере, необходимо сначала получите ссылку на контейнер.</span><span class="sxs-lookup"><span data-stu-id="14a74-156">To list the blobs in a container, first get a container reference.</span></span> <span data-ttu-id="14a74-157">Затем можно использовать контейнер `ListBlobs` метод для извлечения больших двоичных объектов и/или каталогов в ней.</span><span class="sxs-lookup"><span data-stu-id="14a74-157">You can then use the container's `ListBlobs` method to retrieve the blobs and/or directories within it.</span></span> <span data-ttu-id="14a74-158">Для доступа к широкий набор свойств и методов для возвращенной `IListBlobItem`, его необходимо привести к типу `CloudBlockBlob`, `CloudPageBlob`, или `CloudBlobDirectory` объекта.</span><span class="sxs-lookup"><span data-stu-id="14a74-158">To access the rich set of properties and methods for a returned `IListBlobItem`, you must cast it to a `CloudBlockBlob`, `CloudPageBlob`, or `CloudBlobDirectory` object.</span></span> <span data-ttu-id="14a74-159">Если тип неизвестен, чтобы определить, что приведение к типу можно использовать проверку типов.</span><span class="sxs-lookup"><span data-stu-id="14a74-159">If the type is unknown, you can use a type check to determine which to cast it to.</span></span> <span data-ttu-id="14a74-160">Следующий код показывает, как для извлечения и вывода каждого элемента в URI `mydata` контейнера:</span><span class="sxs-lookup"><span data-stu-id="14a74-160">The following code demonstrates how to retrieve and output the URI of each item in the `mydata` container:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L67-L80)]

<span data-ttu-id="14a74-161">Вы также можете имя большие двоичные объекты с сведения о пути, в именах.</span><span class="sxs-lookup"><span data-stu-id="14a74-161">You can also name blobs with path information in their names.</span></span> <span data-ttu-id="14a74-162">Это создает структуру виртуального каталога, в которой можно упорядочивать и просматривать как и традиционные файловой системы.</span><span class="sxs-lookup"><span data-stu-id="14a74-162">This creates a virtual directory structure that you can organize and traverse as you would a traditional file system.</span></span> <span data-ttu-id="14a74-163">Обратите внимание, что структура каталогов виртуального только - только доступные ресурсы в хранилище больших двоичных объектов, контейнеры и большие двоичные объекты.</span><span class="sxs-lookup"><span data-stu-id="14a74-163">Note that the directory structure is virtual only - the only resources available in Blob storage are containers and blobs.</span></span> <span data-ttu-id="14a74-164">Однако клиентская библиотека хранилища предоставляет `CloudBlobDirectory` объекта виртуального каталога и упростить процесс работы с большими двоичными объектами, которые упорядочены таким образом.</span><span class="sxs-lookup"><span data-stu-id="14a74-164">However, the storage client library offers a `CloudBlobDirectory` object to refer to a virtual directory and simplify the process of working with blobs that are organized in this way.</span></span>

<span data-ttu-id="14a74-165">Например, рассмотрим следующий набор блочных больших двоичных объектов в контейнере с именем `photos`:</span><span class="sxs-lookup"><span data-stu-id="14a74-165">For example, consider the following set of block blobs in a container named `photos`:</span></span>

<span data-ttu-id="14a74-166">*photo1.jpg*
*2015/architecture/description.txt*
*2015/architecture/photo3.jpg*
*2015 или Архитектура/photo4.jpg*
*2016/architecture/photo5.jpg*
*2016/architecture/photo6.jpg* 
 *2016/architecture/description.txt*
*2016/photo7.jpg*</span><span class="sxs-lookup"><span data-stu-id="14a74-166">*photo1.jpg*
*2015/architecture/description.txt*
*2015/architecture/photo3.jpg*
*2015/architecture/photo4.jpg*
*2016/architecture/photo5.jpg*
*2016/architecture/photo6.jpg*
*2016/architecture/description.txt*
*2016/photo7.jpg*</span></span>

<span data-ttu-id="14a74-167">При вызове `ListBlobs` в контейнере (как в приведенном выше примере), возвращается иерархический список.</span><span class="sxs-lookup"><span data-stu-id="14a74-167">When you call `ListBlobs` on a container (as in the above sample), a hierarchical listing is returned.</span></span> <span data-ttu-id="14a74-168">Если он содержит оба `CloudBlobDirectory` и `CloudBlockBlob` объекты, представляющие каталоги и большие двоичные объекты в контейнере, соответственно, а затем полученный результат выглядит примерно так:</span><span class="sxs-lookup"><span data-stu-id="14a74-168">If it contains both `CloudBlobDirectory` and `CloudBlockBlob` objects, representing the directories and blobs in the container, respectively, then the resulting output looks similar to this:</span></span>

```console
Directory: https://<accountname>.blob.core.windows.net/photos/2015/
Directory: https://<accountname>.blob.core.windows.net/photos/2016/
Block blob of length 505623: https://<accountname>.blob.core.windows.net/photos/photo1.jpg
```

<span data-ttu-id="14a74-169">При необходимости можно задать `UseFlatBlobListing` параметр `ListBlobs` метод `true`.</span><span class="sxs-lookup"><span data-stu-id="14a74-169">Optionally, you can set the `UseFlatBlobListing` parameter of the `ListBlobs` method to `true`.</span></span> <span data-ttu-id="14a74-170">В этом случае каждый большой двоичный объект в контейнере возвращается в виде `CloudBlockBlob` объекта.</span><span class="sxs-lookup"><span data-stu-id="14a74-170">In this case, every blob in the container is returned as a `CloudBlockBlob` object.</span></span> <span data-ttu-id="14a74-171">Вызов `ListBlobs` для возврата в плоском листинге выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="14a74-171">The call to `ListBlobs` to return a flat listing looks like this:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L82-L89)]

<span data-ttu-id="14a74-172">Кроме того, в зависимости от текущее содержимое контейнера, результаты будут выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="14a74-172">and, depending on the current contents of your container, the results look like this:</span></span>

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

## <a name="download-blobs"></a><span data-ttu-id="14a74-173">Загрузка больших двоичных объектов</span><span class="sxs-lookup"><span data-stu-id="14a74-173">Download blobs</span></span>

<span data-ttu-id="14a74-174">Чтобы загрузить больших двоичных объектов, сначала получить ссылку на большой двоичный объект, а затем вызвать `DownloadToStream` метод.</span><span class="sxs-lookup"><span data-stu-id="14a74-174">To download blobs, first retrieve a blob reference and then call the `DownloadToStream` method.</span></span> <span data-ttu-id="14a74-175">В следующем примере используется `DownloadToStream` способ передачи содержимого большого двоичного объекта в объект потока, могут затем сохраняться в локальный файл.</span><span class="sxs-lookup"><span data-stu-id="14a74-175">The following example uses the `DownloadToStream` method to transfer the blob contents to a stream object that you can then persist to a local file.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L95-L101)]

<span data-ttu-id="14a74-176">Можно также использовать `DownloadToStream` метод для загрузки содержимого большого двоичного объекта в виде текстовой строки.</span><span class="sxs-lookup"><span data-stu-id="14a74-176">You can also use the `DownloadToStream` method to download the contents of a blob as a text string.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L103-L106)]

## <a name="delete-blobs"></a><span data-ttu-id="14a74-177">Удаление больших двоичных объектов</span><span class="sxs-lookup"><span data-stu-id="14a74-177">Delete blobs</span></span>

<span data-ttu-id="14a74-178">Чтобы удалить большой двоичный объект, сначала получить ссылку на большой двоичный объект и затем вызвать `Delete` метода.</span><span class="sxs-lookup"><span data-stu-id="14a74-178">To delete a blob, first get a blob reference and then call the `Delete` method on it.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L112-L116)]

## <a name="list-blobs-in-pages-asynchronously"></a><span data-ttu-id="14a74-179">Перечисление больших двоичных объектов, на страницах асинхронно</span><span class="sxs-lookup"><span data-stu-id="14a74-179">List blobs in pages asynchronously</span></span>

<span data-ttu-id="14a74-180">Если вы хотите управлять количество результатов, возвращаемых в одной операцией получения листинга списка большое количество больших двоичных объектов, можно перечислить большие двоичные объекты в страницы результатов.</span><span class="sxs-lookup"><span data-stu-id="14a74-180">If you are listing a large number of blobs, or you want to control the number of results you return in one listing operation, you can list blobs in pages of results.</span></span> <span data-ttu-id="14a74-181">В этом примере показано, как асинхронно, возвращают результаты в страницах, чтобы выполнение не блокируется во время ожидания для возвращения большого набора результатов.</span><span class="sxs-lookup"><span data-stu-id="14a74-181">This example shows how to return results in pages asynchronously, so that execution is not blocked while waiting to return a large set of results.</span></span>

<span data-ttu-id="14a74-182">В этом примере показано плоский перечисления больших двоичных объектов, но можно также выполнить, задав иерархический список `useFlatBlobListing` параметр `ListBlobsSegmentedAsync` метод `false`.</span><span class="sxs-lookup"><span data-stu-id="14a74-182">This example shows a flat blob listing, but you can also perform a hierarchical listing, by setting the `useFlatBlobListing` parameter of the `ListBlobsSegmentedAsync` method to `false`.</span></span>

<span data-ttu-id="14a74-183">Пример определяет асинхронный метод, с помощью `async` блока.</span><span class="sxs-lookup"><span data-stu-id="14a74-183">The sample defines an asynchronous method, using an `async` block.</span></span> <span data-ttu-id="14a74-184">``let!`` Ключевое слово приостанавливает выполнение образец метода до завершения задачи в список.</span><span class="sxs-lookup"><span data-stu-id="14a74-184">The ``let!`` keyword suspends execution of the sample method until the listing task completes.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L122-L160)]

<span data-ttu-id="14a74-185">Эта процедура асинхронной теперь можно использовать следующим образом.</span><span class="sxs-lookup"><span data-stu-id="14a74-185">We can now use this asynchronous routine as follows.</span></span> <span data-ttu-id="14a74-186">Сначала необходимо отправить некоторые фиктивные данные (с помощью локального файла, созданного ранее в этом учебнике).</span><span class="sxs-lookup"><span data-stu-id="14a74-186">First you upload some dummy data (using the local file created earlier in this tutorial).</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L162-L166)]

<span data-ttu-id="14a74-187">Теперь вызовите процедуру.</span><span class="sxs-lookup"><span data-stu-id="14a74-187">Now, call the routine.</span></span> <span data-ttu-id="14a74-188">Вы используете ``Async.RunSynchronously`` для принудительного выполнения асинхронной операции.</span><span class="sxs-lookup"><span data-stu-id="14a74-188">You use ``Async.RunSynchronously`` to force the execution of the asynchronous operation.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L168-L168)]

## <a name="writing-to-an-append-blob"></a><span data-ttu-id="14a74-189">Запись в добавочный BLOB-объект</span><span class="sxs-lookup"><span data-stu-id="14a74-189">Writing to an append blob</span></span>

<span data-ttu-id="14a74-190">Добавочный большой двоичный объект оптимизирован для операций добавления, например ведение журнала.</span><span class="sxs-lookup"><span data-stu-id="14a74-190">An append blob is optimized for append operations, such as logging.</span></span> <span data-ttu-id="14a74-191">Как большой двоичный объект блока добавочный BLOB-объект состоит из блоков, но при добавлении нового блока добавочный большой двоичный объект всегда добавляются в конец большого двоичного объекта.</span><span class="sxs-lookup"><span data-stu-id="14a74-191">Like a block blob, an append blob is comprised of blocks, but when you add a new block to an append blob, it is always appended to the end of the blob.</span></span> <span data-ttu-id="14a74-192">Нельзя обновить или удалить существующий блок в добавочный большой двоичный объект.</span><span class="sxs-lookup"><span data-stu-id="14a74-192">You cannot update or delete an existing block in an append blob.</span></span> <span data-ttu-id="14a74-193">Идентификаторы блокировок добавочный большой двоичный объект не отображаются, как и для большого двоичного объекта.</span><span class="sxs-lookup"><span data-stu-id="14a74-193">The block IDs for an append blob are not exposed as they are for a block blob.</span></span>

<span data-ttu-id="14a74-194">Каждый блок в добавочный большой двоичный объект может быть разный размер не более 4 МБ и добавочный большой двоичный объект может содержать не более 50 000 блоков.</span><span class="sxs-lookup"><span data-stu-id="14a74-194">Each block in an append blob can be a different size, up to a maximum of 4 MB, and an append blob can include a maximum of 50,000 blocks.</span></span> <span data-ttu-id="14a74-195">Максимальный размер добавочный большой двоичный объект является таким образом немного более 195 ГБ (4 МБ X 50 000 блоков).</span><span class="sxs-lookup"><span data-stu-id="14a74-195">The maximum size of an append blob is therefore slightly more than 195 GB (4 MB X 50,000 blocks).</span></span>

<span data-ttu-id="14a74-196">Следующий пример создает новый добавочный большой двоичный объект и добавляет некоторые данные, имитируя операция простого ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="14a74-196">The following example creates a new append blob and appends some data to it, simulating a simple logging operation.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L174-L203)]

<span data-ttu-id="14a74-197">В разделе [основные сведения о блочных, страничные большие двоичные объекты и добавьте большие двоичные объекты](https://msdn.microsoft.com/library/azure/ee691964.aspx) Дополнительные сведения о различиях между три типа больших двоичных объектов.</span><span class="sxs-lookup"><span data-stu-id="14a74-197">See [Understanding Block Blobs, Page Blobs, and Append Blobs](https://msdn.microsoft.com/library/azure/ee691964.aspx) for more information about the differences between the three types of blobs.</span></span>

## <a name="concurrent-access"></a><span data-ttu-id="14a74-198">Параллельный доступ</span><span class="sxs-lookup"><span data-stu-id="14a74-198">Concurrent access</span></span>

<span data-ttu-id="14a74-199">Для поддержки параллельного доступа в большой двоичный объект из нескольких клиентов или несколько экземпляров процесса, можно использовать **ETags** или **аренды**.</span><span class="sxs-lookup"><span data-stu-id="14a74-199">To support concurrent access to a blob from multiple clients or multiple process instances, you can use **ETags** or **leases**.</span></span>

* <span data-ttu-id="14a74-200">**ETag** -позволяет обнаружить, что большой двоичный объект или контейнер был изменен другим процессом</span><span class="sxs-lookup"><span data-stu-id="14a74-200">**Etag** - provides a way to detect that the blob or container has been modified by another process</span></span>

* <span data-ttu-id="14a74-201">**Аренда** -предоставляет способ получения монопольного, обновляемым, запись или удаление доступа к BLOB-объекта в течение заданного времени</span><span class="sxs-lookup"><span data-stu-id="14a74-201">**Lease** - provides a way to obtain exclusive, renewable, write or delete access to a blob for a period of time</span></span>

<span data-ttu-id="14a74-202">Дополнительные сведения см. в разделе [управление параллелизмом в хранилище Microsoft Azure](https://azure.microsoft.com/blog/managing-concurrency-in-microsoft-azure-storage-2/).</span><span class="sxs-lookup"><span data-stu-id="14a74-202">For more information, see [Managing Concurrency in Microsoft Azure Storage](https://azure.microsoft.com/blog/managing-concurrency-in-microsoft-azure-storage-2/).</span></span>

## <a name="naming-containers"></a><span data-ttu-id="14a74-203">Контейнеры именования</span><span class="sxs-lookup"><span data-stu-id="14a74-203">Naming containers</span></span>

<span data-ttu-id="14a74-204">Каждый BLOB-объектов в хранилище Azure должен находиться в контейнере.</span><span class="sxs-lookup"><span data-stu-id="14a74-204">Every blob in Azure storage must reside in a container.</span></span> <span data-ttu-id="14a74-205">Контейнер составляет часть имени большого двоичного объекта.</span><span class="sxs-lookup"><span data-stu-id="14a74-205">The container forms part of the blob name.</span></span> <span data-ttu-id="14a74-206">Например `mydata` — имя контейнера в этих blob образец идентификаторы URI:</span><span class="sxs-lookup"><span data-stu-id="14a74-206">For example, `mydata` is the name of the container in these sample blob URIs:</span></span>

    https://storagesample.blob.core.windows.net/mydata/blob1.txt
    https://storagesample.blob.core.windows.net/mydata/photos/myphoto.jpg

<span data-ttu-id="14a74-207">Имя контейнера должно быть допустимым именем DNS, удовлетворяющих следующим правилам:</span><span class="sxs-lookup"><span data-stu-id="14a74-207">A container name must be a valid DNS name, conforming to the following naming rules:</span></span>

1. <span data-ttu-id="14a74-208">Имена контейнеров должны начинаться с буквы или цифры и может содержать только буквы, цифры и тире (-).</span><span class="sxs-lookup"><span data-stu-id="14a74-208">Container names must start with a letter or number, and can contain only letters, numbers, and the dash (-) character.</span></span>
1. <span data-ttu-id="14a74-209">Каждому символу тире (-) должен быть немедленно и стоять буква или цифра; последовательные дефисы не допускаются в именах контейнеров.</span><span class="sxs-lookup"><span data-stu-id="14a74-209">Every dash (-) character must be immediately preceded and followed by a letter or number; consecutive dashes are not permitted in container names.</span></span>
1. <span data-ttu-id="14a74-210">Все буквы в имени контейнера должны быть строчными.</span><span class="sxs-lookup"><span data-stu-id="14a74-210">All letters in a container name must be lowercase.</span></span>
1. <span data-ttu-id="14a74-211">Длина имени контейнера должна составлять от 3 до 63 символов.</span><span class="sxs-lookup"><span data-stu-id="14a74-211">Container names must be from 3 through 63 characters long.</span></span>

<span data-ttu-id="14a74-212">Обратите внимание, что имя контейнера всегда должен быть нижнего регистра.</span><span class="sxs-lookup"><span data-stu-id="14a74-212">Note that the name of a container must always be lowercase.</span></span> <span data-ttu-id="14a74-213">Если включить буквой верхнего регистра в имени контейнера или иным образом нарушать правила именования контейнера, может появиться ошибку 400 (неправильный запрос).</span><span class="sxs-lookup"><span data-stu-id="14a74-213">If you include an upper-case letter in a container name, or otherwise violate the container naming rules, you may receive a 400 error (Bad Request).</span></span>

## <a name="managing-security-for-blobs"></a><span data-ttu-id="14a74-214">Управление безопасностью для больших двоичных объектов</span><span class="sxs-lookup"><span data-stu-id="14a74-214">Managing security for blobs</span></span>

<span data-ttu-id="14a74-215">По умолчанию хранилища Azure защищает ваши данные, ограничивая доступ к учетной записи владельца, являющегося владеющим ключей доступа учетных записей.</span><span class="sxs-lookup"><span data-stu-id="14a74-215">By default, Azure Storage keeps your data secure by limiting access to the account owner, who is in possession of the account access keys.</span></span> <span data-ttu-id="14a74-216">Если вам требуется общий доступ к данным BLOB-объектов в вашей учетной записи хранилища, важно сделать без риска для безопасности ключей доступа к учетной записи.</span><span class="sxs-lookup"><span data-stu-id="14a74-216">When you need to share blob data in your storage account, it is important to do so without compromising the security of your account access keys.</span></span> <span data-ttu-id="14a74-217">Кроме того можно зашифровать данные большого двоичного объекта, чтобы обеспечить его безопасность, перейдя по сети и в хранилище Azure.</span><span class="sxs-lookup"><span data-stu-id="14a74-217">Additionally, you can encrypt blob data to ensure that it is secure going over the wire and in Azure Storage.</span></span>

### <a name="controlling-access-to-blob-data"></a><span data-ttu-id="14a74-218">Управление доступом к данным BLOB-объект</span><span class="sxs-lookup"><span data-stu-id="14a74-218">Controlling access to blob data</span></span>

<span data-ttu-id="14a74-219">По умолчанию данные blob в учетной записи доступен только владельцу учетной записи хранилища.</span><span class="sxs-lookup"><span data-stu-id="14a74-219">By default, the blob data in your storage account is accessible only to storage account owner.</span></span> <span data-ttu-id="14a74-220">Проверка подлинности запросов в службу хранилища больших двоичных объектов требуется ключ доступа учетной записи по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="14a74-220">Authenticating requests against Blob storage requires the account access key by default.</span></span> <span data-ttu-id="14a74-221">Тем не менее может потребоваться сделать определенные данные больших двоичных объектов доступным другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="14a74-221">However, you might want to make certain blob data available to other users.</span></span>

<span data-ttu-id="14a74-222">Дополнительные сведения о том, как управлять доступом к хранилищу больших двоичных объектов см. в разделе [руководство по .NET для раздела хранилища больших двоичных объектов для управления доступом](/azure/storage/storage-dotnet-how-to-use-blobs#controlling-access-to-blob-data).</span><span class="sxs-lookup"><span data-stu-id="14a74-222">For details on how to control access to blob storage, see [the .NET guide for blob storage section on access control](/azure/storage/storage-dotnet-how-to-use-blobs#controlling-access-to-blob-data).</span></span>


### <a name="encrypting-blob-data"></a><span data-ttu-id="14a74-223">Шифрование данных больших двоичных объектов</span><span class="sxs-lookup"><span data-stu-id="14a74-223">Encrypting blob data</span></span>

<span data-ttu-id="14a74-224">Хранилище Azure поддерживает шифрование данных больших двоичных объектов как на клиенте, так и на сервере.</span><span class="sxs-lookup"><span data-stu-id="14a74-224">Azure Storage supports encrypting blob data both at the client and on the server.</span></span>

<span data-ttu-id="14a74-225">Дополнительные сведения о шифровании данных больших двоичных объектов см. в разделе [руководство по .NET для раздела хранилища BLOB-объектов на шифрование](/azure/storage/storage-dotnet-how-to-use-blobs#encrypting-blob-data).</span><span class="sxs-lookup"><span data-stu-id="14a74-225">For details on encrypting blob data, see [the .NET guide for blob storage section on encryption](/azure/storage/storage-dotnet-how-to-use-blobs#encrypting-blob-data).</span></span>

## <a name="next-steps"></a><span data-ttu-id="14a74-226">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="14a74-226">Next steps</span></span>

<span data-ttu-id="14a74-227">Теперь, когда вы узнали основы хранилища больших двоичных объектов, приведены по следующим ссылкам, чтобы получить дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="14a74-227">Now that you've learned the basics of Blob storage, follow these links to learn more.</span></span>

### <a name="tools"></a><span data-ttu-id="14a74-228">Инструменты</span><span class="sxs-lookup"><span data-stu-id="14a74-228">Tools</span></span>
- <span data-ttu-id="14a74-229">[F # AzureStorageTypeProvider](http://fsprojects.github.io/AzureStorageTypeProvider/) поставщик типа F #, который можно использовать для изучения средств Blob, таблицы и очереди хранилища Azure и легко применять операции CRUD над ними.</span><span class="sxs-lookup"><span data-stu-id="14a74-229">[F# AzureStorageTypeProvider](http://fsprojects.github.io/AzureStorageTypeProvider/) An F# Type Provider which can be used to explore Blob, Table and Queue Azure Storage assets and easily apply CRUD operations on them.</span></span>
- <span data-ttu-id="14a74-230">[FSharp.Azure.Storage](https://github.com/fsprojects/FSharp.Azure.Storage) API F # для использования службы хранилища таблиц Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="14a74-230">[FSharp.Azure.Storage](https://github.com/fsprojects/FSharp.Azure.Storage) An F# API for using Microsoft Azure Table Storage service</span></span>
- <span data-ttu-id="14a74-231">[Обозреватель хранилища Microsoft Azure (MASE)](/azure/vs-azure-tools-storage-manage-with-storage-explorer) является бесплатно, отдельное приложение от Майкрософт, которая позволяет визуально работать с данными в хранилище Azure в Windows, Linux и OS X.</span><span class="sxs-lookup"><span data-stu-id="14a74-231">[Microsoft Azure Storage Explorer (MASE)](/azure/vs-azure-tools-storage-manage-with-storage-explorer) is a free, standalone app from Microsoft that enables you to work visually with Azure Storage data on Windows, OS X, and Linux.</span></span>

### <a name="blob-storage-reference"></a><span data-ttu-id="14a74-232">Справочник по хранилища больших двоичных объектов</span><span class="sxs-lookup"><span data-stu-id="14a74-232">Blob storage reference</span></span>

- [<span data-ttu-id="14a74-233">Клиентская библиотека хранилища для Справочник по .NET</span><span class="sxs-lookup"><span data-stu-id="14a74-233">Storage Client Library for .NET reference</span></span>](http://go.microsoft.com/fwlink/?LinkID=390731&clcid=0x409)
- [<span data-ttu-id="14a74-234">Справочник по REST API</span><span class="sxs-lookup"><span data-stu-id="14a74-234">REST API reference</span></span>](http://msdn.microsoft.com/library/azure/dd179355)

### <a name="related-guides"></a><span data-ttu-id="14a74-235">Связанные направляющие</span><span class="sxs-lookup"><span data-stu-id="14a74-235">Related guides</span></span>

- [<span data-ttu-id="14a74-236">Приступая к работе с хранилищем BLOB-объектов Azure в C#</span><span class="sxs-lookup"><span data-stu-id="14a74-236">Getting Started with Azure Blob Storage in C#</span></span>](https://azure.microsoft.com/documentation/samples/storage-blob-dotnet-getting-started/)
- [<span data-ttu-id="14a74-237">Перенесите данные с помощью программы командной строки AzCopy</span><span class="sxs-lookup"><span data-stu-id="14a74-237">Transfer data with the AzCopy command-line utility</span></span>](/azure/storage/storage-use-azcopy)
- [<span data-ttu-id="14a74-238">Настройка строк подключения</span><span class="sxs-lookup"><span data-stu-id="14a74-238">Configuring Connection Strings</span></span>](http://msdn.microsoft.com/library/azure/ee758697.aspx)
- [<span data-ttu-id="14a74-239">Блог группы разработчиков хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="14a74-239">Azure Storage Team Blog</span></span>](http://blogs.msdn.com/b/windowsazurestorage/)
