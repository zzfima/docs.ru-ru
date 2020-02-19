---
title: Перенос из .NET на платформу WCF
ms.date: 03/30/2017
ms.assetid: 16902a42-ef80-40e9-8c4c-90e61ddfdfe5
ms.openlocfilehash: 4b6996b01da6312486649482ffbb812fcb021306
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452556"
---
# <a name="migrating-from-net-remoting-to-wcf"></a>Перенос из .NET на платформу WCF
В этой статье описан процесс переноса приложения с переходом от использования удаленного взаимодействия .NET к использованию Windows Communication Foundation (WCF). В ней сравниваются сходные принципы работы с этими продуктами и описывается выполнение некоторых наиболее распространенных сценариев удаленного взаимодействия в WCF.  
  
 Удаленное взаимодействие .NET — это устаревший продукт, который поддерживается только в целях обеспечения обратной совместимости. Использование этого продукта в средах со смешанными уровнями доверия не является безопасным, поскольку он не может поддерживать отдельные уровни доверия для клиента и сервера. Например, ни при каких обстоятельствах не следует предоставлять конечную точку удаленного взаимодействия .NET интернет-клиентам или недоверенным клиентам. Рекомендуется перенести существующие приложения удаленного взаимодействия на базу более новых и безопасных технологий. Если в структуре приложения используется только протокол HTTP и архитектура RESTful, рекомендуется воспользоваться веб-API ASP.NET. Дополнительные сведения см. в статье, посвященной веб-API ASP.NET. Если приложение основано на SOAP или требует использования протоколов, отличных от HTTP, например TCP, рекомендуется использовать WCF.  

## <a name="comparing-net-remoting-to-wcf"></a>Сравнение удаленного взаимодействия .NET и WCF  
 В этом разделе сравниваются основные структурные элементы системы удаленного взаимодействия .NET с аналогичными элементами WCF. Эти стандартные блоки будут использоваться позже для создания некоторых распространенных сценариев клиент-сервер в WCF. На следующей диаграмме представлены основные сходства и различия между удаленным взаимодействием .NET и WCF.  
  
||Удаленное взаимодействие .NET|WCF|  
|-|-------------------|---------|  
|Тип сервера|Подкласс MarshalByRefObject|Отметка атрибутом [ServiceContract]|  
|Служебные операции|Открытые методы для типа сервера|Отметка атрибутом [OperationContract]|  
|Сериализация|ISerializable или [Serializable]|DataContractSerializer или XmlSerializer|  
|Передаваемые объекты|По значению или по ссылке|Только по значению|  
|Ошибки и исключения|Любые сериализуемые исключения|Фаултконтракт\<Тдетаил >|  
|Прокси-объекты клиента|Строго типизированные прозрачные прокси-объекты создаются автоматически из MarshalByRefObjects.|Строго типизированные прокси-серверы создаются по запросу с помощью ChannelFactory\<TChannel >|  
|Требуемая платформа|Клиент и сервер должны использовать ОС Microsoft и .NET.|Кроссплатформенный|  
|Формат сообщений|Private|Отраслевые стандарты (SOAP, WS-* и т. п.)|  
  
### <a name="server-implementation-comparison"></a>Сравнение реализации сервера  
  
#### <a name="creating-a-server-in-net-remoting"></a>Создание сервера в системе удаленного взаимодействия .NET  
 Типы сервера удаленного взаимодействия .NET должны производиться из подкласса MarshalByRefObject и определять методы, которые может вызывать клиент, следующим образом.  
  
```csharp
public class RemotingServer : MarshalByRefObject  
{  
    public Customer GetCustomer(int customerId) { … }  
}  
```  
  
 Открытые методы этого типа сервера становятся открытым контрактом, доступным для клиентов.  Открытый интерфейс сервера и его реализация не разделяются и обрабатываются одним типом.  
  
 После определения типа сервера его можно сделать доступным для клиентов, как показано в следующем примере:  
  
```csharp
TcpChannel channel = new TcpChannel(8080);  
ChannelServices.RegisterChannel(channel, ensureSecurity : true);  
RemotingConfiguration.RegisterWellKnownServiceType(  
    typeof(RemotingServer),   
    "RemotingServer",   
    WellKnownObjectMode.Singleton);  
Console.WriteLine("RemotingServer is running.  Press ENTER to terminate...");  
Console.ReadLine();  
```  
  
 Существуют различные способы предоставления доступа к типу удаленного взаимодействия как к серверу, включая использование файлов конфигурации. Это лишь один пример.  
  
