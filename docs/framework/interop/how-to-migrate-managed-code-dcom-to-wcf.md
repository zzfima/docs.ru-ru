---
title: Практическое руководство. Миграция DCOM с управляемым кодов в WCF
ms.date: 03/30/2017
ms.assetid: 52961ffc-d1c7-4f83-832c-786444b951ba
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6fdd5c9b285bdc948af876c72e85590500dd41c8
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039598"
---
# <a name="how-to-migrate-managed-code-dcom-to-wcf"></a>Практическое руководство. Миграция DCOM с управляемым кодов в WCF
Для вызовов управляемого кода между серверами и клиентами в распределенной среде рекомендуется использовать технологию Windows Communication Foundation (WCF), а не модель DCOM, из соображений безопасности. В этом разделе описывается, как перенести код из DCOM в WCF в перечисленных ниже ситуациях.  
  
- Удаленная служба возвращает клиенту объект по значению.  
  
- Клиент отправляет удаленной службе объект по значению.  
  
- Удаленная служба возвращает клиенту объект по ссылке.  
  
 По соображениям безопасности отправка объекта по ссылке от клиента службе в WCF запрещена. Сценарий, при котором клиенту и серверу необходимо обмениваться сообщениями друг с другом, можно реализовать в WCF с помощью дуплексной службы.  Дополнительные сведения о дуплексных службах см. в разделе [Дуплексные службы](../wcf/feature-details/duplex-services.md).  
  
 Дополнительные сведения о создании служб WCF и клиентов для них см. в разделах [Базовое программирование для WCF](../wcf/basic-wcf-programming.md), [Проектирование и реализация служб](../wcf/designing-and-implementing-services.md), а также [Создание клиентов](../wcf/building-clients.md).  
  
## <a name="dcom-example-code"></a>Пример кода DCOM  
 Для этих сценариев интерфейсы DCOM, проиллюстрированные с помощью WCF, имеют приведенную ниже структуру.  
  
```csharp  
[ComVisible(true)]  
[Guid("AA9C4CDB-55EA-4413-90D2-843F1A49E6E6")]  
public interface IRemoteService  
{  
   Customer GetObjectByValue();  
   IRemoteObject GetObjectByReference();  
   void SendObjectByValue(Customer customer);  
}  
  
[ComVisible(true)]  
[Guid("A12C98DE-B6A1-463D-8C24-81E4BBC4351B")]  
public interface IRemoteObject  
{  
}  
  
public class Customer  
{  
}  
```  
  
## <a name="the-service-returns-an-object-by-value"></a>Служба возвращает объект по значению  
 В этом сценарии выполняется вызов службы, а ее метод возвращает объект, который передается по значению с сервера клиенту. Такой сценарий представляет приведенный ниже вызов COM.  
  
```csharp  
public interface IRemoteService  
{  
    Customer GetObjectByValue();  
}  
```  
  
 В этом случае клиент получает из удаленной службы десериализованную копию объекта. Клиент может взаимодействовать с этой локальной копией, не выполняя обратные вызовы в службу.  Иными словами, клиент получает гарантию, что при вызове методов применительно к локальной копии служба не будет задействована никоим образом. WCF всегда возвращает объекты из службы по значению, поэтому ниже описывается создание стандартной службы WCF.  
  
### <a name="step-1-define-the-wcf-service-interface"></a>Шаг 1. Определение интерфейса службы WCF  
 Определите открытый интерфейс для службы WCF и пометьте его атрибутом [<xref:System.ServiceModel.ServiceContractAttribute>].  Пометьте атрибутом [<xref:System.ServiceModel.OperationContractAttribute>] методы, к которым необходимо предоставить доступ клиентам. В примере ниже показано использование этих атрибутов для определения интерфейса на стороне сервера и методов интерфейса, которые может вызывать клиент. Метод, используемый в этом сценарии, выделен полужирным шрифтом.  
  
```csharp  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.ServiceModel.Web;   
. . .  
[ServiceContract]  
public interface ICustomerManager  
{  
    [OperationContract]  
    void StoreCustomer(Customer customer);  
  
    [OperationContract]     Customer GetCustomer(string firstName, string lastName);   
  
}  
```  
  
