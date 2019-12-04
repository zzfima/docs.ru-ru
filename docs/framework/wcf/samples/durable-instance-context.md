---
title: Устойчивый контекст экземпляра
ms.date: 03/30/2017
ms.assetid: 97bc2994-5a2c-47c7-927a-c4cd273153df
ms.openlocfilehash: 3ff4cbcf7a6007339d98820384f5e2d4164d1b0b
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711938"
---
# <a name="durable-instance-context"></a>Устойчивый контекст экземпляра

В этом примере демонстрируется настройка среды выполнения Windows Communication Foundation (WCF) для включения устойчивых контекстов экземпляра. В качестве резервного хранилища в этом примере используется SQL Server 2005, а именно SQL Server 2005 Express. Этот сервер также предоставляет возможность доступа к пользовательским механизмам хранения.

> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.

Этот пример включает расширение уровня канала и уровня модели службы WCF. Поэтому прежде чем перейти к реализации, необходимо ознакомиться с основными понятиями.

Устойчивые контексты экземпляров довольно часто встречаются в реальных сценариях. Например, в приложении, в котором используется покупательская корзина, предусмотрена возможность приостановить процедуру приобретения товаров и продолжить ее в другой день. Таким образом, при обращении к покупательской корзине на следующий день восстанавливается исходный контекст. Важно отметить, что приложение (на сервере) не хранит экземпляр покупательской корзины, когда пользователь отключен от приложения. Вместо этого оно сохраняет его состояние на устойчивом носителе, который затем используется, чтобы создать новый экземпляр для восстановленного контекста. Поэтому экземпляр службы, используемый для того же контекста, отличается от предыдущего экземпляра (т. е. имеет другой адрес памяти).

Устойчивый контекст экземпляра обеспечивается несложным протоколом, с помощью которого выполняется обмен ИД контекста между клиентом и службой. Этот ИД контекста создается на клиенте и передается службе. При создании экземпляра службы среда выполнения службы пытается загрузить сохраненное состояние, соответствующее данному ИД контекста, из постоянного хранилища (которым по умолчанию является база данных SQL Server 2005). Если состояние недоступно, новый экземпляр устанавливается в состояние по умолчанию. Реализация службы использует пользовательский атрибут для отметки операций, изменяющих состояние реализации службы, чтобы среда выполнения могла сохранять экземпляр службы после выполнения этих операций.

Для достижения этой цели необходимо выполнить два действия:

1. изменить сообщение, передаваемое по линии связи, включив в него ИД контекста;

2. изменить локальное поведение службы для реализации пользовательской логики создания экземпляров.

Поскольку первое действие влияет на сообщения, передаваемые по линии связи, его следует реализовать в виде пользовательского канала и привязать к уровню канала. Последнее действие влияет только на локальное поведение службы и поэтому может быть реализовано путем расширения нескольких точек расширяемости службы. Каждое из таких расширений рассматривается в следующих разделах.

## <a name="durable-instancecontext-channel"></a>Устойчивый канал InstanceContext

Прежде всего необходимо обратить внимание на расширение уровня канала. Первый этап создания пользовательского канала - определение структуры взаимодействия канала. После представления нового протокола передачи данных по линии связи канал должен работать практически со всеми другими каналами в стеке каналов. Поэтому он должен поддерживать все шаблоны обмена сообщениями. Однако основная функциональность канала остается прежней несмотря на его структуру взаимодействия. Конкретнее, на стороне клиента он должен записывать ИД контекста в сообщения, а на стороне службы он должен считывать этот ИД контекста из сообщений и передавать его на верхние уровни. Поэтому создается класс `DurableInstanceContextChannelBase`, являющийся абстрактным базовым классом для всех реализаций канала устойчивого контекста экземпляра. Этот класс содержит функции управления на основе общего конечного автомата и два защищенных члена для применения сведений контекста к сообщениям и чтения этих сведений из них.

```csharp
class DurableInstanceContextChannelBase
{
  //…
  protected void ApplyContext(Message message)
  {
    //…
  }
  protected string ReadContextId(Message message)
  {
    //…
  }
}
```