#### <a name="creating-a-server-in-wcf"></a>Создание сервера в WCF  
 Эквивалентное действие в WCF включает создание двух типов: открытого «контракта службы» и конкретной реализации. Первый тип объявляется как интерфейс, отмеченный атрибутом [ServiceContract]. Доступные клиентам методы отмечаются атрибутом [OperationContract]:  
  
```csharp
[ServiceContract]  
public interface IWCFServer  
{  
    [OperationContract]  
    Customer GetCustomer(int customerId);  
}  
```  
  
 Реализация сервера определяется в отдельном конкретном классе, как показано в следующем примере:  
  
```csharp
public class WCFServer : IWCFServer  
{  
    public Customer GetCustomer(int customerId) { … }  
}  
```  
  
 После определения этих типов клиентам можно предоставить доступ к серверу WCF, как показано в следующем примере:  
  
```csharp
NetTcpBinding binding = new NetTcpBinding();  
Uri baseAddress = new Uri("net.tcp://localhost:8000/wcfserver");  
  
using (ServiceHost serviceHost = new ServiceHost(typeof(WCFServer), baseAddress))  
{  
    serviceHost.AddServiceEndpoint(typeof(IWCFServer), binding, baseAddress);  
    serviceHost.Open();  
  
    Console.WriteLine($"The WCF server is ready at {baseAddress}.");
    Console.WriteLine("Press <ENTER> to terminate service...");  
    Console.WriteLine();  
    Console.ReadLine();  
}  
```  
  
> [!NOTE]
> В обоих примерах используется TCP для обеспечения максимального сходства. См. пошаговые руководства по сценариям, приведенные далее в этой статье, чтобы ознакомиться с примерами с использованием HTTP.  
  
 Существуют различные способы настройки и размещения служб WCF. Это лишь один пример размещения, называемый «резидентным размещением». Дополнительные сведения см. в следующих разделах:  
  
- [Практическое руководство. Определение контракта службы](how-to-define-a-wcf-service-contract.md)  
  
- [Настройка служб с использованием файлов конфигурации](configuring-services-using-configuration-files.md)  
  
- [Размещение служб](hosting-services.md)  
  
### <a name="client-implementation-comparison"></a>Сравнение реализации клиента  
  
#### <a name="creating-a-client-in-net-remoting"></a>Создание клиента в системе удаленного взаимодействия .NET  
 После создания доступного объекта-сервера удаленного взаимодействия .NET он может использоваться клиентами, как показано в следующем примере:  
  
```csharp
TcpChannel channel = new TcpChannel();  
ChannelServices.RegisterChannel(channel, ensureSecurity : true);  
RemotingServer server = (RemotingServer)Activator.GetObject(  
                            typeof(RemotingServer),   
                            "tcp://localhost:8080/RemotingServer");  
  
RemotingCustomer customer = server.GetCustomer(42);  
Console.WriteLine($"Customer {customer.FirstName} {customer.LastName} received.");
```  
  
 Экземпляр RemotingServer, возвращаемый Activator.GetObject(), называется «прозрачным прокси-сервером». Он реализует открытый API для типа RemotingServer на стороне клиента, но все методы вызова объекта-сервера выполняются в рамках другого процесса или на другом компьютере.  
  
#### <a name="creating-a-client-in-wcf"></a>Создание клиента в WCF  
 Аналогичное действие в WCF предполагает использование фабрики каналов для создания прокси-объектов явным образом. Как и в системе удаленного взаимодействия, прокси-объект можно использовать для вызова операций на сервере, как показано в следующем примере:  
  
```csharp
NetTcpBinding binding = new NetTcpBinding();  
String url = "net.tcp://localhost:8000/wcfserver";  
EndpointAddress address = new EndpointAddress(url);  
ChannelFactory<IWCFServer> channelFactory =   
    new ChannelFactory<IWCFServer>(binding, address);  
IWCFServer server = channelFactory.CreateChannel();  
  
Customer customer = server.GetCustomer(42);  
Console.WriteLine($"  Customer {customer.FirstName} {customer.LastName} received.");
```  
  
 Это пример программирования на уровне канала, так как он обладает максимальным сходством с примером удаленного взаимодействия. Также доступен **Добавление ссылки на службу** подход в Visual Studio, который создает код для упрощения программирования клиента. Дополнительные сведения см. в следующих разделах:  
  
- [Программирование клиентов на уровне канала](./extending/client-channel-level-programming.md)  
  
- [Как добавить, обновить или удалить ссылку на службу](/visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference)  
  
### <a name="serialization-usage"></a>Использование сериализации  
 Удаленное взаимодействие .NET и WCF используют сериализацию для передачи объектов между клиентом и сервером, но они отличаются в следующих важных аспектах.  
  
