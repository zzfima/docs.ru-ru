---
title: Пользовательские службы времени существования
ms.date: 08/20/2018
ms.assetid: 52806c07-b91c-48fe-b992-88a41924f51f
ms.openlocfilehash: 1946608c69401fb08f6eb458a8adabea24563963
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43520775"
---
# <a name="custom-lifetime"></a><span data-ttu-id="05ca5-102">Пользовательские службы времени существования</span><span class="sxs-lookup"><span data-stu-id="05ca5-102">Custom lifetime</span></span>

<span data-ttu-id="05ca5-103">В этом примере показано, как написать расширение Windows Communication Foundation (WCF) для предоставления пользовательских служб времени существования для общих экземпляров службы WCF.</span><span class="sxs-lookup"><span data-stu-id="05ca5-103">This sample demonstrates how to write a Windows Communication Foundation (WCF) extension to provide custom lifetime services for shared WCF service instances.</span></span>

> [!NOTE]
> <span data-ttu-id="05ca5-104">Процедура настройки и инструкции по построению для данного примера приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="05ca5-104">The setup procedure and build instructions for this sample are located at the end of this article.</span></span>

## <a name="shared-instancing"></a><span data-ttu-id="05ca5-105">Создание общих экземпляров</span><span class="sxs-lookup"><span data-stu-id="05ca5-105">Shared instancing</span></span>

<span data-ttu-id="05ca5-106">WCF предлагает несколько режимов создания экземпляров служб.</span><span class="sxs-lookup"><span data-stu-id="05ca5-106">WCF offers several instancing modes for your service instances.</span></span> <span data-ttu-id="05ca5-107">Режим создания общих экземпляров в этой статье рассматриваются предоставляет способ совместного использования экземпляра службы несколькими каналами.</span><span class="sxs-lookup"><span data-stu-id="05ca5-107">The shared instancing mode covered in this article provides a way to share a service instance between multiple channels.</span></span> <span data-ttu-id="05ca5-108">Клиенты смогут обратиться к методу производства в службе и создать новый канал, чтобы начать обмен данными.</span><span class="sxs-lookup"><span data-stu-id="05ca5-108">Clients can contact a factory method in the service and create a new channel to start communication.</span></span> <span data-ttu-id="05ca5-109">В следующем фрагменте кода показано, как клиентское приложение создает новый канал к существующему экземпляру службы:</span><span class="sxs-lookup"><span data-stu-id="05ca5-109">The following code snippet shows how a client application creates a new channel to an existing service instance:</span></span>

```csharp
// Create a header for the shared instance id
MessageHeader shareableInstanceContextHeader = MessageHeader.CreateHeader(
        CustomHeader.HeaderName,
        CustomHeader.HeaderNamespace,
        Guid.NewGuid().ToString());

// Create the channel factory
ChannelFactory<IEchoService> channelFactory =
    new ChannelFactory<IEchoService>("echoservice");

// Create the first channel
IEchoService proxy = channelFactory.CreateChannel();

// Call an operation to create shared service instance
using (new OperationContextScope((IClientChannel)proxy))
{
    OperationContext.Current.OutgoingMessageHeaders.Add(shareableInstanceContextHeader);
    Console.WriteLine("Service returned: " + proxy.Echo("Apple"));
}

((IChannel)proxy).Close();

// Create the second channel
IEchoService proxy2 = channelFactory.CreateChannel();

// Call an operation using the same header that will reuse the shared service instance
using (new OperationContextScope((IClientChannel)proxy2))
{
    OperationContext.Current.OutgoingMessageHeaders.Add(shareableInstanceContextHeader);
    Console.WriteLine("Service returned: " + proxy2.Echo("Apple"));
}
```

