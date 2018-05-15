---
title: 'Начало работы с хранилищем файлов Azure, с помощью F #'
description: Хранить файл данных в облаке с хранилищем файлов Azure и подключения к общей папке облака на основе Azure виртуальной машины (VM) или из локального приложения под управлением Windows.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: e772da5f81d2e6827295d0dfe150934a415eb3bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="get-started-with-azure-file-storage-using-f"></a><span data-ttu-id="a0ced-103">Начало работы с хранилищем файлов Azure, с помощью F #</span><span class="sxs-lookup"><span data-stu-id="a0ced-103">Get started with Azure File storage using F#</span></span> #

<span data-ttu-id="a0ced-104">Хранилище Azure файл — это служба, предоставляющая файловыми ресурсами общего доступа в облаке с использованием стандарта [протокола Server Message Block (SMB)](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx).</span><span class="sxs-lookup"><span data-stu-id="a0ced-104">Azure File storage is a service that offers file shares in the cloud using the standard [Server Message Block (SMB) Protocol](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx).</span></span> <span data-ttu-id="a0ced-105">Поддерживаются SMB 2.1 и SMB 3.0.</span><span class="sxs-lookup"><span data-stu-id="a0ced-105">Both SMB 2.1 and SMB 3.0 are supported.</span></span> <span data-ttu-id="a0ced-106">При хранении файлов Azure можно перенести старых приложений, использующих общим файловым ресурсам в Azure, быстро и без дорогостоящей излишнего копирования.</span><span class="sxs-lookup"><span data-stu-id="a0ced-106">With Azure File storage, you can migrate legacy applications that rely on file shares to Azure quickly and without costly rewrites.</span></span> <span data-ttu-id="a0ced-107">Приложения, работающие в Azure виртуальные машины или облачные службы или от локальных клиентов можно подключить общую папку в облаке, так же, как настольного приложения подключает обычной общей папки SMB.</span><span class="sxs-lookup"><span data-stu-id="a0ced-107">Applications running in Azure virtual machines or cloud services or from on-premises clients can mount a file share in the cloud, just as a desktop application mounts a typical SMB share.</span></span> <span data-ttu-id="a0ced-108">Любое количество компонентов приложения можно подключить и одновременно получить доступ к общей папки хранилища.</span><span class="sxs-lookup"><span data-stu-id="a0ced-108">Any number of application components can then mount and access the File storage share simultaneously.</span></span>

<span data-ttu-id="a0ced-109">Концептуальный обзор хранилища файлов, см. в разделе [руководство по .NET для хранения файлов](/azure/storage/storage-dotnet-how-to-use-files).</span><span class="sxs-lookup"><span data-stu-id="a0ced-109">For a conceptual overview of file storage, please see [the .NET guide for file storage](/azure/storage/storage-dotnet-how-to-use-files).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a0ced-110">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="a0ced-110">Prerequisites</span></span>

<span data-ttu-id="a0ced-111">Чтобы использовать это руководство, необходимо сначала [создать учетную запись хранилища Azure](/azure/storage/storage-create-storage-account).</span><span class="sxs-lookup"><span data-stu-id="a0ced-111">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span>
<span data-ttu-id="a0ced-112">Кроме того, потребуется ключ доступа хранилища для этой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="a0ced-112">You'll also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="a0ced-113">Создание скрипта F # и начала F #, интерактивный</span><span class="sxs-lookup"><span data-stu-id="a0ced-113">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="a0ced-114">Примеры в этой статье используется в F # приложения или скрипта F #.</span><span class="sxs-lookup"><span data-stu-id="a0ced-114">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="a0ced-115">Чтобы создать скрипт F #, создайте файл с `.fsx` расширение, например `files.fsx`, в среде разработки F #.</span><span class="sxs-lookup"><span data-stu-id="a0ced-115">To create an F# script, create a file with the `.fsx` extension, for example `files.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="a0ced-116">Затем используйте [диспетчера пакетов](package-management.md) такие как [Paket](https://fsprojects.github.io/Paket/) или [NuGet](https://www.nuget.org/) установка `WindowsAzure.Storage` пакета и ссылка `WindowsAzure.Storage.dll` в скрипте с помощью `#r`директивы.</span><span class="sxs-lookup"><span data-stu-id="a0ced-116">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="a0ced-117">Добавьте объявления пространств имен</span><span class="sxs-lookup"><span data-stu-id="a0ced-117">Add namespace declarations</span></span>