1. Они используют разные сериализаторы и соглашения для указания сериализуемых объектов.  
  
2. Система удаленного взаимодействия .NET поддерживает сериализацию «по ссылке» и разрешает доступ к методу или свойству на одном уровне для выполнения кода на другом уровне, что нарушает границы безопасности. Эта возможность создает уязвимости системы безопасности и является одной из основных причин, по которым клиентам, не обладающим должным уровнем доверия, не следует предоставлять доступ к конечным точкам удаленного взаимодействия.  
  
3. Сериализация в системе удаленного взаимодействия строится на принципе явного отказа (с явным исключением объектов, не подлежащих сериализации), а сериализация в WCF — на принципе явного согласия (с явным указанием объектов для сериализации).  
  
#### <a name="serialization-in-net-remoting"></a>Сериализация в среде удаленного взаимодействия .NET  
 Система удаленного взаимодействия .NET поддерживает два способа сериализации и десериализации объектов между клиентом и сервером.  
  
- *По значению* — значения объекта сериализуются через границы уровня, а новый экземпляр этого объекта создается на другом уровне. Любые вызовы методов и свойств этого нового экземпляра выполняются только на локальном компьютере и не влияют на исходный объект или уровень.  
  
- *По ссылке* — специальная "ссылка на объект" сериализуется через границы уровня. Когда один уровень взаимодействует с методами или свойствами данного объекта, он устанавливает обратную связь с исходным объектом на исходном уровне. Объекты по ссылке могут передаваться в любом направлении — с сервера на клиент или с клиента на сервер.  
  
 Типы по значению в системе удаленного взаимодействия обозначены атрибутом [Serializable] или реализуют интерфейс ISerializable, как показано в следующем примере:  
  
```csharp
[Serializable]  
public class RemotingCustomer  
{  
    public string FirstName { get; set; }  
    public string LastName { get; set; }  
    public int CustomerId { get; set; }  
}  
```  
  
 Типы по ссылке являются производными от класса MarshalByRefObject, как показано в следующем примере:  
  
```csharp
public class RemotingCustomerReference : MarshalByRefObject  
{  
    public string FirstName { get; set; }  
    public string LastName { get; set; }  
    public int CustomerId { get; set; }  
}  
```  
  
 Очень важно понимать последствия использования объектов по ссылке в системе удаленного взаимодействия. Если какой-либо уровень (клиент или сервер) отправляет объект по ссылке на другой уровень, все вызовы методов выполняются на уровне, к которому относится объект. Например методы вызова клиента для объекта по ссылке, возвращаемого сервером, выполняют код на сервере. Аналогичным образом, методы вызова сервера объекта по ссылке, предоставляемого клиентом, выполняют код на клиенте. По этой причине использование системы удаленного взаимодействия .NET рекомендуется только в средах с полным доверием. Предоставление открытой конечной точки удаленного взаимодействия .NET ненадежным клиентам делает сервер удаленного взаимодействия уязвимым для атак.  
  
#### <a name="serialization-in-wcf"></a>Сериализация в WCF  
 WCF поддерживает только сериализацию по значению. Наиболее распространенный способ определения типа для обмена между клиентом и сервером показан в следующем примере:  
  
```csharp
[DataContract]  
public class WCFCustomer  
{  
    [DataMember]  
    public string FirstName { get; set; }  
  
    [DataMember]  
    public string LastName { get; set; }  
  
    [DataMember]  
    public int CustomerId { get; set; }  
}  
```  
  
 Атрибут [DataContract] определяет этот тип как тип, доступный для сериализации и десериализации между клиентом и сервером. Атрибут [DataMember] определяет отдельные свойства или поля для сериализации.  
  
 Когда WCF отправляет объект между уровнями, он сериализует только значения и создает новый экземпляр объекта на другом уровне. Любое взаимодействие со значениями объекта осуществляется только на локальном уровне — они не взаимодействуют с другим уровнем в отличие от объектов по ссылке системы удаленного взаимодействия .NET. Дополнительные сведения см. в разделе [сериализация и десериализация](./feature-details/serialization-and-deserialization.md).  
  
### <a name="exception-handling-capabilities"></a>Возможности обработки исключений  
  
#### <a name="exceptions-in-net-remoting"></a>Исключения в системе удаленного взаимодействия .NET  
 Исключения, создаваемые удаленным сервером, сериализуются, отправляются на клиент и возникают локально на стороне клиента так же, как и любые другие исключения. Можно создать пользовательские исключения путем формирования подкласса типа «Исключения» и отметки его атрибутом [Serializable].   Большинство исключений платформы уже отмечены таким образом, что обеспечивает их создание сервером, сериализацию и повторное создание на клиенте. Хотя такой подход удобно применять во время разработки, сведения, хранящиеся на стороне сервера, могут быть случайно раскрыты клиенту. Это одна из многих причин, по которым систему удаленного взаимодействия следует использовать только в средах с полным уровнем доверия.  
  
