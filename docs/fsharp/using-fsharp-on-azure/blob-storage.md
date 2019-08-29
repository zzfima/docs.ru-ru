---
title: Начало работы с хранилищем BLOB-объектов Azure с помощью языка F#
description: Храните неструктурированные данные в облаке с помощью хранилища BLOB-объектов Azure.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: c765f38cba7642e813a5966d3b7754c5ce45abbd
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/28/2019
ms.locfileid: "70107113"
---
# <a name="get-started-with-azure-blob-storage-using-f"></a><span data-ttu-id="b2764-103">Приступая к работе с хранилищем BLOB-объектов Azure с помощью F\#</span><span class="sxs-lookup"><span data-stu-id="b2764-103">Get started with Azure Blob storage using F\#</span></span>

<span data-ttu-id="b2764-104">Хранилище BLOB-объектов Azure — это служба, которая сохраняет неструктурированные данные в облаке в виде BLOB-объектов.</span><span class="sxs-lookup"><span data-stu-id="b2764-104">Azure Blob storage is a service that stores unstructured data in the cloud as objects/blobs.</span></span> <span data-ttu-id="b2764-105">В хранилище BLOB-объектов можно хранить любые типы текстовых или двоичных данных, таких как документы, файлы мультимедиа или установщики приложений.</span><span class="sxs-lookup"><span data-stu-id="b2764-105">Blob storage can store any type of text or binary data, such as a document, media file, or application installer.</span></span> <span data-ttu-id="b2764-106">Хранилище BLOB-объектов также называют хранилищем объектов.</span><span class="sxs-lookup"><span data-stu-id="b2764-106">Blob storage is also referred to as object storage.</span></span>

<span data-ttu-id="b2764-107">В этой статье показано, как выполнять общие задачи с помощью хранилища BLOB-объектов.</span><span class="sxs-lookup"><span data-stu-id="b2764-107">This article shows you how to perform common tasks using Blob storage.</span></span> <span data-ttu-id="b2764-108">Примеры написаны с F# помощью клиентской библиотеки службы хранилища Azure для .NET.</span><span class="sxs-lookup"><span data-stu-id="b2764-108">The samples are written using F# using the Azure Storage Client Library for .NET.</span></span> <span data-ttu-id="b2764-109">В рассмотренных задачах содержатся сведения о передаче, перечислении, скачивании и удалении больших двоичных объектов.</span><span class="sxs-lookup"><span data-stu-id="b2764-109">The tasks covered include how to upload, list, download, and delete blobs.</span></span>

<span data-ttu-id="b2764-110">Общие сведения о хранилище BLOB-объектов см. [в этом](/azure/storage/storage-dotnet-how-to-use-blobs)разделе.</span><span class="sxs-lookup"><span data-stu-id="b2764-110">For a conceptual overview of blob storage, see [the .NET guide for blob storage](/azure/storage/storage-dotnet-how-to-use-blobs).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b2764-111">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="b2764-111">Prerequisites</span></span>

<span data-ttu-id="b2764-112">Для работы с этим руководством необходимо сначала [создать учетную запись хранения Azure](/azure/storage/storage-create-storage-account).</span><span class="sxs-lookup"><span data-stu-id="b2764-112">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span> <span data-ttu-id="b2764-113">Вам также потребуется ключ доступа к хранилищу для этой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="b2764-113">You also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="b2764-114">Создание F# скрипта и запуск F# интерактивного</span><span class="sxs-lookup"><span data-stu-id="b2764-114">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="b2764-115">Примеры в этой статье можно использовать как в F# приложении, так и в F# сценарии.</span><span class="sxs-lookup"><span data-stu-id="b2764-115">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="b2764-116">Чтобы создать F# скрипт, создайте файл с `.fsx` `blobs.fsx`расширением, например в среде F# разработки.</span><span class="sxs-lookup"><span data-stu-id="b2764-116">To create an F# script, create a file with the `.fsx` extension, for example `blobs.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="b2764-117">Затем используйте [Диспетчер пакетов](package-management.md) , например [пакет](https://fsprojects.github.io/Paket/) или `WindowsAzure.Storage` [NuGet](https://www.nuget.org/) , для установки пакетов и `Microsoft.WindowsAzure.ConfigurationManager` ссылок `WindowsAzure.Storage.dll` `Microsoft.WindowsAzure.Configuration.dll` и в скрипте с помощью `#r` директивы.</span><span class="sxs-lookup"><span data-stu-id="b2764-117">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` and `Microsoft.WindowsAzure.ConfigurationManager` packages and reference `WindowsAzure.Storage.dll` and `Microsoft.WindowsAzure.Configuration.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="b2764-118">Добавить объявления пространств имен</span><span class="sxs-lookup"><span data-stu-id="b2764-118">Add namespace declarations</span></span>

<span data-ttu-id="b2764-119">Добавьте следующие `open` инструкции в начало `blobs.fsx` файла:</span><span class="sxs-lookup"><span data-stu-id="b2764-119">Add the following `open` statements to the top of the `blobs.fsx` file:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a><span data-ttu-id="b2764-120">Получение строки подключения</span><span class="sxs-lookup"><span data-stu-id="b2764-120">Get your connection string</span></span>

