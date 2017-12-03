---
title: "Производство каналов и кэширование"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 954f030e-091c-4c0e-a7a2-10f9a6b1f529
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1b06d290760afa9a52274c30899e25f00bc18af2
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="channel-factory-and-caching"></a><span data-ttu-id="ad083-102">Производство каналов и кэширование</span><span class="sxs-lookup"><span data-stu-id="ad083-102">Channel Factory and Caching</span></span>
<span data-ttu-id="ad083-103">Клиентские приложения WCF используют класс <xref:System.ServiceModel.ChannelFactory%601> для создания коммуникационного канала со службой WCF.</span><span class="sxs-lookup"><span data-stu-id="ad083-103">WCF client applications use the <xref:System.ServiceModel.ChannelFactory%601> class to create a communication channel with a WCF service.</span></span>  <span data-ttu-id="ad083-104">Создание экземпляров класса <xref:System.ServiceModel.ChannelFactory%601> оказывает определенное влияние на производительность, поскольку выполняются следующие операции:</span><span class="sxs-lookup"><span data-stu-id="ad083-104">Creating <xref:System.ServiceModel.ChannelFactory%601> instances incurs some overhead because it involves the following operations:</span></span>  
  
-   <span data-ttu-id="ad083-105">Построение дерева <xref:System.ServiceModel.Description.ContractDescription></span><span class="sxs-lookup"><span data-stu-id="ad083-105">Constructing the <xref:System.ServiceModel.Description.ContractDescription> tree</span></span>  
  
-   <span data-ttu-id="ad083-106">Отображение всех необходимых типов CLR</span><span class="sxs-lookup"><span data-stu-id="ad083-106">Reflecting all of the required CLR types</span></span>  
  
-   <span data-ttu-id="ad083-107">Построение стека каналов</span><span class="sxs-lookup"><span data-stu-id="ad083-107">Constructing the channel stack</span></span>  
  
-   <span data-ttu-id="ad083-108">Освобождение ресурсов</span><span class="sxs-lookup"><span data-stu-id="ad083-108">Disposing of resources</span></span>  
  
 <span data-ttu-id="ad083-109">Чтобы уменьшить дополнительные расходы ресурсов, WCF может кэшировать фабрики каналов при использовании прокси клиента WCF.</span><span class="sxs-lookup"><span data-stu-id="ad083-109">To help minimize this overhead, WCF can cache channel factories when you are using a WCF client proxy.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="ad083-110">Вы непосредственно управляете созданием фабрики каналов, когда класс <xref:System.ServiceModel.ChannelFactory%601> используется напрямую.</span><span class="sxs-lookup"><span data-stu-id="ad083-110">You have direct control over channel factory creation when you use the <xref:System.ServiceModel.ChannelFactory%601> class directly.</span></span>  
  
 <span data-ttu-id="ad083-111">Прокси клиента WCF с [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) являются производными от <xref:System.ServiceModel.ClientBase%601>.</span><span class="sxs-lookup"><span data-stu-id="ad083-111">WCF client proxies generated with [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) are derived from <xref:System.ServiceModel.ClientBase%601>.</span></span> <span data-ttu-id="ad083-112"><xref:System.ServiceModel.ClientBase%601> определяет статическое свойство <xref:System.ServiceModel.ClientBase%601.CacheSetting%2A>, которое определяет режим кэширования фабрики каналов.</span><span class="sxs-lookup"><span data-stu-id="ad083-112"><xref:System.ServiceModel.ClientBase%601> defines a static <xref:System.ServiceModel.ClientBase%601.CacheSetting%2A> property that defines channel factory caching behavior.</span></span> <span data-ttu-id="ad083-113">Параметры кэша задаются для определенного типа.</span><span class="sxs-lookup"><span data-stu-id="ad083-113">Cache settings are made for a specific type.</span></span> <span data-ttu-id="ad083-114">Например, установка `ClientBase<ITest>.CacheSettings` одно из значений, указанных ниже повлияет только эти прокси-сервера или ClientBase типа `ITest`.</span><span class="sxs-lookup"><span data-stu-id="ad083-114">For example, setting  `ClientBase<ITest>.CacheSettings` to one of the values defined below will affect only those proxy/ClientBase of type `ITest`.</span></span> <span data-ttu-id="ad083-115">Параметры кэша для конкретного <xref:System.ServiceModel.ClientBase%601> являются неизменяемыми после создания первого экземпляра класса-посредника или ClientBase.</span><span class="sxs-lookup"><span data-stu-id="ad083-115">The cache setting for a particular <xref:System.ServiceModel.ClientBase%601> is immutable as soon as the first proxy/ClientBase instance is created.</span></span>  
  
