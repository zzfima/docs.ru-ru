---
title: Начало работы с хранилищем очередей Azure с использованиемF#
description: Очереди Azure обеспечивают надежный асинхронный обмен сообщениями между компонентами приложения. Облачные системы обмена сообщениями позволяет независимо масштабировать компоненты приложения.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: 58a46dfe905a32be77a13d11df8f0544546ea0ed
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756381"
---
# <a name="get-started-with-azure-queue-storage-using-f"></a><span data-ttu-id="aeda5-104">Начало работы с хранилищем очередей Azure с помощью F\#</span><span class="sxs-lookup"><span data-stu-id="aeda5-104">Get started with Azure Queue storage using F\#</span></span>

<span data-ttu-id="aeda5-105">Хранилище очередей Azure обеспечивает обмен сообщениями между компонентами приложения в облаке.</span><span class="sxs-lookup"><span data-stu-id="aeda5-105">Azure Queue storage provides cloud messaging between application components.</span></span> <span data-ttu-id="aeda5-106">При разработке приложений для масштабирования, компоненты приложения часто не связаны, так что они могут масштабироваться независимо друг от друга.</span><span class="sxs-lookup"><span data-stu-id="aeda5-106">In designing applications for scale, application components are often decoupled, so that they can scale independently.</span></span> <span data-ttu-id="aeda5-107">Хранилище очередей обеспечивает асинхронный обмен сообщениями для взаимодействия между компонентами приложения, ли они выполняются в облаке, на рабочем столе, на локальном сервере или на мобильном устройстве.</span><span class="sxs-lookup"><span data-stu-id="aeda5-107">Queue storage delivers asynchronous messaging for communication between application components, whether they are running in the cloud, on the desktop, on an on-premises server, or on a mobile device.</span></span> <span data-ttu-id="aeda5-108">Хранилище очередей также поддерживает управление асинхронными задачами и создание рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="aeda5-108">Queue storage also supports managing asynchronous tasks and building process work flows.</span></span>

### <a name="about-this-tutorial"></a><span data-ttu-id="aeda5-109">Сведения об этом руководстве</span><span class="sxs-lookup"><span data-stu-id="aeda5-109">About this tutorial</span></span>

<span data-ttu-id="aeda5-110">Этот учебник демонстрирует запись F# код для некоторых типичных задач, с помощью хранилища очередей Azure.</span><span class="sxs-lookup"><span data-stu-id="aeda5-110">This tutorial shows how to write F# code for some common tasks using Azure Queue storage.</span></span> <span data-ttu-id="aeda5-111">Рассмотренные задачи включают создание и удаление очередей и добавление, чтение и удаление сообщений очереди.</span><span class="sxs-lookup"><span data-stu-id="aeda5-111">Tasks covered include creating and deleting queues and adding, reading, and deleting queue messages.</span></span>

<span data-ttu-id="aeda5-112">Общие сведения о хранилище очередей, см. в разделе [руководство по .NET для хранилища очередей](/azure/storage/storage-dotnet-how-to-use-queues).</span><span class="sxs-lookup"><span data-stu-id="aeda5-112">For a conceptual overview of queue storage, please see [the .NET guide for queue storage](/azure/storage/storage-dotnet-how-to-use-queues).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="aeda5-113">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="aeda5-113">Prerequisites</span></span>

<span data-ttu-id="aeda5-114">Чтобы использовать это руководство, необходимо сначала [создать учетную запись хранения](/azure/storage/storage-create-storage-account).</span><span class="sxs-lookup"><span data-stu-id="aeda5-114">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span>
<span data-ttu-id="aeda5-115">Вам также потребуется ключ доступа к хранилищу для этой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="aeda5-115">You'll also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="aeda5-116">Создание F# сценариев и запустить F# интерактивный</span><span class="sxs-lookup"><span data-stu-id="aeda5-116">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="aeda5-117">Примеры в этой статье можно использовать в любом F# приложения или F# скрипта.</span><span class="sxs-lookup"><span data-stu-id="aeda5-117">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="aeda5-118">Чтобы создать F# скрипт, создайте файл с `.fsx` расширение, например `queues.fsx`в вашей F# среды разработки.</span><span class="sxs-lookup"><span data-stu-id="aeda5-118">To create an F# script, create a file with the `.fsx` extension, for example `queues.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="aeda5-119">Затем используйте [диспетчера пакетов](package-management.md) например [Paket](https://fsprojects.github.io/Paket/) или [NuGet](https://www.nuget.org/) для установки `WindowsAzure.Storage` пакета и ссылка `WindowsAzure.Storage.dll` в скрипте, с помощью `#r`директива.</span><span class="sxs-lookup"><span data-stu-id="aeda5-119">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="aeda5-120">Добавьте объявления пространств имен</span><span class="sxs-lookup"><span data-stu-id="aeda5-120">Add namespace declarations</span></span>

