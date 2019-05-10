---
title: Инициализация создания экземпляров
ms.date: 03/30/2017
ms.assetid: 154d049f-2140-4696-b494-c7e53f6775ef
ms.openlocfilehash: e5dd48ce53fc45e9a970ff5b123860f057fb5759
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648329"
---
# <a name="instancing-initialization"></a><span data-ttu-id="5f7f7-102">Инициализация создания экземпляров</span><span class="sxs-lookup"><span data-stu-id="5f7f7-102">Instancing Initialization</span></span>
<span data-ttu-id="5f7f7-103">Этот пример расширяет [Pooling](../../../../docs/framework/wcf/samples/pooling.md) образец путем определения интерфейса, `IObjectControl`, который изменяет процесс инициализации объекта путем активации или деактивации.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-103">This sample extends the [Pooling](../../../../docs/framework/wcf/samples/pooling.md) sample by defining an interface, `IObjectControl`, which customizes the initialization of an object by activating and deactivating it.</span></span> <span data-ttu-id="5f7f7-104">Клиент вызывает методы, которые возвращают объект в пул и не возвращают объект в пул.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-104">The client invokes methods that return the object to the pool and that do not return the object to the pool.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5f7f7-105">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
## <a name="extensibility-points"></a><span data-ttu-id="5f7f7-106">Точки расширяемости</span><span class="sxs-lookup"><span data-stu-id="5f7f7-106">Extensibility Points</span></span>  
 <span data-ttu-id="5f7f7-107">Создание расширения Windows Communication Foundation (WCF) первым делом следует точки расширяемости будут использоваться.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-107">The first step in creating a Windows Communication Foundation (WCF) extension is to decide the extensibility point to use.</span></span> <span data-ttu-id="5f7f7-108">В WCF термин *EndpointDispatcher* относится к компоненту времени выполнения отвечает за преобразование входящих сообщений в вызовы метода в службе пользователя и для преобразования значения, возвращаемые из этого метода в исходящие сообщения .</span><span class="sxs-lookup"><span data-stu-id="5f7f7-108">In WCF, the term *EndpointDispatcher* refers to a run-time component responsible for converting incoming messages into method invocations on the user’s service and for converting return values from that method to an outgoing message.</span></span> <span data-ttu-id="5f7f7-109">Службы WCF создает объект EndpointDispatcher для каждой конечной точки.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-109">A WCF service creates an EndpointDispatcher for each endpoint.</span></span>  
  
 <span data-ttu-id="5f7f7-110">EndpointDispatcher реализует расширяемость области конечной точки (для всех сообщений, получаемых и отправляемых службой) с помощью класса <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-110">The EndpointDispatcher offers endpoint scope (for all messages received or sent by the service) extensibility using the <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> class.</span></span> <span data-ttu-id="5f7f7-111">Этот класс позволяет настраивать различные свойства, управляющие поведением EndpointDispatcher.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-111">This class allows you to customize various properties that control the behavior of the EndpointDispatcher.</span></span> <span data-ttu-id="5f7f7-112">В этом образце рассматривается свойство <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A>, которое указывает на объект, предоставляющий экземпляры класса службы.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-112">This sample focuses on the <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A> property that points to the object that provides the instances of the service class.</span></span>  
  
## <a name="iinstanceprovider"></a><span data-ttu-id="5f7f7-113">IInstanceProvider</span><span class="sxs-lookup"><span data-stu-id="5f7f7-113">IInstanceProvider</span></span>  
 <span data-ttu-id="5f7f7-114">В WCF, EndpointDispatcher создает экземпляры класса службы с помощью поставщика экземпляров, реализующий <xref:System.ServiceModel.Dispatcher.IInstanceProvider> интерфейс.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-114">In WCF, the EndpointDispatcher creates instances of a service class by using an instance provider that implements the <xref:System.ServiceModel.Dispatcher.IInstanceProvider> interface.</span></span> <span data-ttu-id="5f7f7-115">У этого интерфейса есть только два метода.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-115">This interface has only two methods:</span></span>  
  