#### <a name="exceptions-and-faults-in-wcf"></a>Исключения и сбои в WCF  
 WCF не допускает возврата произвольных типов исключений с сервера на клиент, поскольку это может привести к непреднамеренному разглашению сведений. Если операция службы вызывает непредвиденное исключение, это приводит к созданию общего исключения FaultException на стороне клиента. Это исключение не несет никакой информации о том, почему или где возникла проблема, и для некоторых приложений этого достаточно. Если приложениям требуется передача на клиент более полных сведений об ошибке, это осуществляется путем определения контракта сбоя.  
  
 Для этого сначала создайте тип [DataContract], содержащий сведения о сбое.  
  
```csharp
[DataContract]  
public class CustomerServiceFault  
{  
    [DataMember]  
    public string ErrorMessage { get; set; }  
  
    [DataMember]  
    public int CustomerId {get;set;}  
}  
```  
  
 Укажите контракт сбоя для каждой операции службы.  
  
```csharp
[ServiceContract]  
public interface IWCFServer  
{  
    [OperationContract]  
    [FaultContract(typeof(CustomerServiceFault))]  
    Customer GetCustomer(int customerId);  
}  
```  
  
 Сервер сообщает о состоянии сбоя путем создания исключения FaultException.  
  
```csharp
throw new FaultException<CustomerServiceFault>(  
    new CustomerServiceFault() {   
        CustomerId = customerId,   
        ErrorMessage = "Illegal customer Id"   
    });  
```  
  
 И каждый раз, когда клиент отправляет запрос на сервер, он может перехватить сбои как обычное исключение.  
  
```csharp
try  
{  
    Customer customer = server.GetCustomer(-1);  
}  
catch (FaultException<CustomerServiceFault> fault)  
{  
    Console.WriteLine($"Fault received: {fault.Detail.ErrorMessage}");
}  
```  
  
 Дополнительные сведения о контрактах сбоев см. в описании класса <xref:System.ServiceModel.FaultException>.  
  
### <a name="security-considerations"></a>Соображения безопасности  
  
#### <a name="security-in-net-remoting"></a>Безопасность в системе удаленного взаимодействия .NET  
 Некоторые каналы удаленного взаимодействия .NET поддерживают различные функции обеспечения безопасности, такие как проверка подлинности и шифрование на уровне канала (IPC и TCP). Для канала HTTP проверка подлинности и шифрование строятся на основе служб Internet Information Services (IIS). Несмотря на это, следует рассматривать систему удаленного взаимодействия .NET как небезопасный протокол связи, который следует использовать только в среде с полным уровнем доверия. Никогда не предоставляйте доступ к открытой конечной точке удаленного взаимодействия интернет-клиентам или клиентам без должного уровня доверия.  
  
#### <a name="security-in-wcf"></a>Безопасность в WCF  
 Система WCF была разработана с учетом аспектов безопасности, в частности для устранения ряда уязвимостей, присущих среде удаленного взаимодействия .NET. WCF обеспечивает безопасность на уровне транспорта и сообщений и предоставляет множество функций для проверки подлинности, авторизации, шифрования и т. д. Дополнительные сведения см. в следующих разделах:  
  
- [Безопасность](./feature-details/security.md)  
  
- [Руководство по безопасности WCF](./feature-details/security-guidance-and-best-practices.md)  
  
## <a name="migrating-to-wcf"></a>Миграция в WCF  
  
### <a name="why-migrate-from-remoting-to-wcf"></a>Почему необходимо выполнить миграцию с переходом от удаленного взаимодействия на WCF?  
  
- **Удаленное взаимодействие .NET — это устаревший продукт.** Как описано в разделе [удаленное взаимодействие .NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507%28v=vs.100%29), оно считается устаревшим продуктом и не рекомендуется для новых разработчиков. Для новых и существующих приложений рекомендуется использовать платформу WCF или веб-интерфейс API ASP.NET.  
  
- **WCF использует кросс-платформенные стандарты.** Решение WCF было разработано с учетом кроссплатформенного взаимодействия и поддерживает различные отраслевые стандарты (SOAP, WS-Security, WS-Trust, и т. д.). Служба WCF может взаимодействовать с клиентами, работающими под управлением других операционных систем, отличных от Windows. Удаленное взаимодействие разрабатывалось главным образом для сред, в которых серверные и клиентские приложения работают с использованием .NET Framework в операционной системе Windows.
  
