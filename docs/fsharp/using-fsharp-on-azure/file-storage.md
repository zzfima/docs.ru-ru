---
title: Начало работы с хранилищем файлов Azure с помощью языка F#
description: Храните данные файлов в облаке с помощью хранилища файлов Azure и подключите облачный файловый ресурс из виртуальной машины Azure или из локального приложения под управлением Windows.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: 9c25ab930abcbe7b358ae63c709aba4e97aed3be
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423865"
---
# <a name="get-started-with-azure-file-storage-using-f"></a><span data-ttu-id="03d8c-103">Начало работы с хранилищем файлов Azure с помощью F\#</span><span class="sxs-lookup"><span data-stu-id="03d8c-103">Get started with Azure File storage using F\#</span></span>

<span data-ttu-id="03d8c-104">Хранилище файлов Azure — это служба, которая предлагает общие файловые ресурсы в облаке с помощью стандартного [протокола SMB](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx).</span><span class="sxs-lookup"><span data-stu-id="03d8c-104">Azure File storage is a service that offers file shares in the cloud using the standard [Server Message Block (SMB) Protocol](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx).</span></span> <span data-ttu-id="03d8c-105">Поддерживаются SMB 2,1 и SMB 3,0.</span><span class="sxs-lookup"><span data-stu-id="03d8c-105">Both SMB 2.1 and SMB 3.0 are supported.</span></span> <span data-ttu-id="03d8c-106">С помощью хранилища файлов Azure можно быстро перенести устаревшие приложения, использующие общие файловые ресурсы, в Azure и без дорогостоящей перезаписи.</span><span class="sxs-lookup"><span data-stu-id="03d8c-106">With Azure File storage, you can migrate legacy applications that rely on file shares to Azure quickly and without costly rewrites.</span></span> <span data-ttu-id="03d8c-107">Приложения, работающие на виртуальных машинах или облачных службах Azure или локальных клиентах, могут подключать общую папку в облаке, так же как настольные приложения подключаются к типичному общему ресурсу SMB.</span><span class="sxs-lookup"><span data-stu-id="03d8c-107">Applications running in Azure virtual machines or cloud services or from on-premises clients can mount a file share in the cloud, just as a desktop application mounts a typical SMB share.</span></span> <span data-ttu-id="03d8c-108">После этого любое количество компонентов приложения может одновременно подключаться и обращаться к общей папке хранилища файлов.</span><span class="sxs-lookup"><span data-stu-id="03d8c-108">Any number of application components can then mount and access the File storage share simultaneously.</span></span>

<span data-ttu-id="03d8c-109">Общие сведения о хранилище файлов см. [в этом](/azure/storage/storage-dotnet-how-to-use-files)разделе.</span><span class="sxs-lookup"><span data-stu-id="03d8c-109">For a conceptual overview of file storage, please see [the .NET guide for file storage](/azure/storage/storage-dotnet-how-to-use-files).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="03d8c-110">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="03d8c-110">Prerequisites</span></span>

<span data-ttu-id="03d8c-111">Для работы с этим руководством необходимо сначала [создать учетную запись хранения Azure](/azure/storage/storage-create-storage-account).</span><span class="sxs-lookup"><span data-stu-id="03d8c-111">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span>
<span data-ttu-id="03d8c-112">Вам также потребуется ключ доступа к хранилищу для этой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="03d8c-112">You'll also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="03d8c-113">Создание F# скрипта и запуск F# интерактивного</span><span class="sxs-lookup"><span data-stu-id="03d8c-113">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="03d8c-114">Примеры в этой статье можно использовать как в F# приложении, так и в F# сценарии.</span><span class="sxs-lookup"><span data-stu-id="03d8c-114">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="03d8c-115">Чтобы создать F# скрипт, создайте файл с расширением `.fsx`, например `files.fsx`, в среде F# разработки.</span><span class="sxs-lookup"><span data-stu-id="03d8c-115">To create an F# script, create a file with the `.fsx` extension, for example `files.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="03d8c-116">Затем используйте [Диспетчер пакетов](package-management.md) , например [пакет](https://fsprojects.github.io/Paket/) или [NuGet](https://www.nuget.org/) , для установки пакета `WindowsAzure.Storage` и ссылку `WindowsAzure.Storage.dll` в скрипте с помощью директивы `#r`.</span><span class="sxs-lookup"><span data-stu-id="03d8c-116">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="03d8c-117">Добавить объявления пространств имен</span><span class="sxs-lookup"><span data-stu-id="03d8c-117">Add namespace declarations</span></span>