- <span data-ttu-id="5f7f7-116"><xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A>: Когда прибывает сообщение, Dispatcher вызывает <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A> метод для создания экземпляра класса службы для обработки сообщения.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-116"><xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A>: When a message arrives, the Dispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A> method to create an instance of the service class to process the message.</span></span> <span data-ttu-id="5f7f7-117">Частота вызовов этого метода определяется свойством <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-117">The frequency of the calls to this method is determined by the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property.</span></span> <span data-ttu-id="5f7f7-118">Например, если свойство <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> имеет значение <xref:System.ServiceModel.InstanceContextMode.PerCall?displayProperty=nameWithType>, для обработки каждого получаемого сообщения создается новый экземпляр класса службы, поэтому метод <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A> вызывается каждый раз, когда приходит сообщение.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-118">For example if the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property is set to <xref:System.ServiceModel.InstanceContextMode.PerCall?displayProperty=nameWithType>, a new instance of service class is created to process each message that arrives, so <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A> is called whenever a message arrives.</span></span>  
  
- <span data-ttu-id="5f7f7-119"><xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A>: Когда экземпляр службы завершает обработку сообщения, EndpointDispatcher вызывает <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-119"><xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A>: When the service instance finishes processing the message, the EndpointDispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> method.</span></span> <span data-ttu-id="5f7f7-120">Как и в случае метода <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A>, частота вызовов этого метода определяется свойством <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-120">As in the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A> method, the frequency of the calls to this method is determined by the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property.</span></span>  
  
## <a name="the-object-pool"></a><span data-ttu-id="5f7f7-121">Пул объектов</span><span class="sxs-lookup"><span data-stu-id="5f7f7-121">The Object Pool</span></span>  
 <span data-ttu-id="5f7f7-122">Класс `ObjectPoolInstanceProvider` содержит реализацию пула объектов.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-122">The `ObjectPoolInstanceProvider` class contains the implementation for the object pool.</span></span> <span data-ttu-id="5f7f7-123">Этот класс реализует интерфейс <xref:System.ServiceModel.Dispatcher.IInstanceProvider> для взаимодействия с уровнем модели службы.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-123">This class implements the <xref:System.ServiceModel.Dispatcher.IInstanceProvider> interface to interact with the service model layer.</span></span> <span data-ttu-id="5f7f7-124">Когда EndpointDispatcher вызывает метод <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A>, вместо создания нового экземпляра, пользовательская реализация находит существующий объект в находящемся в памяти пуле.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-124">When the EndpointDispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A> method, instead of creating a new instance, the custom implementation looks for an existing object in an in-memory pool.</span></span> <span data-ttu-id="5f7f7-125">Если такой объект доступен, метод возвращает его.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-125">If one is available, it is returned.</span></span> <span data-ttu-id="5f7f7-126">В противном случае `ObjectPoolInstanceProvider` проверяет, не достигло ли свойство `ActiveObjectsCount` (количество возвращенных из пула объектов) максимального размера пула.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-126">Otherwise, `ObjectPoolInstanceProvider` checks whether the `ActiveObjectsCount` property (number of objects returned from the pool) has reached the maximum pool size.</span></span> <span data-ttu-id="5f7f7-127">Если нет, то создается и возвращается вызывающей стороне новый экземпляр, а значение `ActiveObjectsCount` увеличивается на единицу.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-127">If not, a new instance is created and returned to the caller and `ActiveObjectsCount` is subsequently incremented.</span></span> <span data-ttu-id="5f7f7-128">В противном случае запрос на создание объекта помещается в очередь на заданное время.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-128">Otherwise an object creation request is queued for a configured period of time.</span></span> <span data-ttu-id="5f7f7-129">Реализация метода `GetObjectFromThePool` показана в следующем образце кода.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-129">The implementation for `GetObjectFromThePool` is shown in the following sample code.</span></span>  
  