### <a name="step-2-define-the-data-contract"></a>Шаг 2. Определение контракта данных  
 Далее следует создать для службы контракт данных, описывающий то, как будет происходить обмен данными между службой и клиентами.  Классы, описываемые в контракте данных, следует пометить атрибутом [<xref:System.Runtime.Serialization.DataContractAttribute>]. Отдельные свойства или поля, которые должны быть видны и для клиента, и для сервера, отмечаются атрибутом [<xref:System.Runtime.Serialization.DataMemberAttribute>]. Чтобы разрешить использование типов, производных от класса, в контракте данных, их следует указать с помощью атрибута [<xref:System.Runtime.Serialization.KnownTypeAttribute>]. WCF сериализует и десериализует только те типы, которые входят в интерфейс службы или определены как известные. При попытке использовать неизвестный тип возникнет исключение.  
  
 Дополнительные сведения о контрактах данных см. в разделе [Контракты данных](../wcf/samples/data-contracts.md).  
  
```csharp  
[DataContract]  
[KnownType(typeof(PremiumCustomer))]  
public class Customer  
{  
    [DataMember]  
    public string Firstname;  
    [DataMember]  
    public string Lastname;  
    [DataMember]  
    public Address DefaultDeliveryAddress;  
    [DataMember]  
    public Address DefaultBillingAddress;  
}  
 [DataContract]  
public class PremiumCustomer : Customer  
{  
    [DataMember]  
    public int AccountID;  
}  
  
 [DataContract]  
public class Address  
{  
    [DataMember]  
    public string Street;  
    [DataMember]  
    public string Zipcode;  
    [DataMember]  
    public string City;  
    [DataMember]  
    public string State;  
    [DataMember]  
    public string Country;  
}  
```  
  
### <a name="step-3-implement-the-wcf-service"></a>Шаг 3. Реализация службы WCF  
 Далее следует реализовать класс службы WCF, который реализует интерфейс, определенный в предыдущем шаге.  
  
```csharp  
public class CustomerService: ICustomerManager    
{  
    public void StoreCustomer(Customer customer)  
    {  
        // write to a database  
    }  
    public Customer GetCustomer(string firstName, string lastName)  
    {  
        // read from a database  
    }  
}  
```  
  
### <a name="step-4-configure-the-service-and-the-client"></a>Шаг 4. Настройка службы и клиента  
 Для запуска службы WCF необходимо объявить конечную точку, предоставляющую доступ к интерфейсу службы по определенному URL-адресу с помощью определенной привязки WCF. Привязка определяет транспорт, кодировку и протокол, используемые для обмена данными между клиентами и сервером. Привязки обычно добавляются в файл конфигурации проекта службы (web.config). Ниже приведен пример записи привязки для службы.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service name="Server.CustomerService">  
        <endpoint address="http://localhost:8083/CustomerManager"   
                  binding="basicHttpBinding"  
                  contract="Shared.ICustomerManager" />  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
 Затем нужно настроить клиент в соответствии с информацией о привязке, определенной в службе. Для этого добавьте в файл конфигурации клиентского приложения (app.config) приведенный ниже код.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <client>  
      <endpoint name="customermanager"   
                address="http://localhost:8083/CustomerManager"   
                binding="basicHttpBinding"   
                contract="Shared.ICustomerManager"/>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
### <a name="step-5-run-the-service"></a>Шаг 5. Запуск службы  
 Наконец, вы можете произвести резидентное размещение в консольном приложении, добавив в приложение службы приведенные ниже строки и запустив его. Дополнительные сведения о других способах размещения приложения службы WCF см. в разделе [Размещение служб](../wcf/hosting-services.md).  
  
```csharp  
ServiceHost customerServiceHost = new ServiceHost(typeof(CustomerService));  
customerServiceHost.Open();  
```  
  
### <a name="step-6-call-the-service-from-the-client"></a>Шаг 6. Вызов службы из клиента  
 Для вызова службы из клиента нужно создать для нее фабрику каналов, а затем запросить канал, чтобы получить возможность вызывать метод `GetCustomer` непосредственно из клиента. Канал реализует интерфейс службы и отвечает за базовую логику запросов и ответов.  Возвращаемое значение метода представляет собой десериализованную копию ответа службы.  
  
