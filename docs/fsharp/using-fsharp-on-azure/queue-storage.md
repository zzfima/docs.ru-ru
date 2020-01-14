---
title: Начало работы с хранилищем очередей Azure с помощью языка F#
description: Очереди хранилища обеспечивают надежный асинхронный обмен сообщениями между компонентами приложения. Обмен сообщениями в облаке позволяет масштабировать компоненты приложения независимо друг от друга.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: 841068ac91aecc53811359e27d984907569a2c6d
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2020
ms.locfileid: "75935496"
---
# <a name="get-started-with-azure-queue-storage-using-f"></a><span data-ttu-id="c2006-104">Приступая к работе с хранилищем очередей Azure с помощью F\#</span><span class="sxs-lookup"><span data-stu-id="c2006-104">Get started with Azure Queue storage using F\#</span></span>

<span data-ttu-id="c2006-105">Хранилище очередей Azure — это служба, обеспечивающая обмен сообщениями в облаке между компонентами приложения.</span><span class="sxs-lookup"><span data-stu-id="c2006-105">Azure Queue storage provides cloud messaging between application components.</span></span> <span data-ttu-id="c2006-106">При разработке приложений для масштабирования компоненты приложения часто не связаны между собой, так что они могут масштабироваться независимо друг от друга.</span><span class="sxs-lookup"><span data-stu-id="c2006-106">In designing applications for scale, application components are often decoupled, so that they can scale independently.</span></span> <span data-ttu-id="c2006-107">Хранилище очередей обеспечивает асинхронный обмен сообщениями для взаимодействия между компонентами приложения независимо от того, где они выполняются: в облаке, на рабочем столе, локальном сервере или мобильном устройстве.</span><span class="sxs-lookup"><span data-stu-id="c2006-107">Queue storage delivers asynchronous messaging for communication between application components, whether they are running in the cloud, on the desktop, on an on-premises server, or on a mobile device.</span></span> <span data-ttu-id="c2006-108">Хранилище очередей также поддерживает управление асинхронными задачами и создание рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="c2006-108">Queue storage also supports managing asynchronous tasks and building process work flows.</span></span>

### <a name="about-this-tutorial"></a><span data-ttu-id="c2006-109">Сведения об этом руководстве</span><span class="sxs-lookup"><span data-stu-id="c2006-109">About this tutorial</span></span>

<span data-ttu-id="c2006-110">В этом руководстве показано, как F# написать код для некоторых распространенных задач с помощью хранилища очередей Azure.</span><span class="sxs-lookup"><span data-stu-id="c2006-110">This tutorial shows how to write F# code for some common tasks using Azure Queue storage.</span></span> <span data-ttu-id="c2006-111">В число описываемых задач входят создание и удаление очередей, а затем Добавление, чтение и удаление сообщений очереди.</span><span class="sxs-lookup"><span data-stu-id="c2006-111">Tasks covered include creating and deleting queues and adding, reading, and deleting queue messages.</span></span>

<span data-ttu-id="c2006-112">Общие сведения о хранилище очередей см. в разделе ["рекомендации по .NET" для хранилища очередей](/azure/storage/storage-dotnet-how-to-use-queues).</span><span class="sxs-lookup"><span data-stu-id="c2006-112">For a conceptual overview of queue storage, please see [the .NET guide for queue storage](/azure/storage/storage-dotnet-how-to-use-queues).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c2006-113">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="c2006-113">Prerequisites</span></span>

<span data-ttu-id="c2006-114">Для работы с этим руководством необходимо сначала [создать учетную запись хранения Azure](/azure/storage/storage-create-storage-account).</span><span class="sxs-lookup"><span data-stu-id="c2006-114">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span>
<span data-ttu-id="c2006-115">Вам также потребуется ключ доступа к хранилищу для этой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="c2006-115">You'll also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="c2006-116">Создание F# скрипта и запуск F# интерактивного</span><span class="sxs-lookup"><span data-stu-id="c2006-116">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="c2006-117">Примеры в этой статье можно использовать как в F# приложении, так и в F# сценарии.</span><span class="sxs-lookup"><span data-stu-id="c2006-117">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="c2006-118">Чтобы создать F# скрипт, создайте файл с расширением `.fsx`, например `queues.fsx`, в среде F# разработки.</span><span class="sxs-lookup"><span data-stu-id="c2006-118">To create an F# script, create a file with the `.fsx` extension, for example `queues.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="c2006-119">Затем используйте [Диспетчер пакетов](package-management.md) , например [пакет](https://fsprojects.github.io/Paket/) или [NuGet](https://www.nuget.org/) , для установки пакета `WindowsAzure.Storage` и ссылки на `WindowsAzure.Storage.dll` в скрипте с помощью директивы `#r`.</span><span class="sxs-lookup"><span data-stu-id="c2006-119">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="c2006-120">Добавление объявлений пространств имен</span><span class="sxs-lookup"><span data-stu-id="c2006-120">Add namespace declarations</span></span>