<span data-ttu-id="03d8c-118">Добавьте следующие `open` операторы в начало файла `files.fsx`:</span><span class="sxs-lookup"><span data-stu-id="03d8c-118">Add the following `open` statements to the top of the `files.fsx` file:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a><span data-ttu-id="03d8c-119">Получение строки подключения</span><span class="sxs-lookup"><span data-stu-id="03d8c-119">Get your connection string</span></span>

<span data-ttu-id="03d8c-120">Для работы с этим руководством вам потребуется строка подключения к службе хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="03d8c-120">You'll need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="03d8c-121">Дополнительные сведения о строках подключения см. в разделе [Настройка строк подключения к хранилищу](/azure/storage/storage-configure-connection-string).</span><span class="sxs-lookup"><span data-stu-id="03d8c-121">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="03d8c-122">В этом руководстве вы введете строку подключения в сценарий следующим образом:</span><span class="sxs-lookup"><span data-stu-id="03d8c-122">For the tutorial, you'll enter your connection string in your script, like this:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L11-L11)]

<span data-ttu-id="03d8c-123">Однако это **не рекомендуется** для реальных проектов.</span><span class="sxs-lookup"><span data-stu-id="03d8c-123">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="03d8c-124">Ключ учетной записи хранения аналогичен корневому паролю для вашей учетной записи хранения.</span><span class="sxs-lookup"><span data-stu-id="03d8c-124">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="03d8c-125">Всегда будьте внимательны, чтобы защитить ключ учетной записи хранения.</span><span class="sxs-lookup"><span data-stu-id="03d8c-125">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="03d8c-126">Не рекомендуется распространять его другим пользователям, жестко программировать или сохранять в виде обычного текстового файла, доступного для других пользователей.</span><span class="sxs-lookup"><span data-stu-id="03d8c-126">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="03d8c-127">Вы можете повторно создать ключ с помощью портала Azure, если считаете, что он был скомпрометирован.</span><span class="sxs-lookup"><span data-stu-id="03d8c-127">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="03d8c-128">Для реальных приложений лучшим способом поддержания строки подключения к хранилищу является файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="03d8c-128">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="03d8c-129">Чтобы получить строку подключения из файла конфигурации, можно сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="03d8c-129">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L13-L15)]

<span data-ttu-id="03d8c-130">Использование Configuration Manager Azure является необязательным.</span><span class="sxs-lookup"><span data-stu-id="03d8c-130">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="03d8c-131">Вы также можете использовать API, например тип .NET Framework `ConfigurationManager`.</span><span class="sxs-lookup"><span data-stu-id="03d8c-131">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="03d8c-132">Анализ строки подключения</span><span class="sxs-lookup"><span data-stu-id="03d8c-132">Parse the connection string</span></span>

<span data-ttu-id="03d8c-133">Чтобы проанализировать строку подключения, используйте:</span><span class="sxs-lookup"><span data-stu-id="03d8c-133">To parse the connection string, use:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L21-L22)]

<span data-ttu-id="03d8c-134">Это приведет к возврату `CloudStorageAccount`.</span><span class="sxs-lookup"><span data-stu-id="03d8c-134">This will return a `CloudStorageAccount`.</span></span>

