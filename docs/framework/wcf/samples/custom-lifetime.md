---
title: Настраиваемое время существования
ms.date: 08/20/2018
ms.assetid: 52806c07-b91c-48fe-b992-88a41924f51f
ms.openlocfilehash: 8625877d9b4d05d5cf06af2c9f8ef10f701e98db
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715470"
---
# <a name="custom-lifetime"></a>Настраиваемое время существования

В этом примере демонстрируется написание расширения Windows Communication Foundation (WCF) для предоставления служб времени жизни для общих экземпляров службы WCF.

> [!NOTE]
> Процедура настройки и инструкции по построению для данного примера приведены в конце этого раздела.

## <a name="shared-instancing"></a>Общий создание экземпляров

WCF предлагает несколько режимов создания экземпляров для экземпляров службы. Режим совместного создания экземпляров, описанный в этой статье, предоставляет способ совместного использования экземпляра службы несколькими каналами. Клиенты могут обратиться к методу фабрики в службе и создать новый канал для запуска обмена данными. В следующем фрагменте кода показано, как клиентское приложение создает новый канал для существующего экземпляра службы:

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

В отличие от других режимов создания экземпляров, режим создания общих экземпляров располагает уникальным способом освобождения экземпляров служб. По умолчанию, когда все каналы закрываются для <xref:System.ServiceModel.InstanceContext>, среда выполнения службы WCF проверяет, настроена ли <xref:System.ServiceModel.InstanceContextMode> службы на <xref:System.ServiceModel.InstanceContextMode.PerCall> или <xref:System.ServiceModel.InstanceContextMode.PerSession>, и, если это так, выпустит экземпляр и заявляет ресурсы. Если используется настраиваемый <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider>, WCF вызывает метод <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> реализации поставщика перед освобождением экземпляра. Если <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> возвращает `true` экземпляр освобождается, в противном случае <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> реализация отвечает за уведомление `Dispatcher` состояния простоя с помощью метода обратного вызова. Это делается путем вызова метода <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> поставщика.

В этом примере показано, как можно отложить освобождение <xref:System.ServiceModel.InstanceContext> с временем ожидания простоя 20 секунд.

## <a name="extending-the-instancecontext"></a>Расширение InstanceContext

В WCF <xref:System.ServiceModel.InstanceContext> является связью между экземпляром службы и `Dispatcher`. WCF позволяет расширить этот компонент среды выполнения, добавив новое состояние или поведение, используя его расширяемый шаблон объектов. Шаблон расширяемого объекта используется в WCF для расширения существующих классов среды выполнения с новыми функциональными возможностями или для добавления новых функций состояния в объект. Предусмотрено три интерфейса в шаблоне расширяемого объекта: <xref:System.ServiceModel.IExtensibleObject%601>, <xref:System.ServiceModel.IExtension%601> и <xref:System.ServiceModel.IExtensionCollection%601>.

Интерфейс <xref:System.ServiceModel.IExtensibleObject%601> реализуется объектами, чтобы разрешить расширения, которые настраивают их функциональность.

Интерфейс <xref:System.ServiceModel.IExtension%601> реализуется объектами, которые могут быть расширениями классов типа `T`.

И наконец, интерфейс <xref:System.ServiceModel.IExtensionCollection%601> представляет собой коллекцию реализаций <xref:System.ServiceModel.IExtension%601>, которые позволяют получить реализацию <xref:System.ServiceModel.IExtension%601> по типу.

Таким образом, чтобы расширить <xref:System.ServiceModel.InstanceContext>, необходимо реализовать интерфейс <xref:System.ServiceModel.IExtension%601>. В этом примере проекта класс `CustomLeaseExtension` содержит эту реализацию.

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

Кроме того, в расширение необходимо добавить требуемую реализацию, чтобы обеспечить поддержку продленного времени существования. Таким образом, интерфейс `ICustomLease` объявляется с нужными методами и реализуется в классе `CustomLeaseExtension`.

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

