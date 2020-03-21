---
title: Инициализация создания экземпляров
ms.date: 03/30/2017
ms.assetid: 154d049f-2140-4696-b494-c7e53f6775ef
ms.openlocfilehash: 897bb62df0a23073827aeed18b54bf77e8c6d4bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183598"
---
# <a name="instancing-initialization"></a>Инициализация создания экземпляров
Этот образец расширяет образец [Пулинга,](../../../../docs/framework/wcf/samples/pooling.md) определяя интерфейс, `IObjectControl`который настраивает инициализацию объекта путем активации и деактивации его. Клиент вызывает методы, которые возвращают объект в пул и не возвращают объект в пул.  
  
> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
## <a name="extensibility-points"></a>Точки расширяемости  
 Первым шагом в создании Windows Communication Foundation (WCF) является решение точки расширения для использования. В WCF термин *EndpointDispatcher* относится к компоненту времени выполнения, ответственному за преобразование входящих сообщений в вызовы метода в службе пользователя и преобразование значений возврата от этого метода к исходящим сообщениям. Служба WCF создает endpointDispatcher для каждой конечной точки.  
  
 EndpointDispatcher реализует расширяемость области конечной точки (для всех сообщений, получаемых и отправляемых службой) с помощью класса <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>. Этот класс позволяет настраивать различные свойства, управляющие поведением EndpointDispatcher. В этом образце рассматривается свойство <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A>, которое указывает на объект, предоставляющий экземпляры класса службы.  
  
## <a name="iinstanceprovider"></a>IInstanceProvider  
 В WCF EndpointDispatcher создает экземпляры класса обслуживания с помощью поставщика <xref:System.ServiceModel.Dispatcher.IInstanceProvider> экземпляров, который реализует интерфейс. У этого интерфейса есть только два метода.  
  
- <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A>. Когда прибывает сообщение, объект Dispatcher вызывает метод <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A>, чтобы создать экземпляр класса службы для обработки сообщения. Частота вызовов этого метода определяется свойством <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>. Например, если свойство <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> имеет значение <xref:System.ServiceModel.InstanceContextMode.PerCall?displayProperty=nameWithType>, для обработки каждого получаемого сообщения создается новый экземпляр класса службы, поэтому метод <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A> вызывается каждый раз, когда приходит сообщение.  
  
- <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A>. Когда экземпляр службы завершает обработку сообщения, EndpointDispatcher вызывает метод <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A>. Как и в случае метода <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A>, частота вызовов этого метода определяется свойством <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>.  
  
## <a name="the-object-pool"></a>Пул объектов  
 Класс `ObjectPoolInstanceProvider` содержит реализацию пула объектов. Этот класс реализует интерфейс <xref:System.ServiceModel.Dispatcher.IInstanceProvider> для взаимодействия с уровнем модели службы. Когда EndpointDispatcher вызывает метод <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A>, вместо создания нового экземпляра, пользовательская реализация находит существующий объект в находящемся в памяти пуле. Если такой объект доступен, метод возвращает его. В противном случае `ObjectPoolInstanceProvider` проверяет, не достигло ли свойство `ActiveObjectsCount` (количество возвращенных из пула объектов) максимального размера пула. Если нет, то создается и возвращается вызывающей стороне новый экземпляр, а значение `ActiveObjectsCount` увеличивается на единицу. В противном случае запрос на создание объекта помещается в очередь на заданное время. Реализация метода `GetObjectFromThePool` показана в следующем образце кода.  
  
```csharp
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
  
 Пользовательская реализация `ReleaseInstance` добавляет освободившийся экземпляр обратно в пул и уменьшает значение `ActiveObjectsCount` на единицу. EndpointDispatcher может вызывать эти методы из различных потоков, поэтому требуется синхронизированный доступ к членам уровня класса в классе `ObjectPoolInstanceProvider`.  
  
```csharp
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
  
 Метод `ReleaseInstance` обеспечивает функцию *очистки инициализации.* Обычно пул поддерживает минимальное число объектов в течение времени существования пула. Однако возможны периоды интенсивного использования, когда требуется создавать в пуле дополнительные объекты, пока не будет достигнуто заданное в конфигурации максимальное значение. В конце концов, когда активность пула снизится, эти дополнительные объекты могут стать излишней нагрузкой. Поэтому когда значение `activeObjectsCount` достигает нуля, запускается таймер бездействия, по истечении времени ожидания которого выполняется цикл очистки.  
  
```csharp  
if (activeObjectsCount == 0)  
{  
    idleTimer.Start();
}  
```  
  
 Расширения уровня ServiceModel выполняются с помощью следующих поведений.  
  
- Поведения служб. Позволяют настраивать всю среду выполнения службы.  
  
- Поведения конечных точек. Позволяют настраивать отдельные конечные точки, включая EndpointDispatcher.  
  
- Поведения контрактов. Позволяют настраивать классы <xref:System.ServiceModel.Dispatcher.ClientRuntime> или <xref:System.ServiceModel.Dispatcher.DispatchRuntime> на стороне клиента или службы соответственно.  
  
- Поведения операций. Позволяют настраивать классы <xref:System.ServiceModel.Dispatcher.ClientOperation> или <xref:System.ServiceModel.Dispatcher.DispatchOperation> на стороне клиента или службы соответственно.  
  
 С целью реализации расширения создания пулов объектов может быть создано поведение конечной точки или поведение службы. В этом примере используется поведение службы, которое применяет поддержку создания пулов объектов ко всем конечным точкам службы. Поведения служб создаются путем реализации интерфейса <xref:System.ServiceModel.Description.IServiceBehavior>. Имеется несколько способов сообщить ServiceModel о пользовательских поведениях:  
  