- **WCF имеет встроенную безопасность.** WCF разрабатывалась с учетом соображений безопасности и предлагает множество вариантов для проверки подлинности, безопасности на уровне транспорта, безопасности на уровне сообщений и т. д. Удаленное взаимодействие было предназначено для упрощения взаимодействия приложений, но не предназначено для обеспечения безопасности в средах, не являющихся доверенными. Решение WCF было разработано для работы как в доверенных, так и в недоверенных средах.  
  
### <a name="migration-recommendations"></a>Рекомендации по миграции  
 Ниже приведены рекомендуемые действия по миграции от удаленного взаимодействия .NET к WCF.  
  
- **Создайте контракт службы.** Определите типы интерфейсов службы и отметьте их атрибутом [ServiceContract]. Отметьте все методы, доступные для вызова клиентами, атрибутом [OperationContract].  
  
- **Создайте контракт данных.** Определите типы данных, которыми будут обмениваться сервер и клиент, и отметьте их атрибутом [DataContract]. Отметьте все поля и свойства, доступные для использования клиентом, атрибутом [DataMember].  
  
- **Создайте контракт сбоя (необязательно).** Создайте типы, которыми будут обмениваться сервер и клиент при возникновении ошибок. Отметьте эти типы атрибутами [DataContract] и [DataMember], чтобы обеспечить возможность их сериализации. Для всех операций службы, отмеченных атрибутом [OperationContract], также задайте атрибут [FaultContract], чтобы указать, какие ошибки они могут возвращать.  
  
- **Настройте и разместите службу.** После создания контракта службы необходимо настроить привязку для предоставления службы в конечной точке. Дополнительные сведения см. в разделе [конечные точки: адреса, привязки и контракты](./feature-details/endpoints-addresses-bindings-and-contracts.md).  
  
 После переноса приложения удаленного взаимодействия на платформу WCF необходимо удалить зависимости от решения удаленного взаимодействия .NET. Это позволит удалить какие-либо уязвимости удаленного взаимодействия из приложения. Вот эти шаги.  
  
- **Прекращение использования MarshalByRefObject.** Тип MarshalByRefObject существует только для решения удаленного взаимодействия и не используется в WCF. Все типы приложений с вложенным классом MarshalByRefObject должны быть удалены или изменены.  
  
- **Прекращение использования [Serializable] и ISerializable.** Атрибут [Serializable] и интерфейс ISerializable изначально были разработаны для сериализации типов в доверенных средах, и они используются при удаленном взаимодействии. При сериализации WCF используются типы с атрибутом [DataContract] и [DataMember]. Типы данных, используемых приложением, следует изменить таким образом, чтобы использовать [DataContract] и отказаться от использования ISerializable или [Serializable].  
  
### <a name="migration-scenarios"></a>Сценарии миграции  
 Теперь давайте рассмотрим выполнение следующих распространенных сценариев удаленного взаимодействия в WCF.  
  
1. Сервер возвращает клиенту объект по значению.  
  
2. Сервер возвращает клиенту объект по ссылке.  
  
3. Клиент отправляет серверу объект по значению.  
  
> [!NOTE]
> В среде WCF отправка клиентом серверу объекта по ссылке не разрешена.  
  
 При просмотре сценариев предполагается, что базовые интерфейсы для удаленного взаимодействия .NET выглядят так, как показано в следующем примере. Реализация удаленного взаимодействия .NET в данном случае не имеет значения, поскольку мы хотим показать только способы использования WCF для реализации аналогичных функциональных возможностей.  
  
```csharp
public class RemotingServer : MarshalByRefObject  
{  
    // Demonstrates server returning object by-value  
    public Customer GetCustomer(int customerId) {…}  
  
    // Demonstrates server returning object by-reference  
    public CustomerReference GetCustomerReference(int customerId) {…}  
  
    // Demonstrates client passing object to server by-value  
    public bool UpdateCustomer(Customer customer) {…}  
}  
```  
  
#### <a name="scenario-1-service-returns-an-object-by-value"></a>Сценарий 1. Служба возвращает объект по значению  
 В этом сценарии показана ситуация, когда сервер возвращает объект клиенту по ссылке. WCF всегда возвращает объекты с сервера по значению, поэтому ниже просто приведено описание создания стандартной службы WCF.  
  
