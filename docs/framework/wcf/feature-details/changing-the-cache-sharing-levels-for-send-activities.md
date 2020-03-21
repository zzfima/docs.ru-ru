---
title: Изменение уровней совместного использования кэша для действий «Send»
ms.date: 03/30/2017
ms.assetid: 03926a64-753d-460e-ac06-2a4ff8e1bbf5
ms.openlocfilehash: 101aab98a7d34ad45ad29efbe252cff0814ca290
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185396"
---
# <a name="changing-the-cache-sharing-levels-for-send-activities"></a><span data-ttu-id="03c8b-102">Изменение уровней совместного использования кэша для действий «Send»</span><span class="sxs-lookup"><span data-stu-id="03c8b-102">Changing the Cache Sharing Levels for Send Activities</span></span>
<span data-ttu-id="03c8b-103">Расширение <xref:System.ServiceModel.Activities.SendMessageChannelCache> позволяет изменить уровни доступа к кэшу, настройки кэша фабрик каналов и настройки кэша канала для рабочих потоков, направляющих сообщения в конечные точки с использованием действий обмена сообщениями <xref:System.ServiceModel.Activities.Send>.</span><span class="sxs-lookup"><span data-stu-id="03c8b-103">The <xref:System.ServiceModel.Activities.SendMessageChannelCache> extension enables you to customize the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using <xref:System.ServiceModel.Activities.Send> messaging activities.</span></span> <span data-ttu-id="03c8b-104">Эти рабочие процессы обычно являются клиентскими, но также могут быть службами рабочих процессов, размещенными в <xref:System.ServiceModel.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="03c8b-104">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span> <span data-ttu-id="03c8b-105">Кэш фабрик каналов содержит кэшированные объекты <xref:System.ServiceModel.ChannelFactory%601>.</span><span class="sxs-lookup"><span data-stu-id="03c8b-105">The channel factory cache contains cached <xref:System.ServiceModel.ChannelFactory%601> objects.</span></span> <span data-ttu-id="03c8b-106">Кэш каналов содержит кэшированные каналы.</span><span class="sxs-lookup"><span data-stu-id="03c8b-106">The channel cache contains cached channels.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="03c8b-107">Рабочие процессы могут использовать действия обмена сообщениями <xref:System.ServiceModel.Activities.Send> для отправки сообщений либо параметров.</span><span class="sxs-lookup"><span data-stu-id="03c8b-107">Workflows can use <xref:System.ServiceModel.Activities.Send> messaging activities to send either messages or parameters.</span></span> <span data-ttu-id="03c8b-108">Среда выполнения рабочих процессов добавляет фабрики каналов, которые создают каналы типа <xref:System.ServiceModel.Channels.IRequestChannel> при использовании действия <xref:System.ServiceModel.Activities.ReceiveReply> вместе с действием <xref:System.ServiceModel.Activities.Send> и каналы типа <xref:System.ServiceModel.Channels.IOutputChannel> при использовании только действия <xref:System.ServiceModel.Activities.Send> (без команды <xref:System.ServiceModel.Activities.ReceiveReply>).</span><span class="sxs-lookup"><span data-stu-id="03c8b-108">The workflow runtime adds channel factories to the cache that create channels of type <xref:System.ServiceModel.Channels.IRequestChannel> when you use a <xref:System.ServiceModel.Activities.ReceiveReply> activity with a <xref:System.ServiceModel.Activities.Send> activity, and an <xref:System.ServiceModel.Channels.IOutputChannel> when just using a <xref:System.ServiceModel.Activities.Send> activity (no <xref:System.ServiceModel.Activities.ReceiveReply>).</span></span>  
  
