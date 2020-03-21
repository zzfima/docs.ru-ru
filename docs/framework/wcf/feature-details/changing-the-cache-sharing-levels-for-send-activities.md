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
# <a name="changing-the-cache-sharing-levels-for-send-activities"></a>Изменение уровней совместного использования кэша для действий «Send»
Расширение <xref:System.ServiceModel.Activities.SendMessageChannelCache> позволяет изменить уровни доступа к кэшу, настройки кэша фабрик каналов и настройки кэша канала для рабочих потоков, направляющих сообщения в конечные точки с использованием действий обмена сообщениями <xref:System.ServiceModel.Activities.Send>. Эти рабочие процессы обычно являются клиентскими, но также могут быть службами рабочих процессов, размещенными в <xref:System.ServiceModel.WorkflowServiceHost>. Кэш фабрик каналов содержит кэшированные объекты <xref:System.ServiceModel.ChannelFactory%601>. Кэш каналов содержит кэшированные каналы.  
  
> [!NOTE]
> Рабочие процессы могут использовать действия обмена сообщениями <xref:System.ServiceModel.Activities.Send> для отправки сообщений либо параметров. Среда выполнения рабочих процессов добавляет фабрики каналов, которые создают каналы типа <xref:System.ServiceModel.Channels.IRequestChannel> при использовании действия <xref:System.ServiceModel.Activities.ReceiveReply> вместе с действием <xref:System.ServiceModel.Activities.Send> и каналы типа <xref:System.ServiceModel.Channels.IOutputChannel> при использовании только действия <xref:System.ServiceModel.Activities.Send> (без команды <xref:System.ServiceModel.Activities.ReceiveReply>).  
  
## <a name="the-cache-sharing-levels"></a>Уровни совместного использования кэша  
 По умолчанию в рабочем процессе, размещенном в <xref:System.ServiceModel.WorkflowServiceHost>, кэш, используемый действиями отправки сообщений <xref:System.ServiceModel.Activities.Send>, совместно используется всеми экземплярами рабочих потоков в <xref:System.ServiceModel.WorkflowServiceHost> (кэширование уровня узла). Для клиентского рабочего процесса, не размещенного в <xref:System.ServiceModel.WorkflowServiceHost>, кэш доступен только для экземпляра рабочего процесса (кэширование уровня экземпляра). Кэш доступен только для действий <xref:System.ServiceModel.Activities.Send>, не использующих конечные точки, определенные в конфигурации, если только не включено небезопасное кэширование.  
  
 Ниже приводятся различные уровни совместного использования кэширования, доступные для действий <xref:System.ServiceModel.Activities.Send> в рабочем процессе, и рекомендации по их использованию.  
  
- **Уровень хоста**: В уровне хоста кэш доступен только для экземпляров рабочего процесса, размещенных в узлах службы рабочего процесса. Кэш может также совместно использоваться узлами служб рабочих процессов в кэше всего процесса.  
  
- **Уровень экземпляра**: В уровне совместного использования экземпляров кэш доступен для определенного экземпляра рабочего процесса на протяжении всего срока службы, но кэш недоступен для других экземпляров рабочего процесса.  
  
- **Нет кэша**: Кэш выключен по умолчанию, если у вас есть рабочий процесс, который использует конечные точки, определенные в конфигурации. В этом случае также рекомендуется отключить кэширование, поскольку его использование может быть небезопасным. Например, если для каждой операции отправки требуется отдельный идентификатор (другие учетные данные или олицетворение).  
  
## <a name="changing-the-cache-sharing-level-for-a-client-workflow"></a>Изменение уровня совместного использования кэша для клиентского рабочего процесса  
 Чтобы задать совместное использование кэша в клиентском рабочем процессе, добавьте экземпляр класса <xref:System.ServiceModel.Activities.SendMessageChannelCache> в качестве расширения к требуемому набору экземпляров рабочих процессов. Это приведет к совместному использованию кэша всеми экземплярами рабочих процессов. В следующих примерах кода показано выполнение этих шагов.  
  
 Сначала объявите экземпляр типа <xref:System.ServiceModel.Activities.SendMessageChannelCache>.  
  
