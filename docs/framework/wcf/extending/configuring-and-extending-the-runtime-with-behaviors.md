---
title: Настройка и расширение среды выполнения с помощью поведений
ms.date: 03/30/2017
helpviewer_keywords:
- attaching extensions using behaviors [WCF]
ms.assetid: 149b99b6-6eb6-4f45-be22-c967279677d9
ms.openlocfilehash: 3a1e369fe52a2a529fb3511d9a65067b4a56ec1e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70797253"
---
# <a name="configuring-and-extending-the-runtime-with-behaviors"></a>Настройка и расширение среды выполнения с помощью поведений
Поведение позволяет изменять поведение по умолчанию и добавлять пользовательские расширения, которые проверяют и проверяют конфигурацию службы или изменяют поведение во время выполнения в приложениях клиента Windows Communication Foundation (WCF) и служб. В этом разделе описаны интерфейсы поведений, способы их реализации, а также порядок их добавления в описания служб (в приложениях служб) и конечных точек (в клиентских приложениях) как программным образом, так и с помощью файла конфигурации. Дополнительные сведения об использовании предоставляемых системой поведений см. в разделе [Определение поведения службы во время выполнения](../specifying-service-run-time-behavior.md) и [Указание поведения клиента во время выполнения](../specifying-client-run-time-behavior.md).  
  
## <a name="behaviors"></a>поведения  
 Типы поведения добавляются в объекты описания конечной точки службы или службы (в службе или на клиенте соответственно), прежде чем эти объекты будут использоваться Windows Communication Foundation (WCF) для создания среды выполнения, которая выполняет службу WCF или клиент WCF. Если эти поведения вызываются в процессе создания среды выполнения, то они могут получать доступ к свойствам и методам среды выполнения, которые позволяют изменить создаваемую среду выполнения с использованием других контрактов, привязок и адресов.  
  
### <a name="behavior-methods"></a>Методы поведений  
 Все поведения имеют `AddBindingParameters` метод `ApplyDispatchBehavior` , метод, `Validate` метод и `ApplyClientBehavior` метод с одним исключением: Поскольку <xref:System.ServiceModel.Description.IServiceBehavior> не может выполняться в клиенте, он не реализует `ApplyClientBehavior`.  
  
- Метод `AddBindingParameters` служит для изменения или добавления пользовательских объектов в коллекцию, к которой могут общаться пользовательские привязки при создании среды выполнения. Например, с помощью этого метода можно задать требования защиты, которые влияют на способ создания канала, но не известны разработчику канала.  
  
- Метод `Validate` служит для проверки дерева описания и соответствующего объекта среды выполнения, чтобы убедиться, что они соответствуют определенному набору условий.  
  
- Методы `ApplyDispatchBehavior` и `ApplyClientBehavior` служат для проверки дерева описания и изменения среды выполнения в определенной области (на стороне службы или на стороне клиента соответственно). Кроме того, эти методы позволяют вставлять объекты расширения.  
  
    > [!NOTE]
    > Хотя эти методы получают дерево описания, оно доступно им только для проверки. Если изменить дерево описания, поведение станет неопределенным.  
  
 Доступ к свойствам, которые можно изменить, и к интерфейсам настройки, которые можно реализовать, осуществляется через классы среды выполнения службы и клиента. Типами службы являются классы <xref:System.ServiceModel.Dispatcher.DispatchRuntime> и <xref:System.ServiceModel.Dispatcher.DispatchOperation>. Типами клиента являются классы <xref:System.ServiceModel.Dispatcher.ClientRuntime> и <xref:System.ServiceModel.Dispatcher.ClientOperation>. Классы <xref:System.ServiceModel.Dispatcher.ClientRuntime> и <xref:System.ServiceModel.Dispatcher.DispatchRuntime> являются точками входа расширяемости для доступа к коллекциям расширения и свойствам среды выполнения клиента и службы соответственно. Аналогично классы <xref:System.ServiceModel.Dispatcher.ClientOperation> и <xref:System.ServiceModel.Dispatcher.DispatchOperation> предоставляют доступ к коллекциям расширения и свойствам среды выполнения операций клиента и операций службы соответственно. Однако из объекта среды выполнения операции, если это требуется, можно получить доступ к объекту среды выполнения с более широкой областью и наоборот.  
  