## <a name="the-cache-sharing-levels"></a><span data-ttu-id="03c8b-109">Уровни совместного использования кэша</span><span class="sxs-lookup"><span data-stu-id="03c8b-109">The Cache Sharing Levels</span></span>  
 <span data-ttu-id="03c8b-110">По умолчанию в рабочем процессе, размещенном в <xref:System.ServiceModel.WorkflowServiceHost>, кэш, используемый действиями отправки сообщений <xref:System.ServiceModel.Activities.Send>, совместно используется всеми экземплярами рабочих потоков в <xref:System.ServiceModel.WorkflowServiceHost> (кэширование уровня узла).</span><span class="sxs-lookup"><span data-stu-id="03c8b-110">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost> the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="03c8b-111">Для клиентского рабочего процесса, не размещенного в <xref:System.ServiceModel.WorkflowServiceHost>, кэш доступен только для экземпляра рабочего процесса (кэширование уровня экземпляра).</span><span class="sxs-lookup"><span data-stu-id="03c8b-111">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="03c8b-112">Кэш доступен только для действий <xref:System.ServiceModel.Activities.Send>, не использующих конечные точки, определенные в конфигурации, если только не включено небезопасное кэширование.</span><span class="sxs-lookup"><span data-stu-id="03c8b-112">The cache is only available for <xref:System.ServiceModel.Activities.Send> activities that do not use endpoints defined in configuration unless unsafe caching is enabled.</span></span>  
  
 <span data-ttu-id="03c8b-113">Ниже приводятся различные уровни совместного использования кэширования, доступные для действий <xref:System.ServiceModel.Activities.Send> в рабочем процессе, и рекомендации по их использованию.</span><span class="sxs-lookup"><span data-stu-id="03c8b-113">The following are the different cache sharing levels available for <xref:System.ServiceModel.Activities.Send> activities in a workflow and their recommended use:</span></span>  
  
- <span data-ttu-id="03c8b-114">**Уровень хоста**: В уровне хоста кэш доступен только для экземпляров рабочего процесса, размещенных в узлах службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="03c8b-114">**Host Level**: In the host sharing level, the cache is available only to the workflow instances hosted in the workflow service host.</span></span> <span data-ttu-id="03c8b-115">Кэш может также совместно использоваться узлами служб рабочих процессов в кэше всего процесса.</span><span class="sxs-lookup"><span data-stu-id="03c8b-115">A cache can also be shared between workflow service hosts in a process-wide cache.</span></span>  
  
- <span data-ttu-id="03c8b-116">**Уровень экземпляра**: В уровне совместного использования экземпляров кэш доступен для определенного экземпляра рабочего процесса на протяжении всего срока службы, но кэш недоступен для других экземпляров рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="03c8b-116">**Instance Level**: In the instance sharing level, the cache is available to a particular workflow instance throughout its lifetime but the cache is not available to other workflow instances.</span></span>  
  
- <span data-ttu-id="03c8b-117">**Нет кэша**: Кэш выключен по умолчанию, если у вас есть рабочий процесс, который использует конечные точки, определенные в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="03c8b-117">**No Cache**: The cache is turned off by default if you have a workflow that uses endpoints defined in configuration.</span></span> <span data-ttu-id="03c8b-118">В этом случае также рекомендуется отключить кэширование, поскольку его использование может быть небезопасным.</span><span class="sxs-lookup"><span data-stu-id="03c8b-118">It is also recommended to keep the cache turned off in this case because turning it on could be unsecure.</span></span> <span data-ttu-id="03c8b-119">Например, если для каждой операции отправки требуется отдельный идентификатор (другие учетные данные или олицетворение).</span><span class="sxs-lookup"><span data-stu-id="03c8b-119">For example, if a different identity (different credentials or using impersonation) is required for each send.</span></span>  
  
## <a name="changing-the-cache-sharing-level-for-a-client-workflow"></a><span data-ttu-id="03c8b-120">Изменение уровня совместного использования кэша для клиентского рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="03c8b-120">Changing the Cache Sharing Level for a Client Workflow</span></span>  
 <span data-ttu-id="03c8b-121">Чтобы задать совместное использование кэша в клиентском рабочем процессе, добавьте экземпляр класса <xref:System.ServiceModel.Activities.SendMessageChannelCache> в качестве расширения к требуемому набору экземпляров рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="03c8b-121">To set the cache sharing in a client workflow, add an instance of the <xref:System.ServiceModel.Activities.SendMessageChannelCache> class as an extension to the desired set of workflow instances.</span></span> <span data-ttu-id="03c8b-122">Это приведет к совместному использованию кэша всеми экземплярами рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="03c8b-122">This results in sharing the cache across all the workflow instances.</span></span> <span data-ttu-id="03c8b-123">В следующих примерах кода показано выполнение этих шагов.</span><span class="sxs-lookup"><span data-stu-id="03c8b-123">The following code examples show how to perform these steps.</span></span>  
  
 <span data-ttu-id="03c8b-124">Сначала объявите экземпляр типа <xref:System.ServiceModel.Activities.SendMessageChannelCache>.</span><span class="sxs-lookup"><span data-stu-id="03c8b-124">First, declare an instance of type <xref:System.ServiceModel.Activities.SendMessageChannelCache>.</span></span>  
  