<span data-ttu-id="b2764-121">Для работы с этим руководством требуется строка подключения к службе хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="b2764-121">You need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="b2764-122">Дополнительные сведения о строках подключения см. в разделе [Настройка строк подключения к хранилищу](/azure/storage/storage-configure-connection-string).</span><span class="sxs-lookup"><span data-stu-id="b2764-122">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="b2764-123">В этом руководстве вы вводите строку подключения в скрипте следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b2764-123">For the tutorial, you enter your connection string in your script, like this:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L11-L11)]

<span data-ttu-id="b2764-124">Однако это **не рекомендуется** для реальных проектов.</span><span class="sxs-lookup"><span data-stu-id="b2764-124">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="b2764-125">Ключ учетной записи хранения аналогичен корневому паролю для вашей учетной записи хранения.</span><span class="sxs-lookup"><span data-stu-id="b2764-125">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="b2764-126">Всегда будьте внимательны, чтобы защитить ключ учетной записи хранения.</span><span class="sxs-lookup"><span data-stu-id="b2764-126">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="b2764-127">Не рекомендуется распространять его другим пользователям, жестко программировать или сохранять в виде обычного текстового файла, доступного для других пользователей.</span><span class="sxs-lookup"><span data-stu-id="b2764-127">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="b2764-128">Вы можете повторно создать ключ с помощью портала Azure, если считаете, что он был скомпрометирован.</span><span class="sxs-lookup"><span data-stu-id="b2764-128">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="b2764-129">Для реальных приложений лучшим способом поддержания строки подключения к хранилищу является файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b2764-129">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="b2764-130">Чтобы получить строку подключения из файла конфигурации, можно сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="b2764-130">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L13-L15)]

<span data-ttu-id="b2764-131">Использование Configuration Manager Azure является необязательным.</span><span class="sxs-lookup"><span data-stu-id="b2764-131">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="b2764-132">Можно также использовать API, например `ConfigurationManager` тип .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b2764-132">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="b2764-133">Анализ строки подключения</span><span class="sxs-lookup"><span data-stu-id="b2764-133">Parse the connection string</span></span>

<span data-ttu-id="b2764-134">Чтобы проанализировать строку подключения, используйте:</span><span class="sxs-lookup"><span data-stu-id="b2764-134">To parse the connection string, use:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L21-L22)]

<span data-ttu-id="b2764-135">Он возвращает `CloudStorageAccount`.</span><span class="sxs-lookup"><span data-stu-id="b2764-135">This returns a `CloudStorageAccount`.</span></span>

### <a name="create-some-local-dummy-data"></a><span data-ttu-id="b2764-136">Создание локальных фиктивных данных</span><span class="sxs-lookup"><span data-stu-id="b2764-136">Create some local dummy data</span></span>

<span data-ttu-id="b2764-137">Прежде чем начать, создайте в каталоге нашего скрипта некоторые фиктивные локальные данные.</span><span class="sxs-lookup"><span data-stu-id="b2764-137">Before you begin, create some dummy local data in the directory of our script.</span></span> <span data-ttu-id="b2764-138">Позже вы отправите эти данные.</span><span class="sxs-lookup"><span data-stu-id="b2764-138">Later you upload this data.</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L28-L30)]

### <a name="create-the-blob-service-client"></a><span data-ttu-id="b2764-139">Создание клиента службы BLOB-объектов</span><span class="sxs-lookup"><span data-stu-id="b2764-139">Create the Blob service client</span></span>

<span data-ttu-id="b2764-140">`CloudBlobClient` Тип позволяет извлекать контейнеры и большие двоичные объекты, хранящиеся в хранилище BLOB-объектов.</span><span class="sxs-lookup"><span data-stu-id="b2764-140">The `CloudBlobClient` type enables you to retrieve containers and blobs stored in Blob storage.</span></span> <span data-ttu-id="b2764-141">Вот один из способов создания клиента службы:</span><span class="sxs-lookup"><span data-stu-id="b2764-141">Here's one way to create the service client:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L36-L36)]

<span data-ttu-id="b2764-142">Теперь все готово для написания кода, считывающего данные из хранилища BLOB-объектов и записывающего данные в него.</span><span class="sxs-lookup"><span data-stu-id="b2764-142">Now you are ready to write code that reads data from and writes data to Blob storage.</span></span>

## <a name="create-a-container"></a><span data-ttu-id="b2764-143">Создание контейнера</span><span class="sxs-lookup"><span data-stu-id="b2764-143">Create a container</span></span>

<span data-ttu-id="b2764-144">В этом примере показано, как создать контейнер, если он еще не существует:</span><span class="sxs-lookup"><span data-stu-id="b2764-144">This example shows how to create a container if it does not already exist:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L42-L46)]