> [!NOTE]
> Описание свойств среды выполнения и типов расширений, которые можно использовать для изменения поведения клиента, см. в разделе [расширение клиентов](extending-clients.md). Описание свойств среды выполнения и типов расширений, которые можно использовать для изменения поведения при выполнении диспетчера служб, см. в разделе [Расширение диспетчеров](extending-dispatchers.md).  
  
 Большинство пользователей WCF не взаимодействуют с средой выполнения напрямую; Вместо этого они используют основные конструкции модели программирования, такие как конечные точки, контракты, привязки, адреса и атрибуты поведения для классов или поведения в файлах конфигурации. Эти конструкции составляют *дерево Description*, которое является полной спецификацией для создания среды выполнения для поддержки службы или клиента, описываемого деревом описания.  
  
 В WCF существует четыре вида поведения:  
  
- поведения служб (типы <xref:System.ServiceModel.Description.IServiceBehavior>) позволяют настраивать среду выполнения службы целиком, включая <xref:System.ServiceModel.ServiceHostBase>;  
  
- Поведения конечных точек (типы <xref:System.ServiceModel.Description.IEndpointBehavior>) позволяют настраивать конечные точки служб и соответствующие объекты <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>;  
  
- Поведения контрактов (типы <xref:System.ServiceModel.Description.IContractBehavior>) позволяют настраивать классы <xref:System.ServiceModel.Dispatcher.ClientRuntime> и <xref:System.ServiceModel.Dispatcher.DispatchRuntime> в приложениях клиентов и служб соответственно;  
  
- Поведения операций (типы <xref:System.ServiceModel.Description.IOperationBehavior>) позволяют настраивать классы <xref:System.ServiceModel.Dispatcher.ClientOperation> и <xref:System.ServiceModel.Dispatcher.DispatchOperation> в приложениях клиентов и служб.  
  
 Эти поведения можно добавлять в различные объекты описания путем реализации пользовательских атрибутов, с помощью файлов конфигурации приложений или путем их непосредственного добавления в коллекцию поведений соответствующего объекта описания. Однако их обязательно необходимо добавлять в объекты описания службы или конечной точки службы до вызова метода <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> объектов <xref:System.ServiceModel.ServiceHost> и <xref:System.ServiceModel.ChannelFactory%601>.  
  
### <a name="behavior-scopes"></a>Области поведений  
 Каждый из четырех типов поведений соответствует определенной области доступа среды выполнения.  
  
#### <a name="service-behaviors"></a>Поведения служб  
 Поведения служб, реализующие интерфейс <xref:System.ServiceModel.Description.IServiceBehavior>, являются основным механизмом для изменения всей среды выполнения службы. Имеется три механизма добавления поведений служб к службам.  
  
1. С помощью атрибута класса службы.  При создании объекта <xref:System.ServiceModel.ServiceHost> реализация класса <xref:System.ServiceModel.ServiceHost> использует отражение, чтобы обнаружить набор атрибутов типа службы. Все атрибуты, реализующие интерфейс <xref:System.ServiceModel.Description.IServiceBehavior>, добавляются в коллекцию поведений в объекте <xref:System.ServiceModel.Description.ServiceDescription>. Это позволяет таким поведениям участвовать в создании среды выполнения службы.  
  
2. Добавление поведения в коллекцию поведений в объекте <xref:System.ServiceModel.Description.ServiceDescription> программным образом. Эту задачу можно решить с помощью следующего фрагмента кода:  
  
    ```csharp
    ServiceHost host = new ServiceHost(/* Parameters */);  
    host.Description.Behaviors.Add(/* Service Behavior */);  
    ```  
  
3. Реализация пользовательского элемента <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>, который расширяет конфигурацию. Это позволяет использовать поведение службы в файлах конфигурации приложения.  
  
 Примерами поведения службы в WCF являются <xref:System.ServiceModel.ServiceBehaviorAttribute> атрибут <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>, и <xref:System.ServiceModel.Description.ServiceMetadataBehavior> поведение.  
  