```  
private object GetObjectFromThePool()  
{  
    bool didNotTimeout =   
       availableCount.WaitOne(creationTimeout, true);  
    if(didNotTimeout)  
    {  
         object obj = null;  
         lock (poolLock)  
        {  
             if (pool.Count != 0)  
             {  
                   obj = pool.Pop();  
                   activeObjectsCount++;  
             }  
             else if (pool.Count == 0)  
             {  
                   if (activeObjectsCount < maxPoolSize)  
                   {  
                        obj = CreateNewPoolObject();  
                        activeObjectsCount++;  
  
                        #if (DEBUG)  
                        WritePoolMessage(  
                             ResourceHelper.GetString("MsgNewObject"));  
                       #endif  
                   }                          
            }  
           idleTimer.Stop();  
      }  
     // Call the Activate method if possible.  
    if (obj is IObjectControl)  
   {  
         ((IObjectControl)obj).Activate();  
   }  
   return obj;  
}  
throw new TimeoutException(  
ResourceHelper.GetString("ExObjectCreationTimeout"));  
}  
```  
  
 <span data-ttu-id="5f7f7-130">Пользовательская реализация `ReleaseInstance` добавляет освободившийся экземпляр обратно в пул и уменьшает значение `ActiveObjectsCount` на единицу.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-130">The custom `ReleaseInstance` implementation adds the released instance back to the pool and decrements the `ActiveObjectsCount` value.</span></span> <span data-ttu-id="5f7f7-131">EndpointDispatcher может вызывать эти методы из различных потоков, поэтому требуется синхронизированный доступ к членам уровня класса в классе `ObjectPoolInstanceProvider`.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-131">The EndpointDispatcher can call these methods from different threads, and therefore synchronized access to the class level members in the `ObjectPoolInstanceProvider` class is required.</span></span>  
  
```  
public void ReleaseInstance(InstanceContext instanceContext, object instance)  
{  
    lock (poolLock)  
    {  
        // Check whether the object can be pooled.   
        // Call the Deactivate method if possible.  
        if (instance is IObjectControl)  
        {  
            IObjectControl objectControl = (IObjectControl)instance;  
            objectControl.Deactivate();  
  
            if (objectControl.CanBePooled)  
            {  
                pool.Push(instance);  
  
                #if(DEBUG)  
                WritePoolMessage(  
                    ResourceHelper.GetString("MsgObjectPooled"));  
                #endif                          
            }  
            else  
            {  
                #if(DEBUG)  
                WritePoolMessage(  
                    ResourceHelper.GetString("MsgObjectWasNotPooled"));  
                #endif  
            }  
        }  
        else  
        {  
            pool.Push(instance);  
  
            #if(DEBUG)  
            WritePoolMessage(  
                ResourceHelper.GetString("MsgObjectPooled"));  
            #endif   
        }  
  
        activeObjectsCount--;  
  
        if (activeObjectsCount == 0)  
        {  
            idleTimer.Start();                       
        }  
    }  
  
    availableCount.Release(1);  
}  
```  
  
 <span data-ttu-id="5f7f7-132">`ReleaseInstance` Предоставляет метод *инициализации с очисткой* функции.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-132">The `ReleaseInstance` method provides a *clean up initialization* feature.</span></span> <span data-ttu-id="5f7f7-133">Обычно пул поддерживает минимальное число объектов в течение времени существования пула.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-133">Normally the pool maintains a minimum number of objects for the lifetime of the pool.</span></span> <span data-ttu-id="5f7f7-134">Однако возможны периоды интенсивного использования, когда требуется создавать в пуле дополнительные объекты, пока не будет достигнуто заданное в конфигурации максимальное значение.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-134">However, there can be periods of excessive usage that require creating additional objects in the pool to reach the maximum limit specified in the configuration.</span></span> <span data-ttu-id="5f7f7-135">В конце концов, когда активность пула снизится, эти дополнительные объекты могут стать излишней нагрузкой.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-135">Eventually when the pool becomes less active those surplus objects can become an extra overhead.</span></span> <span data-ttu-id="5f7f7-136">Поэтому когда значение `activeObjectsCount` достигает нуля, запускается таймер бездействия, по истечении времени ожидания которого выполняется цикл очистки.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-136">Therefore when the `activeObjectsCount` reaches zero an idle timer is started that triggers and performs a clean-up cycle.</span></span>  
  