<span data-ttu-id="b2764-145">По умолчанию новый контейнер является частным. Это означает, что необходимо указать ключ доступа к хранилищу, чтобы скачать BLOB-объекты из этого контейнера.</span><span class="sxs-lookup"><span data-stu-id="b2764-145">By default, the new container is private, meaning that you must specify your storage access key to download blobs from this container.</span></span> <span data-ttu-id="b2764-146">Если вы хотите сделать файлы в контейнере доступными для всех, можно задать для контейнера значение Public, используя следующий код:</span><span class="sxs-lookup"><span data-stu-id="b2764-146">If you want to make the files within the container available to everyone, you can set the container to be public using the following code:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L48-L49)]

<span data-ttu-id="b2764-147">Любой пользователь в Интернете может видеть большие двоичные объекты в общедоступном контейнере, но вы можете изменить или удалить их только в том случае, если у вас есть соответствующий ключ доступа к учетной записи или подписанный URL-доступ.</span><span class="sxs-lookup"><span data-stu-id="b2764-147">Anyone on the Internet can see blobs in a public container, but you can modify or delete them only if you have the appropriate account access key or a shared access signature.</span></span>

## <a name="upload-a-blob-into-a-container"></a><span data-ttu-id="b2764-148">Отправка большого двоичного объекта в контейнер</span><span class="sxs-lookup"><span data-stu-id="b2764-148">Upload a blob into a container</span></span>

<span data-ttu-id="b2764-149">Хранилище больших двоичных объектов Azure поддерживает блочные и страничные BLOB-объекты.</span><span class="sxs-lookup"><span data-stu-id="b2764-149">Azure Blob Storage supports block blobs and page blobs.</span></span> <span data-ttu-id="b2764-150">В большинстве случаев рекомендуемым типом для использования является Блочный BLOB-объект.</span><span class="sxs-lookup"><span data-stu-id="b2764-150">In most cases, a block blob is the recommended type to use.</span></span>

<span data-ttu-id="b2764-151">Чтобы передать файл в блочный BLOB-объект, получите ссылку на контейнер и используйте его для получения ссылки на блочный BLOB-объект.</span><span class="sxs-lookup"><span data-stu-id="b2764-151">To upload a file to a block blob, get a container reference and use it to get a block blob reference.</span></span> <span data-ttu-id="b2764-152">После получения ссылки на большой двоичный объект можно передать в него любой поток данных, вызвав `UploadFromFile` метод.</span><span class="sxs-lookup"><span data-stu-id="b2764-152">Once you have a blob reference, you can upload any stream of data to it by calling the `UploadFromFile` method.</span></span> <span data-ttu-id="b2764-153">Эта операция создает большой двоичный объект, если он не существовал ранее, или перезаписывает его, если он существует.</span><span class="sxs-lookup"><span data-stu-id="b2764-153">This operation creates the blob if it didn't previously exist, or overwrite it if it does exist.</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L55-L59)]

## <a name="list-the-blobs-in-a-container"></a><span data-ttu-id="b2764-154">Вывод списка больших двоичных объектов в контейнере</span><span class="sxs-lookup"><span data-stu-id="b2764-154">List the blobs in a container</span></span>

<span data-ttu-id="b2764-155">Чтобы получить список больших двоичных объектов в контейнере, сначала получите ссылку на контейнер.</span><span class="sxs-lookup"><span data-stu-id="b2764-155">To list the blobs in a container, first get a container reference.</span></span> <span data-ttu-id="b2764-156">Затем можно использовать `ListBlobs` метод контейнера для извлечения больших двоичных объектов и (или) каталогов внутри него.</span><span class="sxs-lookup"><span data-stu-id="b2764-156">You can then use the container's `ListBlobs` method to retrieve the blobs and/or directories within it.</span></span> <span data-ttu-id="b2764-157">Чтобы получить доступ к широкому набору свойств и методов для `IListBlobItem`возвращаемого значения, необходимо привести его `CloudBlockBlob`к `CloudPageBlob`объекту, `CloudBlobDirectory` или.</span><span class="sxs-lookup"><span data-stu-id="b2764-157">To access the rich set of properties and methods for a returned `IListBlobItem`, you must cast it to a `CloudBlockBlob`, `CloudPageBlob`, or `CloudBlobDirectory` object.</span></span> <span data-ttu-id="b2764-158">Если тип неизвестен, можно использовать проверку типа, чтобы определить, какой из них приводится к типу.</span><span class="sxs-lookup"><span data-stu-id="b2764-158">If the type is unknown, you can use a type check to determine which to cast it to.</span></span> <span data-ttu-id="b2764-159">В следующем коде показано, как получить и вывести URI каждого элемента в `mydata` контейнере:</span><span class="sxs-lookup"><span data-stu-id="b2764-159">The following code demonstrates how to retrieve and output the URI of each item in the `mydata` container:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L67-L80)]