<span data-ttu-id="05ca5-110">В отличие от других режимов создания экземпляров, режим создания общих экземпляров располагает уникальным способом освобождения экземпляров служб.</span><span class="sxs-lookup"><span data-stu-id="05ca5-110">Unlike other instancing modes, the shared instancing mode has a unique way of releasing the service instances.</span></span> <span data-ttu-id="05ca5-111">По умолчанию при закрытии всех каналов для <xref:System.ServiceModel.InstanceContext>, среда выполнения службы WCF проверяет службы <xref:System.ServiceModel.InstanceContextMode> настроен для <xref:System.ServiceModel.InstanceContextMode.PerCall> или <xref:System.ServiceModel.InstanceContextMode.PerSession>и если так освободит экземпляр и объявляет ресурсы.</span><span class="sxs-lookup"><span data-stu-id="05ca5-111">By default, when all the channels are closed for an <xref:System.ServiceModel.InstanceContext>, the WCF service runtime checks to see if the service <xref:System.ServiceModel.InstanceContextMode> is configured to <xref:System.ServiceModel.InstanceContextMode.PerCall> or <xref:System.ServiceModel.InstanceContextMode.PerSession>, and if so releases the instance and claims the resources.</span></span> <span data-ttu-id="05ca5-112">Если пользовательский <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> — используется, то WCF вызывает <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> метод реализации поставщика перед освобождением экземпляра.</span><span class="sxs-lookup"><span data-stu-id="05ca5-112">If a custom <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> is being used, WCF invokes the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method of the provider implementation before releasing the instance.</span></span> <span data-ttu-id="05ca5-113">Если <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> возвращает `true` экземпляр освобождается <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> реализация несет ответственность за уведомление `Dispatcher` о состоянии бездействия с помощью метода обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="05ca5-113">If <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> returns `true` the instance is released, otherwise the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation is responsible for notifying the `Dispatcher` of the idle state by using a callback method.</span></span> <span data-ttu-id="05ca5-114">Это делается путем вызова <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> метода поставщика.</span><span class="sxs-lookup"><span data-stu-id="05ca5-114">This is done by calling the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> method of the provider.</span></span>

<span data-ttu-id="05ca5-115">В этом образце показано, как можно использовать отложенную освобождение <xref:System.ServiceModel.InstanceContext> с время ожидания простоя в 20 секунд.</span><span class="sxs-lookup"><span data-stu-id="05ca5-115">This sample demonstrates how you can delay releasing the <xref:System.ServiceModel.InstanceContext> with an idle timeout of 20 seconds.</span></span>

## <a name="extending-the-instancecontext"></a><span data-ttu-id="05ca5-116">Расширение InstanceContext</span><span class="sxs-lookup"><span data-stu-id="05ca5-116">Extending the InstanceContext</span></span>

<span data-ttu-id="05ca5-117">В WCF <xref:System.ServiceModel.InstanceContext> является каналом между экземпляром службы и `Dispatcher`.</span><span class="sxs-lookup"><span data-stu-id="05ca5-117">In WCF, <xref:System.ServiceModel.InstanceContext> is the link between the service instance and the `Dispatcher`.</span></span> <span data-ttu-id="05ca5-118">WCF позволяет расширять этот компонент среды выполнения путем добавления нового состояния или поведения с помощью шаблона расширяемого объекта.</span><span class="sxs-lookup"><span data-stu-id="05ca5-118">WCF allows you to extend this runtime component by adding new state or behavior by using its extensible object pattern.</span></span> <span data-ttu-id="05ca5-119">Шаблон расширяемого объекта используется в WCF для расширения существующих классов среды выполнения при помощи новых функциональных возможностей или добавления новых возможностей состояния к объекту.</span><span class="sxs-lookup"><span data-stu-id="05ca5-119">The extensible object pattern is used in WCF to either extend existing runtime classes with new functionality or to add new state features to an object.</span></span> <span data-ttu-id="05ca5-120">Предусмотрено три интерфейса в шаблоне расширяемого объекта: <xref:System.ServiceModel.IExtensibleObject%601>, <xref:System.ServiceModel.IExtension%601> и <xref:System.ServiceModel.IExtensionCollection%601>.</span><span class="sxs-lookup"><span data-stu-id="05ca5-120">There are three interfaces in the extensible object pattern: <xref:System.ServiceModel.IExtensibleObject%601>, <xref:System.ServiceModel.IExtension%601>, and <xref:System.ServiceModel.IExtensionCollection%601>.</span></span>

<span data-ttu-id="05ca5-121"><xref:System.ServiceModel.IExtensibleObject%601> Интерфейс реализуется объектами для обеспечения расширений, настраивающих их функциональность.</span><span class="sxs-lookup"><span data-stu-id="05ca5-121">The <xref:System.ServiceModel.IExtensibleObject%601> interface is implemented by objects to allow extensions that customize their functionality.</span></span>