```  
if (activeObjectsCount == 0)  
{  
    idleTimer.Start();   
}  
```  
  
 <span data-ttu-id="5f7f7-137">Расширения уровня ServiceModel выполняются с помощью следующих поведений.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-137">ServiceModel layer extensions are hooked up using the following behaviors:</span></span>  
  
- <span data-ttu-id="5f7f7-138">Поведения служб. Позволяют настраивать всю среду выполнения службы.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-138">Service Behaviors: These allow for the customization of the entire service runtime.</span></span>  
  
- <span data-ttu-id="5f7f7-139">Поведения конечных точек. Они позволяют настраивать конечные точки, включая EndpointDispatcher.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-139">Endpoint Behaviors: These allow for the customization of a particular service endpoint, including the EndpointDispatcher.</span></span>  
  
- <span data-ttu-id="5f7f7-140">Поведения контрактов. Эти поведения позволяют настраивать <xref:System.ServiceModel.Dispatcher.ClientRuntime> или <xref:System.ServiceModel.Dispatcher.DispatchRuntime> классы на стороне клиента или службы соответственно.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-140">Contract Behaviors: These allow for the customization of either <xref:System.ServiceModel.Dispatcher.ClientRuntime> or <xref:System.ServiceModel.Dispatcher.DispatchRuntime> classes on the client or the service respectively.</span></span>  
  
- <span data-ttu-id="5f7f7-141">Поведения операций. Эти поведения позволяют настраивать <xref:System.ServiceModel.Dispatcher.ClientOperation> или <xref:System.ServiceModel.Dispatcher.DispatchOperation> классы на стороне клиента или службы соответственно.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-141">Operation Behaviors: These allow for the customization of either <xref:System.ServiceModel.Dispatcher.ClientOperation> or <xref:System.ServiceModel.Dispatcher.DispatchOperation> classes on the client or the service respectively.</span></span>  
  
 <span data-ttu-id="5f7f7-142">С целью реализации расширения создания пулов объектов может быть создано поведение конечной точки или поведение службы.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-142">For the purpose of an object pooling extension, either an endpoint behavior or a service behavior can be created.</span></span> <span data-ttu-id="5f7f7-143">В этом примере используется поведение службы, которое применяет поддержку создания пулов объектов ко всем конечным точкам службы.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-143">In this example, we use a service behavior, which applies object pooling ability to every endpoint of the service.</span></span> <span data-ttu-id="5f7f7-144">Поведения служб создаются путем реализации интерфейса <xref:System.ServiceModel.Description.IServiceBehavior>.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-144">Service behaviors are created by implementing the <xref:System.ServiceModel.Description.IServiceBehavior> interface.</span></span> <span data-ttu-id="5f7f7-145">Имеется несколько способов сообщить ServiceModel о пользовательских поведениях:</span><span class="sxs-lookup"><span data-stu-id="5f7f7-145">There are several ways to make the ServiceModel aware of the custom behaviors:</span></span>  
  
- <span data-ttu-id="5f7f7-146">с помощью пользовательского атрибута;</span><span class="sxs-lookup"><span data-stu-id="5f7f7-146">Using a custom attribute.</span></span>  
  
- <span data-ttu-id="5f7f7-147">путем ее императивного добавления в коллекцию поведений описания службы;</span><span class="sxs-lookup"><span data-stu-id="5f7f7-147">Imperatively adding it to the service description’s behaviors collection.</span></span>  
  