<span data-ttu-id="b2764-160">Кроме того, в именах больших двоичных объектов можно присвоить сведения о пути.</span><span class="sxs-lookup"><span data-stu-id="b2764-160">You can also name blobs with path information in their names.</span></span> <span data-ttu-id="b2764-161">При этом создается структура виртуального каталога, которую можно упорядочить и просмотреть как традиционную файловую систему.</span><span class="sxs-lookup"><span data-stu-id="b2764-161">This creates a virtual directory structure that you can organize and traverse as you would a traditional file system.</span></span> <span data-ttu-id="b2764-162">Обратите внимание, что структура каталогов является только виртуальной. единственные ресурсы, доступные в хранилище BLOB-объектов, — это контейнеры и большие двоичные объекты.</span><span class="sxs-lookup"><span data-stu-id="b2764-162">Note that the directory structure is virtual only - the only resources available in Blob storage are containers and blobs.</span></span> <span data-ttu-id="b2764-163">Однако клиентская библиотека хранилища предоставляет `CloudBlobDirectory` объект для ссылки на виртуальный каталог и упрощает процесс работы с большими двоичными объектами, организованными таким образом.</span><span class="sxs-lookup"><span data-stu-id="b2764-163">However, the storage client library offers a `CloudBlobDirectory` object to refer to a virtual directory and simplify the process of working with blobs that are organized in this way.</span></span>

<span data-ttu-id="b2764-164">Например, рассмотрим следующий набор блочных BLOB-объектов в контейнере с `photos`именем:</span><span class="sxs-lookup"><span data-stu-id="b2764-164">For example, consider the following set of block blobs in a container named `photos`:</span></span>

<span data-ttu-id="b2764-165">*photo1. jpg*</span><span class="sxs-lookup"><span data-stu-id="b2764-165">*photo1.jpg*</span></span>\
<span data-ttu-id="b2764-166">*2015/архитектура/описание. txt*</span><span class="sxs-lookup"><span data-stu-id="b2764-166">*2015/architecture/description.txt*</span></span>\
<span data-ttu-id="b2764-167">*2015/Architecture/photo3. jpg*</span><span class="sxs-lookup"><span data-stu-id="b2764-167">*2015/architecture/photo3.jpg*</span></span>\
<span data-ttu-id="b2764-168">*2015/Architecture/photo4. jpg*</span><span class="sxs-lookup"><span data-stu-id="b2764-168">*2015/architecture/photo4.jpg*</span></span>\
<span data-ttu-id="b2764-169">*2016/Architecture/photo5. jpg*</span><span class="sxs-lookup"><span data-stu-id="b2764-169">*2016/architecture/photo5.jpg*</span></span>\
<span data-ttu-id="b2764-170">*2016/Architecture/photo6. jpg*</span><span class="sxs-lookup"><span data-stu-id="b2764-170">*2016/architecture/photo6.jpg*</span></span>\
<span data-ttu-id="b2764-171">*2016/архитектура/описание. txt*</span><span class="sxs-lookup"><span data-stu-id="b2764-171">*2016/architecture/description.txt*</span></span>\
<span data-ttu-id="b2764-172">*2016/photo7. jpg*</span><span class="sxs-lookup"><span data-stu-id="b2764-172">*2016/photo7.jpg*</span></span>\

<span data-ttu-id="b2764-173">При вызове `ListBlobs` в контейнере (как в приведенном выше примере) возвращается иерархический список.</span><span class="sxs-lookup"><span data-stu-id="b2764-173">When you call `ListBlobs` on a container (as in the above sample), a hierarchical listing is returned.</span></span> <span data-ttu-id="b2764-174">Если он содержит `CloudBlobDirectory` объекты и `CloudBlockBlob` , представляющие каталоги и большие двоичные объекты в контейнере соответственно, то результирующие выходные данные выглядят примерно так:</span><span class="sxs-lookup"><span data-stu-id="b2764-174">If it contains both `CloudBlobDirectory` and `CloudBlockBlob` objects, representing the directories and blobs in the container, respectively, then the resulting output looks similar to this:</span></span>

```console
Directory: https://<accountname>.blob.core.windows.net/photos/2015/
Directory: https://<accountname>.blob.core.windows.net/photos/2016/
Block blob of length 505623: https://<accountname>.blob.core.windows.net/photos/photo1.jpg
```

<span data-ttu-id="b2764-175">При необходимости можно задать `UseFlatBlobListing` для `true`параметра `ListBlobs` метода значение.</span><span class="sxs-lookup"><span data-stu-id="b2764-175">Optionally, you can set the `UseFlatBlobListing` parameter of the `ListBlobs` method to `true`.</span></span> <span data-ttu-id="b2764-176">В этом случае каждый большой двоичный объект в контейнере возвращается как `CloudBlockBlob` объект.</span><span class="sxs-lookup"><span data-stu-id="b2764-176">In this case, every blob in the container is returned as a `CloudBlockBlob` object.</span></span> <span data-ttu-id="b2764-177">Вызов `ListBlobs` для возврата плоского списка выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b2764-177">The call to `ListBlobs` to return a flat listing looks like this:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L82-L89)]

<span data-ttu-id="b2764-178">в зависимости от текущего содержимого контейнера результаты выглядят следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b2764-178">and, depending on the current contents of your container, the results look like this:</span></span>

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

## <a name="download-blobs"></a><span data-ttu-id="b2764-179">Скачать BLOB-объекты</span><span class="sxs-lookup"><span data-stu-id="b2764-179">Download blobs</span></span>