<span data-ttu-id="a0ced-118">Добавьте следующие `open` инструкции в начало `files.fsx` файла:</span><span class="sxs-lookup"><span data-stu-id="a0ced-118">Add the following `open` statements to the top of the `files.fsx` file:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a><span data-ttu-id="a0ced-119">Получение строки подключения</span><span class="sxs-lookup"><span data-stu-id="a0ced-119">Get your connection string</span></span>

<span data-ttu-id="a0ced-120">Для этого учебника потребуется строку подключения хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="a0ced-120">You'll need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="a0ced-121">Дополнительные сведения о строках соединения см. в разделе [Настройка строки подключения хранилища](/azure/storage/storage-configure-connection-string).</span><span class="sxs-lookup"><span data-stu-id="a0ced-121">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="a0ced-122">Учебник вы введете строки подключения в скрипте, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a0ced-122">For the tutorial, you'll enter your connection string in your script, like this:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L11-L11)]

<span data-ttu-id="a0ced-123">Однако это **не рекомендуется** для реальных проектах.</span><span class="sxs-lookup"><span data-stu-id="a0ced-123">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="a0ced-124">Ключ учетной записи хранилища аналогична корневой пароль для учетной записи хранилища.</span><span class="sxs-lookup"><span data-stu-id="a0ced-124">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="a0ced-125">Всегда будьте внимательны защитить ключ учетной записи хранилища.</span><span class="sxs-lookup"><span data-stu-id="a0ced-125">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="a0ced-126">Избегайте распространением их другим пользователям, жестко запрограммированные ее или сохранить в текстовый файл, доступный другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="a0ced-126">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="a0ced-127">Можно повторно создать ключ с помощью портала Azure, если вы считаете, что он был скомпрометирован.</span><span class="sxs-lookup"><span data-stu-id="a0ced-127">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="a0ced-128">Для реальных приложений для сохранения строки подключения хранилища рекомендуется в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a0ced-128">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="a0ced-129">Чтобы получить строку подключения из файла конфигурации, это можно сделать:</span><span class="sxs-lookup"><span data-stu-id="a0ced-129">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L13-L15)]

<span data-ttu-id="a0ced-130">С помощью диспетчера конфигурации Azure является необязательным.</span><span class="sxs-lookup"><span data-stu-id="a0ced-130">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="a0ced-131">Можно также использовать интерфейс API, например .NET Framework `ConfigurationManager` типа.</span><span class="sxs-lookup"><span data-stu-id="a0ced-131">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="a0ced-132">Синтаксический анализ строки соединения</span><span class="sxs-lookup"><span data-stu-id="a0ced-132">Parse the connection string</span></span>

<span data-ttu-id="a0ced-133">Чтобы обработать строку подключения, используйте:</span><span class="sxs-lookup"><span data-stu-id="a0ced-133">To parse the connection string, use:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L21-L22)]

<span data-ttu-id="a0ced-134">Будет возвращен `CloudStorageAccount`.</span><span class="sxs-lookup"><span data-stu-id="a0ced-134">This will return a `CloudStorageAccount`.</span></span>

### <a name="create-the-file-service-client"></a><span data-ttu-id="a0ced-135">Создание клиента службы файлов</span><span class="sxs-lookup"><span data-stu-id="a0ced-135">Create the File service client</span></span>

<span data-ttu-id="a0ced-136">`CloudFileClient` Тип позволяет программно использовать файлы, хранящиеся в хранилище файлов.</span><span class="sxs-lookup"><span data-stu-id="a0ced-136">The `CloudFileClient` type enables you to programmatically use files stored in File storage.</span></span> <span data-ttu-id="a0ced-137">Вот один из способов создания клиента службы.</span><span class="sxs-lookup"><span data-stu-id="a0ced-137">Here's one way to create the service client:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L28-L28)]

<span data-ttu-id="a0ced-138">Теперь вы готовы написать код, который считывает и записывает данные в хранилище файлов.</span><span class="sxs-lookup"><span data-stu-id="a0ced-138">Now you are ready to write code that reads data from and writes data to File storage.</span></span>

## <a name="create-a-file-share"></a><span data-ttu-id="a0ced-139">Создание общей папки</span><span class="sxs-lookup"><span data-stu-id="a0ced-139">Create a file share</span></span>

<span data-ttu-id="a0ced-140">В этом примере показано, как создать общую папку, если он еще не существует:</span><span class="sxs-lookup"><span data-stu-id="a0ced-140">This example shows how to create a file share if it does not already exist:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L34-L35)]