<span data-ttu-id="05ca5-122">Интерфейс <xref:System.ServiceModel.IExtension%601> реализуется объектами, которые могут быть расширениями классов типа `T`.</span><span class="sxs-lookup"><span data-stu-id="05ca5-122">The <xref:System.ServiceModel.IExtension%601> interface is implemented by objects that can be extensions of classes of type `T`.</span></span>

<span data-ttu-id="05ca5-123">И наконец <xref:System.ServiceModel.IExtensionCollection%601> интерфейс — это коллекция <xref:System.ServiceModel.IExtension%601> реализаций, позволяющую реализацию <xref:System.ServiceModel.IExtension%601> по их типу.</span><span class="sxs-lookup"><span data-stu-id="05ca5-123">And finally, the <xref:System.ServiceModel.IExtensionCollection%601> interface is a collection of <xref:System.ServiceModel.IExtension%601> implementations that allows for retrieving an implementation of <xref:System.ServiceModel.IExtension%601> by their type.</span></span>

<span data-ttu-id="05ca5-124">Таким образом Чтобы расширить <xref:System.ServiceModel.InstanceContext>, необходимо реализовать <xref:System.ServiceModel.IExtension%601> интерфейс.</span><span class="sxs-lookup"><span data-stu-id="05ca5-124">Therefore, in order to extend the <xref:System.ServiceModel.InstanceContext>, you must implement the <xref:System.ServiceModel.IExtension%601> interface.</span></span> <span data-ttu-id="05ca5-125">В данном образце проекта `CustomLeaseExtension` эту реализацию содержит класс.</span><span class="sxs-lookup"><span data-stu-id="05ca5-125">In this sample project, the `CustomLeaseExtension` class contains this implementation.</span></span>

```csharp
class CustomLeaseExtension : IExtension<InstanceContext>
{
}
```

<span data-ttu-id="05ca5-126">У интерфейса <xref:System.ServiceModel.IExtension%601> имеется два метода: <xref:System.ServiceModel.IExtension%601.Attach%2A> и <xref:System.ServiceModel.IExtension%601.Detach%2A>.</span><span class="sxs-lookup"><span data-stu-id="05ca5-126">The <xref:System.ServiceModel.IExtension%601> interface has two methods <xref:System.ServiceModel.IExtension%601.Attach%2A> and <xref:System.ServiceModel.IExtension%601.Detach%2A>.</span></span> <span data-ttu-id="05ca5-127">Как видно по их именам, два этих метода вызываются, когда среда выполнения присоединяет и отсоединяет расширение экземпляра класса <xref:System.ServiceModel.InstanceContext>.</span><span class="sxs-lookup"><span data-stu-id="05ca5-127">As their names imply, these two methods are called when the runtime attaches and detaches the extension to an instance of the <xref:System.ServiceModel.InstanceContext> class.</span></span> <span data-ttu-id="05ca5-128">В этом образце метод `Attach` используется для отслеживания объекта <xref:System.ServiceModel.InstanceContext>, который принадлежит текущему экземпляру расширения.</span><span class="sxs-lookup"><span data-stu-id="05ca5-128">In this sample, the `Attach` method is used to keep track of the <xref:System.ServiceModel.InstanceContext> object that belongs to the current instance of the extension.</span></span>

```csharp
InstanceContext owner;

public void Attach(InstanceContext owner)
{
    this.owner = owner;
}
```

<span data-ttu-id="05ca5-129">Кроме того, в расширение необходимо добавить требуемую реализацию, чтобы обеспечить поддержку продленного времени существования.</span><span class="sxs-lookup"><span data-stu-id="05ca5-129">In addition, you must add the necessary implementation to the extension to provide the extended lifetime support.</span></span> <span data-ttu-id="05ca5-130">Таким образом `ICustomLease` интерфейса объявляется с необходимыми методами и реализуется в `CustomLeaseExtension` класса.</span><span class="sxs-lookup"><span data-stu-id="05ca5-130">Therefore, the `ICustomLease` interface is declared with the desired methods and is implemented in the `CustomLeaseExtension` class.</span></span>

```csharp
interface ICustomLease
{
    bool IsIdle { get; }
    InstanceContextIdleCallback Callback { get; set; }
}

class CustomLeaseExtension : IExtension<InstanceContext>, ICustomLease
{
}
```