```csharp  
// Create an instance of SendMessageChannelCache with default cache settings.  
static SendMessageChannelCache sharedChannelCacheExtension =  
    new SendMessageChannelCache();  
```  
  
 <span data-ttu-id="03c8b-125">Затем добавьте расширение кэша каждому экземпляру клиентского рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="03c8b-125">Next, add the cache extension to each client workflow instance.</span></span>  
  
```csharp
WorkflowApplication clientInstance1 = new WorkflowApplication(new clientWorkflow1());  
WorkflowApplication clientInstance2 = new WorkflowApplication(new clientWorkflow2());  
  
// Share the cache extension object
  
clientInstance1.Extensions.Add(sharedChannelCacheExtension);  
clientInstance2.Extensions.Add(sharedChannelCacheExtension);  
```  
  
## <a name="changing-the-cache-sharing-level-for-a-hosted-workflow-service"></a><span data-ttu-id="03c8b-126">Изменение уровня совместного использования кэша для размещенной службы рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="03c8b-126">Changing the Cache Sharing Level for a Hosted Workflow Service</span></span>  
 <span data-ttu-id="03c8b-127">Чтобы задать совместное использование кэша в размещенной службе рабочего процесса, добавьте экземпляр класса <xref:System.ServiceModel.Activities.SendMessageChannelCache> в качестве модуля всем узлам служб рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="03c8b-127">To set the cache sharing in a hosted workflow service, add an instance of the <xref:System.ServiceModel.Activities.SendMessageChannelCache> class as an extension to all the workflow service hosts.</span></span> <span data-ttu-id="03c8b-128">Это приведет к совместному использованию кэша всеми узлами служб рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="03c8b-128">This results in sharing the cache across all the workflow service hosts.</span></span> <span data-ttu-id="03c8b-129">В следующих примерах кода показано выполнение этих шагов.</span><span class="sxs-lookup"><span data-stu-id="03c8b-129">The following code examples show to perform these steps.</span></span>  
  
 <span data-ttu-id="03c8b-130">Сначала объявите экземпляр типа <xref:System.ServiceModel.Activities.SendMessageChannelCache> на уровне класса.</span><span class="sxs-lookup"><span data-stu-id="03c8b-130">First, declare an instance  of type <xref:System.ServiceModel.Activities.SendMessageChannelCache> at the class level.</span></span>  
  
```csharp  
// Create static instance of SendMessageChannelCache with default cache settings.  
static SendMessageChannelCache sharedChannelCacheExtension = new  
    SendMessageChannelCache();  
```  
  
 <span data-ttu-id="03c8b-131">Затем добавьте статическое расширение кэша каждому узлу службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="03c8b-131">Next, add the static cache extension to each workflow service host.</span></span>  
  
```csharp  
WorkflowServiceHost host1 = new WorkflowServiceHost(new serviceWorkflow1(), new Uri(baseAddress1));  
WorkflowServiceHost host2 = new WorkflowServiceHost(new serviceWorkflow2(), new Uri(baseAddress2));  
  
// Share the static cache to get an AppDomain level cache.  
host1.WorkflowExtensions.Add(sharedChannelCacheExtension);  
host2.WorkflowExtensions.Add(sharedChannelCacheExtension);  
```  
  
 <span data-ttu-id="03c8b-132">Чтобы перевести совместное использование кэша в размещенной службе рабочего процесса до уровня экземпляра, добавьте делегат `Func<SendMessageChannelCache>` в качестве расширения в узел службы рабочего процесса и присвойте его коду, который создаст новый экземпляр класса <xref:System.ServiceModel.Activities.SendMessageChannelCache>.</span><span class="sxs-lookup"><span data-stu-id="03c8b-132">To set the cache sharing in a hosted workflow service to the instance level, add a `Func<SendMessageChannelCache>` delegate as an extension to the workflow service host and assign this delegate to the code that instantiates a new instance of the <xref:System.ServiceModel.Activities.SendMessageChannelCache> class.</span></span> <span data-ttu-id="03c8b-133">Это приведет к использованию разного кэша для каждого отдельно взятого экземпляра рабочего процесса вместо одного кэша для всех экземпляров рабочих процессов на узле службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="03c8b-133">This results in a different cache for each individual workflow instance, instead of a single cache shared by all workflow instances in the workflow service host.</span></span> <span data-ttu-id="03c8b-134">В следующем примере кода показано выполнение этой операции при помощи лямбда-выражения с целью прямого определения модуля <xref:System.ServiceModel.Activities.SendMessageChannelCache>, на который указывает делегат.</span><span class="sxs-lookup"><span data-stu-id="03c8b-134">The following code example shows how to achieve this by using a lambda expression to directly define the <xref:System.ServiceModel.Activities.SendMessageChannelCache> extension that the delegate points to.</span></span>  
  