```csharp  
// Create an instance of SendMessageChannelCache with default cache settings.  
static SendMessageChannelCache sharedChannelCacheExtension =  
    new SendMessageChannelCache();  
```  
  
 Затем добавьте расширение кэша каждому экземпляру клиентского рабочего процесса.  
  
```csharp
WorkflowApplication clientInstance1 = new WorkflowApplication(new clientWorkflow1());  
WorkflowApplication clientInstance2 = new WorkflowApplication(new clientWorkflow2());  
  
// Share the cache extension object
  
clientInstance1.Extensions.Add(sharedChannelCacheExtension);  
clientInstance2.Extensions.Add(sharedChannelCacheExtension);  
```  
  
## <a name="changing-the-cache-sharing-level-for-a-hosted-workflow-service"></a>Изменение уровня совместного использования кэша для размещенной службы рабочего процесса  
 Чтобы задать совместное использование кэша в размещенной службе рабочего процесса, добавьте экземпляр класса <xref:System.ServiceModel.Activities.SendMessageChannelCache> в качестве модуля всем узлам служб рабочих процессов. Это приведет к совместному использованию кэша всеми узлами служб рабочих процессов. В следующих примерах кода показано выполнение этих шагов.  
  
 Сначала объявите экземпляр типа <xref:System.ServiceModel.Activities.SendMessageChannelCache> на уровне класса.  
  
```csharp  
// Create static instance of SendMessageChannelCache with default cache settings.  
static SendMessageChannelCache sharedChannelCacheExtension = new  
    SendMessageChannelCache();  
```  
  
 Затем добавьте статическое расширение кэша каждому узлу службы рабочего процесса.  
  
```csharp  
WorkflowServiceHost host1 = new WorkflowServiceHost(new serviceWorkflow1(), new Uri(baseAddress1));  
WorkflowServiceHost host2 = new WorkflowServiceHost(new serviceWorkflow2(), new Uri(baseAddress2));  
  
// Share the static cache to get an AppDomain level cache.  
host1.WorkflowExtensions.Add(sharedChannelCacheExtension);  
host2.WorkflowExtensions.Add(sharedChannelCacheExtension);  
```  
  
 Чтобы перевести совместное использование кэша в размещенной службе рабочего процесса до уровня экземпляра, добавьте делегат `Func<SendMessageChannelCache>` в качестве расширения в узел службы рабочего процесса и присвойте его коду, который создаст новый экземпляр класса <xref:System.ServiceModel.Activities.SendMessageChannelCache>. Это приведет к использованию разного кэша для каждого отдельно взятого экземпляра рабочего процесса вместо одного кэша для всех экземпляров рабочих процессов на узле службы рабочего процесса. В следующем примере кода показано выполнение этой операции при помощи лямбда-выражения с целью прямого определения модуля <xref:System.ServiceModel.Activities.SendMessageChannelCache>, на который указывает делегат.  
  
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
  
## <a name="customizing-cache-settings"></a>Настройка параметров кэша  
 Параметры кэша можно настраивать для кэша фабрик каналов и кэша каналов. Параметры кэша определяются в классе <xref:System.ServiceModel.Activities.ChannelCacheSettings>. Класс <xref:System.ServiceModel.Activities.SendMessageChannelCache> определяет параметры кэша по умолчанию для кэша фабрики канала и кэша канала в его беспараметрыном конструкторе. Далее приведена таблица, в которой перечислены значения по умолчанию для этих параметров кэша по каждому типу кэша.  
  