#### <a name="contract-behaviors"></a>Поведения контрактов  
 Поведения контрактов, реализующие интерфейс <xref:System.ServiceModel.Description.IContractBehavior>, служат для расширения сред выполнения клиента и службы в рамках контракта.  
  
 Имеется два механизма добавления поведений контрактов к контрактам.  Первый механизм предполагает создание пользовательского атрибута, который будет использоваться в интерфейсе контракта. Когда интерфейс контракта передается либо <xref:System.ServiceModel.ServiceHost> в <xref:System.ServiceModel.ChannelFactory%601>, либо в, WCF проверяет атрибуты интерфейса. Все атрибуты, реализующие интерфейс <xref:System.ServiceModel.Description.IContractBehavior>, добавляются в коллекцию поведений в объекте <xref:System.ServiceModel.Description.ContractDescription?displayProperty=nameWithType>, созданном для этого интерфейса.  
  
 Кроме того, можно реализовать интерфейс <xref:System.ServiceModel.Description.IContractBehaviorAttribute?displayProperty=nameWithType> в атрибуте поведения пользовательского контракта. В этом случае поведение, если оно применяется, выглядит следующим образом:  
  
 •Интерфейс контракта. В этом случае поведение применяется ко всем контрактам этого типа в любой конечной точке, а WCF игнорирует значение <xref:System.ServiceModel.Description.IContractBehaviorAttribute.TargetContract%2A?displayProperty=nameWithType> свойства.  
  
 •Класс службы. В этом случае поведение применяется только к конечным точкам, контракт которых имеет значение, равное значению свойства <xref:System.ServiceModel.Description.IContractBehaviorAttribute.TargetContract%2A>.  
  
 •Класс обратного вызова. В этом случае поведение применяется к конечной точке дуплексного клиента, а WCF игнорирует значение <xref:System.ServiceModel.Description.IContractBehaviorAttribute.TargetContract%2A> свойства.  
  
 Второй механизм предполагает добавление поведения в коллекцию поведений объекта <xref:System.ServiceModel.Description.ContractDescription>.  
  
 Примеры поведения контрактов в WCF включают <xref:System.ServiceModel.DeliveryRequirementsAttribute?displayProperty=nameWithType> атрибут. Дополнительные сведения и пример см. в справочном разделе.  
  
#### <a name="endpoint-behaviors"></a>Поведения конечных точек  
 Поведения конечных точек, реализующие интерфейс <xref:System.ServiceModel.Description.IEndpointBehavior>, являются основным механизмом для изменения всей среды выполнения службы или клиента для конкретной конечной точки.  
  
 Имеется два механизма добавления поведений конечных точек к службам.  
  
1. Добавьте поведение в свойство <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A>.  
  
2. Реализуйте пользовательский элемент <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>, который расширяет конфигурацию.  
  
 Дополнительные сведения и пример см. в справочном разделе.  
  
#### <a name="operation-behaviors"></a>Поведения операций  
 Поведения операций, реализующие интерфейс <xref:System.ServiceModel.Description.IOperationBehavior>, служат для расширения сред выполнения клиента и службы для каждой из операций.  
  
 Имеется два механизма добавления поведений операций к операциям. Первый механизм предполагает создание пользовательского атрибута, который будет использоваться в методе, моделирующем операцию. <xref:System.ServiceModel.ServiceHost> При добавлении операции в <xref:System.ServiceModel.ChannelFactory>или в WCF добавляет любые <xref:System.ServiceModel.Description.IOperationBehavior> атрибуты в коллекцию <xref:System.ServiceModel.Description.OperationDescription> поведений, созданную для этой операции.  
  
 Второй механизм предполагает непосредственное добавление поведения в коллекцию поведений объекта <xref:System.ServiceModel.Description.OperationDescription>.  
  
 Примерами поведения операций в WCF являются <xref:System.ServiceModel.OperationBehaviorAttribute> <xref:System.ServiceModel.TransactionFlowAttribute>и.  
  
 Дополнительные сведения и пример см. в справочном разделе.  
  