1. Сначала определите открытый интерфейс для службы WCF и пометьте его атрибутом [ServiceContract]. Мы используем [OperationContract] для определения методов на стороне сервера, которые будет вызывать клиент.  
  
   ```csharp
   [ServiceContract]  
   public interface ICustomerService  
   {  
       [OperationContract]  
       Customer GetCustomer(int customerId);  
  
       [OperationContract]  
       bool UpdateCustomer(Customer customer);  
   }  
   ```  
  
2. Следующим шагом является создание контракта данных для этой службы. Это осуществляется путем создания классов (а не интерфейсов), отмеченных атрибутом [DataContract]. Отдельные свойства или поля, которые должны быть видны и для клиента, и для сервера, отмечаются атрибутом [DataMember]. Если следует разрешить производные типы, необходимо использовать атрибут [KnownType] для их идентификации. Единственными типами, сериализацию или десериализацию которых для этой службы разрешает WCF, являются типы в интерфейсе службы и эти «известные типы». Попытки обмена любыми другими типами, не указанными в списке, будут отклонены.  
  
   ```csharp
   [DataContract]  
   [KnownType(typeof(PremiumCustomer))]  
   public class Customer  
   {  
       [DataMember]  
       public string FirstName { get; set; }  
  
       [DataMember]  
       public string LastName { get; set; }  
  
       [DataMember]  
       public int CustomerId { get; set; }  
   }  
  
   [DataContract]  
   public class PremiumCustomer : Customer   
   {  
       [DataMember]  
       public int AccountId { get; set; }  
   }  
   ```  
  
3. Далее представлена реализация интерфейса службы.  
  
   ```csharp  
   public class CustomerService : ICustomerService  
   {  
       public Customer GetCustomer(int customerId)  
       {  
           // read from database  
       }  
  
       public bool UpdateCustomer(Customer customer)  
       {  
           // write to database  
       }  
   }  
   ```  
  
4. Для запуска службы WCF необходимо объявить конечную точку, предоставляющую доступ к интерфейсу службы по определенному URL-адресу с помощью определенной привязки WCF. Как правило, это осуществляется путем добавления в файл web.config серверного проекта следующих разделов.  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <services>  
          <service name="Server.CustomerService">  
            <endpoint address="http://localhost:8083/CustomerService"  
                      binding="basicHttpBinding"  
                      contract="Shared.ICustomerService" />  
          </service>  
        </services>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
5. После этого можно запустить службу WCF с помощью следующего кода:  
  
   ```csharp
   ServiceHost customerServiceHost = new ServiceHost(typeof(CustomerService));  
       customerServiceHost.Open();  
   ```  
  
     При запуске метод ServiceHost использует файл web.config для установления надлежащего контракта, привязки и конечной точки. Дополнительные сведения о файлах конфигурации см. в разделе [Настройка служб с помощью файлов конфигурации](./configuring-services-using-configuration-files.md). Этот метод запуска сервера называется резидентным размещением. Дополнительные сведения о других вариантах размещения служб WCF см. в разделе [службы хостинга](./hosting-services.md).  
  
6. В файле app.config клиентского проекта должны быть объявлены соответствующие сведения о привязке для конечной точки службы. Самый простой способ сделать это в Visual Studio — использовать **Добавление ссылки на службу**, который будет автоматически обновлять файл App. config. Эти же изменения также можно добавить вручную.  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <client>  
          <endpoint name="customerservice"  
                    address="http://localhost:8083/CustomerService"  
                    binding="basicHttpBinding"  
                    contract="Shared.ICustomerService"/>  
        </client>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
     Дополнительные сведения об использовании **Добавление ссылки на службу**см. [в разделе как добавить, обновить или удалить ссылку на службу](/visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference).  
  
7. Теперь мы можем вызвать службу WCF из клиента. Для этого мы создаем фабрику каналов для этой службы, запрашиваем канал и напрямую вызываем требуемый метод по этому каналу. Это возможно благодаря тому, что канал реализует интерфейс службы и обрабатывает базовую логику запроса/ответа. Возвращаемым значением при выполнении данного вызова метода является десериализованная копия ответа сервера.  
  
   ```csharp
   ChannelFactory<ICustomerService> factory =  
       new ChannelFactory<ICustomerService>("customerservice");  
   ICustomerService service = factory.CreateChannel();  
   Customer customer = service.GetCustomer(42);  
   Console.WriteLine($"  Customer {customer.FirstName} {customer.LastName} received.");
   ```  
  
 Объекты, возвращаемые WCF с сервера на клиент, всегда передаются по значению. Объекты представляют собой десериализованные копии данных, отправленных сервером. Клиент может вызывать методы в этих локальных копиях без опасности вызова серверного кода в ходе обратных вызовов.  
  
