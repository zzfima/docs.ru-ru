---
title: Практическое руководство. Миграция DCOM с управляемым кодом в WCF
ms.date: 03/30/2017
ms.assetid: 52961ffc-d1c7-4f83-832c-786444b951ba
ms.openlocfilehash: 4d814d9c2e62af9aa5cc2a8d1f84738b69e36ad1
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217180"
---
# <a name="how-to-migrate-managed-code-dcom-to-wcf"></a><span data-ttu-id="cd10a-102">Практическое руководство. Миграция DCOM с управляемым кодом в WCF</span><span class="sxs-lookup"><span data-stu-id="cd10a-102">How to: Migrate Managed-Code DCOM to WCF</span></span>
<span data-ttu-id="cd10a-103">Для вызовов управляемого кода между серверами и клиентами в распределенной среде рекомендуется использовать технологию Windows Communication Foundation (WCF), а не модель DCOM, из соображений безопасности.</span><span class="sxs-lookup"><span data-stu-id="cd10a-103">Windows Communication Foundation (WCF) is the recommended and secure choice over Distributed Component Object Model (DCOM) for managed code calls between servers and clients in a distributed environment.</span></span> <span data-ttu-id="cd10a-104">В этом разделе описывается, как перенести код из DCOM в WCF в перечисленных ниже ситуациях.</span><span class="sxs-lookup"><span data-stu-id="cd10a-104">This article shows how you to migrate code from DCOM to WCF for the following scenarios.</span></span>  
  
- <span data-ttu-id="cd10a-105">Удаленная служба возвращает клиенту объект по значению.</span><span class="sxs-lookup"><span data-stu-id="cd10a-105">The remote service returns an object by-value to the client</span></span>  
  
- <span data-ttu-id="cd10a-106">Клиент отправляет удаленной службе объект по значению.</span><span class="sxs-lookup"><span data-stu-id="cd10a-106">The client sends an object by-value to the remote service</span></span>  
  
- <span data-ttu-id="cd10a-107">Удаленная служба возвращает клиенту объект по ссылке.</span><span class="sxs-lookup"><span data-stu-id="cd10a-107">The remote service returns an object by-reference to the client</span></span>  
  
 <span data-ttu-id="cd10a-108">По соображениям безопасности отправка объекта по ссылке от клиента службе в WCF запрещена.</span><span class="sxs-lookup"><span data-stu-id="cd10a-108">For security reasons, sending an object by-reference from the client to the service is not allowed in WCF.</span></span> <span data-ttu-id="cd10a-109">Сценарий, при котором клиенту и серверу необходимо обмениваться сообщениями друг с другом, можно реализовать в WCF с помощью дуплексной службы.</span><span class="sxs-lookup"><span data-stu-id="cd10a-109">A scenario that requires a conversation back and forth between client and server can be achieved in WCF using a duplex service.</span></span>  <span data-ttu-id="cd10a-110">Дополнительные сведения о дуплексных службах см. в разделе [Дуплексные службы](../wcf/feature-details/duplex-services.md).</span><span class="sxs-lookup"><span data-stu-id="cd10a-110">For more information about duplex services, see [Duplex Services](../wcf/feature-details/duplex-services.md).</span></span>  
  
 <span data-ttu-id="cd10a-111">Дополнительные сведения о создании служб WCF и клиентов для них см. в разделах [Базовое программирование для WCF](../wcf/basic-wcf-programming.md), [Проектирование и реализация служб](../wcf/designing-and-implementing-services.md), а также [Создание клиентов](../wcf/building-clients.md).</span><span class="sxs-lookup"><span data-stu-id="cd10a-111">For more details about creating WCF services and clients for those services, see [Basic WCF Programming](../wcf/basic-wcf-programming.md), [Designing and Implementing Services](../wcf/designing-and-implementing-services.md), and [Building Clients](../wcf/building-clients.md).</span></span>  
  
## <a name="dcom-example-code"></a><span data-ttu-id="cd10a-112">Пример кода DCOM</span><span class="sxs-lookup"><span data-stu-id="cd10a-112">DCOM example code</span></span>  
 <span data-ttu-id="cd10a-113">Для этих сценариев интерфейсы DCOM, проиллюстрированные с помощью WCF, имеют приведенную ниже структуру.</span><span class="sxs-lookup"><span data-stu-id="cd10a-113">For these scenarios, the DCOM interfaces that are illustrated using WCF have the following structure:</span></span>  
  
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
  