<span data-ttu-id="b2764-180">Чтобы скачать большие двоичные объекты, сначала извлеките ссылку на большой `DownloadToStream` двоичный объект, а затем вызовите метод.</span><span class="sxs-lookup"><span data-stu-id="b2764-180">To download blobs, first retrieve a blob reference and then call the `DownloadToStream` method.</span></span> <span data-ttu-id="b2764-181">В следующем примере `DownloadToStream` метод используется для передачи содержимого большого двоичного объекта в объект потока, который затем можно сохранить в локальный файл.</span><span class="sxs-lookup"><span data-stu-id="b2764-181">The following example uses the `DownloadToStream` method to transfer the blob contents to a stream object that you can then persist to a local file.</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L95-L101)]

<span data-ttu-id="b2764-182">Можно также использовать `DownloadToStream` метод для загрузки содержимого большого двоичного объекта в виде текстовой строки.</span><span class="sxs-lookup"><span data-stu-id="b2764-182">You can also use the `DownloadToStream` method to download the contents of a blob as a text string.</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L103-L106)]

## <a name="delete-blobs"></a><span data-ttu-id="b2764-183">Удаление больших двоичных объектов</span><span class="sxs-lookup"><span data-stu-id="b2764-183">Delete blobs</span></span>

<span data-ttu-id="b2764-184">Чтобы удалить большой двоичный объект, сначала получите ссылку на большой двоичный `Delete` объект, а затем вызовите для него метод.</span><span class="sxs-lookup"><span data-stu-id="b2764-184">To delete a blob, first get a blob reference and then call the `Delete` method on it.</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L112-L116)]

## <a name="list-blobs-in-pages-asynchronously"></a><span data-ttu-id="b2764-185">Асинхронное отображение списка больших двоичных объектов в страницах</span><span class="sxs-lookup"><span data-stu-id="b2764-185">List blobs in pages asynchronously</span></span>

<span data-ttu-id="b2764-186">Если вы перечислите большое количество больших двоичных объектов или хотите контролировать количество результатов, возвращаемых в одной операции перечисления, можно вывести список больших двоичных объектов на страницах результатов.</span><span class="sxs-lookup"><span data-stu-id="b2764-186">If you are listing a large number of blobs, or you want to control the number of results you return in one listing operation, you can list blobs in pages of results.</span></span> <span data-ttu-id="b2764-187">В этом примере показано, как асинхронно возвращать результаты на страницах, чтобы выполнение не блокировалось в ожидании возврата большого набора результатов.</span><span class="sxs-lookup"><span data-stu-id="b2764-187">This example shows how to return results in pages asynchronously, so that execution is not blocked while waiting to return a large set of results.</span></span>

<span data-ttu-id="b2764-188">В этом примере показан плоский список больших двоичных объектов, но можно также выполнить иерархическое построение, задав `useFlatBlobListing` для `false`параметра `ListBlobsSegmentedAsync` метода значение.</span><span class="sxs-lookup"><span data-stu-id="b2764-188">This example shows a flat blob listing, but you can also perform a hierarchical listing, by setting the `useFlatBlobListing` parameter of the `ListBlobsSegmentedAsync` method to `false`.</span></span>

<span data-ttu-id="b2764-189">В примере определяется асинхронный метод с помощью `async` блока.</span><span class="sxs-lookup"><span data-stu-id="b2764-189">The sample defines an asynchronous method, using an `async` block.</span></span> <span data-ttu-id="b2764-190">``let!`` Ключевое слово приостанавливает выполнение метода Sample до завершения задачи листинга.</span><span class="sxs-lookup"><span data-stu-id="b2764-190">The ``let!`` keyword suspends execution of the sample method until the listing task completes.</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L122-L160)]

<span data-ttu-id="b2764-191">Теперь мы можем использовать эту асинхронную подпрограммы, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="b2764-191">We can now use this asynchronous routine as follows.</span></span> <span data-ttu-id="b2764-192">Сначала необходимо отправить некоторые фиктивные данные (с помощью локального файла, созданного ранее в этом руководстве).</span><span class="sxs-lookup"><span data-stu-id="b2764-192">First you upload some dummy data (using the local file created earlier in this tutorial).</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L162-L166)]

<span data-ttu-id="b2764-193">Теперь вызовите подпрограммы.</span><span class="sxs-lookup"><span data-stu-id="b2764-193">Now, call the routine.</span></span> <span data-ttu-id="b2764-194">Используется `Async.RunSynchronously` для принудительного выполнения асинхронной операции.</span><span class="sxs-lookup"><span data-stu-id="b2764-194">You use `Async.RunSynchronously` to force the execution of the asynchronous operation.</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L168-L168)]

## <a name="writing-to-an-append-blob"></a><span data-ttu-id="b2764-195">Запись в добавочный BLOB-объект</span><span class="sxs-lookup"><span data-stu-id="b2764-195">Writing to an append blob</span></span>