### <a name="using-configuration-to-create-behaviors"></a>Создание поведений с помощью файла конфигурации  
 Поведения служб, конечных точек и контрактов можно разрабатывать таким образом, чтобы задавать их в коде с помощью атрибутов. Только поведения служб и конечных точек можно настраивать с помощью файлов конфигурации приложения и веб-службы. Предоставление доступа к поведениям с помощью атрибутов позволяет разработчикам задавать поведение во время компиляции; это значит, что такое поведение нельзя добавлять, удалять или изменять во время выполнения. Этот подход часто применяется для поведений, которые обязательно нужны для правильной работы службы (например, связанные с транзакциями параметры атрибута <xref:System.ServiceModel.ServiceBehaviorAttribute?displayProperty=nameWithType>). Предоставление доступа к поведениям с помощью файлов конфигурации позволяет разработчикам переложить обязанности по спецификации и настойке этих поведений на тех, кто будет развертывать службу. Такой подход удобно применять для поведений, которые являются необязательными компонентами, или для других конфигураций, которые зависят от развертывания, например, чтобы определить, нужно ли предоставлять метаданные всей службе или же только конкретной конфигурации авторизации службы.  
  
> [!NOTE]
> Также можно использовать поведения, которые поддерживают файлы конфигурации, для реализации политик применения путем их вставки в файл конфигурации machine.config и блокировки соответствующих элементов от изменений. Описание и пример см. в разделе [как Блокировка конечных точек предприятия](how-to-lock-down-endpoints-in-the-enterprise.md).  
  
 Чтобы сделать поведение доступным с помощью файла конфигурации, разработчик должен создать производный класс для класса <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>, а затем зарегистрировать расширение в конфигурации.  
  
 В следующем примере кода показано, каким образом интерфейс <xref:System.ServiceModel.Description.IEndpointBehavior> реализует объект <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>.  
  
```csharp
// BehaviorExtensionElement members  
public override Type BehaviorType  
{  
  get { return typeof(EndpointBehaviorMessageInspector); }  
}  
  
protected override object CreateBehavior()  
{  
  return new EndpointBehaviorMessageInspector();  
}  
```  
  
 Чтобы система конфигурации загрузила пользовательский объект <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>, он должен быть зарегистрирован в качестве расширения. В следующем примере кода показан файл конфигурации для предыдущего поведения конечной точки.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service   
        name="Microsoft.WCF.Documentation.SampleService"  
        behaviorConfiguration="metadataSupport"  
      >  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost:8080/ServiceMetadata" />  
          </baseAddresses>  
        </host>  
        <endpoint  
          address="/SampleService"  
          binding="wsHttpBinding"  
          behaviorConfiguration="withMessageInspector"   
          contract="Microsoft.WCF.Documentation.ISampleService"  
        />  
        <endpoint  
           address="mex"  
           binding="mexHttpBinding"  
           contract="IMetadataExchange"  
        />  
      </service>  
    </services>  
    <behaviors>  
      <serviceBehaviors>  
      <behavior name="metadataSupport">  
        <serviceMetadata httpGetEnabled="true" httpGetUrl=""/>  
      </behavior>  
      </serviceBehaviors>  
      <endpointBehaviors>  
        <behavior name="withMessageInspector">  
          <endpointMessageInspector />  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <extensions>  
      <behaviorExtensions>  
        <add   
          name="endpointMessageInspector"  
          type="Microsoft.WCF.Documentation.EndpointBehaviorMessageInspector, HostApplication, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null"  
        />  
      </behaviorExtensions>  
    </extensions>  
  </system.serviceModel>  