## <a name="create-a-root-directory-and-a-subdirectory"></a><span data-ttu-id="a0ced-141">Создать корневой каталог и подкаталог</span><span class="sxs-lookup"><span data-stu-id="a0ced-141">Create a root directory and a subdirectory</span></span>

<span data-ttu-id="a0ced-142">Здесь, вы получаете корневой каталог и получить вложенный каталог к корневому каталогу.</span><span class="sxs-lookup"><span data-stu-id="a0ced-142">Here, you get the root directory and get a sub-directory of the root.</span></span> <span data-ttu-id="a0ced-143">Как создать, если они еще не существуют.</span><span class="sxs-lookup"><span data-stu-id="a0ced-143">You create both if they don't already exist.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L41-L43)]

## <a name="upload-text-as-a-file"></a><span data-ttu-id="a0ced-144">Загрузить текст в формате</span><span class="sxs-lookup"><span data-stu-id="a0ced-144">Upload text as a file</span></span>

<span data-ttu-id="a0ced-145">В этом примере показано, как загрузить текст в формате.</span><span class="sxs-lookup"><span data-stu-id="a0ced-145">This example shows how to upload text as a file.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L49-L50)]

### <a name="download-a-file-to-a-local-copy-of-the-file"></a><span data-ttu-id="a0ced-146">Загрузите файл локальную копию файла</span><span class="sxs-lookup"><span data-stu-id="a0ced-146">Download a file to a local copy of the file</span></span>

<span data-ttu-id="a0ced-147">Здесь вы загрузите файл только что создали, добавления содержимого в локальный файл.</span><span class="sxs-lookup"><span data-stu-id="a0ced-147">Here you download the file just created, appending the contents to a local file.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L56-L56)]

### <a name="set-the-maximum-size-for-a-file-share"></a><span data-ttu-id="a0ced-148">Установить максимальный размер для общей папки</span><span class="sxs-lookup"><span data-stu-id="a0ced-148">Set the maximum size for a file share</span></span>

<span data-ttu-id="a0ced-149">В приведенном ниже примере показано, как проверить текущее использование для общей папки и как задать квоту для общей папки.</span><span class="sxs-lookup"><span data-stu-id="a0ced-149">The example below shows how to check the current usage for a share and how to set the quota for the share.</span></span> <span data-ttu-id="a0ced-150">`FetchAttributes` необходимо вызвать, чтобы заполнить общую папку `Properties`, и `SetProperties` переносить локальные изменения в хранилище файлов Azure.</span><span class="sxs-lookup"><span data-stu-id="a0ced-150">`FetchAttributes` must be called to populate a share's `Properties`, and `SetProperties` to propagate local changes to Azure File storage.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L62-L72)]

### <a name="generate-a-shared-access-signature-for-a-file-or-file-share"></a><span data-ttu-id="a0ced-151">Создать подпись общего доступа для файла или общей папки</span><span class="sxs-lookup"><span data-stu-id="a0ced-151">Generate a shared access signature for a file or file share</span></span>

<span data-ttu-id="a0ced-152">Вы можете создать подписанный URL-адрес (SAS) для общей папки или отдельного файла.</span><span class="sxs-lookup"><span data-stu-id="a0ced-152">You can generate a shared access signature (SAS) for a file share or for an individual file.</span></span> <span data-ttu-id="a0ced-153">Можно также создать политики общего доступа на файловом ресурсе, чтобы управлять подписями общего доступа.</span><span class="sxs-lookup"><span data-stu-id="a0ced-153">You can also create a shared access policy on a file share to manage shared access signatures.</span></span> <span data-ttu-id="a0ced-154">Создание политики общего доступа рекомендуется, так как она предоставляет средства отзыва SAS, если он должен быть скомпрометирован.</span><span class="sxs-lookup"><span data-stu-id="a0ced-154">Creating a shared access policy is recommended, as it provides a means of revoking the SAS if it should be compromised.</span></span>

<span data-ttu-id="a0ced-155">Здесь, можно создать общий доступ к политике в общей папке, а затем использовать эту политику для обеспечения ограничения SAS на файл в общей папке.</span><span class="sxs-lookup"><span data-stu-id="a0ced-155">Here, you create a shared access policy on a share, and then use that policy to provide the constraints for a SAS on a file in the share.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L78-L94)]