```csharp  
ChannelFactory<ICustomerManager> factory =   
     new ChannelFactory<ICustomerManager>("customermanager");  
ICustomerManager service = factory.CreateChannel();  
Customer customer = service.GetCustomer("Mary", "Smith");  
```  
  
## <a name="the-client-sends-a-by-value-object-to-the-server"></a>Клиент отправляет серверу объект по значению  
 В этом случае клиент отправляет серверу объект по значению. Это означает, что сервер получит десериализованную копию объекта.  Сервер может вызывать методы применительно к этой копии с гарантией того, что обратные вызовы кода клиента выполняться не будут. Как было замечено ранее, обмен данными с WCF обычно происходит по значению.  Это гарантирует, что вызовы методов объектов выполняются только локально без вызова кода клиента.  
  
 Такой сценарий представляет приведенный ниже вызов метода COM.  
  
```csharp  
public interface IRemoteService  
{  
    void SendObjectByValue(Customer customer);  
}  
```  
  
 В этом сценарии используется тот же интерфейс службы и тот же контракт данных, что и в первом примере. Кроме того, клиент и служба настраиваются точно так же. В этом примере для отправки объекта создается и запускается канал аналогичным образом. Однако в этом примере вы создадите клиент, который вызывает службу, передавая объект по значению. Метод службы, который клиент вызывает в контракте службы, выделен полужирным шрифтом.  
  
```csharp  
[ServiceContract]  
public interface ICustomerManager  
{  
    [OperationContract]     void StoreCustomer(Customer customer);  
  
    [OperationContract]  
    Customer GetCustomer(string firstName, string lastName);  
}  
```  
  
### <a name="add-code-to-the-client-that-sends-a-by-value-object"></a>Добавление в клиент кода для отправки объекта по значению  
 В приведенном ниже коде показано, как клиент создает объект customer для передачи по значению, создает канал для обмена данными со службой `ICustomerManager` и отправляет ей объект customer.  
  
 Объект customer будет сериализован и отправлен в службу, где он десериализуется в новую копию этого объекта.  Любые методы этого объекта, вызываемые службой, будут выполняться только локально на сервере. Важно отметить, что этот код иллюстрирует отправку производного типа (`PremiumCustomer`).  Контракт службы ожидает объекта `Customer`, но в контракте данных службы используется атрибут [<xref:System.Runtime.Serialization.KnownTypeAttribute>], указывающий, что объект `PremiumCustomer` также допустим.  Попытка сериализации или десериализации любого другого типа посредством этого интерфейса службы WCF завершится ошибкой.  
  
```csharp  
PremiumCustomer customer = new PremiumCustomer();  
customer.Firstname = "John";  
customer.Lastname = "Doe";  
customer.DefaultBillingAddress = new Address();  
customer.DefaultBillingAddress.Street = "One Microsoft Way";  
customer.DefaultDeliveryAddress = customer.DefaultBillingAddress;  
customer.AccountID = 42;  
  
ChannelFactory<ICustomerManager> factory =  
   new ChannelFactory<ICustomerManager>("customermanager");  
ICustomerManager customerManager = factory.CreateChannel();  
customerManager.StoreCustomer(customer);  
```  
  
## <a name="the-service-returns-an-object-by-reference"></a>Служба возвращает объект по ссылке  
 В этом случае клиентское приложение вызывает удаленную службу, и метод возвращает объект, который передается по ссылке из службы в клиент.  
  
 Как было замечено ранее, службы WCF всегда возвращают объекты по значению.  Однако вы можете получить требуемый результат с помощью класса <xref:System.ServiceModel.EndpointAddress10>.  <xref:System.ServiceModel.EndpointAddress10> — это сериализуемый объект, передаваемый по значению, с помощью которого клиент может получить на сервере объект, переданный по ссылке в рамках сеанса.  
  
 Поведение переданного по ссылке объекта в WCF, которое показано в этом сценарии, отличается от его поведения в DCOM.  В DCOM сервер может вернуть клиенту объект по ссылке напрямую, и клиент может вызывать методы этого объекта, которые выполняются на сервере.  Однако в WCF объекты всегда возвращаются по значению.  Клиент должен получить объект по значению, представленный <xref:System.ServiceModel.EndpointAddress10>, и с помощью него создать собственный объект, полученный по ссылке в рамках сеанса.  Методы объекта сеанса, вызываемые клиентом, выполняются на сервере. Иными словами, этот полученный по ссылке объект в WCF является обычным объектом WCF, настроенным как объект сеанса.  
  
 В WCF сеанс — это способ согласования нескольких сообщений, пересылаемых между двумя конечными точками.  Это означает, что, как только клиент устанавливает подключение к службе, между ним и сервером создается сеанс.  Клиент использует единственный уникальный экземпляр объекта на стороне сервера для любых взаимодействий в рамках данного сеанса. Контракты сеансов WCF аналогичны схемам запросов и ответов, ориентированным на подключения.  
  
 Этот сценарий представлен приведенным ниже методом DCOM.  
  
