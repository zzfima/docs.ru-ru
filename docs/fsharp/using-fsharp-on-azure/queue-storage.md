---
title: "Начало работы с хранилищем очередей Azure, с помощью F #"
description: "Очереди Azure предоставляют надежного асинхронного обмена сообщениями между компонентами приложения. Облака обмена сообщениями позволяет независимо масштабировать компоненты приложения."
keywords: "Visual f #, f #, функционального программирования, .NET, .NET Core, Azure"
author: sylvanc
ms.author: phcart
ms.date: 09/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 70dc554c-8f4d-42a7-8e2a-6438657d012a
ms.openlocfilehash: 50b2d69a1753add688aa14c3314a0ca2df9f03a4
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2018
---
# <a name="get-started-with-azure-queue-storage-using-f"></a><span data-ttu-id="99c13-105">Начало работы с хранилищем очередей Azure, с помощью F #</span><span class="sxs-lookup"><span data-stu-id="99c13-105">Get started with Azure Queue storage using F#</span></span> #

<span data-ttu-id="99c13-106">Azure хранилище очередей обеспечивает обмен сообщениями между компонентами приложения облака.</span><span class="sxs-lookup"><span data-stu-id="99c13-106">Azure Queue storage provides cloud messaging between application components.</span></span> <span data-ttu-id="99c13-107">В разработке приложений для масштабирования, часто разделены компоненты приложения, так что их можно легко масштабировать независимо друг от друга.</span><span class="sxs-lookup"><span data-stu-id="99c13-107">In designing applications for scale, application components are often decoupled, so that they can scale independently.</span></span> <span data-ttu-id="99c13-108">Хранилище очередей обеспечивает асинхронный обмен сообщениями для взаимодействия между компонентами приложения, ли они выполняются в облаке, на рабочем столе, на локальном сервере или на мобильном устройстве.</span><span class="sxs-lookup"><span data-stu-id="99c13-108">Queue storage delivers asynchronous messaging for communication between application components, whether they are running in the cloud, on the desktop, on an on-premises server, or on a mobile device.</span></span> <span data-ttu-id="99c13-109">Хранилище очередей также поддерживает управление асинхронных задач и построения потоков рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="99c13-109">Queue storage also supports managing asynchronous tasks and building process work flows.</span></span>

### <a name="about-this-tutorial"></a><span data-ttu-id="99c13-110">О этого учебника</span><span class="sxs-lookup"><span data-stu-id="99c13-110">About this tutorial</span></span>

<span data-ttu-id="99c13-111">Этот учебник показывает способы написания кода F # для некоторых типичных задач, с помощью хранилища очередей Azure.</span><span class="sxs-lookup"><span data-stu-id="99c13-111">This tutorial shows how to write F# code for some common tasks using Azure Queue storage.</span></span> <span data-ttu-id="99c13-112">Рассмотренные задачи включают создание и удаление очередей и добавление, чтение и удаление сообщений очереди.</span><span class="sxs-lookup"><span data-stu-id="99c13-112">Tasks covered include creating and deleting queues and adding, reading, and deleting queue messages.</span></span>

<span data-ttu-id="99c13-113">Концептуальный обзор хранилища очередей, см. в разделе [руководство по .NET для хранилища очереди](/azure/storage/storage-dotnet-how-to-use-queues).</span><span class="sxs-lookup"><span data-stu-id="99c13-113">For a conceptual overview of queue storage, please see [the .NET guide for queue storage](/azure/storage/storage-dotnet-how-to-use-queues).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="99c13-114">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="99c13-114">Prerequisites</span></span>

<span data-ttu-id="99c13-115">Чтобы использовать это руководство, необходимо сначала [создать учетную запись хранилища Azure](/azure/storage/storage-create-storage-account).</span><span class="sxs-lookup"><span data-stu-id="99c13-115">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span>
<span data-ttu-id="99c13-116">Кроме того, потребуется ключ доступа хранилища для этой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="99c13-116">You'll also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="99c13-117">Создание скрипта F # и начала F #, интерактивный</span><span class="sxs-lookup"><span data-stu-id="99c13-117">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="99c13-118">Примеры в этой статье используется в F # приложения или скрипта F #.</span><span class="sxs-lookup"><span data-stu-id="99c13-118">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="99c13-119">Чтобы создать скрипт F #, создайте файл с `.fsx` расширение, например `queues.fsx`, в среде разработки F #.</span><span class="sxs-lookup"><span data-stu-id="99c13-119">To create an F# script, create a file with the `.fsx` extension, for example `queues.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="99c13-120">Затем используйте [диспетчера пакетов](package-management.md) такие как [Paket](https://fsprojects.github.io/Paket/) или [NuGet](https://www.nuget.org/) установка `WindowsAzure.Storage` пакета и ссылка `WindowsAzure.Storage.dll` в скрипте с помощью `#r`директивы.</span><span class="sxs-lookup"><span data-stu-id="99c13-120">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="99c13-121">Добавьте объявления пространств имен</span><span class="sxs-lookup"><span data-stu-id="99c13-121">Add namespace declarations</span></span>