### <a name="create-the-file-service-client"></a><span data-ttu-id="03d8c-135">Создание клиента службы файлов</span><span class="sxs-lookup"><span data-stu-id="03d8c-135">Create the File service client</span></span>

<span data-ttu-id="03d8c-136">Тип `CloudFileClient` позволяет программно использовать файлы, хранящиеся в хранилище файлов.</span><span class="sxs-lookup"><span data-stu-id="03d8c-136">The `CloudFileClient` type enables you to programmatically use files stored in File storage.</span></span> <span data-ttu-id="03d8c-137">Вот один из способов создания клиента службы:</span><span class="sxs-lookup"><span data-stu-id="03d8c-137">Here's one way to create the service client:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L28-L28)]

<span data-ttu-id="03d8c-138">Теперь все готово для написания кода, считывающего данные из хранилища файлов и записывающего их в хранилище.</span><span class="sxs-lookup"><span data-stu-id="03d8c-138">Now you are ready to write code that reads data from and writes data to File storage.</span></span>

## <a name="create-a-file-share"></a><span data-ttu-id="03d8c-139">Создание общей папки</span><span class="sxs-lookup"><span data-stu-id="03d8c-139">Create a file share</span></span>

<span data-ttu-id="03d8c-140">В этом примере показано, как создать файловый ресурс, если он еще не существует:</span><span class="sxs-lookup"><span data-stu-id="03d8c-140">This example shows how to create a file share if it does not already exist:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L34-L35)]

## <a name="create-a-root-directory-and-a-subdirectory"></a><span data-ttu-id="03d8c-141">Создание корневого каталога и подкаталога</span><span class="sxs-lookup"><span data-stu-id="03d8c-141">Create a root directory and a subdirectory</span></span>

<span data-ttu-id="03d8c-142">Здесь вы получаете корневой каталог и подкаталогом корневого каталога.</span><span class="sxs-lookup"><span data-stu-id="03d8c-142">Here, you get the root directory and get a sub-directory of the root.</span></span> <span data-ttu-id="03d8c-143">Они создаются, если они еще не существуют.</span><span class="sxs-lookup"><span data-stu-id="03d8c-143">You create both if they don't already exist.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L41-L43)]

## <a name="upload-text-as-a-file"></a><span data-ttu-id="03d8c-144">Отправка текста в виде файла</span><span class="sxs-lookup"><span data-stu-id="03d8c-144">Upload text as a file</span></span>

<span data-ttu-id="03d8c-145">В этом примере показано, как передать текст в виде файла.</span><span class="sxs-lookup"><span data-stu-id="03d8c-145">This example shows how to upload text as a file.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L49-L50)]

### <a name="download-a-file-to-a-local-copy-of-the-file"></a><span data-ttu-id="03d8c-146">Скачать файл в локальную копию файла</span><span class="sxs-lookup"><span data-stu-id="03d8c-146">Download a file to a local copy of the file</span></span>

<span data-ttu-id="03d8c-147">Здесь вы скачиваете только что созданный файл, добавляя содержимое в локальный файл.</span><span class="sxs-lookup"><span data-stu-id="03d8c-147">Here you download the file just created, appending the contents to a local file.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L56-L56)]

### <a name="set-the-maximum-size-for-a-file-share"></a><span data-ttu-id="03d8c-148">Установка максимального размера для общей папки</span><span class="sxs-lookup"><span data-stu-id="03d8c-148">Set the maximum size for a file share</span></span>

<span data-ttu-id="03d8c-149">В приведенном ниже примере показано, как проверить текущее использование общего ресурса и задать квоту для общей папки.</span><span class="sxs-lookup"><span data-stu-id="03d8c-149">The example below shows how to check the current usage for a share and how to set the quota for the share.</span></span> <span data-ttu-id="03d8c-150">для заполнения `Properties`общего ресурса необходимо вызвать `FetchAttributes` и `SetProperties` распространить локальные изменения в хранилище файлов Azure.</span><span class="sxs-lookup"><span data-stu-id="03d8c-150">`FetchAttributes` must be called to populate a share's `Properties`, and `SetProperties` to propagate local changes to Azure File storage.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L62-L72)]

