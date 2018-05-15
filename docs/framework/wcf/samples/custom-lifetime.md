---
title: Пользовательские службы времени существования
ms.date: 03/30/2017
ms.assetid: 52806c07-b91c-48fe-b992-88a41924f51f
ms.openlocfilehash: e41c970739b8036730fa601433ce7157e01d7e19
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="custom-lifetime"></a><span data-ttu-id="6fd0c-102">Пользовательские службы времени существования</span><span class="sxs-lookup"><span data-stu-id="6fd0c-102">Custom Lifetime</span></span>
<span data-ttu-id="6fd0c-103">В этом примере показано, как написать расширение Windows Communication Foundation (WCF) для предоставления пользовательских служб времени существования для общих экземпляров службы WCF.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-103">This sample demonstrates how to write a Windows Communication Foundation (WCF) extension to provide custom lifetime services for shared WCF service instances.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6fd0c-104">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-104">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
## <a name="shared-instancing"></a><span data-ttu-id="6fd0c-105">Создание общих экземпляров</span><span class="sxs-lookup"><span data-stu-id="6fd0c-105">Shared Instancing</span></span>  
 <span data-ttu-id="6fd0c-106">WCF предлагает несколько режимов создания экземпляров служб.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-106">WCF offers several instancing modes for your service instances.</span></span> <span data-ttu-id="6fd0c-107">Режим создания общих экземпляров, описанный в этом разделе, предоставляет способ совместного использования экземпляра службы несколькими каналами.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-107">The Shared Instancing mode covered in this topic provides a way to share a service instance between multiple channels.</span></span> <span data-ttu-id="6fd0c-108">Клиенты могут разрешать адрес конечной точки экземпляра локально или обращаться к методу производства в службе, чтобы получить адрес конечной точки работающего экземпляра.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-108">Clients can either resolve the instance’s endpoint address locally or contact a factory method in the service to obtain the endpoint address of a running instance.</span></span> <span data-ttu-id="6fd0c-109">Получив адрес конечной точки, клиент может создать новый канал и начать обмен данными.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-109">Once it has the endpoint address, it can create a new channel and start communication.</span></span> <span data-ttu-id="6fd0c-110">Следующий фрагмент кода показывает, как клиентское приложение создает новый канал к существующему экземпляру службы.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-110">The following code snippet shows how a client application creates a new channel to an existing service instance.</span></span>  
  
```  
// Create the first channel.  
IEchoService proxy = channelFactory.CreateChannel();  
  
// Resolve the instance.  
EndpointAddress epa = ((IClientChannel)proxy).ResolveInstance();  
  
// Create new channel factory with the endpoint address resolved by   
// previous statement.  
ChannelFactory<IEchoService> channelFactory2 =  
                new ChannelFactory<IEchoService>("echoservice",  
                epa);  
  
// Create the second channel to the same instance.  
IEchoService proxy2 = channelFactory2.CreateChannel();  
```  
  
 <span data-ttu-id="6fd0c-111">В отличие от других режимов создания экземпляров, режим создания общих экземпляров располагает уникальным способом освобождения экземпляров служб.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-111">Unlike other instancing modes, the shared instancing mode has a unique way of releasing the service instances.</span></span> <span data-ttu-id="6fd0c-112">Когда для экземпляра закрыты все каналы, среда выполнения службы WCF запускает таймер.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-112">When all the channels are closed for an instance, the service WCF runtime starts a timer.</span></span> <span data-ttu-id="6fd0c-113">Если никто не установит соединение до истечения времени ожидания, WCF освободит экземпляр и вернет себе ресурсы.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-113">If nobody makes a connection before the timeout expires, WCF releases the instance and claims the resources.</span></span> <span data-ttu-id="6fd0c-114">В рамках процедуры демонтажа WCF вызывает <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> метод всех <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> реализации перед освобождением экземпляра.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-114">As a part of the teardown procedure WCF invokes the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method of all <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementations before releasing the instance.</span></span> <span data-ttu-id="6fd0c-115">Если все они возвратят значение `true`, экземпляр будет освобожден.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-115">If all of them return `true` the instance is released.</span></span> <span data-ttu-id="6fd0c-116">В противном случае реализация <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> отвечает за уведомление `Dispatcher` о состоянии бездействия с помощью метода обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-116">Otherwise the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation is responsible for notifying the `Dispatcher` of the idle state by using a callback method.</span></span>  
  
 <span data-ttu-id="6fd0c-117">По умолчанию значение времени ожидания состояния бездействия <xref:System.ServiceModel.InstanceContext> равно одной минуте.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-117">By default, the idle timeout value of <xref:System.ServiceModel.InstanceContext> is one minute.</span></span> <span data-ttu-id="6fd0c-118">Однако в этом образце показано, как его можно продлить с помощью пользовательского расширения.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-118">However this sample demonstrates how you can extend this using a custom extension.</span></span>  
  