Когда WCF вызывает метод <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> в реализации <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider>, этот вызов направляется методу <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> `CustomLeaseExtension`. Затем `CustomLeaseExtension` проверяет свое частное состояние, чтобы определить, является ли <xref:System.ServiceModel.InstanceContext> бездействием. Если он бездействует, возвращается `true`. В противном случае запускается таймер на указанное продленное время существования.

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

В событии `Elapsed` таймера функция обратного вызова в Dispatcher вызывается для запуска другого цикла очистки.

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

Невозможно продлить выполняющийся таймер, когда поступит новое сообщение для перемещения экземпляра в состояние простоя.

Для перехвата вызовов метода <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> и их перенаправления расширению <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> образец реализует `CustomLeaseExtension`. Реализация <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> содержится в классе `CustomLifetimeLease`. Метод <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> вызывается, когда WCF собирается освободить экземпляр службы. Однако в коллекции `ISharedSessionInstance` ServiceBehavior имеется только один экземпляр конкретной реализации <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider>. Это означает, что не существует способа узнать, закрывается ли <xref:System.ServiceModel.InstanceContext> в момент, когда WCF проверяет метод <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>. Поэтому в этом примере используется блокировка потока для сериализации запросов в метод <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>.

> [!IMPORTANT]
> Использовать блокировку потока не рекомендуется, поскольку сериализация может значительно снизить производительность приложения.

Поле закрытого члена используется в классе `CustomLifetimeLease` для отслеживания состояния простоя и возврата методом <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>. При каждом вызове метода <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> возвращается поле `isIdle` и сбрасывается в `false`.  Важно задать этому параметру значение `false` с тем, чтобы гарантировать вызов диспетчером метода <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A>.

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

Если метод <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType> возвращает `false`, диспетчер регистрирует функцию обратного вызова с помощью метода <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A>. Этот метод получает ссылку на освобождаемый контекст <xref:System.ServiceModel.InstanceContext>. Поэтому пример кода может запросить расширение типа `ICustomLease` и проверить свойство `ICustomLease.IsIdle` в расширенном состоянии.

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

Перед установкой свойства `ICustomLease.IsIdle` необходимо установить свойство обратного вызова, так как это важно для `CustomLeaseExtension` уведомления Dispatcher о состоянии простоя. Если `ICustomLease.IsIdle` возвращает значение `true`, то закрытому элементу `isIdle` в `CustomLifetimeLease` просто устанавливается значение `true` и вызывается метод обратного вызова. Так как код удерживает блокировку, другие потоки не могут изменить значение этого закрытого члена. И при следующем вызове диспетчера вызывается <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType>, он возвращает `true` и позволяет диспетчеру освободить экземпляр.

Завершив подготовительную работу для пользовательского расширения, его необходимо подключить к модели службы. Чтобы подключить `CustomLeaseExtension`ную реализацию к <xref:System.ServiceModel.InstanceContext>, WCF предоставляет интерфейс <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> для выполнения начальной загрузки <xref:System.ServiceModel.InstanceContext>. В этом образце класс `CustomLeaseInitializer` реализует этот интерфейс и добавляет экземпляр `CustomLeaseExtension` в коллекцию <xref:System.ServiceModel.InstanceContext.Extensions%2A> из единственной инициализации метода. Этот метод вызывается диспетчером при инициализации <xref:System.ServiceModel.InstanceContext>.

```csharp
public void InitializeInstanceContext(InstanceContext instanceContext,
    System.ServiceModel.Channels.Message message, IContextChannel channel)

    //...

    IExtension<InstanceContext> customLeaseExtension =
        new CustomLeaseExtension(timeout, headerId);
    instanceContext.Extensions.Add(customLeaseExtension);
}
```

 Наконец, <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider>ная реализация подключена к модели службы с помощью реализации <xref:System.ServiceModel.Description.IServiceBehavior>. Эта реализация помещается в класс `CustomLeaseTimeAttribute`, кроме того, она является производной от базового класса <xref:System.Attribute> для предоставления этого поведения в виде атрибута.

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

1. Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](one-time-setup-procedure-for-the-wcf-samples.md).

2. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](building-the-samples.md).

3. Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](running-the-samples.md).

> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Lifetime`