- <span data-ttu-id="5f7f7-148">путем расширения файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-148">Extending the configuration file.</span></span>  
  
 <span data-ttu-id="5f7f7-149">В этом образце используется пользовательский атрибут.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-149">This sample uses a custom attribute.</span></span> <span data-ttu-id="5f7f7-150">При создании <xref:System.ServiceModel.ServiceHost> проверяются атрибуты, используемые в определении типа службы, а в коллекцию поведений описания службы добавляются доступные поведения.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-150">When the <xref:System.ServiceModel.ServiceHost> is constructed, it examines the attributes used in the service’s type definition and adds the available behaviors to the service description’s behaviors collection.</span></span>  
  
 <span data-ttu-id="5f7f7-151"><xref:System.ServiceModel.Description.IServiceBehavior> Интерфейс содержит три метода: <xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A> `,` <xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A> `,` и <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A>.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-151">The <xref:System.ServiceModel.Description.IServiceBehavior> interface has three methods: <xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A>`,` <xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A>`,` and <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A>.</span></span> <span data-ttu-id="5f7f7-152">Эти методы вызываются платформой WCF при <xref:System.ServiceModel.ServiceHost> выполняется инициализация.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-152">These methods are called by WCF when the <xref:System.ServiceModel.ServiceHost> is being initialized.</span></span> <span data-ttu-id="5f7f7-153">Сначала вызывается метод <xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A?displayProperty=nameWithType>, который позволяет проверить согласованность службы.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-153"><xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A?displayProperty=nameWithType> is called first; it allows the service to be inspected for inconsistencies.</span></span> <span data-ttu-id="5f7f7-154">Затем вызывается метод <xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A?displayProperty=nameWithType>, который используется только в очень сложных сценариях.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-154"><xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A?displayProperty=nameWithType> is called next; this method is only required in very advanced scenarios.</span></span> <span data-ttu-id="5f7f7-155">Метод <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A?displayProperty=nameWithType> вызывается в последнюю очередь и отвечает за настройку среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-155"><xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A?displayProperty=nameWithType> is called last and is responsible for configuring the runtime.</span></span> <span data-ttu-id="5f7f7-156">Следующие параметры передаются методу <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-156">The following parameters are passed into <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A?displayProperty=nameWithType>:</span></span>  
  
- <span data-ttu-id="5f7f7-157">`Description`: Этот параметр содержит описание службы для всей службы.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-157">`Description`: This parameter provides the service description for the entire service.</span></span> <span data-ttu-id="5f7f7-158">Его можно использовать для проверки данных описания о конечных точках, контрактах и привязках службы, а также других связанных со службой данных.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-158">This can be used to inspect description data about the service’s endpoints, contracts, bindings, and other data associated with the service.</span></span>  
  
- <span data-ttu-id="5f7f7-159">`ServiceHostBase`: Этот параметр обеспечивает <xref:System.ServiceModel.ServiceHostBase> , настоящее время инициализируется.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-159">`ServiceHostBase`: This parameter provides the <xref:System.ServiceModel.ServiceHostBase> that is currently being initialized.</span></span>  
  
 <span data-ttu-id="5f7f7-160">В пользовательской реализации <xref:System.ServiceModel.Description.IServiceBehavior> создается новый экземпляр `ObjectPoolInstanceProvider`, который присваивается свойству <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A> в каждом объекте <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>, прикрепленном к <xref:System.ServiceModel.ServiceHostBase>.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-160">In the custom <xref:System.ServiceModel.Description.IServiceBehavior> implementation, a new instance of `ObjectPoolInstanceProvider` is instantiated and assigned to the <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A> property in each <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> that is attached to the <xref:System.ServiceModel.ServiceHostBase>.</span></span>  
  