<span data-ttu-id="a0ced-156">Дополнительные сведения о создании и использовании подписанных URL-адресов см. в разделе [с помощью подписи URL (SAS)](/azure/storage/storage-dotnet-shared-access-signature-part-1) и [Создание и использование SAS с хранилищем больших двоичных объектов](/azure/storage/storage-dotnet-shared-access-signature-part-2).</span><span class="sxs-lookup"><span data-stu-id="a0ced-156">For more information about creating and using shared access signatures, see [Using Shared Access Signatures (SAS)](/azure/storage/storage-dotnet-shared-access-signature-part-1) and [Create and use a SAS with Blob storage](/azure/storage/storage-dotnet-shared-access-signature-part-2).</span></span>

### <a name="copy-files"></a><span data-ttu-id="a0ced-157">Копирование файлов</span><span class="sxs-lookup"><span data-stu-id="a0ced-157">Copy files</span></span>

<span data-ttu-id="a0ced-158">Файл можно скопировать в другой файл или большой двоичный объект или большого двоичного объекта в файл.</span><span class="sxs-lookup"><span data-stu-id="a0ced-158">You can copy a file to another file or to a blob, or a blob to a file.</span></span> <span data-ttu-id="a0ced-159">При копировании большого двоичного объекта в файл или файл в большой двоичный объект можно *должен* использовать подписанный URL-адрес (SAS) для проверки подлинности исходного объекта, даже при копировании данных в одну и ту же учетную запись хранилища.</span><span class="sxs-lookup"><span data-stu-id="a0ced-159">If you are copying a blob to a file, or a file to a blob, you *must* use a shared access signature (SAS) to authenticate the source object, even if you are copying within the same storage account.</span></span>

### <a name="copy-a-file-to-another-file"></a><span data-ttu-id="a0ced-160">Скопируйте файл в другой файл</span><span class="sxs-lookup"><span data-stu-id="a0ced-160">Copy a file to another file</span></span>

<span data-ttu-id="a0ced-161">Здесь можно скопировать файл на другой файл в ту же папку.</span><span class="sxs-lookup"><span data-stu-id="a0ced-161">Here, you copy a file to another file in the same share.</span></span> <span data-ttu-id="a0ced-162">Поскольку эта операция копирования копирует между файлами в учетную запись хранения, можно использовать проверку подлинности Shared Key для выполнения копирования.</span><span class="sxs-lookup"><span data-stu-id="a0ced-162">Because this copy operation copies between files in the same storage account, you can use Shared Key authentication to perform the copy.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L100-L101)]

### <a name="copy-a-file-to-a-blob"></a><span data-ttu-id="a0ced-163">Скопируйте файл в большой двоичный объект</span><span class="sxs-lookup"><span data-stu-id="a0ced-163">Copy a file to a blob</span></span>

<span data-ttu-id="a0ced-164">Здесь, создайте файл и скопируйте его в большой двоичный объект в одну и ту же учетную запись хранилища.</span><span class="sxs-lookup"><span data-stu-id="a0ced-164">Here, you create a file and copy it to a blob within the same storage account.</span></span> <span data-ttu-id="a0ced-165">Можно создать SAS для исходного файла, который используется службой для проверки подлинности доступа к файлу исходного кода во время операции копирования.</span><span class="sxs-lookup"><span data-stu-id="a0ced-165">You create a SAS for the source file, which the service uses to authenticate access to the source file during the copy operation.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L107-L120)]

<span data-ttu-id="a0ced-166">Таким же образом, можно скопировать большого двоичного объекта в файл.</span><span class="sxs-lookup"><span data-stu-id="a0ced-166">You can copy a blob to a file in the same way.</span></span> <span data-ttu-id="a0ced-167">Если исходный объект является большой двоичный объект, необходимо создайте SAS для проверки подлинности доступа к этим большим двоичным объектом во время операции копирования.</span><span class="sxs-lookup"><span data-stu-id="a0ced-167">If the source object is a blob, then create a SAS to authenticate access to that blob during the copy operation.</span></span>

## <a name="troubleshooting-file-storage-using-metrics"></a><span data-ttu-id="a0ced-168">Устранение неполадок с помощью метрик хранилища файлов</span><span class="sxs-lookup"><span data-stu-id="a0ced-168">Troubleshooting File storage using metrics</span></span>

<span data-ttu-id="a0ced-169">Аналитика хранилища Azure поддерживает метрики для хранения файлов.</span><span class="sxs-lookup"><span data-stu-id="a0ced-169">Azure Storage Analytics supports metrics for File storage.</span></span> <span data-ttu-id="a0ced-170">С данными метрик можно отслеживать запросы и диагностировать проблемы.</span><span class="sxs-lookup"><span data-stu-id="a0ced-170">With metrics data, you can trace requests and diagnose issues.</span></span>