<span data-ttu-id="aeda5-121">Добавьте следующий `open` операторы в верхнюю часть `queues.fsx` файла:</span><span class="sxs-lookup"><span data-stu-id="aeda5-121">Add the following `open` statements to the top of the `queues.fsx` file:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L1-L3)]

### <a name="get-your-connection-string"></a><span data-ttu-id="aeda5-122">Получить строку подключения</span><span class="sxs-lookup"><span data-stu-id="aeda5-122">Get your connection string</span></span>

<span data-ttu-id="aeda5-123">В этом руководстве вам потребуется строки подключения к службе хранилища Azure.</span><span class="sxs-lookup"><span data-stu-id="aeda5-123">You'll need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="aeda5-124">Дополнительные сведения о строках подключения см. в разделе [Настройка строк подключения службы хранилища](/azure/storage/storage-configure-connection-string).</span><span class="sxs-lookup"><span data-stu-id="aeda5-124">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="aeda5-125">Для этого руководства вы введете строку подключения в скрипте, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="aeda5-125">For the tutorial, you'll enter your connection string in your script, like this:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L9-L9)]

<span data-ttu-id="aeda5-126">Однако это **не рекомендуется** реальных проектов.</span><span class="sxs-lookup"><span data-stu-id="aeda5-126">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="aeda5-127">Ключ учетной записи хранения похож на корневой пароль для учетной записи хранения.</span><span class="sxs-lookup"><span data-stu-id="aeda5-127">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="aeda5-128">Не забудьте защитить ключ учетной записи хранения.</span><span class="sxs-lookup"><span data-stu-id="aeda5-128">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="aeda5-129">Избегайте распределения его другим пользователям, в коде, или сохранить его в текстовом файле, доступном другим пользователям.</span><span class="sxs-lookup"><span data-stu-id="aeda5-129">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="aeda5-130">Можно повторно создать ключ с помощью портала Azure, если вы считаете, что он мог быть скомпрометирован.</span><span class="sxs-lookup"><span data-stu-id="aeda5-130">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="aeda5-131">Для реальных приложений, чтобы сохранить строку подключения хранилища рекомендуется в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="aeda5-131">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="aeda5-132">Чтобы получить строку подключения из файла конфигурации, это можно сделать:</span><span class="sxs-lookup"><span data-stu-id="aeda5-132">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L11-L13)]

<span data-ttu-id="aeda5-133">Использование диспетчера конфигураций Azure не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="aeda5-133">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="aeda5-134">Можно также использовать API, например .NET Framework `ConfigurationManager` типа.</span><span class="sxs-lookup"><span data-stu-id="aeda5-134">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="aeda5-135">Проанализировать строку подключения</span><span class="sxs-lookup"><span data-stu-id="aeda5-135">Parse the connection string</span></span>

<span data-ttu-id="aeda5-136">Чтобы проанализировать строку подключения, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="aeda5-136">To parse the connection string, use:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L19-L20)]

<span data-ttu-id="aeda5-137">Эта команда возвращает `CloudStorageAccount`.</span><span class="sxs-lookup"><span data-stu-id="aeda5-137">This will return a `CloudStorageAccount`.</span></span>

### <a name="create-the-queue-service-client"></a><span data-ttu-id="aeda5-138">Создание клиента службы очередей</span><span class="sxs-lookup"><span data-stu-id="aeda5-138">Create the Queue service client</span></span>

<span data-ttu-id="aeda5-139">`CloudQueueClient` Класс позволяет получать очереди, хранящиеся в хранилище очередей.</span><span class="sxs-lookup"><span data-stu-id="aeda5-139">The `CloudQueueClient` class enables you to retrieve queues stored in Queue storage.</span></span> <span data-ttu-id="aeda5-140">Вот один из способов создания клиента службы:</span><span class="sxs-lookup"><span data-stu-id="aeda5-140">Here's one way to create the service client:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L26-L26)]

<span data-ttu-id="aeda5-141">Теперь вы готовы написать код, который считывает и записывает данные в хранилище очередей.</span><span class="sxs-lookup"><span data-stu-id="aeda5-141">Now you are ready to write code that reads data from and writes data to Queue storage.</span></span>