<span data-ttu-id="05ca5-131">Когда WCF вызывает <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> метод в <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> реализации, этот вызов направляется на <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> метод `CustomLeaseExtension`.</span><span class="sxs-lookup"><span data-stu-id="05ca5-131">When WCF invokes the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method in the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation, this call is routed to the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method of the `CustomLeaseExtension`.</span></span> <span data-ttu-id="05ca5-132">Затем `CustomLeaseExtension` проверяет его закрытое состояние, чтобы увидеть ли <xref:System.ServiceModel.InstanceContext> бездействует.</span><span class="sxs-lookup"><span data-stu-id="05ca5-132">Then, the `CustomLeaseExtension` checks its private state to see whether the <xref:System.ServiceModel.InstanceContext> is idle.</span></span> <span data-ttu-id="05ca5-133">Если он бездействует, он возвращает `true`.</span><span class="sxs-lookup"><span data-stu-id="05ca5-133">If it is idle, it returns `true`.</span></span> <span data-ttu-id="05ca5-134">В противном случае запускается таймер на указанное продленное время существования.</span><span class="sxs-lookup"><span data-stu-id="05ca5-134">Otherwise, it starts a timer for a specified amount of extended lifetime.</span></span>

```csharp
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

<span data-ttu-id="05ca5-135">В таймера `Elapsed` , функция обратного вызова в диспетчере вызова события для запуска другой цикл очистки.</span><span class="sxs-lookup"><span data-stu-id="05ca5-135">In the timer’s `Elapsed` event, the callback function in the Dispatcher is called in order to start another clean-up cycle.</span></span>

```csharp
void idleTimer_Elapsed(object sender, ElapsedEventArgs args)
{
    lock (thisLock)
    {
        StopTimer();
        isIdle = true;
        Utility.WriteMessageToConsole(
            ResourceHelper.GetString("MsgLeaseExpired"));
        callback(owner);
    }
}
```

<span data-ttu-id="05ca5-136">Нет способа для при поступлении нового сообщения для экземпляра, перемещаемого в состояние бездействия, возобновить работающий таймер.</span><span class="sxs-lookup"><span data-stu-id="05ca5-136">There's no way to renew the running timer when a new message arrives for the instance being moved to the idle state.</span></span>

<span data-ttu-id="05ca5-137">Для перехвата вызовов метода <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> и их перенаправления расширению <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> образец реализует `CustomLeaseExtension`.</span><span class="sxs-lookup"><span data-stu-id="05ca5-137">The sample implements <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> to intercept the calls to the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method and route them to the `CustomLeaseExtension`.</span></span> <span data-ttu-id="05ca5-138">Реализация <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> содержится в классе `CustomLifetimeLease`.</span><span class="sxs-lookup"><span data-stu-id="05ca5-138">The <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation is contained in `CustomLifetimeLease` class.</span></span> <span data-ttu-id="05ca5-139"><xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> Метод вызывается, когда WCF собирается освободить экземпляр службы.</span><span class="sxs-lookup"><span data-stu-id="05ca5-139">The <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method is invoked when WCF is about to release the service instance.</span></span> <span data-ttu-id="05ca5-140">Однако в коллекции `ISharedSessionInstance` ServiceBehavior имеется только один экземпляр конкретной реализации <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider>.</span><span class="sxs-lookup"><span data-stu-id="05ca5-140">However, there is only one instance of a particular `ISharedSessionInstance` implementation in the ServiceBehavior’s <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> collection.</span></span> <span data-ttu-id="05ca5-141">Это означает, что никак не знаем <xref:System.ServiceModel.InstanceContext> закрыт во время WCF проверяет <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="05ca5-141">This means there's no way of knowing if the <xref:System.ServiceModel.InstanceContext> is closed at the time WCF checks the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method.</span></span> <span data-ttu-id="05ca5-142">Таким образом, этот образец использует блокировку потока для сериализации запросов <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="05ca5-142">Therefore, this sample uses thread locking to serialize requests to the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="05ca5-143">Использовать блокировку потока не рекомендуется, поскольку сериализация может значительно снизить производительность приложения.</span><span class="sxs-lookup"><span data-stu-id="05ca5-143">Using thread locking is not a recommended approach because serialization can severely affect the performance of your application.</span></span>

<span data-ttu-id="05ca5-144">Закрытое поле элемента используется в `CustomLifetimeLease` класса для отслеживания в состояние бездействия и возвращается функциями <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="05ca5-144">A private member field is used in the `CustomLifetimeLease` class to track the idle state and is returned by the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method.</span></span> <span data-ttu-id="05ca5-145">Каждый раз <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> вызывается метод, `isIdle` возвращается и сбрасывается для поля `false`.</span><span class="sxs-lookup"><span data-stu-id="05ca5-145">Each time the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method is called, the `isIdle` field is returned and reset to `false`.</span></span>  <span data-ttu-id="05ca5-146">Важно задать этому параметру значение `false` с тем, чтобы гарантировать вызов диспетчером метода <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A>.</span><span class="sxs-lookup"><span data-stu-id="05ca5-146">It is essential to set this value to `false` in order to make sure the Dispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> method.</span></span>

```csharp
public bool IsIdle(InstanceContext instanceContext)
{
    get
    {
        lock (thisLock)
        {
            //...
            bool idleCopy = isIdle;
            isIdle = false;
            return idleCopy;
        }
    }
}
```

<span data-ttu-id="05ca5-147">Если <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType> возвращает `false`, то диспетчер регистрирует функцию обратного вызова с помощью <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="05ca5-147">If the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType> method returns `false`, the Dispatcher registers a callback function by using the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> method.</span></span> <span data-ttu-id="05ca5-148">Этот метод получает ссылку на освобождаемый контекст <xref:System.ServiceModel.InstanceContext>.</span><span class="sxs-lookup"><span data-stu-id="05ca5-148">This method receives a reference to the <xref:System.ServiceModel.InstanceContext> being released.</span></span> <span data-ttu-id="05ca5-149">Таким образом, можно запросить пример кода `ICustomLease` введите расширение и проверьте `ICustomLease.IsIdle` свойства в расширенном состоянии.</span><span class="sxs-lookup"><span data-stu-id="05ca5-149">Therefore, the sample code can query the `ICustomLease` type extension and check the `ICustomLease.IsIdle` property in the extended state.</span></span>

```csharp
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