Эти два метода используют реализации `IContextManager` для записи ИД контекста в сообщения и чтения его из них. (`IContextManager` — это пользовательский интерфейс, используемый для определения контракта для всех диспетчеров контекста.) Канал может либо включать идентификатор контекста в пользовательский заголовок SOAP, либо в заголовок HTTP cookie. Каждая реализация диспетчера контекста наследуется от класса `ContextManagerBase`, в котором содержатся общие функции для всех диспетчеров контекста. Метод `GetContextId` в этом классе используется для получения ИД контекста от клиента. При первом получении ИД контекста этот метод сохраняет его в текстовый файл, имя которого создается на основе адреса удаленной конечной точки (недопустимые символы имени файла в типичных URI заменяются символами "@").

Затем при запросе ИД контекста той же удаленной конечной точкой этот метод проверяет, существует ли соответствующий файл. Если файл существует, метод считывает и возвращает ИД контекста. В противном случае он возвращает вновь созданный ИД контекста и сохраняет его в файл. В случае конфигурации по умолчанию такие файлы размещаются в каталоге ContextStore, который находится во временном каталоге текущего пользователя. Однако это расположение настраивается с помощью элемента привязки.

Механизм, используемый для передачи ИД контекста, является настраиваемым. Он может быть записан в заголовок файла cookie HTTP или в пользовательский заголовок SOAP. В случае подхода на основе пользовательского заголовка SOAP можно использовать этот протокол с протоколами, отличными от HTTP (например, с протоколом TCP или протоколом именованных каналов). Эти две возможности реализуют два класса - `MessageHeaderContextManager` и `HttpCookieContextManager`.

Оба класса позволяют записывать ИД контекста в сообщение соответствующим образом. Например, класс `MessageHeaderContextManager` позволяет записать его в заголовок SOAP с помощью метода `WriteContext`.

```csharp
public override void WriteContext(Message message)
{
  string contextId = this.GetContextId();

  MessageHeader contextHeader =
    MessageHeader.CreateHeader(DurableInstanceContextUtility.HeaderName,
      DurableInstanceContextUtility.HeaderNamespace,
      contextId,
      true);

  message.Headers.Add(contextHeader);
}
```

Методы `ApplyContext` и `ReadContextId` класса `DurableInstanceContextChannelBase` вызывают `IContextManager.ReadContext` и `IContextManager.WriteContext` соответственно. Однако эти диспетчеры контекста не создаются непосредственно с помощью класса `DurableInstanceContextChannelBase`. Для выполнения этой задачи используется класс `ContextManagerFactory`.

```csharp
IContextManager contextManager =
                ContextManagerFactory.CreateContextManager(contextType,
                this.contextStoreLocation,
                this.endpointAddress);
```

Метод `ApplyContext` вызывается отправляющими каналами. Он вставляет ИД контекста в исходящие сообщения. Метод `ReadContextId` вызывается получающими каналами. Этот метод обеспечивает доступность ИД контекста во входящих сообщениях и добавляет его в коллекцию `Properties` класса `Message`. Кроме того, в случае ошибки чтения ИД контекста метод вызывает исключение `CommunicationException`, что приводит к прерыванию работы канала.

```csharp
message.Properties.Add(DurableInstanceContextUtility.ContextIdProperty, contextId);
```

Прежде чем продолжить, важно понять принцип использования коллекции `Properties` в классе `Message`. Как правило, коллекция `Properties` используется при передаче данных с нижнего на верхние уровни канала. Таким образом требуемые данные можно согласованно передавать на верхние уровни независимо от подробностей работы протокола. Другими словами, уровень канала может отправлять и получать ИД контекста в виде заголовка SOAP или заголовка файла cookie HTTP. Однако знание этих подробностей на верхних уровнях не требуется, поскольку уровень канала делает эту информацию доступной в коллекции `Properties`.

Теперь, при наличии класса `DurableInstanceContextChannelBase`, следует реализовать все десять необходимых интерфейсов (IOutputChannel, IInputChannel, IOutputSessionChannel, IInputSessionChannel, IRequestChannel, IReplyChannel, IRequestSessionChannel, IReplySessionChannel, IDuplexChannel, IDuplexSessionChannel). Они напоминают каждый доступный шаблон обмена сообщениями (датаграмма, симплекс, дуплекс и их связанные с сеансами разновидности). Каждая из этих реализаций наследует ранее описанный базовый класс и вызывает `ApplyContext` и `ReadContextId` соответственно. Например, канал `DurableInstanceContextOutputChannel`, реализующий интерфейс IOutputChannel, вызывает метод `ApplyContext` для каждого метода, который отправляет сообщения.