## <a name="create-a-queue"></a><span data-ttu-id="aeda5-142">Создание очереди</span><span class="sxs-lookup"><span data-stu-id="aeda5-142">Create a queue</span></span>

<span data-ttu-id="aeda5-143">В этом примере показано, как создать очередь, если он еще не существует:</span><span class="sxs-lookup"><span data-stu-id="aeda5-143">This example shows how to create a queue if it doesn't already exist:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L32-L36)]

## <a name="insert-a-message-into-a-queue"></a><span data-ttu-id="aeda5-144">Вставка сообщения в очереди</span><span class="sxs-lookup"><span data-stu-id="aeda5-144">Insert a message into a queue</span></span>

<span data-ttu-id="aeda5-145">Чтобы вставить сообщение в существующую очередь, сначала создайте `CloudQueueMessage`.</span><span class="sxs-lookup"><span data-stu-id="aeda5-145">To insert a message into an existing queue, first create a new `CloudQueueMessage`.</span></span> <span data-ttu-id="aeda5-146">Затем вызовите `AddMessage` метод.</span><span class="sxs-lookup"><span data-stu-id="aeda5-146">Next, call the `AddMessage` method.</span></span> <span data-ttu-id="aeda5-147">Объект `CloudQueueMessage` может быть создан из строки (в формате UTF-8) или `byte` массиве, вот так:</span><span class="sxs-lookup"><span data-stu-id="aeda5-147">A `CloudQueueMessage` can be created from either a string (in UTF-8 format) or a `byte` array, like this:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L42-L44)]

## <a name="peek-at-the-next-message"></a><span data-ttu-id="aeda5-148">Просмотр следующего сообщения</span><span class="sxs-lookup"><span data-stu-id="aeda5-148">Peek at the next message</span></span>

<span data-ttu-id="aeda5-149">Вы можете просмотреть сообщение в начале очереди, не удаляя его из очереди, вызвав `PeekMessage` метод.</span><span class="sxs-lookup"><span data-stu-id="aeda5-149">You can peek at the message in the front of a queue, without removing it from the queue, by calling the `PeekMessage` method.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L50-L52)]

## <a name="get-the-next-message-for-processing"></a><span data-ttu-id="aeda5-150">Получить следующее сообщение для обработки</span><span class="sxs-lookup"><span data-stu-id="aeda5-150">Get the next message for processing</span></span>

<span data-ttu-id="aeda5-151">Сообщение в начале очереди для обработки можно получить, вызвав `GetMessage` метод.</span><span class="sxs-lookup"><span data-stu-id="aeda5-151">You can retrieve the message at the front of a queue for processing by calling the `GetMessage` method.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L58-L59)]

<span data-ttu-id="aeda5-152">Позже вы указать успешную обработку сообщения с помощью `DeleteMessage`.</span><span class="sxs-lookup"><span data-stu-id="aeda5-152">You later indicate successful processing of the message by using `DeleteMessage`.</span></span>

## <a name="change-the-contents-of-a-queued-message"></a><span data-ttu-id="aeda5-153">Изменение содержимого сообщения в очереди</span><span class="sxs-lookup"><span data-stu-id="aeda5-153">Change the contents of a queued message</span></span>

<span data-ttu-id="aeda5-154">Можно изменить содержимое полученного сообщения непосредственно в очереди.</span><span class="sxs-lookup"><span data-stu-id="aeda5-154">You can change the contents of a retrieved message in-place in the queue.</span></span> <span data-ttu-id="aeda5-155">Если сообщение представляет собой рабочую задачу, можно использовать эту функцию для обновления состояния рабочей задачи.</span><span class="sxs-lookup"><span data-stu-id="aeda5-155">If the message represents a work task, you could use this feature to update the status of the work task.</span></span> <span data-ttu-id="aeda5-156">Следующий код добавляет новое содержимое сообщения очереди и задает время ожидания видимости, чтобы расширить еще на 60 секунд.</span><span class="sxs-lookup"><span data-stu-id="aeda5-156">The following code updates the queue message with new contents, and sets the visibility timeout to extend another 60 seconds.</span></span> <span data-ttu-id="aeda5-157">Это сохраняет состояние работы, связанной с сообщением и дает еще одной минуты, чтобы продолжить работу с сообщения клиенту.</span><span class="sxs-lookup"><span data-stu-id="aeda5-157">This saves the state of work associated with the message, and gives the client another minute to continue working on the message.</span></span> <span data-ttu-id="aeda5-158">Этот метод можно использовать для отслеживания многошаговых рабочих процессов по сообщениям в очереди, без необходимости начинать с самого начала, если происходит сбой на этапе обработки из-за сбоя оборудования или программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="aeda5-158">You could use this technique to track multi-step workflows on queue messages, without having to start over from the beginning if a processing step fails due to hardware or software failure.</span></span> <span data-ttu-id="aeda5-159">Обычно также сохраняется также числом повторов, и если сообщения превысит больше, чем определенное число раз, нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="aeda5-159">Typically, you would keep a retry count as well, and if the message is retried more than some number of times, you would delete it.</span></span> <span data-ttu-id="aeda5-160">Это обеспечивает защиту от сообщений, которые инициируют ошибку приложения каждый раз при его обработке.</span><span class="sxs-lookup"><span data-stu-id="aeda5-160">This protects against a message that triggers an application error each time it is processed.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L65-L69)]