<span data-ttu-id="c2006-121">Добавьте в начало файла `queues.fsx` следующие инструкции `open`:</span><span class="sxs-lookup"><span data-stu-id="c2006-121">Add the following `open` statements to the top of the `queues.fsx` file:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L1-L3)]

### <a name="get-your-connection-string"></a><span data-ttu-id="c2006-122">Получение строки подключения</span><span class="sxs-lookup"><span data-stu-id="c2006-122">Get your connection string</span></span>

<span data-ttu-id="c2006-123">Для работы с этим руководством вам потребуется строка подключения к службе хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="c2006-123">You'll need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="c2006-124">Дополнительные сведения о строках подключения см. в разделе [Настройка строк подключения к хранилищу](/azure/storage/storage-configure-connection-string).</span><span class="sxs-lookup"><span data-stu-id="c2006-124">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="c2006-125">В этом руководстве вы введете строку подключения в сценарий следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c2006-125">For the tutorial, you'll enter your connection string in your script, like this:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L9-L9)]

<span data-ttu-id="c2006-126">Однако это **не рекомендуется** для реальных проектов.</span><span class="sxs-lookup"><span data-stu-id="c2006-126">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="c2006-127">Ключ учетной записи хранения похож на корневой пароль для вашей учетной записи хранения.</span><span class="sxs-lookup"><span data-stu-id="c2006-127">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="c2006-128">Не забудьте защитить ключ учетной записи хранения.</span><span class="sxs-lookup"><span data-stu-id="c2006-128">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="c2006-129">Не сообщайте его другим пользователям, не определяйте его в коде и не храните его в текстовом файле, доступном другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="c2006-129">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="c2006-130">Вы можете повторно создать ключ с помощью портала Azure, если считаете, что он был скомпрометирован.</span><span class="sxs-lookup"><span data-stu-id="c2006-130">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="c2006-131">Для реальных приложений лучшим способом поддержания строки подключения к хранилищу является файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c2006-131">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="c2006-132">Чтобы получить строку подключения из файла конфигурации, можно сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="c2006-132">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L11-L13)]

<span data-ttu-id="c2006-133">Использование диспетчера конфигураций Azure не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="c2006-133">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="c2006-134">Можно также использовать API, например тип `ConfigurationManager` .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c2006-134">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="c2006-135">Проанализируйте строку подключения</span><span class="sxs-lookup"><span data-stu-id="c2006-135">Parse the connection string</span></span>

<span data-ttu-id="c2006-136">Чтобы проанализировать строку подключения, используйте:</span><span class="sxs-lookup"><span data-stu-id="c2006-136">To parse the connection string, use:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L19-L20)]

<span data-ttu-id="c2006-137">Это приведет к возврату `CloudStorageAccount`.</span><span class="sxs-lookup"><span data-stu-id="c2006-137">This will return a `CloudStorageAccount`.</span></span>

### <a name="create-the-queue-service-client"></a><span data-ttu-id="c2006-138">Создание клиента службы очередей</span><span class="sxs-lookup"><span data-stu-id="c2006-138">Create the Queue service client</span></span>

<span data-ttu-id="c2006-139">Класс `CloudQueueClient` позволяет получать очереди, хранящиеся в хранилище очередей.</span><span class="sxs-lookup"><span data-stu-id="c2006-139">The `CloudQueueClient` class enables you to retrieve queues stored in Queue storage.</span></span> <span data-ttu-id="c2006-140">Вот один из способов создать клиента службы.</span><span class="sxs-lookup"><span data-stu-id="c2006-140">Here's one way to create the service client:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L26-L26)]

<span data-ttu-id="c2006-141">Теперь вы можете написать код, который считывает и записывает данные в хранилище очередей.</span><span class="sxs-lookup"><span data-stu-id="c2006-141">Now you are ready to write code that reads data from and writes data to Queue storage.</span></span>

## <a name="create-a-queue"></a><span data-ttu-id="c2006-142">Создать очередь</span><span class="sxs-lookup"><span data-stu-id="c2006-142">Create a queue</span></span>