## <a name="extending-the-instancecontext"></a><span data-ttu-id="6fd0c-119">Расширение InstanceContext</span><span class="sxs-lookup"><span data-stu-id="6fd0c-119">Extending the InstanceContext</span></span>  
 <span data-ttu-id="6fd0c-120">В WCF <xref:System.ServiceModel.InstanceContext> связывает экземпляр службы и `Dispatcher`.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-120">In WCF, <xref:System.ServiceModel.InstanceContext> is the link between the service instance and the `Dispatcher`.</span></span> <span data-ttu-id="6fd0c-121">WCF позволяет вам расширять данный компонент времени выполнения путем добавления нового состояния или поведения с помощью шаблона расширяемого объекта.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-121">WCF allows you to extend this runtime component by adding new state or behavior by using its extensible object pattern.</span></span> <span data-ttu-id="6fd0c-122">Шаблон расширяемого объекта используется в WCF для расширения существующих классов среды выполнения при помощи новых функциональных возможностей или добавления новых возможностей состояния к объекту.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-122">The extensible object pattern is used in WCF to either extend existing runtime classes with new functionality or to add new state features to an object.</span></span> <span data-ttu-id="6fd0c-123">Предусмотрено три интерфейса в шаблоне расширяемого объекта: `IExtensibleObject<T>`, `IExtension<T>` и `IExtensionCollection<T>`.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-123">There are three interfaces in the extensible object pattern: `IExtensibleObject<T>`, `IExtension<T>`, and `IExtensionCollection<T>`.</span></span>  
  
 <span data-ttu-id="6fd0c-124">Интерфейс `IExtensibleObject<T>` реализуется объектами для обеспечения расширений, которые настраивают их функциональность.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-124">The `IExtensibleObject<T>` interface is implemented by objects to allow extensions which customize their functionality.</span></span>  
  
 <span data-ttu-id="6fd0c-125">Интерфейс `IExtension<T>` реализуется объектами, которые могут быть расширениями классов типа `T`.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-125">The `IExtension<T>` interface is implemented by objects that can be extensions of classes of type `T`.</span></span>  
  
 <span data-ttu-id="6fd0c-126">И наконец, интерфейс `IExtensionCollection<T>` является коллекцией `IExtensions`, которая позволяет получать `IExtensions` по их типу.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-126">And finally, the `IExtensionCollection<T>` interface is a collection of `IExtensions` that allows for retrieving `IExtensions` by their type.</span></span>  
  
 <span data-ttu-id="6fd0c-127">Поэтому, чтобы расширить контекст <xref:System.ServiceModel.InstanceContext>, требуется реализовать интерфейс `IExtension`.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-127">Therefore in order to extend the <xref:System.ServiceModel.InstanceContext> you must implement the `IExtension` interface.</span></span> <span data-ttu-id="6fd0c-128">В данном образце проекта эту реализацию содержит класс `CustomLeaseExtension`.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-128">In this sample project the `CustomLeaseExtension` class contains this implementation.</span></span>  
  
```  
class CustomLeaseExtension : IExtension<InstanceContext>  
{  
}  
```  
  
 <span data-ttu-id="6fd0c-129">У интерфейса `IExtension` имеется два метода: `Attach` и `Detach`.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-129">The `IExtension` interface has two methods `Attach` and `Detach`.</span></span> <span data-ttu-id="6fd0c-130">Как видно по их именам, два этих метода вызываются, когда среда выполнения присоединяет и отсоединяет расширение экземпляра класса <xref:System.ServiceModel.InstanceContext>.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-130">As their names imply, these two methods are called when the runtime attaches and detaches the extension to an instance of the <xref:System.ServiceModel.InstanceContext> class.</span></span> <span data-ttu-id="6fd0c-131">В этом образце метод `Attach` используется для отслеживания объекта <xref:System.ServiceModel.InstanceContext>, который принадлежит текущему экземпляру расширения.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-131">In this sample, the `Attach` method is used to keep track of the <xref:System.ServiceModel.InstanceContext> object that belongs to the current instance of the extension.</span></span>  
  