<span data-ttu-id="a0ced-171">Можно включить метрики для хранения файлов из [портала Azure](https://portal.azure.com), или это можно сделать из F # следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a0ced-171">You can enable metrics for File storage from the [Azure Portal](https://portal.azure.com), or you can do it from F# like this:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L126-L140)]

## <a name="next-steps"></a><span data-ttu-id="a0ced-172">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="a0ced-172">Next steps</span></span>

<span data-ttu-id="a0ced-173">См. Дополнительные сведения о хранилище файлов Azure эти ссылки.</span><span class="sxs-lookup"><span data-stu-id="a0ced-173">See these links for more information about Azure File storage.</span></span>

### <a name="conceptual-articles-and-videos"></a><span data-ttu-id="a0ced-174">Основные статьи и видео</span><span class="sxs-lookup"><span data-stu-id="a0ced-174">Conceptual articles and videos</span></span>

- [<span data-ttu-id="a0ced-175">Хранилище файлов Azure: издержками облака SMB файловой системы для Windows и Linux</span><span class="sxs-lookup"><span data-stu-id="a0ced-175">Azure Files Storage: a frictionless cloud SMB file system for Windows and Linux</span></span>](https://azure.microsoft.com/resources/videos/azurecon-2015-azure-files-storage-a-frictionless-cloud-smb-file-system-for-windows-and-linux/)
- [<span data-ttu-id="a0ced-176">Использование хранилища Azure файла с Linux</span><span class="sxs-lookup"><span data-stu-id="a0ced-176">How to use Azure File Storage with Linux</span></span>](/azure/storage/storage-how-to-use-files-linux)

### <a name="tooling-support-for-file-storage"></a><span data-ttu-id="a0ced-177">Инструменты для хранения файлов</span><span class="sxs-lookup"><span data-stu-id="a0ced-177">Tooling support for File storage</span></span>

- [<span data-ttu-id="a0ced-178">С помощью Azure PowerShell с помощью хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="a0ced-178">Using Azure PowerShell with Azure Storage</span></span>](/azure/storage/storage-powershell-guide-full)
- [<span data-ttu-id="a0ced-179">Как использовать AzCopy с хранилищем Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="a0ced-179">How to use AzCopy with Microsoft Azure Storage</span></span>](/azure/storage/storage-use-azcopy)
- [<span data-ttu-id="a0ced-180">С помощью Azure CLI с помощью хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="a0ced-180">Using the Azure CLI with Azure Storage</span></span>](/azure/storage/storage-azure-cli#create-and-manage-file-shares)

### <a name="reference"></a><span data-ttu-id="a0ced-181">Ссылка</span><span class="sxs-lookup"><span data-stu-id="a0ced-181">Reference</span></span>

- [<span data-ttu-id="a0ced-182">Клиентская библиотека хранилища для Справочник по .NET</span><span class="sxs-lookup"><span data-stu-id="a0ced-182">Storage Client Library for .NET reference</span></span>](https://msdn.microsoft.com/library/azure/mt347887.aspx)
- [<span data-ttu-id="a0ced-183">Справочник по API REST службы файлов</span><span class="sxs-lookup"><span data-stu-id="a0ced-183">File Service REST API reference</span></span>](/rest/api/storageservices/fileservices/File-Service-REST-API)

### <a name="blog-posts"></a><span data-ttu-id="a0ced-184">Сообщения в блогах</span><span class="sxs-lookup"><span data-stu-id="a0ced-184">Blog posts</span></span>

- [<span data-ttu-id="a0ced-185">Хранилище файлов Azure теперь стал общедоступным</span><span class="sxs-lookup"><span data-stu-id="a0ced-185">Azure File storage is now generally available</span></span>](https://azure.microsoft.com/blog/azure-file-storage-now-generally-available/)
- [<span data-ttu-id="a0ced-186">Хранение файлов в Azure</span><span class="sxs-lookup"><span data-stu-id="a0ced-186">Inside Azure File Storage</span></span>](https://azure.microsoft.com/blog/inside-azure-file-storage/) 
- [<span data-ttu-id="a0ced-187">Знакомство с приложением службы файлов Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="a0ced-187">Introducing Microsoft Azure File Service</span></span>](https://blogs.msdn.microsoft.com/windowsazurestorage/2014/05/12/introducing-microsoft-azure-file-service/)
- [<span data-ttu-id="a0ced-188">Сохранение подключения к Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="a0ced-188">Persisting connections to Microsoft Azure Files</span></span>](https://blogs.msdn.microsoft.com/windowsazurestorage/2014/05/26/persisting-connections-to-microsoft-azure-files/)
