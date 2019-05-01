---
title: Пользовательские службы времени существования
ms.date: 08/20/2018
ms.assetid: 52806c07-b91c-48fe-b992-88a41924f51f
ms.openlocfilehash: be6013d568e3625c5eac7e0c145db7df1c6917e3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62003169"
---
# <a name="custom-lifetime"></a>Пользовательские службы времени существования

В этом примере показано, как написать расширение Windows Communication Foundation (WCF) для предоставления пользовательских служб времени существования для общих экземпляров службы WCF.

> [!NOTE]
> Процедура настройки и инструкции по построению для данного примера приведены в конце этого раздела.

## <a name="shared-instancing"></a>Создание общих экземпляров

WCF предлагает несколько режимов создания экземпляров служб. Режим создания общих экземпляров в этой статье рассматриваются предоставляет способ совместного использования экземпляра службы несколькими каналами. Клиенты смогут обратиться к методу производства в службе и создать новый канал, чтобы начать обмен данными. В следующем фрагменте кода показано, как клиентское приложение создает новый канал к существующему экземпляру службы:

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

В отличие от других режимов создания экземпляров, режим создания общих экземпляров располагает уникальным способом освобождения экземпляров служб. По умолчанию при закрытии всех каналов для <xref:System.ServiceModel.InstanceContext>, среда выполнения службы WCF проверяет службы <xref:System.ServiceModel.InstanceContextMode> настроен для <xref:System.ServiceModel.InstanceContextMode.PerCall> или <xref:System.ServiceModel.InstanceContextMode.PerSession>и если так освободит экземпляр и объявляет ресурсы. Если пользовательский <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> — используется, то WCF вызывает <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> метод реализации поставщика перед освобождением экземпляра. Если <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> возвращает `true` экземпляр освобождается <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> реализация несет ответственность за уведомление `Dispatcher` о состоянии бездействия с помощью метода обратного вызова. Это делается путем вызова <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> метода поставщика.

В этом образце показано, как можно использовать отложенную освобождение <xref:System.ServiceModel.InstanceContext> с время ожидания простоя в 20 секунд.

## <a name="extending-the-instancecontext"></a>Расширение InstanceContext

В WCF <xref:System.ServiceModel.InstanceContext> является каналом между экземпляром службы и `Dispatcher`. WCF позволяет расширять этот компонент среды выполнения путем добавления нового состояния или поведения с помощью шаблона расширяемого объекта. Шаблон расширяемого объекта используется в WCF для расширения существующих классов среды выполнения при помощи новых функциональных возможностей или добавления новых возможностей состояния к объекту. Предусмотрено три интерфейса в шаблоне расширяемого объекта: <xref:System.ServiceModel.IExtensibleObject%601>, <xref:System.ServiceModel.IExtension%601> и <xref:System.ServiceModel.IExtensionCollection%601>.

<xref:System.ServiceModel.IExtensibleObject%601> Интерфейс реализуется объектами для обеспечения расширений, настраивающих их функциональность.

Интерфейс <xref:System.ServiceModel.IExtension%601> реализуется объектами, которые могут быть расширениями классов типа `T`.

И наконец <xref:System.ServiceModel.IExtensionCollection%601> интерфейс — это коллекция <xref:System.ServiceModel.IExtension%601> реализаций, позволяющую реализацию <xref:System.ServiceModel.IExtension%601> по их типу.

Таким образом Чтобы расширить <xref:System.ServiceModel.InstanceContext>, необходимо реализовать <xref:System.ServiceModel.IExtension%601> интерфейс. В данном образце проекта `CustomLeaseExtension` эту реализацию содержит класс.

```csharp
class CustomLeaseExtension : IExtension<InstanceContext>
{
}
```

У интерфейса <xref:System.ServiceModel.IExtension%601> имеется два метода: <xref:System.ServiceModel.IExtension%601.Attach%2A> и <xref:System.ServiceModel.IExtension%601.Detach%2A>. Как видно по их именам, два этих метода вызываются, когда среда выполнения присоединяет и отсоединяет расширение экземпляра класса <xref:System.ServiceModel.InstanceContext>. В этом образце метод `Attach` используется для отслеживания объекта <xref:System.ServiceModel.InstanceContext>, который принадлежит текущему экземпляру расширения.

```csharp
InstanceContext owner;

public void Attach(InstanceContext owner)
{
    this.owner = owner;
}
```

Кроме того, в расширение необходимо добавить требуемую реализацию, чтобы обеспечить поддержку продленного времени существования. Таким образом `ICustomLease` интерфейса объявляется с необходимыми методами и реализуется в `CustomLeaseExtension` класса.

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