|Настройки|LeaseTimeout (мин.)|IdleTimeout (мин.)|MaxItemsInCache|  
|-|-|-|-|  
|Кэш фабрики по умолчанию|TimeSpan.MaxValue|2|16|  
|Кэш канала по умолчанию|5|2|16|  
  
 Для изменения параметров кэша фабрик и кэша каналов создайте экземпляр класса <xref:System.ServiceModel.Activities.SendMessageChannelCache> при помощи параметризованного конструктора <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A> и передайте новый экземпляр <xref:System.ServiceModel.Activities.ChannelCacheSettings> с пользовательскими значениями каждому из параметров `factorySettings` и `channelSettings`. Далее добавьте новый экземпляр этого класса как расширение для узла службы рабочего процесса или экземпляра рабочего процесса. В следующем примере кода показано выполнение этих шагов для экземпляра рабочего процесса.  
  
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
  
 Чтобы включить кэширование, если у службы рабочего процесса имеются конечные точки, определенные в конфигурации, создайте экземпляр класса <xref:System.ServiceModel.Activities.SendMessageChannelCache>, используя параметризованный конструктор <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A>, и задайте параметру `allowUnsafeCaching` значение `true`. Далее добавьте новый экземпляр этого класса как расширение для узла службы рабочего процесса или экземпляра рабочего процесса. В следующем примере кода показано включение кэширования для экземпляра рабочего процесса.  
  
```csharp  
SendMessageChannelCache customChannelCacheExtension =
    new SendMessageChannelCache{ AllowUnsafeCaching = true };  
  
clientInstance.Extensions.Add(customChannelCacheExtension);  
```  
  
 Чтобы отключить кэш полностью для фабрик каналов и каналов, отключите кэш фабрик каналов. При этом также будет отключен кэш каналов, поскольку каналы принадлежат соответствующим фабрикам каналов. Чтобы отключить кэш фабрик каналов, передайте параметр `factorySettings` конструктору <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A>, инициализированному для экземпляра <xref:System.ServiceModel.Activities.ChannelCacheSettings>, со значением <xref:System.ServiceModel.Activities.ChannelCacheSettings.MaxItemsInCache%2A>, установленным в 0. Это показано в следующем примере кода.  
  
```csharp  
// Disable the factory cache. This results in the channel cache to be turned off as well.  
ChannelCacheSettings factorySettings = new ChannelCacheSettings  
    { MaxItemsInCache = 0 };  
  
ChannelCacheSettings channelSettings = new ChannelCacheSettings();  
  
SendMessageChannelCache customChannelCacheExtension =
    new SendMessageChannelCache(factorySettings, channelSettings);
  
clientInstance.Extensions.Add(customChannelCacheExtension);  
```  
  
 Можно использовать кэш фабрик каналов и отключить кэш каналов, передав параметр `channelSettings` конструктору <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A>, инициализированному для экземпляра <xref:System.ServiceModel.Activities.ChannelCacheSettings>, со значением <xref:System.ServiceModel.Activities.ChannelCacheSettings.MaxItemsInCache%2A>, установленным в 0. Это показано в следующем примере кода.  
  
```csharp  
ChannelCacheSettings factorySettings = new ChannelCacheSettings();  
// Disable only the channel cache.  
ChannelCacheSettings channelSettings = new ChannelCacheSettings  
    { MaxItemsInCache = 0};  
  
SendMessageChannelCache customChannelCacheExtension =
    new SendMessageChannelCache(factorySettings, channelSettings);
  
clientInstance.Extensions.Add(customChannelCacheExtension);  
```  
  
 В размещенной службе рабочего процесса в файле конфигурации приложения можно указать параметры кэша фабрики и канала. Для этого необходимо создать поведение службы, содержащее параметры для кэша фабрики и канала, и добавить это поведение в службу. В следующем примере отображается содержимое `MyChannelCacheBehavior` файла конфигурации, содержащего поведение службы с настройками кэша назакази и кэша каналов. Это поведение службы добавляется `behaviorConfiguration` в службу через атрибут.  
  
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
