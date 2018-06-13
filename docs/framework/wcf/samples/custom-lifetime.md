---
title: Пользовательские службы времени существования
ms.date: 03/30/2017
ms.assetid: 52806c07-b91c-48fe-b992-88a41924f51f
ms.openlocfilehash: e41c970739b8036730fa601433ce7157e01d7e19
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33809307"
---
# <a name="custom-lifetime"></a>Пользовательские службы времени существования
В этом примере показано, как написать расширение Windows Communication Foundation (WCF) для предоставления пользовательских служб времени существования для общих экземпляров службы WCF.  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
## <a name="shared-instancing"></a>Создание общих экземпляров  
 WCF предлагает несколько режимов создания экземпляров служб. Режим создания общих экземпляров, описанный в этом разделе, предоставляет способ совместного использования экземпляра службы несколькими каналами. Клиенты могут разрешать адрес конечной точки экземпляра локально или обращаться к методу производства в службе, чтобы получить адрес конечной точки работающего экземпляра. Получив адрес конечной точки, клиент может создать новый канал и начать обмен данными. Следующий фрагмент кода показывает, как клиентское приложение создает новый канал к существующему экземпляру службы.  
  
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
  
 В отличие от других режимов создания экземпляров, режим создания общих экземпляров располагает уникальным способом освобождения экземпляров служб. Когда для экземпляра закрыты все каналы, среда выполнения службы WCF запускает таймер. Если никто не установит соединение до истечения времени ожидания, WCF освободит экземпляр и вернет себе ресурсы. В рамках процедуры демонтажа WCF вызывает <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> метод всех <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> реализации перед освобождением экземпляра. Если все они возвратят значение `true`, экземпляр будет освобожден. В противном случае реализация <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> отвечает за уведомление `Dispatcher` о состоянии бездействия с помощью метода обратного вызова.  
  
 По умолчанию значение времени ожидания состояния бездействия <xref:System.ServiceModel.InstanceContext> равно одной минуте. Однако в этом образце показано, как его можно продлить с помощью пользовательского расширения.  
  
## <a name="extending-the-instancecontext"></a>Расширение InstanceContext  
 В WCF <xref:System.ServiceModel.InstanceContext> связывает экземпляр службы и `Dispatcher`. WCF позволяет вам расширять данный компонент времени выполнения путем добавления нового состояния или поведения с помощью шаблона расширяемого объекта. Шаблон расширяемого объекта используется в WCF для расширения существующих классов среды выполнения при помощи новых функциональных возможностей или добавления новых возможностей состояния к объекту. Предусмотрено три интерфейса в шаблоне расширяемого объекта: `IExtensibleObject<T>`, `IExtension<T>` и `IExtensionCollection<T>`.  
  
 Интерфейс `IExtensibleObject<T>` реализуется объектами для обеспечения расширений, которые настраивают их функциональность.  
  
 Интерфейс `IExtension<T>` реализуется объектами, которые могут быть расширениями классов типа `T`.  
  
 И наконец, интерфейс `IExtensionCollection<T>` является коллекцией `IExtensions`, которая позволяет получать `IExtensions` по их типу.  
  
 Поэтому, чтобы расширить контекст <xref:System.ServiceModel.InstanceContext>, требуется реализовать интерфейс `IExtension`. В данном образце проекта эту реализацию содержит класс `CustomLeaseExtension`.  
  
```  
class CustomLeaseExtension : IExtension<InstanceContext>  
{  
}  
```  
  
 У интерфейса `IExtension` имеется два метода: `Attach` и `Detach`. Как видно по их именам, два этих метода вызываются, когда среда выполнения присоединяет и отсоединяет расширение экземпляра класса <xref:System.ServiceModel.InstanceContext>. В этом образце метод `Attach` используется для отслеживания объекта <xref:System.ServiceModel.InstanceContext>, который принадлежит текущему экземпляру расширения.  
  
```  
InstanceContext owner;  
  
public void Attach(InstanceContext owner)  
{  
  this.owner = owner;   
}  
```  
  
 Кроме того, в расширение необходимо добавить требуемую реализацию, чтобы обеспечить поддержку продленного времени существования. Поэтому интерфейс `ICustomLease` объявляется с необходимыми методами и реализуется в классе `CustomLeaseExtension`.  
  
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
  
 Когда WCF вызывает <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> метод в <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> этот вызов направляется в реализации <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> метод `CustomLeaseExtension`. Затем расширение `CustomLeaseExtension` проверяет его закрытое состояние, чтобы определить, бездействует ли контекст <xref:System.ServiceModel.InstanceContext>. Если контекст бездействует, то возвращается значение `true`. В противном случае запускается таймер на указанное продленное время существования.  
  
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
  
 В рамках события `Elapsed` таймера вызывается функция обратного вызова в диспетчере, чтобы запустить еще один цикл очистки.  
  