<span data-ttu-id="c2006-143">В этом примере показано, как создать очередь, если она еще не существует:</span><span class="sxs-lookup"><span data-stu-id="c2006-143">This example shows how to create a queue if it doesn't already exist:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L32-L36)]

## <a name="insert-a-message-into-a-queue"></a><span data-ttu-id="c2006-144">Вставка сообщения в очередь</span><span class="sxs-lookup"><span data-stu-id="c2006-144">Insert a message into a queue</span></span>

<span data-ttu-id="c2006-145">Чтобы вставить сообщение в существующую очередь, сначала создайте новый `CloudQueueMessage`.</span><span class="sxs-lookup"><span data-stu-id="c2006-145">To insert a message into an existing queue, first create a new `CloudQueueMessage`.</span></span> <span data-ttu-id="c2006-146">Затем вызовите метод `AddMessage`.</span><span class="sxs-lookup"><span data-stu-id="c2006-146">Next, call the `AddMessage` method.</span></span> <span data-ttu-id="c2006-147">`CloudQueueMessage` можно создать из строки (в формате UTF-8) или массива `byte` следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c2006-147">A `CloudQueueMessage` can be created from either a string (in UTF-8 format) or a `byte` array, like this:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L42-L44)]

## <a name="peek-at-the-next-message"></a><span data-ttu-id="c2006-148">Просмотр следующего сообщения</span><span class="sxs-lookup"><span data-stu-id="c2006-148">Peek at the next message</span></span>

<span data-ttu-id="c2006-149">Можно взглянуть на сообщение в начале очереди, не удаляя его из очереди, вызвав метод `PeekMessage`.</span><span class="sxs-lookup"><span data-stu-id="c2006-149">You can peek at the message in the front of a queue, without removing it from the queue, by calling the `PeekMessage` method.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L50-L52)]

## <a name="get-the-next-message-for-processing"></a><span data-ttu-id="c2006-150">Получить следующее сообщение для обработки</span><span class="sxs-lookup"><span data-stu-id="c2006-150">Get the next message for processing</span></span>

<span data-ttu-id="c2006-151">Вы можете получить сообщение в начале очереди для обработки, вызвав метод `GetMessage`.</span><span class="sxs-lookup"><span data-stu-id="c2006-151">You can retrieve the message at the front of a queue for processing by calling the `GetMessage` method.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L58-L59)]

<span data-ttu-id="c2006-152">Позднее можно указать успешную обработку сообщения с помощью `DeleteMessage`.</span><span class="sxs-lookup"><span data-stu-id="c2006-152">You later indicate successful processing of the message by using `DeleteMessage`.</span></span>

## <a name="change-the-contents-of-a-queued-message"></a><span data-ttu-id="c2006-153">Изменение содержимого сообщения в очереди</span><span class="sxs-lookup"><span data-stu-id="c2006-153">Change the contents of a queued message</span></span>

<span data-ttu-id="c2006-154">Вы можете изменить содержимое извлеченного сообщения на месте в очереди.</span><span class="sxs-lookup"><span data-stu-id="c2006-154">You can change the contents of a retrieved message in-place in the queue.</span></span> <span data-ttu-id="c2006-155">Если сообщение представляет собой рабочую задачу, можно использовать эту функцию для обновления состояния рабочей задачи.</span><span class="sxs-lookup"><span data-stu-id="c2006-155">If the message represents a work task, you could use this feature to update the status of the work task.</span></span> <span data-ttu-id="c2006-156">Следующий код добавляет новое содержимое в очередь сообщений и продлевает время ожидания видимости еще на 60 секунд.</span><span class="sxs-lookup"><span data-stu-id="c2006-156">The following code updates the queue message with new contents, and sets the visibility timeout to extend another 60 seconds.</span></span> <span data-ttu-id="c2006-157">Это сохраняет состояние работы, связанной с данным сообщением, и позволяет клиенту продолжить работу с сообщением на протяжении еще одной минуты.</span><span class="sxs-lookup"><span data-stu-id="c2006-157">This saves the state of work associated with the message, and gives the client another minute to continue working on the message.</span></span> <span data-ttu-id="c2006-158">Этот метод можно использовать для отслеживания многошаговых рабочих процессов по сообщениям в очереди без необходимости начинать с самого начала в случае сбоя шага обработки в связи с ошибкой аппаратного или программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="c2006-158">You could use this technique to track multi-step workflows on queue messages, without having to start over from the beginning if a processing step fails due to hardware or software failure.</span></span> <span data-ttu-id="c2006-159">Как правило, вы также сохраняете число повторных попыток, и если сообщение повторяется несколько раз, его можно удалить.</span><span class="sxs-lookup"><span data-stu-id="c2006-159">Typically, you would keep a retry count as well, and if the message is retried more than some number of times, you would delete it.</span></span> <span data-ttu-id="c2006-160">Это обеспечивает защиту от сообщений, которые инициируют ошибку приложения при каждой попытке обработки.</span><span class="sxs-lookup"><span data-stu-id="c2006-160">This protects against a message that triggers an application error each time it is processed.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L65-L69)]

