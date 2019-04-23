---
title: Pooling
ms.date: 03/30/2017
ms.assetid: 688dfb30-b79a-4cad-a687-8302f8a9ad6a
ms.openlocfilehash: f4df661ad5d831158da55fe3890805ccc5cd695f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59307214"
---
# <a name="pooling"></a>Pooling
Этот образец демонстрирует расширение Windows Communication Foundation (WCF) для поддержки создания пулов объектов. Этот образец демонстрирует, как создать атрибут, синтаксически и семантически аналогичный функциям атрибута `ObjectPoolingAttribute` служб Enterprise Services. Использование пулов объектов может значительно повысить производительность приложения. Однако при неправильном использовании эффект может быть противоположным. Использование пулов объектов позволяет снизить накладные расходы на повторное создание часто используемых объектов, требующих большого объема инициализации. Однако если завершение вызова метода для объекта из пула занимает много времени, сразу после достижения максимального размера пула функция пулов объектов ставит дополнительные запросы в очередь. В результате возможен сбой обслуживания запросов создания некоторых объектов из-за возникновения исключения времени ожидания.  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 Создание расширения WCF первым делом следует точки расширяемости будут использоваться.  
  
 В WCF термин *dispatcher* относится к компоненту времени выполнения отвечает за преобразование входящих сообщений в вызовы метода в службе пользователя и для преобразования значения, возвращаемые из этого метода в исходящие сообщения. Службы WCF создает диспетчер для каждой конечной точки. Клиент WCF необходимо использовать диспетчер, если контракт, связанный с этим клиентом является дуплексным контрактом.  
  
 Диспетчеры каналов и конечных точек обеспечивают расширяемость на уровне канала и контракта, предоставляя различные свойства, которые управляют поведением диспетчера. Свойство <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.DispatchRuntime%2A> также позволяет контролировать, изменять или настраивать диспетчерский процесс. В этом образце рассматривается свойство <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A>, которое указывает на объект, предоставляющий экземпляры класса службы.  
  
## <a name="the-iinstanceprovider"></a>IInstanceProvider  
 В WCF, диспетчер создает экземпляры класса службы с помощью <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A>, который реализует <xref:System.ServiceModel.Dispatcher.IInstanceProvider> интерфейс. У этого интерфейса есть три метода.  
  
-   <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29>: Когда прибывает сообщение Dispatcher вызывает <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29> метод для создания экземпляра класса службы для обработки сообщения. Частота вызовов этого метода определяется свойством <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>. Например, если свойство <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> имеет значение <xref:System.ServiceModel.InstanceContextMode.PerCall>, для обработки каждого получаемого сообщения создается новый экземпляр класса службы, поэтому метод <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29> вызывается каждый раз, когда приходит сообщение.  
  
-   <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%29>: Это идентичен предыдущему методу, за исключением того, вызывается при отсутствии аргумента Message.  
  
-   <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%28System.ServiceModel.InstanceContext%2CSystem.Object%29>: При истечении времени существования экземпляра службы, Dispatcher вызывает <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%28System.ServiceModel.InstanceContext%2CSystem.Object%29> метод. Как и в случае метода <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29>, частота вызовов этого метода определяется свойством <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>.  
  
## <a name="the-object-pool"></a>Пул объектов  
 Пользовательская реализация <xref:System.ServiceModel.Dispatcher.IInstanceProvider> обеспечивает необходимую семантику пула объектов для службы. Поэтому в образце имеется тип `ObjectPoolingInstanceProvider`, который предоставляет пользовательскую реализацию интерфейса <xref:System.ServiceModel.Dispatcher.IInstanceProvider> для создания пула. Когда `Dispatcher` вызывает метод <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29>, пользовательская реализация вместо создания нового экземпляра ищет существующий объект в находящемся в памяти пуле. Если такой объект доступен, метод возвращает его. В противном случае создается новый объект. Реализация метода `GetInstance` показана в следующем образце кода.  
  
```  
object IInstanceProvider.GetInstance(InstanceContext instanceContext, Message message)  
{  
    object obj = null;  
  
    lock (poolLock)  
    {  
        if (pool.Count > 0)  
        {  
            obj = pool.Pop();  
        }  
        else  
        {  
            obj = CreateNewPoolObject();  
        }  
        activeObjectsCount++;  
    }  
  
    WritePoolMessage(ResourceHelper.GetString("MsgNewObject"));  
  
    idleTimer.Stop();  
  
    return obj;            
}  
```  
  
 Пользовательская реализация `ReleaseInstance` добавляет освободившийся экземпляр обратно в пул и уменьшает значение `ActiveObjectsCount` на единицу. `Dispatcher` может вызывать эти методы из различных потоков, поэтому требуется синхронизированный доступ к членам уровня класса в классе `ObjectPoolingInstanceProvider`.  
  