Когда WCF вызывает <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> метод в <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> реализации, этот вызов направляется на <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> метод `CustomLeaseExtension`. Затем `CustomLeaseExtension` проверяет его закрытое состояние, чтобы увидеть ли <xref:System.ServiceModel.InstanceContext> бездействует. Если он бездействует, он возвращает `true`. В противном случае запускается таймер на указанное продленное время существования.

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

В таймера `Elapsed` , функция обратного вызова в диспетчере вызова события для запуска другой цикл очистки.

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

Нет способа для при поступлении нового сообщения для экземпляра, перемещаемого в состояние бездействия, возобновить работающий таймер.

Для перехвата вызовов метода <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> и их перенаправления расширению <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> образец реализует `CustomLeaseExtension`. Реализация <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> содержится в классе `CustomLifetimeLease`. <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> Метод вызывается, когда WCF собирается освободить экземпляр службы. Однако в коллекции `ISharedSessionInstance` ServiceBehavior имеется только один экземпляр конкретной реализации <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider>. Это означает, что никак не знаем <xref:System.ServiceModel.InstanceContext> закрыт во время WCF проверяет <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> метод. Таким образом, этот образец использует блокировку потока для сериализации запросов <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> метод.

> [!IMPORTANT]
> Использовать блокировку потока не рекомендуется, поскольку сериализация может значительно снизить производительность приложения.

Закрытое поле элемента используется в `CustomLifetimeLease` класса для отслеживания в состояние бездействия и возвращается функциями <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> метод. Каждый раз <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> вызывается метод, `isIdle` возвращается и сбрасывается для поля `false`.  Важно задать этому параметру значение `false` с тем, чтобы гарантировать вызов диспетчером метода <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A>.

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

Если <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType> возвращает `false`, то диспетчер регистрирует функцию обратного вызова с помощью <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> метод. Этот метод получает ссылку на освобождаемый контекст <xref:System.ServiceModel.InstanceContext>. Таким образом, можно запросить пример кода `ICustomLease` введите расширение и проверьте `ICustomLease.IsIdle` свойства в расширенном состоянии.

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

Прежде чем `ICustomLease.IsIdle` свойство проверяется, свойство обратного вызова должен задаваться, поскольку оно требуется для `CustomLeaseExtension` для уведомления диспетчера при переходе в состояние бездействия. Если `ICustomLease.IsIdle` возвращает значение `true`, то закрытому элементу `isIdle` в `CustomLifetimeLease` просто устанавливается значение `true` и вызывается метод обратного вызова. Поскольку код содержит блокировку, другие потоки не могут изменить значение этого закрытого элемента. И последующем Dispatcher вызывает <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType>, он возвращает `true` и при этом диспетчер может освободить экземпляр.

Завершив подготовительную работу для пользовательского расширения, его необходимо подключить к модели службы. Чтобы подключить `CustomLeaseExtension` реализацию <xref:System.ServiceModel.InstanceContext>, WCF предоставляет <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> интерфейс для выполнения начальной загрузки <xref:System.ServiceModel.InstanceContext>. В этом образце класс `CustomLeaseInitializer` реализует этот интерфейс и добавляет экземпляр `CustomLeaseExtension` в коллекцию <xref:System.ServiceModel.InstanceContext.Extensions%2A> из единственной инициализации метода. Этот метод вызывается диспетчером при инициализации <xref:System.ServiceModel.InstanceContext>.

```csharp
public void InitializeInstanceContext(InstanceContext instanceContext,
    System.ServiceModel.Channels.Message message, IContextChannel channel)

    //...

    IExtension<InstanceContext> customLeaseExtension =
        new CustomLeaseExtension(timeout, headerId);
    instanceContext.Extensions.Add(customLeaseExtension);
}
```

 Наконец <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> реализации прикрепленный к модели службы с помощью <xref:System.ServiceModel.Description.IServiceBehavior> реализации. Эта реализация помещается в класс `CustomLeaseTimeAttribute`, кроме того, она является производной от базового класса <xref:System.Attribute> для предоставления этого поведения в виде атрибута.

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

Это поведение можно добавить в класс образца службы, сопроводив его заметкой в вида атрибута `CustomLeaseTime`.

```csharp
[CustomLeaseTime(Timeout = 20000)]
public class EchoService : IEchoService
{
  //…
}
```

При запуске данного примера запросы и ответы операций отображаются в окнах консоли как службы, так и клиента. Нажмите клавишу ВВОД в каждом окне консоли, чтобы закрыть службу и клиент.

### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца

1. Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).

2. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](building-the-samples.md).

3. Чтобы выполнить образец на одном или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](running-the-samples.md).

> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Lifetime`