```  
InstanceContext owner;  
  
public void Attach(InstanceContext owner)  
{  
  this.owner = owner;   
}  
```  
  
 <span data-ttu-id="6fd0c-132">Кроме того, в расширение необходимо добавить требуемую реализацию, чтобы обеспечить поддержку продленного времени существования.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-132">In addition, you must add the necessary implementation to the extension to provide the extended lifetime support.</span></span> <span data-ttu-id="6fd0c-133">Поэтому интерфейс `ICustomLease` объявляется с необходимыми методами и реализуется в классе `CustomLeaseExtension`.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-133">Therefore the `ICustomLease` interface is declared with the desired methods and is implemented in the `CustomLeaseExtension` class.</span></span>  
  
```  
interface ICustomLease  
{  
    bool IsIdle { get; }          
    InstanceContextIdleCallback Callback { get; set; }  
}  
  
class CustomLeaseExtension : IExtension<InstanceContext>, ICustomLease  
{  
}  
```  
  
 <span data-ttu-id="6fd0c-134">Когда WCF вызывает <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> метод в <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> этот вызов направляется в реализации <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> метод `CustomLeaseExtension`.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-134">When WCF invokes the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method in the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation this call is routed to the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method of the `CustomLeaseExtension`.</span></span> <span data-ttu-id="6fd0c-135">Затем расширение `CustomLeaseExtension` проверяет его закрытое состояние, чтобы определить, бездействует ли контекст <xref:System.ServiceModel.InstanceContext>.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-135">Then the `CustomLeaseExtension` checks its private state to see whether the <xref:System.ServiceModel.InstanceContext> is idle.</span></span> <span data-ttu-id="6fd0c-136">Если контекст бездействует, то возвращается значение `true`.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-136">If it is idle it returns `true`.</span></span> <span data-ttu-id="6fd0c-137">В противном случае запускается таймер на указанное продленное время существования.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-137">Otherwise, it starts a timer for a specified amount of extended lifetime.</span></span>  
  
```  
public bool IsIdle  
{  
  get  
  {  
    lock (thisLock)  
    {  
      if (isIdle)  
      {  
        return true;  
      }  
      else  
      {  
        StartTimer();  
        return false;  
      }  
    }  
  }  
}  
```  
  
 <span data-ttu-id="6fd0c-138">В рамках события `Elapsed` таймера вызывается функция обратного вызова в диспетчере, чтобы запустить еще один цикл очистки.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-138">In the timer’s `Elapsed` event the callback function in the Dispatcher is called in order to start another clean up cycle.</span></span>  
  
```  
void idleTimer_Elapsed(object sender, ElapsedEventArgs args)  
{  
    idleTimer.Stop();  
    isIdle = true;    
    callback(owner);  
}  
```  
  
 <span data-ttu-id="6fd0c-139">При поступлении нового сообщения для экземпляра, перемещаемого в состояние бездействия, возобновить работающий таймер невозможно.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-139">There is no way to renew the running timer when a new message arrives for the instance being moved to the idle state.</span></span>  
  
 <span data-ttu-id="6fd0c-140">Для перехвата вызовов метода <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> и их перенаправления расширению <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> образец реализует `CustomLeaseExtension`.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-140">The sample implements <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> to intercept the calls to the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method and route them to the `CustomLeaseExtension`.</span></span> <span data-ttu-id="6fd0c-141">Реализация <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> содержится в классе `CustomLifetimeLease`.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-141">The <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation is contained in `CustomLifetimeLease` class.</span></span> <span data-ttu-id="6fd0c-142"><xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> Метод вызывается, когда WCF собирается освободить экземпляр службы.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-142">The <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method is invoked when WCF is about to release the service instance.</span></span> <span data-ttu-id="6fd0c-143">Однако в коллекции `ISharedSessionInstance` ServiceBehavior имеется только один экземпляр конкретной реализации <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider>.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-143">However, there is only one instance of a particular `ISharedSessionInstance` implementation in the ServiceBehavior’s <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> collection.</span></span> <span data-ttu-id="6fd0c-144">Это означает, что нет способа узнать <xref:System.ServiceModel.InstanceContext> закрыт во время проверки WCF <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-144">This means there is no way of knowing the <xref:System.ServiceModel.InstanceContext> being closed at the time WCF checks the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method.</span></span> <span data-ttu-id="6fd0c-145">Поэтому этот образец использует блокировку потока для сериализации запросов в метод <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-145">Therefore this sample uses thread locking to serialize requests to the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6fd0c-146">Использовать блокировку потока не рекомендуется, поскольку сериализация может значительно снизить производительность приложения.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-146">Using thread locking is not a recommended approach because serialization can severely affect the performance of your application.</span></span>  
  
 <span data-ttu-id="6fd0c-147">Для отслеживания значения `CustomLeaseExtension` в классе `IsIdle` используется переменная закрытого элемента.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-147">A private member variable is used in the `CustomLeaseExtension` class to track the `IsIdle` value.</span></span> <span data-ttu-id="6fd0c-148">Каждый раз при получении значения <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> закрытый элемент `IsIdle` возвращается и сбрасывается в значение `false`.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-148">Each time the value of <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> is retrieved the `IsIdle` private member is returned and reset to `false`.</span></span> <span data-ttu-id="6fd0c-149">Важно задать этому параметру значение `false` с тем, чтобы гарантировать вызов диспетчером метода <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A>.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-149">It is essential to set this value to `false` in order to make sure the Dispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> method.</span></span>  
  