### <a name="generate-a-shared-access-signature-for-a-file-or-file-share"></a><span data-ttu-id="03d8c-151">Создание подписи общего доступа для файла или файлового ресурса</span><span class="sxs-lookup"><span data-stu-id="03d8c-151">Generate a shared access signature for a file or file share</span></span>

<span data-ttu-id="03d8c-152">Вы можете создать подписанный URL-адрес (SAS) для общей папки или отдельного файла.</span><span class="sxs-lookup"><span data-stu-id="03d8c-152">You can generate a shared access signature (SAS) for a file share or for an individual file.</span></span> <span data-ttu-id="03d8c-153">Кроме того, можно создать политику общего доступа в общей папке для управления подписанными URL-доступом.</span><span class="sxs-lookup"><span data-stu-id="03d8c-153">You can also create a shared access policy on a file share to manage shared access signatures.</span></span> <span data-ttu-id="03d8c-154">Рекомендуется создать политику общего доступа, так как она предоставляет средства отмены SAS, если она должна быть скомпрометирована.</span><span class="sxs-lookup"><span data-stu-id="03d8c-154">Creating a shared access policy is recommended, as it provides a means of revoking the SAS if it should be compromised.</span></span>

<span data-ttu-id="03d8c-155">Здесь вы создаете политику общего доступа для общей папки, а затем используете эту политику для предоставления ограничений для SAS для файла в общей папке.</span><span class="sxs-lookup"><span data-stu-id="03d8c-155">Here, you create a shared access policy on a share, and then use that policy to provide the constraints for a SAS on a file in the share.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L78-L94)]

<span data-ttu-id="03d8c-156">Дополнительные сведения о создании и использовании подписанных URL-адресов см. в статьях [Использование подписей общего доступа (SAS)](/azure/storage/storage-dotnet-shared-access-signature-part-1) и [Создание и использование SAS с хранилищем BLOB-объектов](/azure/storage/storage-dotnet-shared-access-signature-part-2).</span><span class="sxs-lookup"><span data-stu-id="03d8c-156">For more information about creating and using shared access signatures, see [Using Shared Access Signatures (SAS)](/azure/storage/storage-dotnet-shared-access-signature-part-1) and [Create and use a SAS with Blob storage](/azure/storage/storage-dotnet-shared-access-signature-part-2).</span></span>

### <a name="copy-files"></a><span data-ttu-id="03d8c-157">Копирование файлов</span><span class="sxs-lookup"><span data-stu-id="03d8c-157">Copy files</span></span>

<span data-ttu-id="03d8c-158">Файл можно скопировать в другой файл или в большой двоичный объект или в большой двоичный объект в файл.</span><span class="sxs-lookup"><span data-stu-id="03d8c-158">You can copy a file to another file or to a blob, or a blob to a file.</span></span> <span data-ttu-id="03d8c-159">Если вы копируете большой двоичный объект в файл или файл в большой двоичный объект, *необходимо* использовать подписанный URL-адрес (SAS) для проверки подлинности исходного объекта, даже если вы копируете его в ту же учетную запись хранения.</span><span class="sxs-lookup"><span data-stu-id="03d8c-159">If you are copying a blob to a file, or a file to a blob, you *must* use a shared access signature (SAS) to authenticate the source object, even if you are copying within the same storage account.</span></span>

### <a name="copy-a-file-to-another-file"></a><span data-ttu-id="03d8c-160">Копирование файла в другой файл</span><span class="sxs-lookup"><span data-stu-id="03d8c-160">Copy a file to another file</span></span>