<span data-ttu-id="05ca5-150">Прежде чем `ICustomLease.IsIdle` свойство проверяется, свойство обратного вызова должен задаваться, поскольку оно требуется для `CustomLeaseExtension` для уведомления диспетчера при переходе в состояние бездействия.</span><span class="sxs-lookup"><span data-stu-id="05ca5-150">Before the `ICustomLease.IsIdle` property is checked, the Callback property needs to be set as this is essential for `CustomLeaseExtension` to notify the Dispatcher when it becomes idle.</span></span> <span data-ttu-id="05ca5-151">Если `ICustomLease.IsIdle` возвращает значение `true`, то закрытому элементу `isIdle` в `CustomLifetimeLease` просто устанавливается значение `true` и вызывается метод обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="05ca5-151">If `ICustomLease.IsIdle` returns `true`, the `isIdle` private member is simply set in `CustomLifetimeLease` to `true` and calls the callback method.</span></span> <span data-ttu-id="05ca5-152">Поскольку код содержит блокировку, другие потоки не могут изменить значение этого закрытого элемента.</span><span class="sxs-lookup"><span data-stu-id="05ca5-152">Because the code holds a lock, other threads can't change the value of this private member.</span></span> <span data-ttu-id="05ca5-153">И последующем Dispatcher вызывает <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType>, он возвращает `true` и при этом диспетчер может освободить экземпляр.</span><span class="sxs-lookup"><span data-stu-id="05ca5-153">And the next time Dispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType>, it returns `true` and lets Dispatcher release the instance.</span></span>