```csharp
public void Send(Message message, TimeSpan timeout)
{
    // Apply the context information before sending the message.
    this.ApplyContext(message);
    //…
}
```

И наоборот, канал `DurableInstanceContextInputChannel`, реализующий интерфейс `IInputChannel`, вызывает метод `ReadContextId` в каждом методе, который получает сообщения.

```csharp
public Message Receive(TimeSpan timeout)
{
    //…
      ReadContextId(message);
      return message;
}
```

Кроме того, эти реализации каналов делегируют вызовы методов каналу, расположенному ниже них в стеке каналов. Однако у связанных с сеансами разновидностей имеется базовая логика, обеспечивающая отправку и чтение ИД контекста только для первого сообщения, которое приводит к созданию сеанса.

```csharp
if (isFirstMessage)
{
//…
    this.ApplyContext(message);
    isFirstMessage = false;
}
```

Эти реализации каналов затем добавляются в среду выполнения канала WCF классом `DurableInstanceContextBindingElement` и соответствующим образом `DurableInstanceContextBindingElementSection` класса. Дополнительные сведения об элементах привязки и разделах привязки элементов см. в образце документации по каналу [хттпкукиесессион](../../../../docs/framework/wcf/samples/httpcookiesession.md) .

## <a name="service-model-layer-extensions"></a>Расширения уровня модели служб

Теперь, когда ИД контекста прошел через уровень канала, можно реализовать поведение службы для настройки создания экземпляров. В этом образце диспетчер хранилища используется для загрузки состояния из постоянного хранилища, а также сохранения состояния в него. Как отмечалось ранее, этот образец предоставляет диспетчер хранилища SQL Server 2005 в качестве резервного хранилища. Однако также можно добавить к этому расширению пользовательские механизмы хранения. Для этого объявляется открытый интерфейс, который должен быть реализован всеми диспетчерами хранилища.

```csharp
public interface IStorageManager
{
    object GetInstance(string contextId, Type type);
    void SaveInstance(string contextId, object state);
}
```

Класс `SqlServerStorageManager` содержит реализацию `IStorageManager` по умолчанию. В методе `SaveInstance` заданный объект сериализуется с помощью сериализатора XmlSerializer и сохраняется в базе данных SQL Server.

```csharp
XmlSerializer serializer = new XmlSerializer(state.GetType());
string data;

using (StringWriter writer = new StringWriter(CultureInfo.InvariantCulture))
{
    serializer.Serialize(writer, state);
    data = writer.ToString();
}

using (SqlConnection connection = new SqlConnection(GetConnectionString()))
{
    connection.Open();

    string update = @"UPDATE Instances SET Instance = @instance WHERE ContextId = @contextId";

    using (SqlCommand command = new SqlCommand(update, connection))
    {
        command.Parameters.Add("@instance", SqlDbType.VarChar, 2147483647).Value = data;
        command.Parameters.Add("@contextId", SqlDbType.VarChar, 256).Value = contextId;

        int rows = command.ExecuteNonQuery();

        if (rows == 0)
        {
            string insert = @"INSERT INTO Instances(ContextId, Instance) VALUES(@contextId, @instance)";
            command.CommandText = insert;
            command.ExecuteNonQuery();
        }
    }
}
```

В методе `GetInstance` сериализованные данные считываются для заданного ИД контекста, и созданный из них объект возвращается вызывающему коду.

```csharp
object data;
using (SqlConnection connection = new SqlConnection(GetConnectionString()))
{
    connection.Open();

    string select = "SELECT Instance FROM Instances WHERE ContextId = @contextId";
    using (SqlCommand command = new SqlCommand(select, connection))
    {
        command.Parameters.Add("@contextId", SqlDbType.VarChar, 256).Value = contextId;
        data = command.ExecuteScalar();
    }
}

if (data != null)
{
    XmlSerializer serializer = new XmlSerializer(type);
    using (StringReader reader = new StringReader((string)data))
    {
        object instance = serializer.Deserialize(reader);
        return instance;
    }
}
```