#### <a name="scenario-2-server-returns-an-object-by-reference"></a>Сценарий 2. Служба возвращает объект по ссылке  
 В этом сценарии показана ситуация, когда сервер предоставляет объект клиенту по ссылке. В удаленном взаимодействии .NET эта операция обрабатывается автоматически для любого типа, производного от MarshalByRefObject, который сериализуется по ссылке. Примером такого сценария является разрешение нескольким клиентам иметь независимые объекты, связанные с сеансами, на стороне сервера. Как упоминалось ранее, объекты, возвращаемые службой WCF, всегда передаются по значению, поэтому прямой эквивалент объектов, передаваемых по ссылке, отсутствует, но существует возможность реализации метода, сходного с семантикой возвращения по ссылке, с использованием объекта <xref:System.ServiceModel.EndpointAddress10>. Это сериализуемый объект, передаваемый по значению, с помощью которого клиент может получить на сервере объект, переданный по ссылке в рамках сеанса. Это обеспечивает возможность реализации сценария, при котором различные клиенты обладают независимыми объектами, связанными с сеансами, на стороне сервера.  
  
1. Сначала необходимо определить контракт службы WCF, соответствующий самому объекту, связанному с сеансами.  
  
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
  
    > [!TIP]
    > Обратите внимание, что объект, связанный с сеансами, отмечен атрибутом [ServiceContract], что делает его обычным интерфейсом службы WCF. Настройка свойства SessionMode указывает на связь службы с сеансом. В WCF сеанс — это способ согласования нескольких сообщений, пересылаемых между двумя конечными точками. Это означает, что, как только клиент устанавливает подключение к службе, между ним и сервером создается сеанс. Клиент использует единственный уникальный экземпляр объекта на стороне сервера для любых взаимодействий в рамках данного сеанса.  
  
2. Далее необходимо представить реализацию этого интерфейса службы. Обозначение его при помощи атрибута [ServiceBehavior] и настройка InstanceContextMode позволяет сообщить WCF, что мы хотим использовать уникальный экземпляр этого типа для каждого сеанса.  
  
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
  
3. Теперь нам требуется способ получения экземпляра этого объекта, связанного с сеансом. Для этого необходимо создать другой интерфейс службы WCF, который возвращает объект EndpointAddress10. Это сериализуемая форма конечной точки, с помощью которой клиент может создать объект сеанса.  
  
   ```csharp
   [ServiceContract]  
       public interface ISessionBoundFactory  
       {  
           [OperationContract]  
           EndpointAddress10 GetInstanceAddress();  
       }  
   ```  
  
     И мы реализуем эту службу WCF:  
  
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
  
     Эта реализация поддерживает единственную фабрику каналов для создания объектов, связанных с сеансами. При вызове метода GetInstanceAddress() создается канал и объект EndpointAddress10, указывающий на удаленный адрес, связанный с этим каналом. EndpointAddress10 — это просто тип данных, который можно вернуть клиенту по значению.  
  
4. Нам нужно изменить файл конфигурации сервера, выполнив два действия, представленные в следующем примере:  
  
    1. Объявите \<> клиента, описывающий конечную точку для объекта сеанса. Это необходимо, поскольку сервер также выступает в качестве клиента в данной ситуации.  
  
    2. Объявите конечные точки для фабрики и объекта, связанного с сеансом. Это необходимо, чтобы клиент мог взаимодействовать с конечными точками службы для получения EndpointAddress10 и создания канала сеанса.  
  
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
          <service name="Server.CustomerService">  
            <endpoint address="http://localhost:8083/CustomerService"  
                      binding="basicHttpBinding"  
                      contract="Shared.ICustomerService" />  
          </service>  
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
  
     И затем мы можем запустить эти службы:  
  
   ```csharp
   ServiceHost factoryHost = new ServiceHost(typeof(SessionBoundFactory));  
   factoryHost.Open();  
  
   ServiceHost sessionHost = new ServiceHost(typeof(MySessionBoundObject));  
   sessionHost.Open();  
   ```  
  
5. Мы настраиваем клиент путем объявления тех же конечных точек в файле app.config проекта.  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <client>  
          <endpoint name="customerservice"  
                    address="http://localhost:8083/CustomerService"  
                    binding="basicHttpBinding"  
                    contract="Shared.ICustomerService"/>  
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
  