## <a name="de-queue-the-next-message"></a><span data-ttu-id="aeda5-161">Удаление следующего сообщения из очереди</span><span class="sxs-lookup"><span data-stu-id="aeda5-161">De-queue the next message</span></span>

<span data-ttu-id="aeda5-162">Код исключении из очереди сообщения из очереди в два этапа.</span><span class="sxs-lookup"><span data-stu-id="aeda5-162">Your code de-queues a message from a queue in two steps.</span></span> <span data-ttu-id="aeda5-163">При вызове `GetMessage`, вы получаете следующее сообщение в очереди.</span><span class="sxs-lookup"><span data-stu-id="aeda5-163">When you call `GetMessage`, you get the next message in a queue.</span></span> <span data-ttu-id="aeda5-164">Сообщение, возвращаемое методом `GetMessage` становится невидимым для другого кода, считывающего сообщения из этой очереди.</span><span class="sxs-lookup"><span data-stu-id="aeda5-164">A message returned from `GetMessage` becomes invisible to any other code reading messages from this queue.</span></span> <span data-ttu-id="aeda5-165">По умолчанию это сообщение остается невидимым в течение 30 секунд.</span><span class="sxs-lookup"><span data-stu-id="aeda5-165">By default, this message stays invisible for 30 seconds.</span></span> <span data-ttu-id="aeda5-166">Чтобы завершить удаление сообщения из очереди, необходимо также вызвать `DeleteMessage`.</span><span class="sxs-lookup"><span data-stu-id="aeda5-166">To finish removing the message from the queue, you must also call `DeleteMessage`.</span></span> <span data-ttu-id="aeda5-167">Этот двухэтапный процесс удаления сообщения позволяет удостовериться, что если коду не удастся обработать сообщение из-за сбоя оборудования или программного обеспечения, другой экземпляр кода можно получить то же сообщение и повторить попытку.</span><span class="sxs-lookup"><span data-stu-id="aeda5-167">This two-step process of removing a message assures that if your code fails to process a message due to hardware or software failure, another instance of your code can get the same message and try again.</span></span> <span data-ttu-id="aeda5-168">Код вызывает метод `DeleteMessage` сразу после обработки сообщения.</span><span class="sxs-lookup"><span data-stu-id="aeda5-168">Your code calls `DeleteMessage` right after the message has been processed.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L75-L76)]

## <a name="use-async-workflows-with-common-queue-storage-apis"></a><span data-ttu-id="aeda5-169">Использование асинхронных рабочих процессов со стандартными интерфейсами API хранилища очередей</span><span class="sxs-lookup"><span data-stu-id="aeda5-169">Use Async workflows with common Queue storage APIs</span></span>

<span data-ttu-id="aeda5-170">В этом примере показано, как использовать поток async со стандартными интерфейсами API хранилища очередей.</span><span class="sxs-lookup"><span data-stu-id="aeda5-170">This example shows how to use an async workflow with common Queue storage APIs.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L82-L91)]

## <a name="additional-options-for-de-queuing-messages"></a><span data-ttu-id="aeda5-171">Дополнительные параметры для удаления сообщений из очереди</span><span class="sxs-lookup"><span data-stu-id="aeda5-171">Additional options for de-queuing messages</span></span>