```  
void IInstanceProvider.ReleaseInstance(InstanceContext instanceContext, object instance)  
{  
    lock (poolLock)  
    {  
        pool.Push(instance);  
        activeObjectsCount--;  
  
        WritePoolMessage(  
        ResourceHelper.GetString("MsgObjectPooled"));  
  
        // When the service goes completely idle (no requests   
        // are being processed), the idle timer is started  
        if (activeObjectsCount == 0)  
            idleTimer.Start();                       
    }  
}  
```  
  
 `ReleaseInstance` Метод предоставляет возможность «инициализации с очисткой». Обычно пул поддерживает минимальное число объектов в течение времени существования пула. Однако возможны периоды интенсивного использования, когда требуется создавать в пуле дополнительные объекты, пока не будет достигнуто заданное в конфигурации максимальное значение. В конце концов, когда активность пула снизится, эти дополнительные объекты могут стать излишней нагрузкой. Поэтому когда значение `activeObjectsCount` достигает нуля, запускается таймер бездействия, по истечении времени ожидания которого выполняется цикл очистки.  
  
## <a name="adding-the-behavior"></a>Добавление поведения  
 Расширения уровня диспетчера подключаются с помощью следующих поведений.  
  
-   Поведения служб. Позволяют настраивать всю среду выполнения службы.  
  
-   Поведения конечных точек. Позволяют настраивать конечные точки службы, включая диспетчера каналов и конечных точек.  
  
-   Поведения контрактов. Эти поведения позволяют настраивать классы <xref:System.ServiceModel.Dispatcher.ClientRuntime> и <xref:System.ServiceModel.Dispatcher.DispatchRuntime> в клиенте и службе соответственно.  
  
 С целью реализации расширения создания пулов объектов должно быть создано поведение службы. Поведения служб создаются путем реализации интерфейса <xref:System.ServiceModel.Description.IServiceBehavior>. Имеется несколько способов сообщить модели службы о пользовательских поведениях:  
  
-   с помощью пользовательского атрибута;  
  
-   путем ее императивного добавления в коллекцию поведений описания службы;  
  
-   путем расширения файла конфигурации.  
  
 В этом образце используется пользовательский атрибут. При создании <xref:System.ServiceModel.ServiceHost> проверяются атрибуты, используемые в определении типа службы, а в коллекцию поведений описания службы добавляются доступные поведения.  
  
 У интерфейса <xref:System.ServiceModel.Description.IServiceBehavior> имеется три метода — <xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A>, <xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A> и <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A>. Метод <xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A> используется для обеспечения того, что поведение может быть применено к службе. В этом образце реализация обеспечивает, что служба не настраивается с <xref:System.ServiceModel.InstanceContextMode.Single>. Метод <xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A> используется для настройки привязок службы. Это не требуется в данном сценарии. Метод <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A> используется для настройки диспетчеров службы. Этот метод вызывается платформой WCF при <xref:System.ServiceModel.ServiceHost> выполняется инициализация. Этому методу передаются следующие параметры.  
  
-   `Description`: Этот аргумент содержит описание службы для всей службы. Его можно использовать для проверки данных описания о конечных точках, контрактах и привязках службы, а также других данных.  
  
-   `ServiceHostBase`: Этот аргумент содержит <xref:System.ServiceModel.ServiceHostBase> , настоящее время инициализируется.  
  
 В пользовательской реализации <xref:System.ServiceModel.Description.IServiceBehavior> создается новый экземпляр `ObjectPoolingInstanceProvider`, который присваивается свойству <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A> в каждом объекте <xref:System.ServiceModel.Dispatcher.DispatchRuntime> в ServiceHostBase.  
  