<span data-ttu-id="99c13-122">Добавьте следующие `open` инструкции в начало `queues.fsx` файла:</span><span class="sxs-lookup"><span data-stu-id="99c13-122">Add the following `open` statements to the top of the `queues.fsx` file:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L1-L3)]

### <a name="get-your-connection-string"></a><span data-ttu-id="99c13-123">Получение строки подключения</span><span class="sxs-lookup"><span data-stu-id="99c13-123">Get your connection string</span></span>

<span data-ttu-id="99c13-124">Для этого учебника потребуется строку подключения хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="99c13-124">You'll need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="99c13-125">Дополнительные сведения о строках соединения см. в разделе [Настройка строки подключения хранилища](/azure/storage/storage-configure-connection-string).</span><span class="sxs-lookup"><span data-stu-id="99c13-125">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="99c13-126">Учебник вы введете строки подключения в скрипте, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="99c13-126">For the tutorial, you'll enter your connection string in your script, like this:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L9-L9)]

<span data-ttu-id="99c13-127">Однако это **не рекомендуется** для реальных проектах.</span><span class="sxs-lookup"><span data-stu-id="99c13-127">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="99c13-128">Ключ учетной записи хранилища аналогична корневой пароль для учетной записи хранилища.</span><span class="sxs-lookup"><span data-stu-id="99c13-128">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="99c13-129">Всегда будьте внимательны защитить ключ учетной записи хранилища.</span><span class="sxs-lookup"><span data-stu-id="99c13-129">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="99c13-130">Избегайте распространением их другим пользователям, жестко запрограммированные ее или сохранить в текстовый файл, доступный другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="99c13-130">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="99c13-131">Можно повторно создать ключ с помощью портала Azure, если вы считаете, что он был скомпрометирован.</span><span class="sxs-lookup"><span data-stu-id="99c13-131">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="99c13-132">Для реальных приложений для сохранения строки подключения хранилища рекомендуется в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="99c13-132">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="99c13-133">Чтобы получить строку подключения из файла конфигурации, это можно сделать:</span><span class="sxs-lookup"><span data-stu-id="99c13-133">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L11-L13)]

<span data-ttu-id="99c13-134">С помощью диспетчера конфигурации Azure является необязательным.</span><span class="sxs-lookup"><span data-stu-id="99c13-134">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="99c13-135">Можно также использовать интерфейс API, например .NET Framework `ConfigurationManager` типа.</span><span class="sxs-lookup"><span data-stu-id="99c13-135">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="99c13-136">Синтаксический анализ строки соединения</span><span class="sxs-lookup"><span data-stu-id="99c13-136">Parse the connection string</span></span>

<span data-ttu-id="99c13-137">Чтобы обработать строку подключения, используйте:</span><span class="sxs-lookup"><span data-stu-id="99c13-137">To parse the connection string, use:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L19-L20)]

<span data-ttu-id="99c13-138">Будет возвращен `CloudStorageAccount`.</span><span class="sxs-lookup"><span data-stu-id="99c13-138">This will return a `CloudStorageAccount`.</span></span>

### <a name="create-the-queue-service-client"></a><span data-ttu-id="99c13-139">Создание клиента службы очередей</span><span class="sxs-lookup"><span data-stu-id="99c13-139">Create the Queue service client</span></span>

<span data-ttu-id="99c13-140">`CloudQueueClient` Позволяет получить очереди, хранящиеся в очереди хранилища.</span><span class="sxs-lookup"><span data-stu-id="99c13-140">The `CloudQueueClient` class enables you to retrieve queues stored in Queue storage.</span></span> <span data-ttu-id="99c13-141">Вот один из способов создания клиента службы.</span><span class="sxs-lookup"><span data-stu-id="99c13-141">Here's one way to create the service client:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L26-L26)]

<span data-ttu-id="99c13-142">Теперь вы готовы написать код, который считывает и записывает данные в очереди хранилища.</span><span class="sxs-lookup"><span data-stu-id="99c13-142">Now you are ready to write code that reads data from and writes data to Queue storage.</span></span>