<span data-ttu-id="03d8c-161">Здесь вы копируете файл в другой файл в той же общей папке.</span><span class="sxs-lookup"><span data-stu-id="03d8c-161">Here, you copy a file to another file in the same share.</span></span> <span data-ttu-id="03d8c-162">Так как эта операция копирования копирует между файлами в одной учетной записи хранения, для копирования можно использовать проверку подлинности с помощью общего ключа.</span><span class="sxs-lookup"><span data-stu-id="03d8c-162">Because this copy operation copies between files in the same storage account, you can use Shared Key authentication to perform the copy.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L100-L101)]

### <a name="copy-a-file-to-a-blob"></a><span data-ttu-id="03d8c-163">Копирование файла в большой двоичный объект</span><span class="sxs-lookup"><span data-stu-id="03d8c-163">Copy a file to a blob</span></span>

<span data-ttu-id="03d8c-164">Здесь вы создаете файл и копируете его в большой двоичный объект в той же учетной записи хранения.</span><span class="sxs-lookup"><span data-stu-id="03d8c-164">Here, you create a file and copy it to a blob within the same storage account.</span></span> <span data-ttu-id="03d8c-165">Создайте SAS для исходного файла, который служба использует для проверки подлинности доступа к исходному файлу во время операции копирования.</span><span class="sxs-lookup"><span data-stu-id="03d8c-165">You create a SAS for the source file, which the service uses to authenticate access to the source file during the copy operation.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L107-L120)]

<span data-ttu-id="03d8c-166">Вы можете скопировать большой двоичный объект в файл таким же образом.</span><span class="sxs-lookup"><span data-stu-id="03d8c-166">You can copy a blob to a file in the same way.</span></span> <span data-ttu-id="03d8c-167">Если исходный объект является BLOB-объектом, создайте SAS для проверки подлинности доступа к этому большому двоичному объекту во время операции копирования.</span><span class="sxs-lookup"><span data-stu-id="03d8c-167">If the source object is a blob, then create a SAS to authenticate access to that blob during the copy operation.</span></span>

## <a name="troubleshooting-file-storage-using-metrics"></a><span data-ttu-id="03d8c-168">Устранение неполадок хранилища файлов с помощью метрик</span><span class="sxs-lookup"><span data-stu-id="03d8c-168">Troubleshooting File storage using metrics</span></span>

<span data-ttu-id="03d8c-169">Аналитика Службы хранилища Azure поддерживает метрики для хранилища файлов.</span><span class="sxs-lookup"><span data-stu-id="03d8c-169">Azure Storage Analytics supports metrics for File storage.</span></span> <span data-ttu-id="03d8c-170">С помощью данных метрик можно отслеживать запросы и диагностировать проблемы.</span><span class="sxs-lookup"><span data-stu-id="03d8c-170">With metrics data, you can trace requests and diagnose issues.</span></span>