```csharp  
public interface IRemoteService  
{  
    IRemoteObject GetObjectByReference();  
}  
```  
  
### <a name="step-1-define-the-sessionful-wcf-service-interface-and-implementation"></a>Шаг 1. Определение интерфейса сеанса службы WCF и его реализация  
 Сначала определите интерфейс службы WCF, содержащий объект сеанса.  
  
 В этом коде объект сеанса помечен атрибутом `ServiceContract`, который определяет его как обычный интерфейс службы WCF.  Кроме того, свойству <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A> присвоено значение, указывающее, что это будет служба сеанса.  
  
```csharp  
[ServiceContract(SessionMode = SessionMode.Allowed)]  
public interface ISessionBoundObject  
{  
    [OperationContract]  
    string GetCurrentValue();  
  
    [OperationContract]  
    void SetCurrentValue(string value);  
}  
```  
  
 В приведенном ниже коде показана реализация службы.  
  
 Служба помечена атрибутом [ServiceBehavior], а ее свойству InstanceContextMode присвоено значение InstanceContextMode.PerSessions, указывающее, что для каждого сеанса должен создаваться уникальный экземпляр этого типа.  
  
```csharp  
[ServiceBehavior(InstanceContextMode = InstanceContextMode.PerSession)]  
    public class MySessionBoundObject : ISessionBoundObject  
    {  
        private string _value;  
  
        public string GetCurrentValue()  
        {  
            return _value;  
        }  
  
        public void SetCurrentValue(string val)  
        {  
            _value = val;  
        }  
  
    }  
```  
  
### <a name="step-2-define-the-wcf-factory-service-for-the-sessionful-object"></a>Шаг 2. Определение службы фабрики WCF для объекта сеанса  
 Необходимо определить и реализовать службу, создающую объект сеанса. В следующем примере кода показано, как это сделать: Этот код создает еще одну службу WCF, которая возвращает объект <xref:System.ServiceModel.EndpointAddress10>.  Это сериализуемая форма конечной точки, с помощью которой можно создать объект сеанса.  
  
```csharp  
[ServiceContract]  
    public interface ISessionBoundFactory  
    {  
        [OperationContract]  
        EndpointAddress10 GetInstanceAddress();  
    }  
```  
  
 Ниже приведена реализация этой службы. Эта реализация поддерживает единственную фабрику каналов для создания объектов, связанных с сеансами.  При вызове метода `GetInstanceAddress` создается канал и объект <xref:System.ServiceModel.EndpointAddress10>, указывающий на удаленный адрес, связанный с этим каналом.   <xref:System.ServiceModel.EndpointAddress10> — это тип данных, который можно вернуть клиенту по значению.
  
```csharp  
public class SessionBoundFactory : ISessionBoundFactory  
    {  
        public static ChannelFactory<ISessionBoundObject> _factory =   
            new ChannelFactory<ISessionBoundObject>("sessionbound");  
  
        public SessionBoundFactory()  
        {  
        }  
  
        public EndpointAddress10 GetInstanceAddress()  
        {  
            IClientChannel channel = (IClientChannel)_factory.CreateChannel();  
            return EndpointAddress10.FromEndpointAddress(channel.RemoteAddress);  
        }  
    }  
```  
  
### <a name="step-3-configure-and-start-the-wcf-services"></a>Шаг 3. Настройка и запуск служб WCF  
 Для размещения этих служб необходимо добавить указанные ниже записи в файл конфигурации сервера (web.config).  
  