## <a name="create-a-queue"></a><span data-ttu-id="99c13-143">Создание очереди</span><span class="sxs-lookup"><span data-stu-id="99c13-143">Create a queue</span></span>

<span data-ttu-id="99c13-144">В этом примере показано, как создать очередь, если он еще не существует:</span><span class="sxs-lookup"><span data-stu-id="99c13-144">This example shows how to create a queue if it doesn't already exist:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L32-L36)]

## <a name="insert-a-message-into-a-queue"></a><span data-ttu-id="99c13-145">Вставлять сообщения в очереди</span><span class="sxs-lookup"><span data-stu-id="99c13-145">Insert a message into a queue</span></span>

<span data-ttu-id="99c13-146">Чтобы вставить сообщение в существующую очередь, сначала создайте `CloudQueueMessage`.</span><span class="sxs-lookup"><span data-stu-id="99c13-146">To insert a message into an existing queue, first create a new `CloudQueueMessage`.</span></span> <span data-ttu-id="99c13-147">Затем вызовите `AddMessage` метод.</span><span class="sxs-lookup"><span data-stu-id="99c13-147">Next, call the `AddMessage` method.</span></span> <span data-ttu-id="99c13-148">Объект `CloudQueueMessage` могут создаваться из любой строки (в формате UTF-8) или `byte` массива следующим образом:</span><span class="sxs-lookup"><span data-stu-id="99c13-148">A `CloudQueueMessage` can be created from either a string (in UTF-8 format) or a `byte` array, like this:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L42-L44)]

## <a name="peek-at-the-next-message"></a><span data-ttu-id="99c13-149">Просмотр следующего сообщения</span><span class="sxs-lookup"><span data-stu-id="99c13-149">Peek at the next message</span></span>

<span data-ttu-id="99c13-150">Можно считывать сообщения в начале очереди, не удаляя его из очереди, путем вызова `PeekMessage` метод.</span><span class="sxs-lookup"><span data-stu-id="99c13-150">You can peek at the message in the front of a queue, without removing it from the queue, by calling the `PeekMessage` method.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L50-L52)]

## <a name="get-the-next-message-for-processing"></a><span data-ttu-id="99c13-151">Получение следующего сообщения для обработки</span><span class="sxs-lookup"><span data-stu-id="99c13-151">Get the next message for processing</span></span>

<span data-ttu-id="99c13-152">Сообщения в начале очереди для обработки можно получить, вызвав `GetMessage` метод.</span><span class="sxs-lookup"><span data-stu-id="99c13-152">You can retrieve the message at the front of a queue for processing by calling the `GetMessage` method.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L58-L59)]

<span data-ttu-id="99c13-153">Позднее указать успешную обработку сообщения с помощью `DeleteMessage`.</span><span class="sxs-lookup"><span data-stu-id="99c13-153">You later indicate successful processing of the message by using `DeleteMessage`.</span></span>

## <a name="change-the-contents-of-a-queued-message"></a><span data-ttu-id="99c13-154">Изменение содержимого сообщения из очереди</span><span class="sxs-lookup"><span data-stu-id="99c13-154">Change the contents of a queued message</span></span>

<span data-ttu-id="99c13-155">Можно изменить содержимое получено сообщение на месте в очереди.</span><span class="sxs-lookup"><span data-stu-id="99c13-155">You can change the contents of a retrieved message in-place in the queue.</span></span> <span data-ttu-id="99c13-156">Если сообщение представляет рабочей задачи, можно использовать эту функцию для обновления состояния рабочих задач.</span><span class="sxs-lookup"><span data-stu-id="99c13-156">If the message represents a work task, you could use this feature to update the status of the work task.</span></span> <span data-ttu-id="99c13-157">Следующий код обновляет новое содержимое сообщения в очереди и задает время ожидания видимости для расширения другой 60 секунд.</span><span class="sxs-lookup"><span data-stu-id="99c13-157">The following code updates the queue message with new contents, and sets the visibility timeout to extend another 60 seconds.</span></span> <span data-ttu-id="99c13-158">Сохраняет состояние работ, сопряженные с сообщением и предоставляет клиенту другой минуту, чтобы продолжить работу с сообщения.</span><span class="sxs-lookup"><span data-stu-id="99c13-158">This saves the state of work associated with the message, and gives the client another minute to continue working on the message.</span></span> <span data-ttu-id="99c13-159">Этот метод можно использовать для отслеживания многоэтапной рабочих процессов в очередь сообщения, без необходимости начать заново с самого начала, при выполнении шага обработки происходит сбой из-за сбоя оборудования или программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="99c13-159">You could use this technique to track multi-step workflows on queue messages, without having to start over from the beginning if a processing step fails due to hardware or software failure.</span></span> <span data-ttu-id="99c13-160">Как правило будет хранить значение числа повторов и если сообщение будет предпринята повторная попытка больше, чем определенное число раз, следует удалить его.</span><span class="sxs-lookup"><span data-stu-id="99c13-160">Typically, you would keep a retry count as well, and if the message is retried more than some number of times, you would delete it.</span></span> <span data-ttu-id="99c13-161">Это обеспечивает защиту от сообщений, который срабатывает каждый раз, когда оно обрабатывается, происходит ошибка приложения.</span><span class="sxs-lookup"><span data-stu-id="99c13-161">This protects against a message that triggers an application error each time it is processed.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L65-L69)]