```  
public void ApplyDispatchBehavior(ServiceDescription description, ServiceHostBase serviceHostBase)  
{  
    if (enabled)  
    {  
        // Create an instance of the ObjectPoolInstanceProvider.  
        instanceProvider = new ObjectPoolInstanceProvider(description.ServiceType,  
        maxPoolSize, minPoolSize, creationTimeout);  
  
        // Assign our instance provider to Dispatch behavior in each   
        // endpoint.  
        foreach (ChannelDispatcherBase cdb in serviceHostBase.ChannelDispatchers)  
        {  
             ChannelDispatcher cd = cdb as ChannelDispatcher;  
             if (cd != null)  
             {  
                 foreach (EndpointDispatcher ed in cd.Endpoints)  
                 {  
                        ed.DispatchRuntime.InstanceProvider = instanceProvider;  
                 }  
             }  
         }  
     }  
}   
```  
  
 <span data-ttu-id="5f7f7-161">Помимо реализации интерфейса <xref:System.ServiceModel.Description.IServiceBehavior> у класса `ObjectPoolingAttribute` имеется несколько членов для настройки пула объектов с помощью аргументов атрибута.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-161">In addition to an <xref:System.ServiceModel.Description.IServiceBehavior> implementation the `ObjectPoolingAttribute` class has several members to customize the object pool using the attribute arguments.</span></span> <span data-ttu-id="5f7f7-162">К этим членам относятся `MaxSize`, `MinSize`, `Enabled` и `CreationTimeout`, и они должны соответствовать набору возможностей пула, предоставляемому службами .NET Enterprise Services.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-162">These members include `MaxSize`, `MinSize`, `Enabled` and `CreationTimeout`, to match the object pooling feature set provided by .NET Enterprise Services.</span></span>  
  
 <span data-ttu-id="5f7f7-163">Поведение пула объектов, могут теперь добавляться службы WCF, добавив аннотации для реализации службы с новым пользовательским `ObjectPooling` атрибута.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-163">The object pooling behavior can now be added to a WCF service by annotating the service implementation with the newly created custom `ObjectPooling` attribute.</span></span>  
  
```  
[ObjectPooling(MaxSize=1024, MinSize=10, CreationTimeout=30000]      
public class PoolService : IPoolService  
{  
  // …  
}  
```  
  
## <a name="hooking-activation-and-deactivation"></a><span data-ttu-id="5f7f7-164">Активация и деактивация связывания</span><span class="sxs-lookup"><span data-stu-id="5f7f7-164">Hooking Activation and Deactivation</span></span>  
 <span data-ttu-id="5f7f7-165">Основной целью создания пулов объектов является оптимизация использования объектов с небольшим временем существования, чтобы экономить на ресурсоемких процедурах создания и инициализации.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-165">The primary objective of object pooling is to optimize short-lived objects with relatively expensive creation and initialization.</span></span> <span data-ttu-id="5f7f7-166">Поэтому создание пулов при его правильном использовании позволяет значительно повысить производительность приложения.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-166">Therefore it can give a dramatic performance boost to an application if properly used.</span></span> <span data-ttu-id="5f7f7-167">Поскольку объект возвращается из пула, конструктор вызывается только один раз.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-167">Because the object is returned from the pool, the constructor is called only once.</span></span> <span data-ttu-id="5f7f7-168">Однако некоторым приложениями требуется более высокий уровень контроля, чтобы они могли инициализировать и высвобождать ресурсы в рамках одного контекста.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-168">However, some applications require some level of control so that they can initialize and clean-up the resources used during a single context.</span></span> <span data-ttu-id="5f7f7-169">Например, объект, используемый для набора вычислений, может сбрасывать значения своих закрытых полей, прежде чем переходить к следующим вычислениям.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-169">For example, an object being used for a set of calculations can reset its private fields before processing the next calculation.</span></span> <span data-ttu-id="5f7f7-170">Службы Enterprise Services поддерживают такую инициализацию в зависимости от контекста, позволяя разработчику объектов переопределять методы `Activate` и `Deactivate` из базового класса <xref:System.EnterpriseServices.ServicedComponent>.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-170">Enterprise Services enabled this kind of context-specific initialization by letting the object developer override `Activate` and `Deactivate` methods from the <xref:System.EnterpriseServices.ServicedComponent> base class.</span></span>  
  
 <span data-ttu-id="5f7f7-171">Пул объектов вызывает метод `Activate` непосредственно перед возвращением объекта из пула.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-171">The object pool calls the `Activate` method just before returning the object from the pool.</span></span> <span data-ttu-id="5f7f7-172">Метод `Deactivate` вызывается при возвращении объекта в пул.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-172">`Deactivate` is called when the object returns back to the pool.</span></span> <span data-ttu-id="5f7f7-173">Кроме того, у базового класса <xref:System.EnterpriseServices.ServicedComponent> имеется свойство типа `boolean` с именем `CanBePooled`, с помощью которого можно уведомить пул о том, можно ли и дальше размещать объект в пуле.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-173">The <xref:System.EnterpriseServices.ServicedComponent> base class also has a `boolean` property called `CanBePooled`, which can be used to notify the pool whether the object can be pooled further.</span></span>  
  
 <span data-ttu-id="5f7f7-174">Чтобы сымитировать эту функциональность, в этом образце объявляется открытый интерфейс (`IObjectControl`), имеющий указанные выше члены.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-174">To mimic this functionality, the sample declares a public interface (`IObjectControl`) that has the aforementioned members.</span></span> <span data-ttu-id="5f7f7-175">Затем этот интерфейс реализуется классами службы, предназначенными для инициализации с учетом контекста.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-175">This interface is then implemented by service classes intended to provide context specific initialization.</span></span> <span data-ttu-id="5f7f7-176">Реализацию <xref:System.ServiceModel.Dispatcher.IInstanceProvider> необходимо изменить, чтобы она удовлетворяла этим требованиям.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-176">The <xref:System.ServiceModel.Dispatcher.IInstanceProvider> implementation must be modified to meet these requirements.</span></span> <span data-ttu-id="5f7f7-177">Теперь при каждом получении объекта путем вызова `GetInstance` метод, необходимо проверить, реализует ли объект `IObjectControl.` в этом случае необходимо вызвать `Activate` метод соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-177">Now, each time you get an object by calling the `GetInstance` method, you must check whether the object implements `IObjectControl.` If it does, you must call the `Activate` method appropriately.</span></span>  
  