<span data-ttu-id="b2764-196">Добавочный BLOB-объект оптимизирован для операций добавления, таких как ведение журнала.</span><span class="sxs-lookup"><span data-stu-id="b2764-196">An append blob is optimized for append operations, such as logging.</span></span> <span data-ttu-id="b2764-197">Как и блочный BLOB-объект, добавочный большой двоичный объект состоит из блоков, но при добавлении нового блока в добавочный большой двоичный объект всегда добавляется в конец большого двоичного объекта.</span><span class="sxs-lookup"><span data-stu-id="b2764-197">Like a block blob, an append blob is comprised of blocks, but when you add a new block to an append blob, it is always appended to the end of the blob.</span></span> <span data-ttu-id="b2764-198">Нельзя обновить или удалить существующий блок в добавочном большом двоичном объекте.</span><span class="sxs-lookup"><span data-stu-id="b2764-198">You cannot update or delete an existing block in an append blob.</span></span> <span data-ttu-id="b2764-199">Идентификаторы блоков для добавочного большого двоичного объекта не предоставляются, так как они предназначены для блочного BLOB-объекта.</span><span class="sxs-lookup"><span data-stu-id="b2764-199">The block IDs for an append blob are not exposed as they are for a block blob.</span></span>

<span data-ttu-id="b2764-200">Каждый блок в добавочном BLOB-объекте может иметь другой размер, не более 4 МБ, а добавочный BLOB-объект может включать не более 50 000 блоков.</span><span class="sxs-lookup"><span data-stu-id="b2764-200">Each block in an append blob can be a different size, up to a maximum of 4 MB, and an append blob can include a maximum of 50,000 blocks.</span></span> <span data-ttu-id="b2764-201">Таким образом, максимальный размер добавочного большого двоичного объекта немного превышает 195 ГБ (4 МБ X 50 000 блоков).</span><span class="sxs-lookup"><span data-stu-id="b2764-201">The maximum size of an append blob is therefore slightly more than 195 GB (4 MB X 50,000 blocks).</span></span>

<span data-ttu-id="b2764-202">В следующем примере создается новый добавочный BLOB-объект и к нему добавляются некоторые данные, имитируя простую операцию ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="b2764-202">The following example creates a new append blob and appends some data to it, simulating a simple logging operation.</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L174-L203)]