## <a name="the-service-returns-an-object-by-value"></a><span data-ttu-id="cd10a-114">Служба возвращает объект по значению</span><span class="sxs-lookup"><span data-stu-id="cd10a-114">The service returns an object by-value</span></span>  
 <span data-ttu-id="cd10a-115">В этом сценарии выполняется вызов службы, а ее метод возвращает объект, который передается по значению с сервера клиенту.</span><span class="sxs-lookup"><span data-stu-id="cd10a-115">For this scenario, you make a call to a service and it method returns an object, which is passed by-value from the server to the client.</span></span> <span data-ttu-id="cd10a-116">Такой сценарий представляет приведенный ниже вызов COM.</span><span class="sxs-lookup"><span data-stu-id="cd10a-116">This scenario represents the following COM call:</span></span>  
  
```csharp  
public interface IRemoteService  
{  
    Customer GetObjectByValue();  
}  
```  
  
 <span data-ttu-id="cd10a-117">В этом случае клиент получает из удаленной службы десериализованную копию объекта.</span><span class="sxs-lookup"><span data-stu-id="cd10a-117">In this scenario, the client receives a deserialized copy of an object from the remote service.</span></span> <span data-ttu-id="cd10a-118">Клиент может взаимодействовать с этой локальной копией, не выполняя обратные вызовы в службу.</span><span class="sxs-lookup"><span data-stu-id="cd10a-118">The client can interact with this local copy without calling back to the service.</span></span>  <span data-ttu-id="cd10a-119">Иными словами, клиент получает гарантию, что при вызове методов применительно к локальной копии служба не будет задействована никоим образом.</span><span class="sxs-lookup"><span data-stu-id="cd10a-119">In other words, the client is guaranteed the service will not be involved in any way when methods on the local copy are called.</span></span> <span data-ttu-id="cd10a-120">WCF всегда возвращает объекты из службы по значению, поэтому ниже описывается создание стандартной службы WCF.</span><span class="sxs-lookup"><span data-stu-id="cd10a-120">WCF always returns objects from the service by value, so the following steps describe creating a regular WCF service.</span></span>  
  
### <a name="step-1-define-the-wcf-service-interface"></a><span data-ttu-id="cd10a-121">Шаг 1. Определение интерфейса службы WCF</span><span class="sxs-lookup"><span data-stu-id="cd10a-121">Step 1: Define the WCF service interface</span></span>  
 <span data-ttu-id="cd10a-122">Определите открытый интерфейс для службы WCF и пометьте его атрибутом [<xref:System.ServiceModel.ServiceContractAttribute>].</span><span class="sxs-lookup"><span data-stu-id="cd10a-122">Define a public interface for the WCF service and mark it with the [<xref:System.ServiceModel.ServiceContractAttribute>] attribute.</span></span>  <span data-ttu-id="cd10a-123">Пометьте атрибутом [<xref:System.ServiceModel.OperationContractAttribute>] методы, к которым необходимо предоставить доступ клиентам.</span><span class="sxs-lookup"><span data-stu-id="cd10a-123">Mark the methods you want to expose to clients with the [<xref:System.ServiceModel.OperationContractAttribute>] attribute.</span></span> <span data-ttu-id="cd10a-124">В примере ниже показано использование этих атрибутов для определения интерфейса на стороне сервера и методов интерфейса, которые может вызывать клиент.</span><span class="sxs-lookup"><span data-stu-id="cd10a-124">The following example shows using these attributes to identify the server-side interface and interface methods a client can call.</span></span> <span data-ttu-id="cd10a-125">Метод, используемый в этом сценарии, выделен полужирным шрифтом.</span><span class="sxs-lookup"><span data-stu-id="cd10a-125">The method used for this scenario is shown in bold.</span></span>  
  
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
  