Пользователи этих диспетчеров хранилища не должны создавать их экземпляры непосредственно. Они используют класс `StorageManagerFactory`, абстрагирующий их от подробностей создания диспетчера хранилища. В этом классе имеется один статический член, `GetStorageManager`, который создает экземпляр заданного типа диспетчера хранилища. Если параметр типа имеет значение `null`, этот метод создает и возвращает экземпляр класса по умолчанию `SqlServerStorageManager`. Он также проверяет, что заданный тип реализует интерфейс `IStorageManager`.

```csharp
public static IStorageManager GetStorageManager(Type storageManagerType)
{
IStorageManager storageManager = null;

if (storageManagerType == null)
{
    return new SqlServerStorageManager();
}
else
{
    object obj = Activator.CreateInstance(storageManagerType);

    // Throw if the specified storage manager type does not
    // implement IStorageManager.
    if (obj is IStorageManager)
    {
        storageManager = (IStorageManager)obj;
    }
    else
    {
        throw new InvalidOperationException(
                  ResourceHelper.GetString("ExInvalidStorageManager"));
    }

    return storageManager;
}
}
```

Инфраструктура, необходимая для чтения и записи экземпляров из постоянного хранилища, реализована. Теперь следует выполнить необходимые шаги по изменению поведения службы.

На первом шаге этого процесса нужно сохранить ИД контекста, поступивший через уровень канала в текущий контекст InstanceContext. InstanceContext — это компонент среды выполнения, который выступает в качестве связи между диспетчером WCF и экземпляром службы. Его можно использовать для предоставления дополнительного состояния и поведения экземпляру службы. Это важно, поскольку в связанном с сеансами взаимодействии ИД контекста отправляется только с первым сообщением.

WCF позволяет расширять компонент среды выполнения InstanceContext, добавляя новое состояние и поведение с помощью шаблона расширяемых объектов. Шаблон расширяемого объекта используется в WCF для расширения существующих классов среды выполнения с новыми функциональными возможностями или для добавления новых функций состояния в объект. Существует три интерфейса в расширяемом шаблоне объекта — IExtensibleObject\<T >, IExtension\<T > и Иекстенсионколлектион\<T >:

- Интерфейс IExtensibleObject\<T > реализуется объектами, разрешающими расширения, которые настраивают их функциональность.

- Интерфейс IExtension\<T > реализуется объектами, которые являются расширениями классов типа T.

- Интерфейс Иекстенсионколлектион\<T > — это коллекция Иекстенсионс, которая позволяет извлекать Иекстенсионс по типу.

Таким образом, необходимо создать класс InstanceContextExtension, реализующий интерфейс IExtension и определяющий требуемое состояние для сохранения идентификатора контекста. Этот класс также предоставляет состояние для фиксации используемого диспетчера хранилища. После сохранения нового состояния его должно быть невозможно изменить. Поэтому состояние предоставляется и сохраняется в экземпляре в момент его создания, после чего доступ к нему осуществляется только с помощью свойств, доступных только для чтения.

```csharp
// Constructor
public DurableInstanceContextExtension(string contextId,
            IStorageManager storageManager)
{
    this.contextId = contextId;
    this.storageManager = storageManager;
}

// Read only properties
public string ContextId
{
    get { return this.contextId; }
}

public IStorageManager StorageManager
{
    get { return this.storageManager; }
}
```

Класс InstanceContextInitializer реализует интерфейс IInstanceContextInitializer и добавляет расширение контекста экземпляра в коллекцию Extensions создаваемого контекста InstanceContext.

```csharp
public void Initialize(InstanceContext instanceContext, Message message)
{
    string contextId =
  (string)message.Properties[DurableInstanceContextUtility.ContextIdProperty];

    DurableInstanceContextExtension extension =
                new DurableInstanceContextExtension(contextId,
                     storageManager);
    instanceContext.Extensions.Add(extension);
}
```

Как отмечалось ранее, ИД контекста считывается из коллекции `Properties` класса `Message` и передается конструктору класса расширения. Это демонстрирует, как можно согласованно обмениваться информацией между уровнями.