```csharp
serviceHost.WorkflowExtensions.Add(() => new SendMessageChannelCache  
{  
    // Use FactorySettings property to add custom factory cache settings.  
    FactorySettings = new ChannelCacheSettings
    { MaxItemsInCache = 5, },  
    // Use ChannelSettings property to add custom channel cache settings.  
    ChannelSettings = new ChannelCacheSettings
    { MaxItemsInCache = 10 },  
});  
```  
  
## <a name="customizing-cache-settings"></a><span data-ttu-id="03c8b-135">Настройка параметров кэша</span><span class="sxs-lookup"><span data-stu-id="03c8b-135">Customizing Cache Settings</span></span>  
 <span data-ttu-id="03c8b-136">Параметры кэша можно настраивать для кэша фабрик каналов и кэша каналов.</span><span class="sxs-lookup"><span data-stu-id="03c8b-136">You can customize the cache settings for the channel factory cache and the channel cache.</span></span> <span data-ttu-id="03c8b-137">Параметры кэша определяются в классе <xref:System.ServiceModel.Activities.ChannelCacheSettings>.</span><span class="sxs-lookup"><span data-stu-id="03c8b-137">The cache settings are defined in the <xref:System.ServiceModel.Activities.ChannelCacheSettings> class.</span></span> <span data-ttu-id="03c8b-138">Класс <xref:System.ServiceModel.Activities.SendMessageChannelCache> определяет параметры кэша по умолчанию для кэша фабрики канала и кэша канала в его беспараметрыном конструкторе.</span><span class="sxs-lookup"><span data-stu-id="03c8b-138">The <xref:System.ServiceModel.Activities.SendMessageChannelCache> class defines default cache settings for the channel factory cache and the channel cache in its parameterless constructor.</span></span> <span data-ttu-id="03c8b-139">Далее приведена таблица, в которой перечислены значения по умолчанию для этих параметров кэша по каждому типу кэша.</span><span class="sxs-lookup"><span data-stu-id="03c8b-139">The following table lists the default values of these cache settings for each type of cache.</span></span>  
  
|<span data-ttu-id="03c8b-140">Настройки</span><span class="sxs-lookup"><span data-stu-id="03c8b-140">Settings</span></span>|<span data-ttu-id="03c8b-141">LeaseTimeout (мин.)</span><span class="sxs-lookup"><span data-stu-id="03c8b-141">LeaseTimeout (min)</span></span>|<span data-ttu-id="03c8b-142">IdleTimeout (мин.)</span><span class="sxs-lookup"><span data-stu-id="03c8b-142">IdleTimeout (min)</span></span>|<span data-ttu-id="03c8b-143">MaxItemsInCache</span><span class="sxs-lookup"><span data-stu-id="03c8b-143">MaxItemsInCache</span></span>|  
|-|-|-|-|  
|<span data-ttu-id="03c8b-144">Кэш фабрики по умолчанию</span><span class="sxs-lookup"><span data-stu-id="03c8b-144">Factory Cache Default</span></span>|<span data-ttu-id="03c8b-145">TimeSpan.MaxValue</span><span class="sxs-lookup"><span data-stu-id="03c8b-145">TimeSpan.MaxValue</span></span>|<span data-ttu-id="03c8b-146">2</span><span class="sxs-lookup"><span data-stu-id="03c8b-146">2</span></span>|<span data-ttu-id="03c8b-147">16</span><span class="sxs-lookup"><span data-stu-id="03c8b-147">16</span></span>|  
|<span data-ttu-id="03c8b-148">Кэш канала по умолчанию</span><span class="sxs-lookup"><span data-stu-id="03c8b-148">Channel Cache Default</span></span>|<span data-ttu-id="03c8b-149">5</span><span class="sxs-lookup"><span data-stu-id="03c8b-149">5</span></span>|<span data-ttu-id="03c8b-150">2</span><span class="sxs-lookup"><span data-stu-id="03c8b-150">2</span></span>|<span data-ttu-id="03c8b-151">16</span><span class="sxs-lookup"><span data-stu-id="03c8b-151">16</span></span>|  
  
 <span data-ttu-id="03c8b-152">Для изменения параметров кэша фабрик и кэша каналов создайте экземпляр класса <xref:System.ServiceModel.Activities.SendMessageChannelCache> при помощи параметризованного конструктора <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A> и передайте новый экземпляр <xref:System.ServiceModel.Activities.ChannelCacheSettings> с пользовательскими значениями каждому из параметров `factorySettings` и `channelSettings`.</span><span class="sxs-lookup"><span data-stu-id="03c8b-152">To customize the factory cache and channel cache settings, instantiate the <xref:System.ServiceModel.Activities.SendMessageChannelCache> class using the parameterized constructor <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A> and pass a new instance of the <xref:System.ServiceModel.Activities.ChannelCacheSettings> with custom values to each of the `factorySettings` and `channelSettings` parameters.</span></span> <span data-ttu-id="03c8b-153">Далее добавьте новый экземпляр этого класса как расширение для узла службы рабочего процесса или экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="03c8b-153">Next, add the new instance of this class as an extension to a workflow service host or a workflow instance.</span></span> <span data-ttu-id="03c8b-154">В следующем примере кода показано выполнение этих шагов для экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="03c8b-154">The following code example shows how to perform these steps for a workflow instance.</span></span>  
  