### <a name="step-2-define-the-data-contract"></a><span data-ttu-id="cd10a-126">Шаг 2. Определение контракта данных</span><span class="sxs-lookup"><span data-stu-id="cd10a-126">Step 2: Define the data contract</span></span>  
 <span data-ttu-id="cd10a-127">Далее следует создать для службы контракт данных, описывающий то, как будет происходить обмен данными между службой и клиентами.</span><span class="sxs-lookup"><span data-stu-id="cd10a-127">Next you should create a data contract for the service, which will describe how the data will be exchanged between the service and its clients.</span></span>  <span data-ttu-id="cd10a-128">Классы, описываемые в контракте данных, следует пометить атрибутом [<xref:System.Runtime.Serialization.DataContractAttribute>].</span><span class="sxs-lookup"><span data-stu-id="cd10a-128">Classes described in the data contract should be marked with the [<xref:System.Runtime.Serialization.DataContractAttribute>] attribute.</span></span> <span data-ttu-id="cd10a-129">Отдельные свойства или поля, которые должны быть видны и для клиента, и для сервера, отмечаются атрибутом [<xref:System.Runtime.Serialization.DataMemberAttribute>].</span><span class="sxs-lookup"><span data-stu-id="cd10a-129">The individual properties or fields you want visible to both client and server should be marked with the [<xref:System.Runtime.Serialization.DataMemberAttribute>] attribute.</span></span> <span data-ttu-id="cd10a-130">Чтобы разрешить использование типов, производных от класса, в контракте данных, их следует указать с помощью атрибута [<xref:System.Runtime.Serialization.KnownTypeAttribute>].</span><span class="sxs-lookup"><span data-stu-id="cd10a-130">If you want types derived from a class in the data contract to be allowed, you must identify them with the [<xref:System.Runtime.Serialization.KnownTypeAttribute>] attribute.</span></span> <span data-ttu-id="cd10a-131">WCF сериализует и десериализует только те типы, которые входят в интерфейс службы или определены как известные.</span><span class="sxs-lookup"><span data-stu-id="cd10a-131">WCF will only serialize or deserialize types in the service interface and types identified as known types.</span></span> <span data-ttu-id="cd10a-132">При попытке использовать неизвестный тип возникнет исключение.</span><span class="sxs-lookup"><span data-stu-id="cd10a-132">If you attempt to use a type that is not a known type, an exception will occur.</span></span>  
  
 <span data-ttu-id="cd10a-133">Дополнительные сведения о контрактах данных см. в разделе [Контракты данных](../wcf/samples/data-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="cd10a-133">For more information about data contracts, see [Data Contracts](../wcf/samples/data-contracts.md).</span></span>  
  
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
  
### <a name="step-3-implement-the-wcf-service"></a><span data-ttu-id="cd10a-134">Шаг 3. Реализация службы WCF</span><span class="sxs-lookup"><span data-stu-id="cd10a-134">Step 3: Implement the WCF service</span></span>  
 <span data-ttu-id="cd10a-135">Далее следует реализовать класс службы WCF, который реализует интерфейс, определенный в предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="cd10a-135">Next, you should implement the WCF service class that implements the interface you defined in the previous step.</span></span>  
  
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
  
### <a name="step-4-configure-the-service-and-the-client"></a><span data-ttu-id="cd10a-136">Шаг 4. Настройка службы и клиента</span><span class="sxs-lookup"><span data-stu-id="cd10a-136">Step 4: Configure the service and the client</span></span>  
 <span data-ttu-id="cd10a-137">Для запуска службы WCF необходимо объявить конечную точку, предоставляющую доступ к интерфейсу службы по определенному URL-адресу с помощью определенной привязки WCF.</span><span class="sxs-lookup"><span data-stu-id="cd10a-137">To run a WCF service, you need to declare an endpoint that exposes that service interface at a specific URL using a specific WCF binding.</span></span> <span data-ttu-id="cd10a-138">Привязка определяет транспорт, кодировку и протокол, используемые для обмена данными между клиентами и сервером.</span><span class="sxs-lookup"><span data-stu-id="cd10a-138">A binding specifies the transport, encoding and protocol details for the clients and server to communicate.</span></span> <span data-ttu-id="cd10a-139">Привязки обычно добавляются в файл конфигурации проекта службы (web.config).</span><span class="sxs-lookup"><span data-stu-id="cd10a-139">You typically add bindings to the service project’s configuration file (web.config).</span></span> <span data-ttu-id="cd10a-140">Ниже приведен пример записи привязки для службы.</span><span class="sxs-lookup"><span data-stu-id="cd10a-140">The following shows a binding entry for the example service:</span></span>  
  
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
  
 <span data-ttu-id="cd10a-141">Затем нужно настроить клиент в соответствии с информацией о привязке, определенной в службе.</span><span class="sxs-lookup"><span data-stu-id="cd10a-141">Next, you need to configure the client to match the binding information specified by the service.</span></span> <span data-ttu-id="cd10a-142">Для этого добавьте в файл конфигурации клиентского приложения (app.config) приведенный ниже код.</span><span class="sxs-lookup"><span data-stu-id="cd10a-142">To do so, add the following to the client’s application configuration (app.config) file.</span></span>  
  
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
  
### <a name="step-5-run-the-service"></a><span data-ttu-id="cd10a-143">Шаг 5. Запуск службы</span><span class="sxs-lookup"><span data-stu-id="cd10a-143">Step 5: Run the service</span></span>  
 <span data-ttu-id="cd10a-144">Наконец, вы можете произвести резидентное размещение в консольном приложении, добавив в приложение службы приведенные ниже строки и запустив его.</span><span class="sxs-lookup"><span data-stu-id="cd10a-144">Finally, you can self-host it in a console application by adding the following lines to the service app, and starting the app.</span></span> <span data-ttu-id="cd10a-145">Дополнительные сведения о других способах размещения приложения службы WCF см. в разделе [Размещение служб](../wcf/hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="cd10a-145">For more information about other ways to host a WCF service application, [Hosting Services](../wcf/hosting-services.md).</span></span>  
  
```csharp  
ServiceHost customerServiceHost = new ServiceHost(typeof(CustomerService));  
customerServiceHost.Open();  
```  
  
### <a name="step-6-call-the-service-from-the-client"></a><span data-ttu-id="cd10a-146">Шаг 6. Вызов службы из клиента</span><span class="sxs-lookup"><span data-stu-id="cd10a-146">Step 6: Call the service from the client</span></span>  
 <span data-ttu-id="cd10a-147">Для вызова службы из клиента нужно создать для нее фабрику каналов, а затем запросить канал, чтобы получить возможность вызывать метод `GetCustomer` непосредственно из клиента.</span><span class="sxs-lookup"><span data-stu-id="cd10a-147">To call the service from the client, you need to create a channel factory for the service, and request a channel, which will enable you to directly call the `GetCustomer` method directly from the client.</span></span> <span data-ttu-id="cd10a-148">Канал реализует интерфейс службы и отвечает за базовую логику запросов и ответов.</span><span class="sxs-lookup"><span data-stu-id="cd10a-148">The channel implements the service’s interface and handles the underlying request/reply logic for you.</span></span>  <span data-ttu-id="cd10a-149">Возвращаемое значение метода представляет собой десериализованную копию ответа службы.</span><span class="sxs-lookup"><span data-stu-id="cd10a-149">The return value from that method call is the deserialized copy of the service response.</span></span>  
  
```csharp  
ChannelFactory<ICustomerManager> factory =   
     new ChannelFactory<ICustomerManager>("customermanager");  
ICustomerManager service = factory.CreateChannel();  
Customer customer = service.GetCustomer("Mary", "Smith");  
```  
  
## <a name="the-client-sends-a-by-value-object-to-the-server"></a><span data-ttu-id="cd10a-150">Клиент отправляет серверу объект по значению</span><span class="sxs-lookup"><span data-stu-id="cd10a-150">The client sends a by-value object to the server</span></span>  
 <span data-ttu-id="cd10a-151">В этом случае клиент отправляет серверу объект по значению.</span><span class="sxs-lookup"><span data-stu-id="cd10a-151">In this scenario, the client sends an object to the server, by-value.</span></span> <span data-ttu-id="cd10a-152">Это означает, что сервер получит десериализованную копию объекта.</span><span class="sxs-lookup"><span data-stu-id="cd10a-152">This means that the server will receive a deserialized copy of the object.</span></span>  <span data-ttu-id="cd10a-153">Сервер может вызывать методы применительно к этой копии с гарантией того, что обратные вызовы кода клиента выполняться не будут.</span><span class="sxs-lookup"><span data-stu-id="cd10a-153">The server can call methods on that copy and be guaranteed there is no callback into client code.</span></span> <span data-ttu-id="cd10a-154">Как было замечено ранее, обмен данными с WCF обычно происходит по значению.</span><span class="sxs-lookup"><span data-stu-id="cd10a-154">As mentioned previously, normal WCF exchanges of data are by-value.</span></span>  <span data-ttu-id="cd10a-155">Это гарантирует, что вызовы методов объектов выполняются только локально без вызова кода клиента.</span><span class="sxs-lookup"><span data-stu-id="cd10a-155">This guarantees that calling methods on one of these objects executes locally only – it will not invoke code on the client.</span></span>  
  
 <span data-ttu-id="cd10a-156">Такой сценарий представляет приведенный ниже вызов метода COM.</span><span class="sxs-lookup"><span data-stu-id="cd10a-156">This scenario represents the following COM method call:</span></span>  
  
```csharp  
public interface IRemoteService  
{  
    void SendObjectByValue(Customer customer);  
}  
```  
  
 <span data-ttu-id="cd10a-157">В этом сценарии используется тот же интерфейс службы и тот же контракт данных, что и в первом примере.</span><span class="sxs-lookup"><span data-stu-id="cd10a-157">This scenario uses the same service interface and data contract as shown in the first example.</span></span> <span data-ttu-id="cd10a-158">Кроме того, клиент и служба настраиваются точно так же.</span><span class="sxs-lookup"><span data-stu-id="cd10a-158">In addition, the client and service will be configured in the same way.</span></span> <span data-ttu-id="cd10a-159">В этом примере для отправки объекта создается и запускается канал аналогичным образом.</span><span class="sxs-lookup"><span data-stu-id="cd10a-159">In this example, a channel is created to send the object and run the same way.</span></span> <span data-ttu-id="cd10a-160">Однако в этом примере вы создадите клиент, который вызывает службу, передавая объект по значению.</span><span class="sxs-lookup"><span data-stu-id="cd10a-160">However, for this example, you will create a client that calls the service, passing an object by-value.</span></span> <span data-ttu-id="cd10a-161">Метод службы, который клиент вызывает в контракте службы, выделен полужирным шрифтом.</span><span class="sxs-lookup"><span data-stu-id="cd10a-161">The service method the client will call in the service contract is shown in bold:</span></span>  
  
```csharp  
[ServiceContract]  
public interface ICustomerManager  
{  
    [OperationContract]     void StoreCustomer(Customer customer);  
  
    [OperationContract]  
    Customer GetCustomer(string firstName, string lastName);  
}  
```  
  
### <a name="add-code-to-the-client-that-sends-a-by-value-object"></a><span data-ttu-id="cd10a-162">Добавление в клиент кода для отправки объекта по значению</span><span class="sxs-lookup"><span data-stu-id="cd10a-162">Add code to the client that sends a by-value object</span></span>  
 <span data-ttu-id="cd10a-163">В приведенном ниже коде показано, как клиент создает объект customer для передачи по значению, создает канал для обмена данными со службой `ICustomerManager` и отправляет ей объект customer.</span><span class="sxs-lookup"><span data-stu-id="cd10a-163">The following code shows how the client creates a new by-value customer object, creates a channel to communicate with the `ICustomerManager` service, and sends the customer object to it.</span></span>  
  
 <span data-ttu-id="cd10a-164">Объект customer будет сериализован и отправлен в службу, где он десериализуется в новую копию этого объекта.</span><span class="sxs-lookup"><span data-stu-id="cd10a-164">The customer object will be serialized, and sent to the service, where it is deserialized by the service into a new copy of that object.</span></span>  <span data-ttu-id="cd10a-165">Любые методы этого объекта, вызываемые службой, будут выполняться только локально на сервере.</span><span class="sxs-lookup"><span data-stu-id="cd10a-165">Any methods the service calls on this object will execute only locally on the server.</span></span> <span data-ttu-id="cd10a-166">Важно отметить, что этот код иллюстрирует отправку производного типа (`PremiumCustomer`).</span><span class="sxs-lookup"><span data-stu-id="cd10a-166">It’s important to note that this code illustrates sending a derived type (`PremiumCustomer`).</span></span>  <span data-ttu-id="cd10a-167">Контракт службы ожидает объекта `Customer`, но в контракте данных службы используется атрибут [<xref:System.Runtime.Serialization.KnownTypeAttribute>], указывающий, что объект `PremiumCustomer` также допустим.</span><span class="sxs-lookup"><span data-stu-id="cd10a-167">The service contract expects a `Customer` object, but the service data contract uses the [<xref:System.Runtime.Serialization.KnownTypeAttribute>] attribute to indicate that `PremiumCustomer` is also allowed.</span></span>  <span data-ttu-id="cd10a-168">Попытка сериализации или десериализации любого другого типа посредством этого интерфейса службы WCF завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="cd10a-168">WCF will fail attempts to serialize or deserialize any other type via this service interface.</span></span>  
  
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
  
## <a name="the-service-returns-an-object-by-reference"></a><span data-ttu-id="cd10a-169">Служба возвращает объект по ссылке</span><span class="sxs-lookup"><span data-stu-id="cd10a-169">The service returns an object by reference</span></span>  
 <span data-ttu-id="cd10a-170">В этом случае клиентское приложение вызывает удаленную службу, и метод возвращает объект, который передается по ссылке из службы в клиент.</span><span class="sxs-lookup"><span data-stu-id="cd10a-170">For this scenario, the client app makes a call to the remote service and the method returns an object, which is passed by reference from the service to the client.</span></span>  
  
 <span data-ttu-id="cd10a-171">Как было замечено ранее, службы WCF всегда возвращают объекты по значению.</span><span class="sxs-lookup"><span data-stu-id="cd10a-171">As mentioned previously, WCF services always return object by value.</span></span>  <span data-ttu-id="cd10a-172">Однако вы можете получить требуемый результат с помощью класса <xref:System.ServiceModel.EndpointAddress10>.</span><span class="sxs-lookup"><span data-stu-id="cd10a-172">However, you can achieve a similar result by using the <xref:System.ServiceModel.EndpointAddress10> class.</span></span>  <span data-ttu-id="cd10a-173"><xref:System.ServiceModel.EndpointAddress10> — это сериализуемый объект, передаваемый по значению, с помощью которого клиент может получить на сервере объект, переданный по ссылке в рамках сеанса.</span><span class="sxs-lookup"><span data-stu-id="cd10a-173">The <xref:System.ServiceModel.EndpointAddress10> is a serializable by-value object that can be used by the client to obtain a sessionful by-reference object on the server.</span></span>  
  
 <span data-ttu-id="cd10a-174">Поведение переданного по ссылке объекта в WCF, которое показано в этом сценарии, отличается от его поведения в DCOM.</span><span class="sxs-lookup"><span data-stu-id="cd10a-174">The behavior of the by-reference object in WCF shown in this scenario is different than DCOM.</span></span>  <span data-ttu-id="cd10a-175">В DCOM сервер может вернуть клиенту объект по ссылке напрямую, и клиент может вызывать методы этого объекта, которые выполняются на сервере.</span><span class="sxs-lookup"><span data-stu-id="cd10a-175">In DCOM, the server can return a by-reference object to the client directly, and the client can call that object’s methods, which execute on the server.</span></span>  <span data-ttu-id="cd10a-176">Однако в WCF объекты всегда возвращаются по значению.</span><span class="sxs-lookup"><span data-stu-id="cd10a-176">In WCF, however, the object returned is always by-value.</span></span>  <span data-ttu-id="cd10a-177">Клиент должен получить объект по значению, представленный <xref:System.ServiceModel.EndpointAddress10>, и с помощью него создать собственный объект, полученный по ссылке в рамках сеанса.</span><span class="sxs-lookup"><span data-stu-id="cd10a-177">The client must take that by-value object, represented by <xref:System.ServiceModel.EndpointAddress10> and use it to create its own sessionful by-reference object.</span></span>  <span data-ttu-id="cd10a-178">Методы объекта сеанса, вызываемые клиентом, выполняются на сервере. Иными словами, этот полученный по ссылке объект в WCF является обычным объектом WCF, настроенным как объект сеанса.</span><span class="sxs-lookup"><span data-stu-id="cd10a-178">The client method calls on the sessionful object execute on the server.In other words, this by-reference object in WCF is a normal WCF service that is configured to be sessionful.</span></span>  
  
 <span data-ttu-id="cd10a-179">В WCF сеанс — это способ согласования нескольких сообщений, пересылаемых между двумя конечными точками.</span><span class="sxs-lookup"><span data-stu-id="cd10a-179">In WCF, a session is a way of correlating multiple messages sent between two endpoints.</span></span>  <span data-ttu-id="cd10a-180">Это означает, что, как только клиент устанавливает подключение к службе, между ним и сервером создается сеанс.</span><span class="sxs-lookup"><span data-stu-id="cd10a-180">This means that once a client obtains a connection to this service, a session will be established between the client and the server.</span></span>  <span data-ttu-id="cd10a-181">Клиент использует единственный уникальный экземпляр объекта на стороне сервера для любых взаимодействий в рамках данного сеанса.</span><span class="sxs-lookup"><span data-stu-id="cd10a-181">The client will use a single unique instance of the server-side object for all its interactions within this single session.</span></span> <span data-ttu-id="cd10a-182">Контракты сеансов WCF аналогичны схемам запросов и ответов, ориентированным на подключения.</span><span class="sxs-lookup"><span data-stu-id="cd10a-182">Sessionful WCF contracts are similar to connection-oriented network request/response patterns.</span></span>  
  
 <span data-ttu-id="cd10a-183">Этот сценарий представлен приведенным ниже методом DCOM.</span><span class="sxs-lookup"><span data-stu-id="cd10a-183">This scenario is represented by the following DCOM method.</span></span>  
  
```csharp  
public interface IRemoteService  
{  
    IRemoteObject GetObjectByReference();  
}  
```  
  
### <a name="step-1-define-the-sessionful-wcf-service-interface-and-implementation"></a><span data-ttu-id="cd10a-184">Шаг 1. Определение интерфейса сеанса службы WCF и его реализация</span><span class="sxs-lookup"><span data-stu-id="cd10a-184">Step 1: Define the Sessionful WCF service interface and implementation</span></span>  
 <span data-ttu-id="cd10a-185">Сначала определите интерфейс службы WCF, содержащий объект сеанса.</span><span class="sxs-lookup"><span data-stu-id="cd10a-185">First, define a WCF service interface that contains the sessionful object.</span></span>  
  
 <span data-ttu-id="cd10a-186">В этом коде объект сеанса помечен атрибутом `ServiceContract`, который определяет его как обычный интерфейс службы WCF.</span><span class="sxs-lookup"><span data-stu-id="cd10a-186">In this code, the sessionful object is marked with the `ServiceContract` attribute, which identifies it as a regular WCF service interface.</span></span>  <span data-ttu-id="cd10a-187">Кроме того, свойству <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A> присвоено значение, указывающее, что это будет служба сеанса.</span><span class="sxs-lookup"><span data-stu-id="cd10a-187">In addition, the <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A> property is set to indicate it will be a sessionful service.</span></span>  
  
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
  
 <span data-ttu-id="cd10a-188">В приведенном ниже коде показана реализация службы.</span><span class="sxs-lookup"><span data-stu-id="cd10a-188">The following code shows the service implementation.</span></span>  
  
 <span data-ttu-id="cd10a-189">Служба помечена атрибутом [ServiceBehavior], а ее свойству InstanceContextMode присвоено значение InstanceContextMode.PerSessions, указывающее, что для каждого сеанса должен создаваться уникальный экземпляр этого типа.</span><span class="sxs-lookup"><span data-stu-id="cd10a-189">The service is marked with the [ServiceBehavior] attribute, and its InstanceContextMode property set to InstanceContextMode.PerSessions to indicate that a unique instance of this type should be created for each session.</span></span>  
  
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
  
### <a name="step-2-define-the-wcf-factory-service-for-the-sessionful-object"></a><span data-ttu-id="cd10a-190">Шаг 2. Определение службы фабрики WCF для объекта сеанса</span><span class="sxs-lookup"><span data-stu-id="cd10a-190">Step 2: Define the WCF factory service for the sessionful object</span></span>  
 <span data-ttu-id="cd10a-191">Необходимо определить и реализовать службу, создающую объект сеанса.</span><span class="sxs-lookup"><span data-stu-id="cd10a-191">The service that creates the sessionful object must be defined and implemented.</span></span> <span data-ttu-id="cd10a-192">В следующем примере кода показано, как это сделать:</span><span class="sxs-lookup"><span data-stu-id="cd10a-192">The following code shows how to do this.</span></span> <span data-ttu-id="cd10a-193">Этот код создает еще одну службу WCF, которая возвращает объект <xref:System.ServiceModel.EndpointAddress10>.</span><span class="sxs-lookup"><span data-stu-id="cd10a-193">This code creates another WCF service that returns an <xref:System.ServiceModel.EndpointAddress10> object.</span></span>  <span data-ttu-id="cd10a-194">Это сериализуемая форма конечной точки, с помощью которой можно создать объект сеанса.</span><span class="sxs-lookup"><span data-stu-id="cd10a-194">This is a serializable form of an endpoint the can use to create the session-full object.</span></span>  
  
```csharp  
[ServiceContract]  
    public interface ISessionBoundFactory  
    {  
        [OperationContract]  
        EndpointAddress10 GetInstanceAddress();  
    }  
```  
  
 <span data-ttu-id="cd10a-195">Ниже приведена реализация этой службы.</span><span class="sxs-lookup"><span data-stu-id="cd10a-195">The following is the implementation of this service.</span></span> <span data-ttu-id="cd10a-196">Эта реализация поддерживает единственную фабрику каналов для создания объектов, связанных с сеансами.</span><span class="sxs-lookup"><span data-stu-id="cd10a-196">This implementation maintains a singleton channel factory to create sessionful objects.</span></span>  <span data-ttu-id="cd10a-197">При вызове метода `GetInstanceAddress` создается канал и объект <xref:System.ServiceModel.EndpointAddress10>, указывающий на удаленный адрес, связанный с этим каналом.</span><span class="sxs-lookup"><span data-stu-id="cd10a-197">When `GetInstanceAddress` is called, it creates a channel and creates an <xref:System.ServiceModel.EndpointAddress10> object that points to the remote address associated with this channel.</span></span>   <span data-ttu-id="cd10a-198"><xref:System.ServiceModel.EndpointAddress10> — это тип данных, который можно вернуть клиенту по значению.</span><span class="sxs-lookup"><span data-stu-id="cd10a-198"><xref:System.ServiceModel.EndpointAddress10> is a data type that can be returned to the client by-value.</span></span>
  
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
  
### <a name="step-3-configure-and-start-the-wcf-services"></a><span data-ttu-id="cd10a-199">Шаг 3. Настройка и запуск служб WCF</span><span class="sxs-lookup"><span data-stu-id="cd10a-199">Step 3: Configure and start the WCF services</span></span>  
 <span data-ttu-id="cd10a-200">Для размещения этих служб необходимо добавить указанные ниже записи в файл конфигурации сервера (web.config).</span><span class="sxs-lookup"><span data-stu-id="cd10a-200">To host these services, you will need to make the following additions to the server’s configuration file (web.config).</span></span>  
  
1. <span data-ttu-id="cd10a-201">Добавьте раздел `<client>`, который описывает конечную точку для объекта сеанса.</span><span class="sxs-lookup"><span data-stu-id="cd10a-201">Add a `<client>` section that describes the endpoint for the sessionful object.</span></span>  <span data-ttu-id="cd10a-202">В этом сценарии сервер также выступает в роли клиента, и его нужно настроить соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="cd10a-202">In this scenario, the server also acts as a client and must be configured to enable this.</span></span>  
  
2. <span data-ttu-id="cd10a-203">В разделе `<services>` объявите конечные точки службы для фабрики и объекта сеанса.</span><span class="sxs-lookup"><span data-stu-id="cd10a-203">In the `<services>` section, declare service endpoints for the factory and sessionful object.</span></span>  <span data-ttu-id="cd10a-204">Это позволит клиенту связаться с конечными точками службы, получить адрес <xref:System.ServiceModel.EndpointAddress10> и создать канал сеанса.</span><span class="sxs-lookup"><span data-stu-id="cd10a-204">This enables the client to communicate with the service endpoints, acquire the <xref:System.ServiceModel.EndpointAddress10> and create the sessionful channel.</span></span>  
  
 <span data-ttu-id="cd10a-205">Ниже приведен пример файла конфигурации с этими параметрами.</span><span class="sxs-lookup"><span data-stu-id="cd10a-205">The following is an example configuration file with these settings:</span></span>  
  
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
  
 <span data-ttu-id="cd10a-206">Добавьте приведенные ниже строки в консольное приложение для резидентного размещения службы и запустите приложение.</span><span class="sxs-lookup"><span data-stu-id="cd10a-206">Add the following lines to a console application, to self-host the service, and start the app.</span></span>  
  
```csharp  
ServiceHost factoryHost = new ServiceHost(typeof(SessionBoundFactory));  
factoryHost.Open();  
  
ServiceHost sessionBoundServiceHost = new ServiceHost(  
typeof(MySessionBoundObject));  
sessionBoundServiceHost.Open();  
```  
  
### <a name="step-4-configure-the-client-and-call-the-service"></a><span data-ttu-id="cd10a-207">Шаг 4. Настройка клиента и вызов службы</span><span class="sxs-lookup"><span data-stu-id="cd10a-207">Step 4: Configure the client and call the service</span></span>  
 <span data-ttu-id="cd10a-208">Настройте клиент так, чтобы он мог связываться со службами WCF, добавив указанные ниже записи в файл конфигурации приложения проекта (app.config).</span><span class="sxs-lookup"><span data-stu-id="cd10a-208">Configure the client to communicate with the WCF services by making the following entries in the project’s application configuration file (app.config).</span></span>  
  
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
  
 <span data-ttu-id="cd10a-209">Для вызова службы добавьте в клиент код, выполняющий следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="cd10a-209">To call the service, add the code to the client to do the following:</span></span>  
  
1. <span data-ttu-id="cd10a-210">создание канала для связи со службой `ISessionBoundFactory`;</span><span class="sxs-lookup"><span data-stu-id="cd10a-210">Create a channel to the `ISessionBoundFactory` service.</span></span>  
  
2. <span data-ttu-id="cd10a-211">использование канала для вызова службы `ISessionBoundFactory` и получения объекта <xref:System.ServiceModel.EndpointAddress10>;</span><span class="sxs-lookup"><span data-stu-id="cd10a-211">Use the channel to invoke the `ISessionBoundFactory` service an obtain an <xref:System.ServiceModel.EndpointAddress10> object.</span></span>  
  
3. <span data-ttu-id="cd10a-212">создание канала для получения объекта сеанса с помощью адреса <xref:System.ServiceModel.EndpointAddress10>;</span><span class="sxs-lookup"><span data-stu-id="cd10a-212">Use the <xref:System.ServiceModel.EndpointAddress10> to create a channel to obtain a sessionful object.</span></span>  
  
4. <span data-ttu-id="cd10a-213">вызов методов `SetCurrentValue` и `GetCurrentValue` для демонстрации того, что в рамках нескольких вызовов используется один и тот же экземпляр объекта.</span><span class="sxs-lookup"><span data-stu-id="cd10a-213">Call the `SetCurrentValue` and `GetCurrentValue` methods to demonstrate it remains the same object instance is used across multiple calls.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cd10a-214">См. также:</span><span class="sxs-lookup"><span data-stu-id="cd10a-214">See also</span></span>

- [<span data-ttu-id="cd10a-215">Базовое программирование для WCF</span><span class="sxs-lookup"><span data-stu-id="cd10a-215">Basic WCF Programming</span></span>](../wcf/basic-wcf-programming.md)
- [<span data-ttu-id="cd10a-216">Проектирование и реализация служб</span><span class="sxs-lookup"><span data-stu-id="cd10a-216">Designing and Implementing Services</span></span>](../wcf/designing-and-implementing-services.md)
- [<span data-ttu-id="cd10a-217">Создание клиентов</span><span class="sxs-lookup"><span data-stu-id="cd10a-217">Building Clients</span></span>](../wcf/building-clients.md)
- [<span data-ttu-id="cd10a-218">Дуплексные службы</span><span class="sxs-lookup"><span data-stu-id="cd10a-218">Duplex Services</span></span>](../wcf/feature-details/duplex-services.md)