<span data-ttu-id="b2764-203">Дополнительные сведения о различиях между тремя типами больших двоичных объектов см. в разделе Основные данные о [блочных и страничных BLOB-](https://msdn.microsoft.com/library/azure/ee691964.aspx) объектах.</span><span class="sxs-lookup"><span data-stu-id="b2764-203">See [Understanding Block Blobs, Page Blobs, and Append Blobs](https://msdn.microsoft.com/library/azure/ee691964.aspx) for more information about the differences between the three types of blobs.</span></span>

## <a name="concurrent-access"></a><span data-ttu-id="b2764-204">Одновременный доступ</span><span class="sxs-lookup"><span data-stu-id="b2764-204">Concurrent access</span></span>

<span data-ttu-id="b2764-205">Для поддержки одновременного доступа к большому двоичному объекту из нескольких клиентов или нескольких экземпляров процесса можно использовать **теги eTag** или **аренды**.</span><span class="sxs-lookup"><span data-stu-id="b2764-205">To support concurrent access to a blob from multiple clients or multiple process instances, you can use **ETags** or **leases**.</span></span>

- <span data-ttu-id="b2764-206">**ETag** — позволяет определить, что большой двоичный объект или контейнер был изменен другим процессом</span><span class="sxs-lookup"><span data-stu-id="b2764-206">**Etag** - provides a way to detect that the blob or container has been modified by another process</span></span>

- <span data-ttu-id="b2764-207">**Аренда** — предоставляет способ получения монопольного доступа, устанавливать возобновляемую, записи или удаления большого двоичного объекта в течение определенного периода времени.</span><span class="sxs-lookup"><span data-stu-id="b2764-207">**Lease** - provides a way to obtain exclusive, renewable, write or delete access to a blob for a period of time</span></span>

<span data-ttu-id="b2764-208">Дополнительные сведения см. [в разделе Управление параллелизмом в Служба хранилища Microsoft Azure](https://azure.microsoft.com/blog/managing-concurrency-in-microsoft-azure-storage-2/).</span><span class="sxs-lookup"><span data-stu-id="b2764-208">For more information, see [Managing Concurrency in Microsoft Azure Storage](https://azure.microsoft.com/blog/managing-concurrency-in-microsoft-azure-storage-2/).</span></span>

## <a name="naming-containers"></a><span data-ttu-id="b2764-209">Именование контейнеров</span><span class="sxs-lookup"><span data-stu-id="b2764-209">Naming containers</span></span>

<span data-ttu-id="b2764-210">Каждый BLOB-объект в хранилище Azure должен находиться в контейнере.</span><span class="sxs-lookup"><span data-stu-id="b2764-210">Every blob in Azure storage must reside in a container.</span></span> <span data-ttu-id="b2764-211">Контейнер образует часть имени большого двоичного объекта.</span><span class="sxs-lookup"><span data-stu-id="b2764-211">The container forms part of the blob name.</span></span> <span data-ttu-id="b2764-212">Например, `mydata` — это имя контейнера в этих примерах URI больших двоичных объектов:</span><span class="sxs-lookup"><span data-stu-id="b2764-212">For example, `mydata` is the name of the container in these sample blob URIs:</span></span>

- https://storagesample.blob.core.windows.net/mydata/blob1.txt
- https://storagesample.blob.core.windows.net/mydata/photos/myphoto.jpg

<span data-ttu-id="b2764-213">Имя контейнера должно быть допустимым DNS-именем, удовлетворяющим следующим правилам именования:</span><span class="sxs-lookup"><span data-stu-id="b2764-213">A container name must be a valid DNS name, conforming to the following naming rules:</span></span>

1. <span data-ttu-id="b2764-214">Имена контейнеров должны начинаться с буквы или цифры и могут содержать только буквы, цифры и знак тире (-).</span><span class="sxs-lookup"><span data-stu-id="b2764-214">Container names must start with a letter or number, and can contain only letters, numbers, and the dash (-) character.</span></span>
1. <span data-ttu-id="b2764-215">Перед символом дефиса (-) перед ним должна стоять буква или цифра. в именах контейнеров не допускаются последовательные дефисы.</span><span class="sxs-lookup"><span data-stu-id="b2764-215">Every dash (-) character must be immediately preceded and followed by a letter or number; consecutive dashes are not permitted in container names.</span></span>
1. <span data-ttu-id="b2764-216">Все буквы в имени контейнера должны быть строчными.</span><span class="sxs-lookup"><span data-stu-id="b2764-216">All letters in a container name must be lowercase.</span></span>
1. <span data-ttu-id="b2764-217">Имена контейнеров должны иметь длину от 3 до 63 символов.</span><span class="sxs-lookup"><span data-stu-id="b2764-217">Container names must be from 3 through 63 characters long.</span></span>

<span data-ttu-id="b2764-218">Обратите внимание, что имя контейнера всегда должно быть строчным.</span><span class="sxs-lookup"><span data-stu-id="b2764-218">Note that the name of a container must always be lowercase.</span></span> <span data-ttu-id="b2764-219">Если вы включили в имя контейнера прописную букву или нарушаете правила именования контейнеров, может возникнуть ошибка 400 (недопустимый запрос).</span><span class="sxs-lookup"><span data-stu-id="b2764-219">If you include an upper-case letter in a container name, or otherwise violate the container naming rules, you may receive a 400 error (Bad Request).</span></span>

## <a name="managing-security-for-blobs"></a><span data-ttu-id="b2764-220">Управление безопасностью для больших двоичных объектов</span><span class="sxs-lookup"><span data-stu-id="b2764-220">Managing security for blobs</span></span>

<span data-ttu-id="b2764-221">По умолчанию служба хранилища Azure защищает ваши данные, ограничивая доступ к владельцу учетной записи, который имеет ключи доступа к учетной записи.</span><span class="sxs-lookup"><span data-stu-id="b2764-221">By default, Azure Storage keeps your data secure by limiting access to the account owner, who is in possession of the account access keys.</span></span> <span data-ttu-id="b2764-222">Если необходимо предоставить общий доступ к данным большого двоичного объекта в учетной записи хранения, важно сделать это, не нарушая безопасность ключей доступа к учетной записи.</span><span class="sxs-lookup"><span data-stu-id="b2764-222">When you need to share blob data in your storage account, it is important to do so without compromising the security of your account access keys.</span></span> <span data-ttu-id="b2764-223">Кроме того, можно зашифровать данные большого двоичного объекта, чтобы обеспечить их безопасность при передаче по сети и в службе хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="b2764-223">Additionally, you can encrypt blob data to ensure that it is secure going over the wire and in Azure Storage.</span></span>

### <a name="controlling-access-to-blob-data"></a><span data-ttu-id="b2764-224">Управление доступом к данным большого двоичного объекта</span><span class="sxs-lookup"><span data-stu-id="b2764-224">Controlling access to blob data</span></span>

<span data-ttu-id="b2764-225">По умолчанию данные большого двоичного объекта в вашей учетной записи хранения доступны только владельцу учетной записи хранения.</span><span class="sxs-lookup"><span data-stu-id="b2764-225">By default, the blob data in your storage account is accessible only to storage account owner.</span></span> <span data-ttu-id="b2764-226">Для проверки подлинности запросов к хранилищу BLOB-объектов требуется ключ доступа к учетной записи по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b2764-226">Authenticating requests against Blob storage requires the account access key by default.</span></span> <span data-ttu-id="b2764-227">Однако может потребоваться предоставить другим пользователям доступ к данным большого двоичного объекта.</span><span class="sxs-lookup"><span data-stu-id="b2764-227">However, you might want to make certain blob data available to other users.</span></span>

### <a name="encrypting-blob-data"></a><span data-ttu-id="b2764-228">Шифрование данных больших двоичных объектов</span><span class="sxs-lookup"><span data-stu-id="b2764-228">Encrypting blob data</span></span>

<span data-ttu-id="b2764-229">Служба хранилища Azure поддерживает шифрование данных большого двоичного объекта как на клиенте, так и на сервере.</span><span class="sxs-lookup"><span data-stu-id="b2764-229">Azure Storage supports encrypting blob data both at the client and on the server.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b2764-230">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="b2764-230">Next steps</span></span>

<span data-ttu-id="b2764-231">Теперь, когда вы узнали основы хранилища BLOB-объектов, воспользуйтесь следующими ссылками для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="b2764-231">Now that you've learned the basics of Blob storage, follow these links to learn more.</span></span>

### <a name="tools"></a><span data-ttu-id="b2764-232">Сервис</span><span class="sxs-lookup"><span data-stu-id="b2764-232">Tools</span></span>

- <span data-ttu-id="b2764-233">[F#азуресторажетипепровидер](https://fsprojects.github.io/AzureStorageTypeProvider/)</span><span class="sxs-lookup"><span data-stu-id="b2764-233">[F# AzureStorageTypeProvider](https://fsprojects.github.io/AzureStorageTypeProvider/)</span></span>\
<span data-ttu-id="b2764-234">Поставщик F# типов, который можно использовать для просмотра ресурсов хранилища Azure BLOB-объектов, таблиц и очередей, а также для простого применения операций CRUD к ним.</span><span class="sxs-lookup"><span data-stu-id="b2764-234">An F# Type Provider which can be used to explore Blob, Table and Queue Azure Storage assets and easily apply CRUD operations on them.</span></span>

- <span data-ttu-id="b2764-235">[FSharp. Azure. Storage](https://github.com/fsprojects/FSharp.Azure.Storage)</span><span class="sxs-lookup"><span data-stu-id="b2764-235">[FSharp.Azure.Storage](https://github.com/fsprojects/FSharp.Azure.Storage)</span></span>\
<span data-ttu-id="b2764-236">F# API для использования службы хранилища таблиц Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="b2764-236">An F# API for using Microsoft Azure Table Storage service</span></span>

- <span data-ttu-id="b2764-237">[Обозреватель службы хранилища Microsoft Azure (MASE)](/azure/vs-azure-tools-storage-manage-with-storage-explorer)</span><span class="sxs-lookup"><span data-stu-id="b2764-237">[Microsoft Azure Storage Explorer (MASE)](/azure/vs-azure-tools-storage-manage-with-storage-explorer)</span></span>\
<span data-ttu-id="b2764-238">Бесплатное автономное приложение от корпорации Майкрософт, позволяющее визуально работать с данными службы хранилища Azure в Windows, OS X и Linux.</span><span class="sxs-lookup"><span data-stu-id="b2764-238">A free, standalone app from Microsoft that enables you to work visually with Azure Storage data on Windows, OS X, and Linux.</span></span>

### <a name="blob-storage-reference"></a><span data-ttu-id="b2764-239">Ссылка на хранилище BLOB-объектов</span><span class="sxs-lookup"><span data-stu-id="b2764-239">Blob storage reference</span></span>

- [<span data-ttu-id="b2764-240">API-интерфейсы службы хранилища Azure для .NET</span><span class="sxs-lookup"><span data-stu-id="b2764-240">Azure Storage APIs for .NET</span></span>](/dotnet/api/overview/azure/storage)
- [<span data-ttu-id="b2764-241">Справочник по службам хранилища Azure REST API</span><span class="sxs-lookup"><span data-stu-id="b2764-241">Azure Storage Services REST API Reference</span></span>](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)

### <a name="related-guides"></a><span data-ttu-id="b2764-242">Связанные руководства</span><span class="sxs-lookup"><span data-stu-id="b2764-242">Related guides</span></span>

- [<span data-ttu-id="b2764-243">начало работы с хранилищем BLOB-объектов Azure вC#</span><span class="sxs-lookup"><span data-stu-id="b2764-243">Getting Started with Azure Blob Storage in C#</span></span>](https://azure.microsoft.com/resources/samples/storage-blob-dotnet-getting-started/)
- [<span data-ttu-id="b2764-244">Перенос данных с помощью служебной программы командной строки AzCopy в Windows</span><span class="sxs-lookup"><span data-stu-id="b2764-244">Transfer data with the AzCopy command-line utility on Windows</span></span>](/azure/storage/common/storage-use-azcopy)
- [<span data-ttu-id="b2764-245">Перенос данных с помощью служебной программы командной строки AzCopy в Linux</span><span class="sxs-lookup"><span data-stu-id="b2764-245">Transfer data with the AzCopy command-line utility on Linux</span></span>](/azure/storage/common/storage-use-azcopy-linux)
- [<span data-ttu-id="b2764-246">Настройка строк подключения службы хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="b2764-246">Configure Azure Storage connection strings</span></span>](/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="b2764-247">Блог команды разработчиков службы хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="b2764-247">Azure Storage Team Blog</span></span>](https://blogs.msdn.microsoft.com/windowsazurestorage/)
- [<span data-ttu-id="b2764-248">Краткое руководство Создание большого двоичного объекта в хранилище объектов с помощью .NET</span><span class="sxs-lookup"><span data-stu-id="b2764-248">Quickstart: Use .NET to create a blob in object storage</span></span>](/azure/storage/blobs/storage-quickstart-blobs-dotnet)