<span data-ttu-id="03d8c-171">Вы можете включить метрики для хранилища файлов на [портале Azure](https://portal.azure.com). также можно сделать это F# следующим образом:</span><span class="sxs-lookup"><span data-stu-id="03d8c-171">You can enable metrics for File storage from the [Azure Portal](https://portal.azure.com), or you can do it from F# like this:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L126-L140)]

## <a name="next-steps"></a><span data-ttu-id="03d8c-172">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="03d8c-172">Next steps</span></span>

<span data-ttu-id="03d8c-173">Дополнительные сведения о хранилище файлов Azure см. в этих ссылках.</span><span class="sxs-lookup"><span data-stu-id="03d8c-173">See these links for more information about Azure File storage.</span></span>

### <a name="conceptual-articles-and-videos"></a><span data-ttu-id="03d8c-174">Концептуальные статьи и видеоматериалы</span><span class="sxs-lookup"><span data-stu-id="03d8c-174">Conceptual articles and videos</span></span>

- [<span data-ttu-id="03d8c-175">Хранилище файлов Azure. облачная файловая система SMB для Windows и Linux</span><span class="sxs-lookup"><span data-stu-id="03d8c-175">Azure Files Storage: a frictionless cloud SMB file system for Windows and Linux</span></span>](https://azure.microsoft.com/resources/videos/azurecon-2015-azure-files-storage-a-frictionless-cloud-smb-file-system-for-windows-and-linux/)
- [<span data-ttu-id="03d8c-176">Использование хранилища файлов Azure с Linux</span><span class="sxs-lookup"><span data-stu-id="03d8c-176">How to use Azure File Storage with Linux</span></span>](/azure/storage/storage-how-to-use-files-linux)

### <a name="tooling-support-for-file-storage"></a><span data-ttu-id="03d8c-177">Поддержка инструментария для хранилища файлов</span><span class="sxs-lookup"><span data-stu-id="03d8c-177">Tooling support for File storage</span></span>

- [<span data-ttu-id="03d8c-178">Использование Azure PowerShell с хранилищем Azure</span><span class="sxs-lookup"><span data-stu-id="03d8c-178">Using Azure PowerShell with Azure Storage</span></span>](/azure/storage/storage-powershell-guide-full)
- [<span data-ttu-id="03d8c-179">Использование AzCopy с служба хранилища Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="03d8c-179">How to use AzCopy with Microsoft Azure Storage</span></span>](/azure/storage/storage-use-azcopy)
- [<span data-ttu-id="03d8c-180">Использование Azure CLI с хранилищем Azure</span><span class="sxs-lookup"><span data-stu-id="03d8c-180">Using the Azure CLI with Azure Storage</span></span>](/azure/storage/storage-azure-cli#create-and-manage-file-shares)

### <a name="reference"></a><span data-ttu-id="03d8c-181">Справочники</span><span class="sxs-lookup"><span data-stu-id="03d8c-181">Reference</span></span>

- [<span data-ttu-id="03d8c-182">Справочник по клиентской библиотеке хранилища для .NET</span><span class="sxs-lookup"><span data-stu-id="03d8c-182">Storage Client Library for .NET reference</span></span>](https://msdn.microsoft.com/library/azure/mt347887.aspx)
- [<span data-ttu-id="03d8c-183">Справочник по REST API службы файлов</span><span class="sxs-lookup"><span data-stu-id="03d8c-183">File Service REST API reference</span></span>](/rest/api/storageservices/fileservices/File-Service-REST-API)

### <a name="blog-posts"></a><span data-ttu-id="03d8c-184">Записи блога</span><span class="sxs-lookup"><span data-stu-id="03d8c-184">Blog posts</span></span>

- [<span data-ttu-id="03d8c-185">Хранилище файлов Azure теперь общедоступно</span><span class="sxs-lookup"><span data-stu-id="03d8c-185">Azure File storage is now generally available</span></span>](https://azure.microsoft.com/blog/azure-file-storage-now-generally-available/)
- [<span data-ttu-id="03d8c-186">Внутреннее хранилище файлов Azure</span><span class="sxs-lookup"><span data-stu-id="03d8c-186">Inside Azure File Storage</span></span>](https://azure.microsoft.com/blog/inside-azure-file-storage/)
- [<span data-ttu-id="03d8c-187">Введение в Microsoft Azure файловую службу</span><span class="sxs-lookup"><span data-stu-id="03d8c-187">Introducing Microsoft Azure File Service</span></span>](https://blogs.msdn.microsoft.com/windowsazurestorage/2014/05/12/introducing-microsoft-azure-file-service/)
- [<span data-ttu-id="03d8c-188">Сохранение соединений с файлами Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="03d8c-188">Persisting connections to Microsoft Azure Files</span></span>](https://blogs.msdn.microsoft.com/windowsazurestorage/2014/05/26/persisting-connections-to-microsoft-azure-files/)