## <a name="de-queue-the-next-message"></a><span data-ttu-id="99c13-162">Отмена следующего сообщения в очередь</span><span class="sxs-lookup"><span data-stu-id="99c13-162">De-queue the next message</span></span>

<span data-ttu-id="99c13-163">Код исключении из очереди сообщения из очереди в два этапа.</span><span class="sxs-lookup"><span data-stu-id="99c13-163">Your code de-queues a message from a queue in two steps.</span></span> <span data-ttu-id="99c13-164">При вызове `GetMessage`, вы получаете следующее сообщение в очереди.</span><span class="sxs-lookup"><span data-stu-id="99c13-164">When you call `GetMessage`, you get the next message in a queue.</span></span> <span data-ttu-id="99c13-165">Сообщение, возвращенное из `GetMessage` становится невидимым для любого другого кода, чтение сообщений из этой очереди.</span><span class="sxs-lookup"><span data-stu-id="99c13-165">A message returned from `GetMessage` becomes invisible to any other code reading messages from this queue.</span></span> <span data-ttu-id="99c13-166">По умолчанию это сообщение будет невидимым в течение 30 секунд.</span><span class="sxs-lookup"><span data-stu-id="99c13-166">By default, this message stays invisible for 30 seconds.</span></span> <span data-ttu-id="99c13-167">Чтобы завершить удаление сообщения из очереди, необходимо вызвать `DeleteMessage`.</span><span class="sxs-lookup"><span data-stu-id="99c13-167">To finish removing the message from the queue, you must also call `DeleteMessage`.</span></span> <span data-ttu-id="99c13-168">Это двухэтапный процесс удаления сообщения подтверждает, что если код не может обработать сообщение из-за сбоя оборудования или программного обеспечения, другой экземпляр кода можно получить то же сообщение и повторите попытку.</span><span class="sxs-lookup"><span data-stu-id="99c13-168">This two-step process of removing a message assures that if your code fails to process a message due to hardware or software failure, another instance of your code can get the same message and try again.</span></span> <span data-ttu-id="99c13-169">Вызовы кода `DeleteMessage` сразу после обработки сообщения.</span><span class="sxs-lookup"><span data-stu-id="99c13-169">Your code calls `DeleteMessage` right after the message has been processed.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L75-L76)]

## <a name="use-async-workflows-with-common-queue-storage-apis"></a><span data-ttu-id="99c13-170">Использование асинхронных рабочих процессов с хранилищем общих очередей API-интерфейсы</span><span class="sxs-lookup"><span data-stu-id="99c13-170">Use Async workflows with common Queue storage APIs</span></span>

<span data-ttu-id="99c13-171">В этом примере показано, как использовать это асинхронный рабочий процесс с хранилищем общих очередей API-интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="99c13-171">This example shows how to use an async workflow with common Queue storage APIs.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L82-L91)]

## <a name="additional-options-for-de-queuing-messages"></a><span data-ttu-id="99c13-172">Дополнительные параметры для удаляется из очереди сообщений</span><span class="sxs-lookup"><span data-stu-id="99c13-172">Additional options for de-queuing messages</span></span>