```  
void IServiceBehavior.ApplyDispatchBehavior(ServiceDescription description, ServiceHostBase serviceHostBase)  
{  
    // Create an instance of the ObjectPoolInstanceProvider.  
    ObjectPoolingInstanceProvider instanceProvider = new  
           ObjectPoolingInstanceProvider(description.ServiceType,   
                                                    minPoolSize);  
  
    // Forward the call if we created a ServiceThrottlingBehavior.  
    if (this.throttlingBehavior != null)  
    {  
        ((IServiceBehavior)this.throttlingBehavior).ApplyDispatchBehavior(description, serviceHostBase);  
    }  
  
    // In case there was already a ServiceThrottlingBehavior   
    // (this.throttlingBehavior==null), it should have initialized   
    // a single ServiceThrottle on all ChannelDispatchers.    
    // As we loop through the ChannelDispatchers, we verify that   
    // and modify the ServiceThrottle to guard MaxPoolSize.  
    ServiceThrottle throttle = null;  
  
    foreach (ChannelDispatcherBase cdb in   
            serviceHostBase.ChannelDispatchers)  
    {  
        ChannelDispatcher cd = cdb as ChannelDispatcher;  
        if (cd != null)  
        {  
            // Make sure there is exactly one throttle used by all   
            // endpoints. If there were others, we could not enforce   
            // MaxPoolSize.  
            if ((this.throttlingBehavior == null) &&   
                        (this.maxPoolSize != Int32.MaxValue))  
            {  
                if (throttle == null)  
                {  
                    throttle = cd.ServiceThrottle;  
                }  
                if (cd.ServiceThrottle == null)  
                {  
                    throw new   
InvalidOperationException(ResourceHelper.GetString("ExNullThrottle"));  
                }  
                if (throttle != cd.ServiceThrottle)  
                {  
                    throw new InvalidOperationException(ResourceHelper.GetString("ExDifferentThrottle"));  
                }  
             }  
  
             foreach (EndpointDispatcher ed in cd.Endpoints)  
             {  
                 // Assign it to DispatchBehavior in each endpoint.  
                 ed.DispatchRuntime.InstanceProvider =   
                                      instanceProvider;  
             }  
         }  
     }  
  
     // Set the MaxConcurrentInstances to limit the number of items   
     // that will ever be requested from the pool.  
     if ((throttle != null) && (throttle.MaxConcurrentInstances >   
                                      this.maxPoolSize))  
     {  
         throttle.MaxConcurrentInstances = this.maxPoolSize;  
     }  
}  
```  
  
 Помимо реализации интерфейса <xref:System.ServiceModel.Description.IServiceBehavior> у класса <xref:System.EnterpriseServices.ObjectPoolingAttribute> имеется несколько членов для настройки пула объектов с помощью аргументов атрибута. К этим членам относятся <xref:System.EnterpriseServices.ObjectPoolingAttribute.MaxPoolSize%2A>, <xref:System.EnterpriseServices.ObjectPoolingAttribute.MinPoolSize%2A> и <xref:System.EnterpriseServices.ObjectPoolingAttribute.CreationTimeout%2A>, и они должны соответствовать набору возможностей пула, предоставляемому службами .NET Enterprise Services.  
  
 Поведение пула объектов, могут теперь добавляться службы WCF, добавив аннотации для реализации службы с новым пользовательским `ObjectPooling` атрибута.  
  
```  
[ObjectPooling(MaxPoolSize=1024, MinPoolSize=10, CreationTimeout=30000)]      
public class PoolService : IPoolService  
{  
  // …  
}  
```  
  
## <a name="running-the-sample"></a>Запуск примера  
 В этом образце демонстрируются преимущества в производительности, которые могут быть получены при использовании пула объектов в различных сценариях.  
  
 Приложение службы реализует две службы - `WorkService` и `ObjectPooledWorkService`. Обе службы совместно используют одну реализацию - обеим требуется обширная инициализация, а затем обе предоставляют метод `DoWork()`, требующий относительно малых затрат. Единственное отличие заключается в том, что в службе `ObjectPooledWorkService` настроено использование пула объектов.  
  
```  
[ObjectPooling(MinPoolSize = 0, MaxPoolSize = 5)]  
public class ObjectPooledWorkService : IDoWork  
{  
    public ObjectPooledWorkService()  
    {  
        Thread.Sleep(5000);  
        ColorConsole.WriteLine(ConsoleColor.Blue, "ObjectPooledWorkService instance created.");  
    }  
  
    public void DoWork()  
    {  
        ColorConsole.WriteLine(ConsoleColor.Blue, "ObjectPooledWorkService.GetData() completed.");  
    }          
}  
```  
  
 При выполнении клиента он измеряет время 5-кратного вызова службы `WorkService`. Затем измеряется время 5-кратного вызова службы `ObjectPooledWorkService`. Затем отображается разница во времени:  
  
```  
Press <ENTER> to start the client.  
  
Calling WorkService:  
1 - DoWork() Done  
2 - DoWork() Done  
3 - DoWork() Done  
4 - DoWork() Done  
5 - DoWork() Done  
Calling WorkService took: 26722 ms.  
Calling ObjectPooledWorkService:  
1 - DoWork() Done  
2 - DoWork() Done  
3 - DoWork() Done  
4 - DoWork() Done  
5 - DoWork() Done  
Calling ObjectPooledWorkService took: 5323 ms.  
Press <ENTER> to exit.  
```  
  
> [!NOTE]
>  При первом запуске клиента обращение к обеим службам занимает приблизительно одинаковое время. При повторном запуске образца видно, что служба `ObjectPooledWorkService` возвращает результаты намного быстрее, потому что экземпляр этого объекта уже существует в пуле.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Чтобы построить решение, следуйте инструкциям в [сборка образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Чтобы выполнить образец на одном или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!NOTE]
>  Если для восстановления конфигурации этого образца используется программа Svcutil.exe, измените имя конечной точки в конфигурации клиента, чтобы оно соответствовало клиентскому коду.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Pooling`  