</configuration>  
```  
  
 Где `Microsoft.WCF.Documentation.EndpointBehaviorMessageInspector` — это тип расширения поведения, `HostApplication` а — имя сборки, в которую был скомпилирован этот класс.  
  
### <a name="evaluation-order"></a>Порядок вычисления  
 Классы <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType> и <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType> отвечают за построение среды выполнения на основе модели программирования и описания. Как было сказано выше, поведения участвуют в этом процессе, оказывая влияние на службы, конечные точки, контракты и операции.  
  
 Объект <xref:System.ServiceModel.ServiceHost> применяет поведения в следующем порядке.  
  
1. Служба  
  
2. Контракт  
  
3. Конечная точка  
  
4. Операция  
  
 В рамках одной коллекции поведений порядок не гарантируется.  
  
 Объект <xref:System.ServiceModel.ChannelFactory%601> применяет поведения в следующем порядке.  
  
1. Контракт  
  
2. Конечная точка  
  
3. Операция  
  
 В рамках одной коллекции поведений порядок также не гарантируется.  
  
### <a name="adding-behaviors-programmatically"></a>Добавление поведений программным образом  
 Свойства объекта <xref:System.ServiceModel.Description.ServiceDescription?displayProperty=nameWithType> в приложении службы нельзя изменять после вызова метода <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A?displayProperty=nameWithType> для объекта <xref:System.ServiceModel.ServiceHostBase?displayProperty=nameWithType>. Некоторые члены, например свойство <xref:System.ServiceModel.ServiceHostBase.Credentials%2A?displayProperty=nameWithType> и методы `AddServiceEndpoint` классов <xref:System.ServiceModel.ServiceHostBase> и <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType> создают исключения, если их изменить на этом этапе. Другие члены можно изменять без появления исключения, но результат при этом будет неопределенным.  
  
 Аналогично, на стороне клиента нельзя изменять значения <xref:System.ServiceModel.Description.ServiceEndpoint?displayProperty=nameWithType> после вызова метода <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> для объекта <xref:System.ServiceModel.ChannelFactory?displayProperty=nameWithType>. Если свойство <xref:System.ServiceModel.ChannelFactory.Credentials%2A?displayProperty=nameWithType> изменить на этом этапе, будет создано исключение. Другие значения описания клиента можно изменять без возникновения ошибки, однако результат в этом случае будет неопределенным.  
  
 Как для службы, так и для клиента, рекомендуется изменять описание до вызова метода <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A?displayProperty=nameWithType>.  
  
### <a name="inheritance-rules-for-behavior-attributes"></a>Правила наследования атрибутов поведений  
 Поведения всех четырех типов можно определять с использованием атрибутов - поведений служб и контрактов. Поскольку атрибуты определяются в управляемых объектах и членах, а управляемые объекты и члены поддерживают наследование, необходимо определить, как атрибуты поведений ведут себя в контексте наследования.  
  
 На верхнем уровне действует следующее правило: для конкретной области (например, для службы, контракта или операции) применяются все атрибуты поведений в иерархии наследования для данной области. Если имеется два атрибута поведений одного типа, используется тип более низкого уровня иерархии.  
  
#### <a name="service-behaviors"></a>Поведения служб  
 Для заданного класса службы применяются все атрибуты поведения службы для этого класса и всех его родительских классов. Если атрибуты одного и того же типа встречаются на различных уровнях иерархии наследования, используется тип более низкого уровня иерархии.  
  
```csharp  
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Multiple)]  
[AspNetCompatibilityRequirementsAttribute(  
    AspNetCompatibilityRequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]  
public class A { /* … */ }  
  
[ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
public class B : A { /* … */}  
```  
  
 В приведенном выше примере у службы B атрибут <xref:System.ServiceModel.InstanceContextMode> имеет значение <xref:System.ServiceModel.InstanceContextMode.Single>, атрибут <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode> - значение <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed>, а атрибут <xref:System.ServiceModel.ConcurrencyMode> - значение <xref:System.ServiceModel.ConcurrencyMode.Single>. Атрибут <xref:System.ServiceModel.ConcurrencyMode> будет равняться <xref:System.ServiceModel.ConcurrencyMode.Single>, потому что атрибут <xref:System.ServiceModel.ServiceBehaviorAttribute> службы B расположен на более низком уровне иерархии по сравнению со службой A.  
  
#### <a name="contract-behaviors"></a>Поведения контрактов  
 Для заданного контракта применяются все атрибуты поведения контракта для этого интерфейса и всех его родительских интерфейсов. Если атрибуты одного и того же типа встречаются на различных уровнях иерархии наследования, используется тип более низкого уровня иерархии.  
  
#### <a name="operation-behaviors"></a>Поведения операций  
 Если данная операция не переопределяет существующую абстрактную или виртуальную операцию, никакие правила наследования не применяются.  
  
 Если операция переопределяет существующую операцию, то применяются все атрибуты поведения данной операции и ее родительских операций.  Если атрибуты одного и того же типа встречаются на различных уровнях иерархии наследования, используется тип более низкого уровня иерархии.