<span data-ttu-id="99c13-173">Существует два способа, можно настроить получение сообщений из очереди.</span><span class="sxs-lookup"><span data-stu-id="99c13-173">There are two ways you can customize message retrieval from a queue.</span></span>
<span data-ttu-id="99c13-174">Во-первых можно получить пакет сообщений (не более 32).</span><span class="sxs-lookup"><span data-stu-id="99c13-174">First, you can get a batch of messages (up to 32).</span></span> <span data-ttu-id="99c13-175">Во-вторых можно установить более длинный или короткий невидимости тайм-аута, позволяя вашему коду больше или меньше времени для полной обработки каждого сообщения.</span><span class="sxs-lookup"><span data-stu-id="99c13-175">Second, you can set a longer or shorter invisibility timeout, allowing your code more or less time to fully process each message.</span></span> <span data-ttu-id="99c13-176">Следующий пример кода использует `GetMessages` для получения 20 сообщений в одном вызова и затем обрабатывает каждое сообщение.</span><span class="sxs-lookup"><span data-stu-id="99c13-176">The following code example uses `GetMessages` to get 20 messages in one call and then processes each message.</span></span> <span data-ttu-id="99c13-177">Также устанавливает время ожидания невидимости до пяти минут для каждого сообщения.</span><span class="sxs-lookup"><span data-stu-id="99c13-177">It also sets the invisibility timeout to five minutes for each message.</span></span> <span data-ttu-id="99c13-178">Обратите внимание, что начинается за 5 минут для всех сообщений, в то же время, переданный после имеют 5 минут после вызова `GetMessages`, все сообщения, которые не были удалены становятся видимыми.</span><span class="sxs-lookup"><span data-stu-id="99c13-178">Note that the 5 minutes starts for all messages at the same time, so after 5 minutes have passed since the call to `GetMessages`, any messages which have not been deleted will become visible again.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L97-L99)]

## <a name="get-the-queue-length"></a><span data-ttu-id="99c13-179">Получает длину очереди</span><span class="sxs-lookup"><span data-stu-id="99c13-179">Get the queue length</span></span>

<span data-ttu-id="99c13-180">Можно получить приблизительное количество сообщений в очереди.</span><span class="sxs-lookup"><span data-stu-id="99c13-180">You can get an estimate of the number of messages in a queue.</span></span> <span data-ttu-id="99c13-181">`FetchAttributes` Метод запрашивает у службы очередей для получения атрибутов очереди, включая количество сообщений.</span><span class="sxs-lookup"><span data-stu-id="99c13-181">The `FetchAttributes` method asks the Queue service to retrieve the queue attributes, including the message count.</span></span> <span data-ttu-id="99c13-182">`ApproximateMessageCount` Свойство возвращает последнее значение, полученное по `FetchAttributes` метод без вызова службы очередей.</span><span class="sxs-lookup"><span data-stu-id="99c13-182">The `ApproximateMessageCount` property returns the last value retrieved by the `FetchAttributes` method, without calling the Queue service.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L105-L106)]

## <a name="delete-a-queue"></a><span data-ttu-id="99c13-183">Удаление очереди</span><span class="sxs-lookup"><span data-stu-id="99c13-183">Delete a queue</span></span>

<span data-ttu-id="99c13-184">Чтобы удалить все содержащиеся в нем сообщения и очереди, вызовите `Delete` метод объекта очереди.</span><span class="sxs-lookup"><span data-stu-id="99c13-184">To delete a queue and all the messages contained in it, call the `Delete` method on the queue object.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L112-L113)]

## <a name="next-steps"></a><span data-ttu-id="99c13-185">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="99c13-185">Next steps</span></span>

<span data-ttu-id="99c13-186">Теперь, когда вы узнали основы очереди хранилища, перейдите по соответствующей ссылке для получения сведений о более сложных задач хранилища.</span><span class="sxs-lookup"><span data-stu-id="99c13-186">Now that you've learned the basics of Queue storage, follow these links to learn about more complex storage tasks.</span></span>

- [<span data-ttu-id="99c13-187">API-интерфейсов хранилища Azure для .NET</span><span class="sxs-lookup"><span data-stu-id="99c13-187">Azure Storage APIs for .NET</span></span>](/dotnet/api/overview/azure/storage)
- [<span data-ttu-id="99c13-188">Тип поставщика хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="99c13-188">Azure Storage Type Provider</span></span>](https://github.com/fsprojects/AzureStorageTypeProvider)
- [<span data-ttu-id="99c13-189">Блог группы разработчиков хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="99c13-189">Azure Storage Team Blog</span></span>](https://blogs.msdn.microsoft.com/windowsazurestorage/)
- [<span data-ttu-id="99c13-190">Настройка строки подключения хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="99c13-190">Configure Azure Storage connection strings</span></span>](/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="99c13-191">Справочник по API REST служб хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="99c13-191">Azure Storage Services REST API Reference</span></span>](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)