## <a name="de-queue-the-next-message"></a><span data-ttu-id="c2006-161">Удаление следующего сообщения из очереди</span><span class="sxs-lookup"><span data-stu-id="c2006-161">De-queue the next message</span></span>

<span data-ttu-id="c2006-162">Код удаляет сообщение из очереди в два этапа.</span><span class="sxs-lookup"><span data-stu-id="c2006-162">Your code de-queues a message from a queue in two steps.</span></span> <span data-ttu-id="c2006-163">При вызове `GetMessage`вы получаете следующее сообщение в очереди.</span><span class="sxs-lookup"><span data-stu-id="c2006-163">When you call `GetMessage`, you get the next message in a queue.</span></span> <span data-ttu-id="c2006-164">Сообщение, возвращаемое методом `GetMessage`, становится невидимым для другого кода, считывающего сообщения из этой очереди.</span><span class="sxs-lookup"><span data-stu-id="c2006-164">A message returned from `GetMessage` becomes invisible to any other code reading messages from this queue.</span></span> <span data-ttu-id="c2006-165">По умолчанию это сообщение остается невидимым в течение 30 секунд.</span><span class="sxs-lookup"><span data-stu-id="c2006-165">By default, this message stays invisible for 30 seconds.</span></span> <span data-ttu-id="c2006-166">Чтобы завершить удаление сообщения из очереди, необходимо также вызвать `DeleteMessage`.</span><span class="sxs-lookup"><span data-stu-id="c2006-166">To finish removing the message from the queue, you must also call `DeleteMessage`.</span></span> <span data-ttu-id="c2006-167">Этот двухэтапный процесс удаления сообщения позволяет удостовериться, что если коду не удастся обработать сообщение из-за сбоя оборудования или программного обеспечения, другой экземпляр кода сможет получить то же сообщение и повторить попытку.</span><span class="sxs-lookup"><span data-stu-id="c2006-167">This two-step process of removing a message assures that if your code fails to process a message due to hardware or software failure, another instance of your code can get the same message and try again.</span></span> <span data-ttu-id="c2006-168">Код вызывает `DeleteMessage` сразу после обработки сообщения.</span><span class="sxs-lookup"><span data-stu-id="c2006-168">Your code calls `DeleteMessage` right after the message has been processed.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L75-L76)]

## <a name="use-async-workflows-with-common-queue-storage-apis"></a><span data-ttu-id="c2006-169">Использование асинхронных рабочих процессов с общими интерфейсами API хранилища очередей</span><span class="sxs-lookup"><span data-stu-id="c2006-169">Use Async workflows with common Queue storage APIs</span></span>

<span data-ttu-id="c2006-170">В этом примере показано, как использовать асинхронный рабочий процесс с общими интерфейсами API хранилища очередей.</span><span class="sxs-lookup"><span data-stu-id="c2006-170">This example shows how to use an async workflow with common Queue storage APIs.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L82-L91)]

## <a name="additional-options-for-de-queuing-messages"></a><span data-ttu-id="c2006-171">Дополнительные параметры для удаления сообщений из очереди</span><span class="sxs-lookup"><span data-stu-id="c2006-171">Additional options for de-queuing messages</span></span>