<span data-ttu-id="05ca5-154">Завершив подготовительную работу для пользовательского расширения, его необходимо подключить к модели службы.</span><span class="sxs-lookup"><span data-stu-id="05ca5-154">Now that the groundwork for the custom extension is completed, it has to be hooked up to the service model.</span></span> <span data-ttu-id="05ca5-155">Чтобы подключить `CustomLeaseExtension` реализацию <xref:System.ServiceModel.InstanceContext>, WCF предоставляет <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> интерфейс для выполнения начальной загрузки <xref:System.ServiceModel.InstanceContext>.</span><span class="sxs-lookup"><span data-stu-id="05ca5-155">To hook up the `CustomLeaseExtension` implementation to the <xref:System.ServiceModel.InstanceContext>, WCF provides the <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> interface to perform the bootstrapping of <xref:System.ServiceModel.InstanceContext>.</span></span> <span data-ttu-id="05ca5-156">В этом образце класс `CustomLeaseInitializer` реализует этот интерфейс и добавляет экземпляр `CustomLeaseExtension` в коллекцию <xref:System.ServiceModel.InstanceContext.Extensions%2A> из единственной инициализации метода.</span><span class="sxs-lookup"><span data-stu-id="05ca5-156">In the sample, the `CustomLeaseInitializer` class implements this interface and adds an instance of `CustomLeaseExtension` to the <xref:System.ServiceModel.InstanceContext.Extensions%2A> collection from the only method initialization.</span></span> <span data-ttu-id="05ca5-157">Этот метод вызывается диспетчером при инициализации <xref:System.ServiceModel.InstanceContext>.</span><span class="sxs-lookup"><span data-stu-id="05ca5-157">This method is called by Dispatcher while initializing the <xref:System.ServiceModel.InstanceContext>.</span></span>

```csharp
public void InitializeInstanceContext(InstanceContext instanceContext,
    System.ServiceModel.Channels.Message message, IContextChannel channel)

    //...

    IExtension<InstanceContext> customLeaseExtension =
        new CustomLeaseExtension(timeout, headerId);
    instanceContext.Extensions.Add(customLeaseExtension);
}
```

 <span data-ttu-id="05ca5-158">Наконец <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> реализации прикрепленный к модели службы с помощью <xref:System.ServiceModel.Description.IServiceBehavior> реализации.</span><span class="sxs-lookup"><span data-stu-id="05ca5-158">Finally the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation is hooked up to the service model by using the <xref:System.ServiceModel.Description.IServiceBehavior> implementation.</span></span> <span data-ttu-id="05ca5-159">Эта реализация помещается в класс `CustomLeaseTimeAttribute`, кроме того, она является производной от базового класса `Attribute` для предоставления этого поведения в виде атрибута.</span><span class="sxs-lookup"><span data-stu-id="05ca5-159">This implementation is placed in the `CustomLeaseTimeAttribute` class and it also derives from the `Attribute` base class to expose this behavior as an attribute.</span></span>

```csharp
public void ApplyDispatchBehavior(ServiceDescription description,
           ServiceHostBase serviceHostBase)
{
    CustomLifetimeLease customLease = new CustomLifetimeLease(timeout);

    foreach (ChannelDispatcherBase cdb in serviceHostBase.ChannelDispatchers)
    {
        ChannelDispatcher cd = cdb as ChannelDispatcher;

        if (cd != null)
        {
            foreach (EndpointDispatcher ed in cd.Endpoints)
            {
                ed.DispatchRuntime.InstanceContextProvider = customLease;
            }
        }
    }
}
```

<span data-ttu-id="05ca5-160">Это поведение можно добавить в класс образца службы, сопроводив его заметкой в вида атрибута `CustomLeaseTime`.</span><span class="sxs-lookup"><span data-stu-id="05ca5-160">This behavior can be added to a sample service class by annotating it with the `CustomLeaseTime` attribute.</span></span>

```csharp
[CustomLeaseTime(Timeout = 20000)]
public class EchoService : IEchoService
{
  //…
}
```

<span data-ttu-id="05ca5-161">При запуске данного примера запросы и ответы операций отображаются в окнах консоли как службы, так и клиента.</span><span class="sxs-lookup"><span data-stu-id="05ca5-161">When you run the sample, the operation requests and responses are displayed in both the service and client console windows.</span></span> <span data-ttu-id="05ca5-162">Нажмите клавишу ВВОД в каждом окне консоли, чтобы закрыть службу и клиент.</span><span class="sxs-lookup"><span data-stu-id="05ca5-162">Press ENTER in each console window to shut down the service and client.</span></span>

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="05ca5-163">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="05ca5-163">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="05ca5-164">Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="05ca5-164">Ensure that you've performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="05ca5-165">Чтобы создать выпуск решения на C# или Visual Basic .NET, следуйте инструкциям в [сборка образцов Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="05ca5-165">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="05ca5-166">Чтобы выполнить образец на одном или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="05ca5-166">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="05ca5-167">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="05ca5-167">The samples may already be installed on your machine.</span></span> <span data-ttu-id="05ca5-168">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="05ca5-168">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="05ca5-169">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="05ca5-169">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="05ca5-170">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="05ca5-170">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Lifetime`