```  
if (obj is IObjectControl)  
{  
    ((IObjectControl)obj).Activate();  
}  
```  
  
 <span data-ttu-id="5f7f7-178">При возврате объекта в пул необходимо проверить свойство `CanBePooled`, прежде чем добавлять объект обратно в пул.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-178">When returning an object to the pool, a check is required for the `CanBePooled` property before adding the object back to the pool.</span></span>  
  
```  
if (instance is IObjectControl)  
{  
    IObjectControl objectControl = (IObjectControl)instance;  
    objectControl.Deactivate();  
    if (objectControl.CanBePooled)  
    {  
       pool.Push(instance);  
    }  
}  
```  
  
 <span data-ttu-id="5f7f7-179">Поскольку разработчик может решать, можно ли помещать объект в пул, в определенный момент значение счетчика объектов в пуле может оказаться меньше минимального размера пула.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-179">Because the service developer can decide whether an object can be pooled, the object count in the pool at a given time can go below the minimum size.</span></span> <span data-ttu-id="5f7f7-180">Поэтому необходимо сравнивать число объектов с минимальным размером и при необходимости выполнять инициализацию в процедуре очистки.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-180">Therefore you must check whether the object count has gone below the minimum level and perform the necessary initialization in the clean-up procedure.</span></span>  
  
```  
// Remove the surplus objects.  
if (pool.Count > minPoolSize)  
{  
  // Clean the surplus objects.  
}                      
else if (pool.Count < minPoolSize)  
{  
  // Reinitialize the missing objects.  
  while(pool.Count != minPoolSize)  
  {  
    pool.Push(CreateNewPoolObject());  
  }  
}  
```  
  
 <span data-ttu-id="5f7f7-181">При запуске данного примера запросы и ответы операций отображаются в окнах консоли как службы, так и клиента.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-181">When you run the sample, the operation requests and responses are displayed in both the service and client console windows.</span></span> <span data-ttu-id="5f7f7-182">Нажмите клавишу ВВОД в каждом окне консоли, чтобы закрыть службу и клиент.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-182">Press Enter in each console window to shut down the service and client.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="5f7f7-183">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="5f7f7-183">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="5f7f7-184">Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="5f7f7-184">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="5f7f7-185">Чтобы построить решение, следуйте инструкциям в [сборка образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="5f7f7-185">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="5f7f7-186">Чтобы выполнить образец на одном или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="5f7f7-186">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5f7f7-187">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-187">The samples may already be installed on your machine.</span></span> <span data-ttu-id="5f7f7-188">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="5f7f7-188">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="5f7f7-189">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-189">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5f7f7-190">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="5f7f7-190">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Initialization`  