```csharp  
ChannelCacheSettings factorySettings = new ChannelCacheSettings{  
                        MaxItemsInCache = 5,
                        IdleTimeout = TimeSpan.FromMinutes(5),
                        LeaseTimeout = TimeSpan.FromMinutes(20)};  
  
ChannelCacheSettings channelSettings = new ChannelCacheSettings{  
                        MaxItemsInCache = 5,
                        IdleTimeout = TimeSpan.FromMinutes(2),  
                        LeaseTimeout = TimeSpan.FromMinutes(10) };  
  
SendMessageChannelCache customChannelCacheExtension =
    new SendMessageChannelCache(factorySettings, channelSettings);  
  
clientInstance.Extensions.Add(customChannelCacheExtension);  
```  
  
 <span data-ttu-id="03c8b-155">Чтобы включить кэширование, если у службы рабочего процесса имеются конечные точки, определенные в конфигурации, создайте экземпляр класса <xref:System.ServiceModel.Activities.SendMessageChannelCache>, используя параметризованный конструктор <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A>, и задайте параметру `allowUnsafeCaching` значение `true`.</span><span class="sxs-lookup"><span data-stu-id="03c8b-155">To enable caching when your workflow service has endpoints defined in configuration, instantiate the <xref:System.ServiceModel.Activities.SendMessageChannelCache> class using the parameterized constructor <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A> with the `allowUnsafeCaching` parameter set to `true`.</span></span> <span data-ttu-id="03c8b-156">Далее добавьте новый экземпляр этого класса как расширение для узла службы рабочего процесса или экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="03c8b-156">Next, add the new instance of this class as an extension to a workflow service host or a workflow instance.</span></span> <span data-ttu-id="03c8b-157">В следующем примере кода показано включение кэширования для экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="03c8b-157">The following code example shows how to enable caching for a workflow instance.</span></span>  
  
```csharp  
SendMessageChannelCache customChannelCacheExtension =
    new SendMessageChannelCache{ AllowUnsafeCaching = true };  
  
clientInstance.Extensions.Add(customChannelCacheExtension);  
```  
  
 <span data-ttu-id="03c8b-158">Чтобы отключить кэш полностью для фабрик каналов и каналов, отключите кэш фабрик каналов.</span><span class="sxs-lookup"><span data-stu-id="03c8b-158">To disable the cache completely for the channel factories and the channels, disable the channel factory cache.</span></span> <span data-ttu-id="03c8b-159">При этом также будет отключен кэш каналов, поскольку каналы принадлежат соответствующим фабрикам каналов.</span><span class="sxs-lookup"><span data-stu-id="03c8b-159">Doing so also turns off the channel cache as the channels are owned by their corresponding channel factories.</span></span> <span data-ttu-id="03c8b-160">Чтобы отключить кэш фабрик каналов, передайте параметр `factorySettings` конструктору <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A>, инициализированному для экземпляра <xref:System.ServiceModel.Activities.ChannelCacheSettings>, со значением <xref:System.ServiceModel.Activities.ChannelCacheSettings.MaxItemsInCache%2A>, установленным в 0.</span><span class="sxs-lookup"><span data-stu-id="03c8b-160">To disable the channel factory cache, pass the `factorySettings` parameter to the <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A> constructor initialized to a <xref:System.ServiceModel.Activities.ChannelCacheSettings> instance with a <xref:System.ServiceModel.Activities.ChannelCacheSettings.MaxItemsInCache%2A> value of 0.</span></span> <span data-ttu-id="03c8b-161">Это показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="03c8b-161">The following code example shows this.</span></span>  
  