1. Добавьте раздел `<client>`, который описывает конечную точку для объекта сеанса.  В этом сценарии сервер также выступает в роли клиента, и его нужно настроить соответствующим образом.  
  
2. В разделе `<services>` объявите конечные точки службы для фабрики и объекта сеанса.  Это позволит клиенту связаться с конечными точками службы, получить адрес <xref:System.ServiceModel.EndpointAddress10> и создать канал сеанса.  
  
 Ниже приведен пример файла конфигурации с этими параметрами.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <client>  
      <endpoint name="sessionbound"  
                address="net.tcp://localhost:8081/SessionBoundObject"  
                binding="netTcpBinding"  
                contract="Shared.ISessionBoundObject"/>  
    </client>  
  
    <services>  
      <service name="Server.MySessionBoundObject">  
        <endpoint address="net.tcp://localhost:8081/SessionBoundObject"  
                  binding="netTcpBinding"   
                  contract="Shared.ISessionBoundObject" />  
      </service>  
      <service name="Server.SessionBoundFactory">  
        <endpoint address="net.tcp://localhost:8081/SessionBoundFactory"  
                  binding="netTcpBinding"   
                  contract="Shared.ISessionBoundFactory" />  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
 Добавьте приведенные ниже строки в консольное приложение для резидентного размещения службы и запустите приложение.  
  
```csharp  
ServiceHost factoryHost = new ServiceHost(typeof(SessionBoundFactory));  
factoryHost.Open();  
  
ServiceHost sessionBoundServiceHost = new ServiceHost(  
typeof(MySessionBoundObject));  
sessionBoundServiceHost.Open();  
```  
  
### <a name="step-4-configure-the-client-and-call-the-service"></a>Шаг 4. Настройка клиента и вызов службы  
 Настройте клиент так, чтобы он мог связываться со службами WCF, добавив указанные ниже записи в файл конфигурации приложения проекта (app.config).  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <client>  
      <endpoint name="sessionbound"   
                address="net.tcp://localhost:8081/SessionBoundObject"   
                binding="netTcpBinding"   
                contract="Shared.ISessionBoundObject"/>  
      <endpoint name="factory"   
                address="net.tcp://localhost:8081/SessionBoundFactory"   
                binding="netTcpBinding"   
                contract="Shared.ISessionBoundFactory"/>  
    </client>    
  </system.serviceModel>  
</configuration>  
```  
  
 Для вызова службы добавьте в клиент код, выполняющий следующие задачи:  
  
1. создание канала для связи со службой `ISessionBoundFactory`;  
  
2. использование канала для вызова службы `ISessionBoundFactory` и получения объекта <xref:System.ServiceModel.EndpointAddress10>;  
  
3. создание канала для получения объекта сеанса с помощью адреса <xref:System.ServiceModel.EndpointAddress10>;  
  
4. вызов методов `SetCurrentValue` и `GetCurrentValue` для демонстрации того, что в рамках нескольких вызовов используется один и тот же экземпляр объекта.  
  
```csharp  
ChannelFactory<ISessionBoundFactory> factory =  
        new ChannelFactory<ISessionBoundFactory>("factory");  
  
ISessionBoundFactory sessionBoundFactory = factory.CreateChannel();  
  
EndpointAddress10 address = sessionBoundFactory.GetInstanceAddress();  
  
ChannelFactory<ISessionBoundObject> sessionBoundObjectFactory =  
    new ChannelFactory<ISessionBoundObject>(  
        new NetTcpBinding(),  
        address.ToEndpointAddress());  
  
ISessionBoundObject sessionBoundObject =  
        sessionBoundObjectFactory.CreateChannel();  
  
sessionBoundObject.SetCurrentValue("Hello");  
if (sessionBoundObject.GetCurrentValue() == "Hello")  
{  
    Console.WriteLine("Session-full instance management works as expected");  
}  
```  
  
## <a name="see-also"></a>См. также

- [Базовое программирование для WCF](../wcf/basic-wcf-programming.md)
- [Проектирование и реализация служб](../wcf/designing-and-implementing-services.md)
- [Создание клиентов](../wcf/building-clients.md)
- [Дуплексные службы](../wcf/feature-details/duplex-services.md)