<span data-ttu-id="aeda5-172">Существует два способа настройки извлечения сообщения из очереди.</span><span class="sxs-lookup"><span data-stu-id="aeda5-172">There are two ways you can customize message retrieval from a queue.</span></span>
<span data-ttu-id="aeda5-173">Во-первых можно получить пакет сообщений (до 32).</span><span class="sxs-lookup"><span data-stu-id="aeda5-173">First, you can get a batch of messages (up to 32).</span></span> <span data-ttu-id="aeda5-174">Во-вторых можно задать время ожидания невидимости длинный или короткий, предоставить коду больше или меньше времени на полную обработку каждого сообщения.</span><span class="sxs-lookup"><span data-stu-id="aeda5-174">Second, you can set a longer or shorter invisibility timeout, allowing your code more or less time to fully process each message.</span></span> <span data-ttu-id="aeda5-175">В следующем примере кода используется `GetMessages` для получения 20 сообщений в один вызов и затем обрабатывает каждое сообщение.</span><span class="sxs-lookup"><span data-stu-id="aeda5-175">The following code example uses `GetMessages` to get 20 messages in one call and then processes each message.</span></span> <span data-ttu-id="aeda5-176">Он также задает время ожидания невидимости пять минут для каждого сообщения.</span><span class="sxs-lookup"><span data-stu-id="aeda5-176">It also sets the invisibility timeout to five minutes for each message.</span></span> <span data-ttu-id="aeda5-177">Обратите внимание, что начинается для всех сообщений, в то же время, поэтому 5 минут по прошествии с момента вызова `GetMessages`, все сообщения, которые не были удалены становятся видимыми.</span><span class="sxs-lookup"><span data-stu-id="aeda5-177">Note that the 5 minutes starts for all messages at the same time, so after 5 minutes have passed since the call to `GetMessages`, any messages which have not been deleted will become visible again.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L97-L99)]

## <a name="get-the-queue-length"></a><span data-ttu-id="aeda5-178">Получение длины очереди</span><span class="sxs-lookup"><span data-stu-id="aeda5-178">Get the queue length</span></span>

<span data-ttu-id="aeda5-179">Можно получить приблизительное количество сообщений в очереди.</span><span class="sxs-lookup"><span data-stu-id="aeda5-179">You can get an estimate of the number of messages in a queue.</span></span> <span data-ttu-id="aeda5-180">`FetchAttributes` Метод запрашивает у службы очередей на извлечение атрибутов очереди, включая количество сообщений.</span><span class="sxs-lookup"><span data-stu-id="aeda5-180">The `FetchAttributes` method asks the Queue service to retrieve the queue attributes, including the message count.</span></span> <span data-ttu-id="aeda5-181">`ApproximateMessageCount` Свойство возвращает последнее значение, полученное путем `FetchAttributes` метод без обращения к службе очередей.</span><span class="sxs-lookup"><span data-stu-id="aeda5-181">The `ApproximateMessageCount` property returns the last value retrieved by the `FetchAttributes` method, without calling the Queue service.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L105-L106)]

## <a name="delete-a-queue"></a><span data-ttu-id="aeda5-182">Удаление очереди</span><span class="sxs-lookup"><span data-stu-id="aeda5-182">Delete a queue</span></span>

<span data-ttu-id="aeda5-183">Чтобы удалить очередь и все сообщения, содержащиеся в ней, вызовите `Delete` метода для объекта очереди.</span><span class="sxs-lookup"><span data-stu-id="aeda5-183">To delete a queue and all the messages contained in it, call the `Delete` method on the queue object.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L112-L113)]

## <a name="next-steps"></a><span data-ttu-id="aeda5-184">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="aeda5-184">Next steps</span></span>

<span data-ttu-id="aeda5-185">Теперь, когда ознакомились с основными понятиями хранилища очередей, по следующим ссылкам, чтобы узнать о более сложных задачах хранилища.</span><span class="sxs-lookup"><span data-stu-id="aeda5-185">Now that you've learned the basics of Queue storage, follow these links to learn about more complex storage tasks.</span></span>

- [<span data-ttu-id="aeda5-186">API службы хранилища Azure для .NET</span><span class="sxs-lookup"><span data-stu-id="aeda5-186">Azure Storage APIs for .NET</span></span>](/dotnet/api/overview/azure/storage)
- [<span data-ttu-id="aeda5-187">Тип поставщика хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="aeda5-187">Azure Storage Type Provider</span></span>](https://github.com/fsprojects/AzureStorageTypeProvider)
- [<span data-ttu-id="aeda5-188">Блог группы разработчиков хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="aeda5-188">Azure Storage Team Blog</span></span>](https://blogs.msdn.microsoft.com/windowsazurestorage/)
- [<span data-ttu-id="aeda5-189">Настройка строк подключения службы хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="aeda5-189">Configure Azure Storage connection strings</span></span>](/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="aeda5-190">Справочник по API REST служб хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="aeda5-190">Azure Storage Services REST API Reference</span></span>](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)