## <a name="specifying-caching-behavior"></a><span data-ttu-id="ad083-116">Установка режима кэширования</span><span class="sxs-lookup"><span data-stu-id="ad083-116">Specifying Caching Behavior</span></span>  
 <span data-ttu-id="ad083-117">Режим кэширования задается установкой свойства <xref:System.ServiceModel.ClientBase%601.CacheSetting> в одно из следующих значений.</span><span class="sxs-lookup"><span data-stu-id="ad083-117">Caching behavior is specified by setting the <xref:System.ServiceModel.ClientBase%601.CacheSetting> property to one of the following values.</span></span>  
  
|<span data-ttu-id="ad083-118">Значение параметра кэша</span><span class="sxs-lookup"><span data-stu-id="ad083-118">Cache Setting Value</span></span>|<span data-ttu-id="ad083-119">Описание</span><span class="sxs-lookup"><span data-stu-id="ad083-119">Description</span></span>|  
|-------------------------|-----------------|  
|<xref:System.ServiceModel.CacheSetting.AlwaysOn>|<span data-ttu-id="ad083-120">Все экземпляры <xref:System.ServiceModel.ClientBase%601> в пределах домена приложения могут участвовать в кэшировании.</span><span class="sxs-lookup"><span data-stu-id="ad083-120">All instances of <xref:System.ServiceModel.ClientBase%601> within the app-domain can participate in caching.</span></span> <span data-ttu-id="ad083-121">Разработчик определил, что при кэшировании не будет неблагоприятных последствий для безопасности.</span><span class="sxs-lookup"><span data-stu-id="ad083-121">The developer has determined that there are no adverse security implications to caching.</span></span> <span data-ttu-id="ad083-122">Кэширование не отключается даже в том случае, если «секретным» свойств <xref:System.ServiceModel.ClientBase%601> осуществляется.</span><span class="sxs-lookup"><span data-stu-id="ad083-122">Caching will not be turned off even if "security-sensitive" properties on <xref:System.ServiceModel.ClientBase%601> are accessed.</span></span> <span data-ttu-id="ad083-123">Свойства «секретным» <xref:System.ServiceModel.ClientBase%601> , <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>, <xref:System.ServiceModel.ClientBase%601.Endpoint%2A> и <xref:System.ServiceModel.ClientBase%601.ChannelFactory%2A>.</span><span class="sxs-lookup"><span data-stu-id="ad083-123">The "security-sensitive" properties of <xref:System.ServiceModel.ClientBase%601> are <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>, <xref:System.ServiceModel.ClientBase%601.Endpoint%2A> and <xref:System.ServiceModel.ClientBase%601.ChannelFactory%2A>.</span></span>|  
|<xref:System.ServiceModel.CacheSetting.Default>|<span data-ttu-id="ad083-124">Только экземпляры <xref:System.ServiceModel.ClientBase%601>, созданные на основе конечных точек, определенных в файлах конфигурации, участвуют в кэшировании внутри домена приложения.</span><span class="sxs-lookup"><span data-stu-id="ad083-124">Only instances of <xref:System.ServiceModel.ClientBase%601> created from endpoints defined in configuration files participate in caching within the app-domain.</span></span> <span data-ttu-id="ad083-125">Ни один экземпляр <xref:System.ServiceModel.ClientBase%601>, созданный программно внутри домена приложения, не будет участвовать в кэшировании.</span><span class="sxs-lookup"><span data-stu-id="ad083-125">Any instances of <xref:System.ServiceModel.ClientBase%601> created programmatically within that app-domain will not participate in caching.</span></span> <span data-ttu-id="ad083-126">Кроме того, кэширование будет отключено для экземпляра <xref:System.ServiceModel.ClientBase%601> после любого из его свойств «секретным» осуществляется.</span><span class="sxs-lookup"><span data-stu-id="ad083-126">Also, caching will be disabled for an instance of <xref:System.ServiceModel.ClientBase%601> once any of its "security-sensitive" properties is accessed.</span></span>|  
|<xref:System.ServiceModel.CacheSetting.AlwaysOff>|<span data-ttu-id="ad083-127">Кэширование отключается для всех экземпляров <xref:System.ServiceModel.ClientBase%601> определенного типа в пределах домена приложений.</span><span class="sxs-lookup"><span data-stu-id="ad083-127">Caching is turned off for all instances of <xref:System.ServiceModel.ClientBase%601> of a particular type within the app-domain in question.</span></span>|  
  
 <span data-ttu-id="ad083-128">Следующие фрагменты кода показывают использование свойства <xref:System.ServiceModel.ClientBase%601.CacheSetting%2A>.</span><span class="sxs-lookup"><span data-stu-id="ad083-128">The following code snippets illustrate how to use the <xref:System.ServiceModel.ClientBase%601.CacheSetting%2A> property.</span></span>  
  