```csharp  
// Disable the factory cache. This results in the channel cache to be turned off as well.  
ChannelCacheSettings factorySettings = new ChannelCacheSettings  
    { MaxItemsInCache = 0 };  
  
ChannelCacheSettings channelSettings = new ChannelCacheSettings();  
  
SendMessageChannelCache customChannelCacheExtension =
    new SendMessageChannelCache(factorySettings, channelSettings);
  
clientInstance.Extensions.Add(customChannelCacheExtension);  
```  
  
 <span data-ttu-id="03c8b-162">Можно использовать кэш фабрик каналов и отключить кэш каналов, передав параметр `channelSettings` конструктору <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A>, инициализированному для экземпляра <xref:System.ServiceModel.Activities.ChannelCacheSettings>, со значением <xref:System.ServiceModel.Activities.ChannelCacheSettings.MaxItemsInCache%2A>, установленным в 0.</span><span class="sxs-lookup"><span data-stu-id="03c8b-162">You can choose to use only the channel factory cache and disable the channel cache by passing the `channelSettings` parameter to the <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A> constructor initialized to a <xref:System.ServiceModel.Activities.ChannelCacheSettings> instance with a <xref:System.ServiceModel.Activities.ChannelCacheSettings.MaxItemsInCache%2A> value of 0.</span></span> <span data-ttu-id="03c8b-163">Это показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="03c8b-163">The following code example shows this.</span></span>  
  
```csharp  
ChannelCacheSettings factorySettings = new ChannelCacheSettings();  
// Disable only the channel cache.  
ChannelCacheSettings channelSettings = new ChannelCacheSettings  
    { MaxItemsInCache = 0};  
  
SendMessageChannelCache customChannelCacheExtension =
    new SendMessageChannelCache(factorySettings, channelSettings);
  
clientInstance.Extensions.Add(customChannelCacheExtension);  
```  
  
 <span data-ttu-id="03c8b-164">В размещенной службе рабочего процесса в файле конфигурации приложения можно указать параметры кэша фабрики и канала.</span><span class="sxs-lookup"><span data-stu-id="03c8b-164">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="03c8b-165">Для этого необходимо создать поведение службы, содержащее параметры для кэша фабрики и канала, и добавить это поведение в службу.</span><span class="sxs-lookup"><span data-stu-id="03c8b-165">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="03c8b-166">В следующем примере отображается содержимое `MyChannelCacheBehavior` файла конфигурации, содержащего поведение службы с настройками кэша назакази и кэша каналов.</span><span class="sxs-lookup"><span data-stu-id="03c8b-166">The following example shows the contents of a configuration file that contains the `MyChannelCacheBehavior` service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="03c8b-167">Это поведение службы добавляется `behaviorConfiguration` в службу через атрибут.</span><span class="sxs-lookup"><span data-stu-id="03c8b-167">This service behavior is added to the service through the `behaviorConfiguration` attribute.</span></span>  
  
```xml  
<configuration>
  <system.serviceModel>  
    <!-- List of other config sections here -->
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="MyChannelCacheBehavior">  
          <sendMessageChannelCache allowUnsafeCaching ="false" >  
            <!-- Control only the host level settings -->
            <factorySettings maxItemsInCache = "8" idleTimeout = "00:05:00" leaseTimeout="10:00:00" />  
            <channelSettings maxItemsInCache = "32" idleTimeout = "00:05:00" leaseTimeout="00:06:00" />  
          </sendMessageChannelCache>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service name="MyService" behaviorConfiguration="MyChannelCacheBehavior" />  
    </services>  
  </system.serviceModel>  
</configuration>  
```