Следующий важный шаг - переопределение процесса создания экземпляров службы. WCF позволяет реализовать поведение пользовательских экземпляров и присоединить их к среде выполнения с помощью интерфейса Иинстанцепровидер. Для выполнения этой задачи реализуется новый класс `InstanceProvider`. Конструктор принимает тип службы, ожидаемый от поставщика экземпляров. Затем он используется для создания новых экземпляров. В реализации `GetInstance` создается экземпляр диспетчера хранилища, который выполняет поиск постоянного хранилища. Если он возвращает значение `null`, новый экземпляр типа службы создается и возвращается вызывающему коду.

```csharp
public object GetInstance(InstanceContext instanceContext, Message message)
{
    object instance = null;

    DurableInstanceContextExtension extension =
    instanceContext.Extensions.Find<DurableInstanceContextExtension>();

    string contextId = extension.ContextId;
    IStorageManager storageManager = extension.StorageManager;

    instance = storageManager.GetInstance(contextId, serviceType);

    instance ??= Activator.CreateInstance(serviceType);
    return instance;
}
```

Следующий важный шаг - установка классов `InstanceContextExtension`, `InstanceContextInitializer` и `InstanceProvider` в среде выполнения модели служб. С помощью пользовательского атрибута можно отметить классы реализации службы для установки поведения. `DurableInstanceContextAttribute` содержит реализацию этого атрибута и реализует интерфейс `IServiceBehavior` для расширения всей среды выполнения службы.

В этом классе имеется свойство, принимающее тип используемого диспетчера хранилища. Таким образом реализация позволяет пользователю указать его собственную реализацию `IStorageManager` в качестве параметра данного атрибута.

В реализации `ApplyDispatchBehavior` проверяется свойство `InstanceContextMode` текущего атрибута `ServiceBehavior`. Если это свойство имеет значение Singleton, устойчивое создание экземпляров невозможно и для уведомления узла создается исключение `InvalidOperationException`.

```csharp
ServiceBehaviorAttribute serviceBehavior =
    serviceDescription.Behaviors.Find<ServiceBehaviorAttribute>();

if (serviceBehavior != null &&
     serviceBehavior.InstanceContextMode == InstanceContextMode.Single)
{
    throw new InvalidOperationException(
       ResourceHelper.GetString("ExSingletonInstancingNotSupported"));
}
```

После этого экземпляры диспетчера хранилища, инициализатор контекста экземпляра и поставщик экземпляров создаются и устанавливаются в объекте `DispatchRuntime`, созданном для каждой конечной точки.

```csharp
IStorageManager storageManager =
    StorageManagerFactory.GetStorageManager(storageManagerType);

InstanceContextInitializer contextInitializer =
    new InstanceContextInitializer(storageManager);

InstanceProvider instanceProvider =
    new InstanceProvider(description.ServiceType);

foreach (ChannelDispatcherBase cdb in serviceHostBase.ChannelDispatchers)
{
    ChannelDispatcher cd = cdb as ChannelDispatcher;

    if (cd != null)
    {
        foreach (EndpointDispatcher ed in cd.Endpoints)
        {
            ed.DispatchRuntime.InstanceContextInitializers.Add(contextInitializer);
            ed.DispatchRuntime.InstanceProvider = instanceProvider;
        }
    }
}
```

Итак, на данный момент создан канал, который обеспечивает пользовательский протокол передачи данных по линии связи для обмена пользовательским ИД контекста и переопределяет поведение создания экземпляров по умолчанию для загрузки экземпляров из постоянного хранилища.

Остается найти способ сохранения экземпляра службы в хранилище сохраняемости. Как отмечалось ранее, уже имеется требуемая функциональность для сохранения состояния в реализации `IStorageManager`. Теперь это необходимо интегрировать со средой выполнения WCF. Требуется другой атрибут, применимый к методам в классе реализации службы. Этот атрибут должен применяться к методам, изменяющим состояние экземпляра службы.

Класс `SaveStateAttribute` реализует данную функциональность. Он также реализует класс `IOperationBehavior`, чтобы изменить среду выполнения WCF для каждой операции. Если метод помечен с помощью этого атрибута, среда выполнения WCF вызывает метод `ApplyBehavior` при создании соответствующего `DispatchOperation`. В этой реализации метода содержится одна строка кода:

```csharp
dispatch.Invoker = new OperationInvoker(dispatch.Invoker);
```

Эта инструкция создает экземпляр типа `OperationInvoker` и присваивает его свойству `Invoker` создаваемого объекта `DispatchOperation`. Класс `OperationInvoker` является оболочкой для средства вызова операции по умолчанию, созданного для `DispatchOperation`. Этот класс реализует интерфейс `IOperationInvoker` . В реализации метода `Invoke` фактический метод вызова делегируется внутреннему средству вызова операции. Однако перед возвратом результатов диспетчер хранилища в `InstanceContext` используется для сохранения экземпляра службы.

```csharp
object result = innerOperationInvoker.Invoke(instance,
    inputs, out outputs);

// Save the instance using the storage manager saved in the
// current InstanceContext.
InstanceContextExtension extension =
    OperationContext.Current.InstanceContext.Extensions.Find<InstanceContextExtension>();

extension.StorageManager.SaveInstance(extension.ContextId, instance);
return result;
```

## <a name="using-the-extension"></a>Использование расширения

Расширения уровня канала и модели службы выполняются, и теперь их можно использовать в приложениях WCF. Службам необходимо добавить канал в стек каналов с помощью пользовательской привязки и отметить классы реализации службы соответствующими атрибутами.

```csharp
[DurableInstanceContext]
[ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]
public class ShoppingCart : IShoppingCart
{
//…
     [SaveState]
     public int AddItem(string item)
     {
         //…
     }
//…
 }
```

Клиентским приложениям необходимо добавить канал DurableInstanceContextChannel в стек каналов с помощью пользовательской привязки. Чтобы настроить канал декларативно в файле конфигурации, необходимо добавить раздел элемента привязки в коллекцию расширений элемента привязки.

```xml
<system.serviceModel>
 <extensions>
   <bindingElementExtensions>
     <add name="durableInstanceContext"
type="Microsoft.ServiceModel.Samples.DurableInstanceContextBindingElementSection, DurableInstanceContextExtension, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null"/>
   </bindingElementExtensions>
 </extensions>
```

Теперь элемент привязки можно использовать с пользовательской привязкой аналогично другим стандартным элементам привязки.

```xml
<bindings>
 <customBinding>
   <binding name="TextOverHttp">
     <durableInstanceContext contextType="HttpCookie"/>
     <reliableSession />
     <textMessageEncoding />
     <httpTransport />
   </binding>
 </customBinding>
</bindings>
```

## <a name="conclusion"></a>Заключение

В этом образце показано, как создать пользовательский канал протокола и настроить поведение службы, чтобы задействовать этот канал.

Расширение можно усовершенствовать, позволив пользователям указывать реализацию `IStorageManager` с помощью раздела конфигурации. Это делает возможным изменение резервного хранилища без повторной компиляции кода службы.

Более того, можно попытаться реализовать класс (например, `StateBag`), инкапсулирующий состояние экземпляра. Этот класс отвечает за сохранение состояния при каждом его изменении. Таким образом можно избегать использования атрибута `SaveState` и более точно выполнять операции сохранения (например, можно сохранять состояние при его фактическом изменении, а не при каждом вызове метода с атрибутом `SaveState`).

При выполнении образца получается следующий результат. Клиент добавляет две единицы продукции в свою покупательскую корзину и получает список имеющихся в ней единиц продукции от службы. Нажмите клавишу ВВОД в каждом окне консоли, чтобы закрыть службу и клиент.

```console
Enter the name of the product: apples
Enter the name of the product: bananas

Shopping cart currently contains the following items.
apples
bananas
Press ENTER to shut down client
```

> [!NOTE]
> Повторное построение службы приводит к перезаписи файла базы данных. Для просмотра состояния, сохраняемого между несколькими запусками образца, не следует выполнять повторная сборка образца между запусками.

#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца

1. Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).

2. Чтобы выполнить сборку решения, следуйте инструкциям в разделе [Создание примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).

3. Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).

> [!NOTE]
> Для выполнения этого образца необходимо использовать SQL Server 2005 или SQL Express 2005. При использовании SQL Server 2005 необходимо изменить конфигурацию строки подключения службы. При выполнении примера на нескольких компьютерах использование SQL Server требуется только на компьютере-сервере.

> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Durable`