```  
public bool IsIdle  
{  
    get   
    {  
       lock (thisLock)  
       {  
           bool idleCopy = isIdle;  
           isIdle = false;  
           return idleCopy;  
       }  
    }  
}  
```  
  
 <span data-ttu-id="6fd0c-150">Если свойство `ISharedSessionLifetime.IsIdle` возвращает значение `false`, то диспетчер регистрирует функцию обратного вызова с помощью метода `NotifyIdle`.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-150">If the `ISharedSessionLifetime.IsIdle` property returns `false` the Dispatcher registers a callback function by using the `NotifyIdle` method.</span></span> <span data-ttu-id="6fd0c-151">Этот метод получает ссылку на освобождаемый контекст <xref:System.ServiceModel.InstanceContext>.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-151">This method receives a reference to the <xref:System.ServiceModel.InstanceContext> being released.</span></span> <span data-ttu-id="6fd0c-152">Поэтому образец кода может запросить расширение типа `ICustomLease` и проверить свойство `ICustomLease.IsIdle` в расширенном состоянии.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-152">Therefore the sample code can query the `ICustomLease` type extension and check the `ICustomLease.IsIdle` property in the extended state.</span></span>  
  
```  
public void NotifyIdle(InstanceContextIdleCallback callback,   
            InstanceContext instanceContext)  
{  
    lock (thisLock)  
    {  
       ICustomLease customLease =  
           instanceContext.Extensions.Find<ICustomLease>();  
       customLease.Callback = callback;   
       isIdle = customLease.IsIdle;  
       if (isIdle)  
       {  
             callback(instanceContext);  
       }  
    }   
}  
```  
  
 <span data-ttu-id="6fd0c-153">Перед проверкой свойства `ICustomLease.IsIdle` необходимо задать значение свойства Callback, поскольку оно требуется `CustomLeaseExtension` для уведомления диспетчера при переходе в состояние бездействия.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-153">Before the `ICustomLease.IsIdle` property is checked the Callback property needs to be set as this is essential for `CustomLeaseExtension` to notify the Dispatcher when it becomes idle.</span></span> <span data-ttu-id="6fd0c-154">Если `ICustomLease.IsIdle` возвращает значение `true`, то закрытому элементу `isIdle` в `CustomLifetimeLease` просто устанавливается значение `true` и вызывается метод обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-154">If `ICustomLease.IsIdle` returns `true`, the `isIdle` private member is simply set in `CustomLifetimeLease` to `true` and calls the callback method.</span></span> <span data-ttu-id="6fd0c-155">Поскольку код содержит блокировку, другие потоки не могут изменить значение этого закрытого элемента.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-155">Because the code holds a lock, other threads cannot change the value of this private member.</span></span> <span data-ttu-id="6fd0c-156">При следующей проверке диспетчером `ISharedSessionLifetime.IsIdle` возвращается значение `true`, при этом диспетчер может освободить экземпляр.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-156">And the next time Dispatcher checks the `ISharedSessionLifetime.IsIdle`, it returns `true` and lets Dispatcher release the instance.</span></span>  
  
 <span data-ttu-id="6fd0c-157">Завершив подготовительную работу для пользовательского расширения, его необходимо подключить к модели службы.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-157">Now that the groundwork for the custom extension is completed, it has to be hooked up to the service model.</span></span> <span data-ttu-id="6fd0c-158">Чтобы подключить `CustomLeaseExtension` реализации <xref:System.ServiceModel.InstanceContext>, WCF предоставляет <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> интерфейс для выполнения начальной загрузки <xref:System.ServiceModel.InstanceContext>.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-158">To hook up the `CustomLeaseExtension` implementation to the <xref:System.ServiceModel.InstanceContext>, WCF provides the <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> interface to perform the bootstrapping of <xref:System.ServiceModel.InstanceContext>.</span></span> <span data-ttu-id="6fd0c-159">В этом образце класс `CustomLeaseInitializer` реализует этот интерфейс и добавляет экземпляр `CustomLeaseExtension` в коллекцию <xref:System.ServiceModel.InstanceContext.Extensions%2A> из единственной инициализации метода.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-159">In the sample, the `CustomLeaseInitializer` class implements this interface and adds an instance of `CustomLeaseExtension` to the <xref:System.ServiceModel.InstanceContext.Extensions%2A> collection from the only method initialization.</span></span> <span data-ttu-id="6fd0c-160">Этот метод вызывается диспетчером при инициализации <xref:System.ServiceModel.InstanceContext>.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-160">This method is called by Dispatcher while initializing the <xref:System.ServiceModel.InstanceContext>.</span></span>  
  