6. Чтобы создать и использовать этот объект, связанный с сеансом, клиент должен выполнить следующие действия.  
  
    1. Создать канал для службы ISessionBoundFactory.  
  
    2. Использовать этот канал для вызова данной службы в целях получения EndpointAddress10.  
  
    3. Использовать EndpointAddress10 для создания канала в целях получения объекта, связанного с сеансом.  
  
    4. Взаимодействовать с объектом, связанным с сеансом, чтобы продемонстрировать сохранение одного и того же экземпляра при нескольких вызовах.  
  
   ```csharp
   ChannelFactory<ISessionBoundFactory> channelFactory =   
       new ChannelFactory<ISessionBoundFactory>("factory");  
   ISessionBoundFactory sessionFactory = channelFactory.CreateChannel();  
  
   EndpointAddress10 address1 = sessionFactory.GetInstanceAddress();  
   EndpointAddress10 address2 = sessionFactory.GetInstanceAddress();  
  
   ChannelFactory<ISessionBoundObject> sessionObjectFactory1 =   
       new ChannelFactory<ISessionBoundObject>(new NetTcpBinding(),   
                                               address1.ToEndpointAddress());  
   ChannelFactory<ISessionBoundObject> sessionObjectFactory2 =   
       new ChannelFactory<ISessionBoundObject>(new NetTcpBinding(),   
                                               address2.ToEndpointAddress());  
  
   ISessionBoundObject sessionInstance1 = sessionObjectFactory1.CreateChannel();  
   ISessionBoundObject sessionInstance2 = sessionObjectFactory2.CreateChannel();  
  
   sessionInstance1.SetCurrentValue("Hello");  
   sessionInstance2.SetCurrentValue("World");  
  
   if (sessionInstance1.GetCurrentValue() == "Hello" &&  
       sessionInstance2.GetCurrentValue() == "World")  
   {  
       Console.WriteLine("sessionful server object works as expected");  
   }  
   ```  
  
 WCF всегда возвращает объекты по значению, но существует возможность поддержки аналога семантики возвращения по ссылке посредством EndpointAddress10. Это позволяет клиенту запрашивать экземпляр службы WCF, связанный с сеансом, после чего он может взаимодействовать с ней так же, как и с любой другой службой WCF.  
  
#### <a name="scenario-3-client-sends-server-a-by-value-instance"></a>Сценарий 3. Клиент отправляет серверу экземпляр по значению  
 В этом сценарии показан клиент, отправляющий серверу экземпляр объекта, не являющийся примитивом, по значению. Поскольку WCF отправляет объекты только по значению, в этом сценарии показано обычное использование WCF.  
  
1. Используйте ту же службу WCF, которая использовалась в сценарии 1.  
  
2. Используйте клиент для создания нового объекта по значению (Customer), создайте канал для взаимодействия со службой ICustomerService и отправьте в нее объект.  
  
   ```csharp
   ChannelFactory<ICustomerService> factory =  
       new ChannelFactory<ICustomerService>("customerservice");  
   ICustomerService service = factory.CreateChannel();  
   PremiumCustomer customer = new PremiumCustomer {   
   FirstName = "Bob",   
   LastName = "Jones",   
   CustomerId = 43,   
   AccountId = 99};  
   bool success = service.UpdateCustomer(customer);  
   Console.WriteLine($"  Server returned {success}.");
   ```  
  
     Объект Customer будет сериализован и отправлен на сервер, где он десериализуется в новую копию этого объекта.  
  
    > [!NOTE]
    > Этот код также демонстрирует отправку производного типа (PremiumCustomer). Интерфейс службы ожидает получения объекта Customer, но атрибут [KnownType] класса Customer указывает, что был также разрешен тип PremiumCustomer. Любая попытка сериализации или десериализации любого другого типа посредством этого интерфейса службы WCF завершится ошибкой.  
  
 Стандартные обмены данными в службе WCF осуществляются по значению. Это гарантирует, что методы вызова этих объектов данных реализуются только локально без вызова кода на другом уровне. Хотя можно получить нечто вроде объектов по ссылке, возвращаемых *с* сервера, клиент не может *передать на сервер объект по* ссылке. Сценарий, при котором клиенту и серверу необходимо обмениваться сообщениями друг с другом, можно реализовать в WCF с помощью дуплексной службы. Дополнительные сведения см. в разделе [Дуплексные службы](./feature-details/duplex-services.md).  
  
## <a name="summary"></a>Сводка  
 Удаленное взаимодействие .NET — это платформа взаимодействия, предназначенная для использования только в средах с полным доверием. Это устаревший продукт, который поддерживается только в целях обеспечения обратной совместимости. Он не должен использоваться для разработки новых приложений. И напротив, служба WCF была разработана с учетом безопасности, поэтому ее рекомендуется использовать для поддержки новых и существующих приложений. Корпорация Майкрософт рекомендует выполнить перенос существующих приложений удаленного взаимодействия с переходом к использованию WCF или веб-интерфейса API ASP.NET.