```  
void idleTimer_Elapsed(object sender, ElapsedEventArgs args)  
{  
    idleTimer.Stop();  
    isIdle = true;    
    callback(owner);  
}  
```  
  
 При поступлении нового сообщения для экземпляра, перемещаемого в состояние бездействия, возобновить работающий таймер невозможно.  
  
 Для перехвата вызовов метода <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> и их перенаправления расширению <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> образец реализует `CustomLeaseExtension`. Реализация <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> содержится в классе `CustomLifetimeLease`. <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> Метод вызывается, когда WCF собирается освободить экземпляр службы. Однако в коллекции `ISharedSessionInstance` ServiceBehavior имеется только один экземпляр конкретной реализации <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider>. Это означает, что нет способа узнать <xref:System.ServiceModel.InstanceContext> закрыт во время проверки WCF <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> метод. Поэтому этот образец использует блокировку потока для сериализации запросов в метод <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A>.  
  
> [!IMPORTANT]
>  Использовать блокировку потока не рекомендуется, поскольку сериализация может значительно снизить производительность приложения.  
  
 Для отслеживания значения `CustomLeaseExtension` в классе `IsIdle` используется переменная закрытого элемента. Каждый раз при получении значения <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> закрытый элемент `IsIdle` возвращается и сбрасывается в значение `false`. Важно задать этому параметру значение `false` с тем, чтобы гарантировать вызов диспетчером метода <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A>.  
  
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
  
 Если свойство `ISharedSessionLifetime.IsIdle` возвращает значение `false`, то диспетчер регистрирует функцию обратного вызова с помощью метода `NotifyIdle`. Этот метод получает ссылку на освобождаемый контекст <xref:System.ServiceModel.InstanceContext>. Поэтому образец кода может запросить расширение типа `ICustomLease` и проверить свойство `ICustomLease.IsIdle` в расширенном состоянии.  
  
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
  
 Перед проверкой свойства `ICustomLease.IsIdle` необходимо задать значение свойства Callback, поскольку оно требуется `CustomLeaseExtension` для уведомления диспетчера при переходе в состояние бездействия. Если `ICustomLease.IsIdle` возвращает значение `true`, то закрытому элементу `isIdle` в `CustomLifetimeLease` просто устанавливается значение `true` и вызывается метод обратного вызова. Поскольку код содержит блокировку, другие потоки не могут изменить значение этого закрытого элемента. При следующей проверке диспетчером `ISharedSessionLifetime.IsIdle` возвращается значение `true`, при этом диспетчер может освободить экземпляр.  
  
 Завершив подготовительную работу для пользовательского расширения, его необходимо подключить к модели службы. Чтобы подключить `CustomLeaseExtension` реализации <xref:System.ServiceModel.InstanceContext>, WCF предоставляет <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> интерфейс для выполнения начальной загрузки <xref:System.ServiceModel.InstanceContext>. В этом образце класс `CustomLeaseInitializer` реализует этот интерфейс и добавляет экземпляр `CustomLeaseExtension` в коллекцию <xref:System.ServiceModel.InstanceContext.Extensions%2A> из единственной инициализации метода. Этот метод вызывается диспетчером при инициализации <xref:System.ServiceModel.InstanceContext>.  
  
```  
public void Initialize(InstanceContext instanceContext, Message message)  
{  
  IExtension<InstanceContext> customLeaseExtension =  
    new CustomLeaseExtension(timeout);  
  instanceContext.Extensions.Add(customLeaseExtension);  
}  
```  
  
 Наконец `System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime` и <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> реализаций — изогнутыми до модели службы с помощью <xref:System.ServiceModel.Description.IServiceBehavior> реализации. Эта реализация помещается в класс `CustomLeaseTimeAttribute`, кроме того, она является производной от базового класса `Attribute` для предоставления этого поведения в виде атрибута. В методе `IServiceBehavior.ApplyBehavior` экземпляры реализаций <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> и `System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime` добавляются в коллекции `System.ServiceModel.Dispatcher.DispatchRuntime.InstanceContextLifetimes` и <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceContextInitializers%2A> диспетчера <xref:System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime> соответственно.  
  
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
  
 Это поведение можно добавить в класс образца службы, сопроводив его заметкой в вида атрибута `CustomLeaseTime`.  
  
```  
[ServiceBehavior(InstanceContextMode=InstanceContextMode.Shareable)]  
[CustomLeaseTime(Timeout = 20000)]  
public class EchoService : IEchoService  
{  
  //…  
}  
```  
  
 При запуске данного примера запросы и ответы операций отображаются в окнах консоли как службы, так и клиента. Нажмите клавишу ВВОД в каждом окне консоли, чтобы закрыть службу и клиент.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Для запуска образца в конфигурации одного или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Lifetime`  
  
## <a name="see-also"></a>См. также