```  
public void Initialize(InstanceContext instanceContext, Message message)  
{  
  IExtension<InstanceContext> customLeaseExtension =  
    new CustomLeaseExtension(timeout);  
  instanceContext.Extensions.Add(customLeaseExtension);  
}  
```  
  
 <span data-ttu-id="6fd0c-161">Наконец `System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime` и <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> реализаций — изогнутыми до модели службы с помощью <xref:System.ServiceModel.Description.IServiceBehavior> реализации.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-161">Finally the `System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime` and <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> implementations are is hooked up to the service model by using the <xref:System.ServiceModel.Description.IServiceBehavior> implementation.</span></span> <span data-ttu-id="6fd0c-162">Эта реализация помещается в класс `CustomLeaseTimeAttribute`, кроме того, она является производной от базового класса `Attribute` для предоставления этого поведения в виде атрибута.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-162">This implementation is placed in the `CustomLeaseTimeAttribute` class and it also derives from the `Attribute` base class to expose this behavior as an attribute.</span></span> <span data-ttu-id="6fd0c-163">В методе `IServiceBehavior.ApplyBehavior` экземпляры реализаций <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> и `System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime` добавляются в коллекции `System.ServiceModel.Dispatcher.DispatchRuntime.InstanceContextLifetimes` и <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceContextInitializers%2A> диспетчера <xref:System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime> соответственно.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-163">In the `IServiceBehavior.ApplyBehavior` method, instances of <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> and `System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime` implementations are added to the `System.ServiceModel.Dispatcher.DispatchRuntime.InstanceContextLifetimes` and <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceContextInitializers%2A> collections of the <xref:System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime> respectively.</span></span>  
  
```  
public void ApplyBehavior(ServiceDescription description,   
           ServiceHostBase serviceHostBase,   
           Collection<DispatchBehavior> behaviors,  
           Collection<BindingParameterCollection> parameters)  
{  
    CustomLifetimeLease customLease = new CustomLifetimeLease();  
    CustomLeaseInitializer initializer =   
                new CustomLeaseInitializer(timeout);  
  
    foreach (DispatchBehavior dispatchBehavior in behaviors)  
    {  
        dispatchBehavior.InstanceContextLifetimes.Add(customLease);  
        dispatchBehavior.InstanceContextInitializers.Add(initializer);  
    }  
}  
```  
  
 <span data-ttu-id="6fd0c-164">Это поведение можно добавить в класс образца службы, сопроводив его заметкой в вида атрибута `CustomLeaseTime`.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-164">This behavior can be added to a sample service class by annotating it with the `CustomLeaseTime` attribute.</span></span>  
  
```  
[ServiceBehavior(InstanceContextMode=InstanceContextMode.Shareable)]  
[CustomLeaseTime(Timeout = 20000)]  
public class EchoService : IEchoService  
{  
  //…  
}  
```  
  
 <span data-ttu-id="6fd0c-165">При запуске данного примера запросы и ответы операций отображаются в окнах консоли как службы, так и клиента.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-165">When you run the sample, the operation requests and responses are displayed in both the service and client console windows.</span></span> <span data-ttu-id="6fd0c-166">Нажмите клавишу ВВОД в каждом окне консоли, чтобы закрыть службу и клиент.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-166">Press ENTER in each console window to shut down the service and client.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="6fd0c-167">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="6fd0c-167">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="6fd0c-168">Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="6fd0c-168">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="6fd0c-169">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="6fd0c-169">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="6fd0c-170">Для запуска образца в конфигурации одного или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="6fd0c-170">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6fd0c-171">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-171">The samples may already be installed on your machine.</span></span> <span data-ttu-id="6fd0c-172">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="6fd0c-172">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="6fd0c-173">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-173">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6fd0c-174">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="6fd0c-174">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Lifetime`  
  
## <a name="see-also"></a><span data-ttu-id="6fd0c-175">См. также</span><span class="sxs-lookup"><span data-stu-id="6fd0c-175">See Also</span></span>