- с помощью пользовательского атрибута;  
  
- путем ее императивного добавления в коллекцию поведений описания службы;  
  
- путем расширения файла конфигурации.  
  
 В этом образце используется пользовательский атрибут. При создании <xref:System.ServiceModel.ServiceHost> проверяются атрибуты, используемые в определении типа службы, а в коллекцию поведений описания службы добавляются доступные поведения.  
  
 Интерфейс <xref:System.ServiceModel.Description.IServiceBehavior> имеет <xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A> `,` <xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A> `,` три метода: и <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A>. Эти методы называются WCF, когда <xref:System.ServiceModel.ServiceHost> инициализируется. Сначала вызывается метод <xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A?displayProperty=nameWithType>, который позволяет проверить согласованность службы. Затем вызывается метод <xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A?displayProperty=nameWithType>, который используется только в очень сложных сценариях. Метод <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A?displayProperty=nameWithType> вызывается в последнюю очередь и отвечает за настройку среды выполнения. Следующие параметры передаются методу <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A?displayProperty=nameWithType>.  
  
- `Description`: этот параметр содержит описание службы для всей службы. Его можно использовать для проверки данных описания о конечных точках, контрактах и привязках службы, а также других связанных со службой данных.  
  
- `ServiceHostBase`: этот параметр содержит инициализируемый в данный момент объект <xref:System.ServiceModel.ServiceHostBase>.  
  
 В пользовательской реализации <xref:System.ServiceModel.Description.IServiceBehavior> создается новый экземпляр `ObjectPoolInstanceProvider`, который присваивается свойству <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A> в каждом объекте <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>, прикрепленном к <xref:System.ServiceModel.ServiceHostBase>.  
  
```csharp
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
  
 Помимо реализации интерфейса <xref:System.ServiceModel.Description.IServiceBehavior> у класса `ObjectPoolingAttribute` имеется несколько членов для настройки пула объектов с помощью аргументов атрибута. К этим членам относятся `MaxSize`, `MinSize`, `Enabled` и `CreationTimeout`, и они должны соответствовать набору возможностей пула, предоставляемому службами .NET Enterprise Services.  
  
 Поведение объединения объектов теперь можно добавить в службу WCF, аннотируя `ObjectPooling` реализацию службы с помощью недавно созданного пользовательского атрибута.  
  
```csharp  
[ObjectPooling(MaxSize=1024, MinSize=10, CreationTimeout=30000]
public class PoolService : IPoolService  
{  
  // …  
}  
```  
  
## <a name="hooking-activation-and-deactivation"></a>Активация и деактивация связывания  
 Основной целью создания пулов объектов является оптимизация использования объектов с небольшим временем существования, чтобы экономить на ресурсоемких процедурах создания и инициализации. Поэтому создание пулов при его правильном использовании позволяет значительно повысить производительность приложения. Поскольку объект возвращается из пула, конструктор вызывается только один раз. Однако некоторым приложениями требуется более высокий уровень контроля, чтобы они могли инициализировать и высвобождать ресурсы в рамках одного контекста. Например, объект, используемый для набора вычислений, может сбрасывать значения своих закрытых полей, прежде чем переходить к следующим вычислениям. Службы Enterprise Services поддерживают такую инициализацию в зависимости от контекста, позволяя разработчику объектов переопределять методы `Activate` и `Deactivate` из базового класса <xref:System.EnterpriseServices.ServicedComponent>.  
  
 Пул объектов вызывает метод `Activate` непосредственно перед возвращением объекта из пула. Метод `Deactivate` вызывается при возвращении объекта в пул. Кроме того, у базового класса <xref:System.EnterpriseServices.ServicedComponent> имеется свойство типа `boolean` с именем `CanBePooled`, с помощью которого можно уведомить пул о том, можно ли и дальше размещать объект в пуле.  
  
 Чтобы сымитировать эту функциональность, в этом образце объявляется открытый интерфейс (`IObjectControl`), имеющий указанные выше члены. Затем этот интерфейс реализуется классами службы, предназначенными для инициализации с учетом контекста. Реализацию <xref:System.ServiceModel.Dispatcher.IInstanceProvider> необходимо изменить, чтобы она удовлетворяла этим требованиям. Теперь, каждый раз, когда `GetInstance` вы получаете объект, вызывая метод, вы должны проверить, реализует `IObjectControl.` ли объект Если это так, вы должны вызвать `Activate` метод соответствующим образом.  
  
```csharp  
if (obj is IObjectControl)  
{  
    ((IObjectControl)obj).Activate();  
}  
```  
  
 При возврате объекта в пул необходимо проверить свойство `CanBePooled`, прежде чем добавлять объект обратно в пул.  
  
```csharp  
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
  
 Поскольку разработчик может решать, можно ли помещать объект в пул, в определенный момент значение счетчика объектов в пуле может оказаться меньше минимального размера пула. Поэтому необходимо сравнивать число объектов с минимальным размером и при необходимости выполнять инициализацию в процедуре очистки.  
  
```csharp  
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
  
 При запуске данного примера запросы и ответы операций отображаются в окнах консоли как службы, так и клиента. Нажмите клавишу ВВОД в каждом окне консоли, чтобы закрыть службу и клиент.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Убедитесь, что вы выполнили [одноразовую процедуру настройки для образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)  
  
2. Чтобы создать решение, следуйте инструкциям по [созданию образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/building-the-samples.md)  
  
3. Чтобы запустить образец в одно- или кросс-машинной конфигурации, следуйте инструкциям в [Запуске образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/running-the-samples.md)  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы. Этот образец расположен в следующем каталоге.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Initialization`  