<span data-ttu-id="c2006-172">Способ извлечения сообщения из очереди можно настроить двумя способами.</span><span class="sxs-lookup"><span data-stu-id="c2006-172">There are two ways you can customize message retrieval from a queue.</span></span>
<span data-ttu-id="c2006-173">Во-первых, можно получить пакет сообщений (до 32 сообщений).</span><span class="sxs-lookup"><span data-stu-id="c2006-173">First, you can get a batch of messages (up to 32).</span></span> <span data-ttu-id="c2006-174">Во-вторых, можно задать более длительное или короткое время ожидания видимости, чтобы предоставить коду больше или меньше времени на полную обработку каждого сообщения.</span><span class="sxs-lookup"><span data-stu-id="c2006-174">Second, you can set a longer or shorter invisibility timeout, allowing your code more or less time to fully process each message.</span></span> <span data-ttu-id="c2006-175">В следующем примере кода используется `GetMessages` для получения 20 сообщений в одном вызове и последующей обработки каждого сообщения.</span><span class="sxs-lookup"><span data-stu-id="c2006-175">The following code example uses `GetMessages` to get 20 messages in one call and then processes each message.</span></span> <span data-ttu-id="c2006-176">Он также задает время ожидания невидимости 5 минут для каждого сообщения.</span><span class="sxs-lookup"><span data-stu-id="c2006-176">It also sets the invisibility timeout to five minutes for each message.</span></span> <span data-ttu-id="c2006-177">Обратите внимание, что 5 минут начинается для всех сообщений одновременно, поэтому спустя 5 минут после вызова `GetMessages`все сообщения, которые не были удалены, снова станут видимыми.</span><span class="sxs-lookup"><span data-stu-id="c2006-177">Note that the 5 minutes starts for all messages at the same time, so after 5 minutes have passed since the call to `GetMessages`, any messages which have not been deleted will become visible again.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L97-L99)]

## <a name="get-the-queue-length"></a><span data-ttu-id="c2006-178">Получение длины очереди</span><span class="sxs-lookup"><span data-stu-id="c2006-178">Get the queue length</span></span>

<span data-ttu-id="c2006-179">Вы можете узнать приблизительное количество сообщений в очереди.</span><span class="sxs-lookup"><span data-stu-id="c2006-179">You can get an estimate of the number of messages in a queue.</span></span> <span data-ttu-id="c2006-180">Метод `FetchAttributes` запрашивает у служба очередей получение атрибутов очереди, включая число сообщений.</span><span class="sxs-lookup"><span data-stu-id="c2006-180">The `FetchAttributes` method asks the Queue service to retrieve the queue attributes, including the message count.</span></span> <span data-ttu-id="c2006-181">Свойство `ApproximateMessageCount` возвращает последнее значение, полученное методом `FetchAttributes`, без вызова служба очередей.</span><span class="sxs-lookup"><span data-stu-id="c2006-181">The `ApproximateMessageCount` property returns the last value retrieved by the `FetchAttributes` method, without calling the Queue service.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L105-L106)]

## <a name="delete-a-queue"></a><span data-ttu-id="c2006-182">Удаление очереди</span><span class="sxs-lookup"><span data-stu-id="c2006-182">Delete a queue</span></span>

<span data-ttu-id="c2006-183">Чтобы удалить очередь и все сообщения, содержащиеся в ней, вызовите метод `Delete` для объекта Queue.</span><span class="sxs-lookup"><span data-stu-id="c2006-183">To delete a queue and all the messages contained in it, call the `Delete` method on the queue object.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L112-L113)]

## <a name="next-steps"></a><span data-ttu-id="c2006-184">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="c2006-184">Next steps</span></span>

<span data-ttu-id="c2006-185">Вы изучили основные сведения о хранилище очередей. Дополнительные сведения о более сложных задачах по использованию хранилища можно найти по следующим ссылкам.</span><span class="sxs-lookup"><span data-stu-id="c2006-185">Now that you've learned the basics of Queue storage, follow these links to learn about more complex storage tasks.</span></span>

- [<span data-ttu-id="c2006-186">API-интерфейсы хранилища Azure для .NET</span><span class="sxs-lookup"><span data-stu-id="c2006-186">Azure Storage APIs for .NET</span></span>](/dotnet/api/overview/azure/storage)
- [<span data-ttu-id="c2006-187">Поставщик типов службы хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="c2006-187">Azure Storage Type Provider</span></span>](https://github.com/fsprojects/AzureStorageTypeProvider)
- [<span data-ttu-id="c2006-188">Блог рабочей группы службы хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="c2006-188">Azure Storage Team Blog</span></span>](https://docs.microsoft.com/archive/blogs/windowsazurestorage/)
- [<span data-ttu-id="c2006-189">Настройка строк подключения службы хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="c2006-189">Configure Azure Storage connection strings</span></span>](/azure/storage/common/storage-configure-connection-string)
- <span data-ttu-id="c2006-190">[Azure Storage Services REST API Reference](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference) (Справочник по REST API службы хранилища Azure)</span><span class="sxs-lookup"><span data-stu-id="c2006-190">[Azure Storage Services REST API Reference](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)</span></span>