```  
class Program   
{   
   static void Main(string[] args)   
   {   
      ClientBase<ITest>.CacheSettings = CacheSettings.AlwaysOn;   
      foreach (string msg in messages)   
      {   
         using (TestClient proxy = new TestClient (new BasicHttpBinding(), new EndpointAddress(address)))   
         {   
            // ...  
            proxy.Test(msg);   
            // ...  
         }   
      }   
   }   
}  
// Generated by SvcUtil.exe     
public partial class TestClient : System.ServiceModel.ClientBase, ITest { }  
```  
  
 <span data-ttu-id="ad083-129">В приведенном выше коде все экземпляры `TestClient` будут использовать одну и ту же фабрику каналов.</span><span class="sxs-lookup"><span data-stu-id="ad083-129">In the above code, all instances of `TestClient` will use the same channel factory.</span></span>  
  
```  
class Program   
{   
   static void Main(string[] args)   
   {   
      ClientBase.CacheSettings = CacheSettings.Default;   
      int i = 1;   
      foreach (string msg in messages)   
      {   
         using (TestClient proxy = new TestClient ("MyEndpoint", new EndpointAddress(address)))   
         {   
            if (i == 4)   
            {   
               ServiceEndpoint endpoint = proxy.Endpoint;   
               ... // use endpoint in some way   
            }   
            proxy.Test(msg);   
         }   
         i++;   
   }   
}   
  
// Generated by SvcUtil.exe     
public partial class TestClient : System.ServiceModel.ClientBase, ITest {}  
```  
  
 <span data-ttu-id="ad083-130">В приведенном выше примере все экземпляры `TestClient` будут использовать одну и ту же фабрику каналов, за исключением экземпляра № 4.</span><span class="sxs-lookup"><span data-stu-id="ad083-130">In the example above, all instances of `TestClient` would use the same channel factory except instance #4.</span></span> <span data-ttu-id="ad083-131">Экземпляр № 4 будет использовать фабрику каналов, созданную специально для этой цели.</span><span class="sxs-lookup"><span data-stu-id="ad083-131">Instance #4 would use a channel factory that is created specifically for its use.</span></span> <span data-ttu-id="ad083-132">Этот параметр не работает в сценариях, где определенной конечной точке необходимы различные параметры безопасности из других конечных точек того же типа фабрики каналов (в данном случае `ITest`).</span><span class="sxs-lookup"><span data-stu-id="ad083-132">This setting would work for scenarios where a particular endpoint needs different security settings from the other endpoints of the same channel factory type (in this case `ITest`).</span></span>  
  
```  
class Program   
{   
   static void Main(string[] args)   
   {   
      ClientBase.CacheSettings = CacheSettings.AlwaysOff;   
      foreach (string msg in messages)   
      {   
         using (TestClient proxy = new TestClient ("MyEndpoint", new EndpointAddress(address)))   
         {   
            proxy.Test(msg);   
         }           
      }   
   }  
}  
  
// Generated by SvcUtil.exe   
public partial class TestClient : System.ServiceModel.ClientBase, ITest {}  
```  
  
 <span data-ttu-id="ad083-133">В приведенном выше примере все экземпляры `TestClient` будут использовать различные фабрики каналов.</span><span class="sxs-lookup"><span data-stu-id="ad083-133">In the example above, all instances of `TestClient` would use different channel factories.</span></span> <span data-ttu-id="ad083-134">Это полезно в случае, если каждая конечная точка имеет различные требования к безопасности и нет смысла выполнять кэширование.</span><span class="sxs-lookup"><span data-stu-id="ad083-134">This is useful when each endpoint has different security requirements and it makes no sense to cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad083-135">См. также</span><span class="sxs-lookup"><span data-stu-id="ad083-135">See Also</span></span>  
 <xref:System.ServiceModel.ClientBase%601>  
 [<span data-ttu-id="ad083-136">Создание клиентов</span><span class="sxs-lookup"><span data-stu-id="ad083-136">Building Clients</span></span>](../../../../docs/framework/wcf/building-clients.md)  
 [<span data-ttu-id="ad083-137">Клиенты</span><span class="sxs-lookup"><span data-stu-id="ad083-137">Clients</span></span>](../../../../docs/framework/wcf/feature-details/clients.md)  
 [<span data-ttu-id="ad083-138">Обращение к службам с помощью клиента WCF</span><span class="sxs-lookup"><span data-stu-id="ad083-138">Accessing Services Using a WCF Client</span></span>](../../../../docs/framework/wcf/accessing-services-using-a-wcf-client.md)  
 [<span data-ttu-id="ad083-139">Как: использование ChannelFactory</span><span class="sxs-lookup"><span data-stu-id="ad083-139">How to: Use the ChannelFactory</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-channelfactory.md)
