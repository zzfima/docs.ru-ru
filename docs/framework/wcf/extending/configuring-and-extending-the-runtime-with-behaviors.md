---
title: "Настройка и расширение среды выполнения с помощью поведений"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: attaching extensions using behaviors [WCF]
ms.assetid: 149b99b6-6eb6-4f45-be22-c967279677d9
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7eb8e0853adbc24deb43fc1006804d7707d9a4b8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="configuring-and-extending-the-runtime-with-behaviors"></a>Настройка и расширение среды выполнения с помощью поведений
Поведения позволяют изменять функциональность по умолчанию и добавлять пользовательские элементы, которые проверяют конфигурацию службы или изменяют поведение клиентских приложений и приложений служб [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] во время выполнения. В этом разделе описаны интерфейсы поведений, способы их реализации, а также порядок их добавления в описания служб (в приложениях служб) и конечных точек (в клиентских приложениях) как программным образом, так и с помощью файла конфигурации. Дополнительные сведения об использовании предоставляемых системой поведений см. в разделе [указание поведения службы во время выполнения](../../../../docs/framework/wcf/specifying-service-run-time-behavior.md) и [указание поведения клиента во время выполнения](../../../../docs/framework/wcf/specifying-client-run-time-behavior.md).  
  
## <a name="behaviors"></a>поведения  
 Типы поведений добавляются в объекты описания службы или конечной точки службы (на стороне службы или клиента соответственно) перед использованием этих объектов средой [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] для создания среды выполнения, в которой выполняется служба [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] или клиент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Если эти поведения вызываются в процессе создания среды выполнения, то они могут получать доступ к свойствам и методам среды выполнения, которые позволяют изменить создаваемую среду выполнения с использованием других контрактов, привязок и адресов.  
  
### <a name="behavior-methods"></a>Методы поведений  
 У всех поведений имеется метод `AddBindingParameters`, метод `ApplyDispatchBehavior`, метод `Validate` и метод `ApplyClientBehavior` за единственным исключением: поскольку интерфейс <xref:System.ServiceModel.Description.IServiceBehavior> не может выполняться на клиенте, он не реализует метод `ApplyClientBehavior`.  
  
-   Метод `AddBindingParameters` служит для изменения или добавления пользовательских объектов в коллекцию, к которой могут общаться пользовательские привязки при создании среды выполнения. Например, с помощью этого метода можно задать требования защиты, которые влияют на способ создания канала, но не известны разработчику канала.  
  
-   Метод `Validate` служит для проверки дерева описания и соответствующего объекта среды выполнения, чтобы убедиться, что они соответствуют определенному набору условий.  
  
-   Методы `ApplyDispatchBehavior` и `ApplyClientBehavior` служат для проверки дерева описания и изменения среды выполнения в определенной области (на стороне службы или на стороне клиента соответственно). Кроме того, эти методы позволяют вставлять объекты расширения.  
  
    > [!NOTE]
    >  Хотя эти методы получают дерево описания, оно доступно им только для проверки. Если изменить дерево описания, поведение станет неопределенным.  
  
 Доступ к свойствам, которые можно изменить, и к интерфейсам настройки, которые можно реализовать, осуществляется через классы среды выполнения службы и клиента. Типами службы являются классы <xref:System.ServiceModel.Dispatcher.DispatchRuntime> и <xref:System.ServiceModel.Dispatcher.DispatchOperation>. Типами клиента являются классы <xref:System.ServiceModel.Dispatcher.ClientRuntime> и <xref:System.ServiceModel.Dispatcher.ClientOperation>. Классы <xref:System.ServiceModel.Dispatcher.ClientRuntime> и <xref:System.ServiceModel.Dispatcher.DispatchRuntime> являются точками входа расширяемости для доступа к коллекциям расширения и свойствам среды выполнения клиента и службы соответственно. Аналогично классы <xref:System.ServiceModel.Dispatcher.ClientOperation> и <xref:System.ServiceModel.Dispatcher.DispatchOperation> предоставляют доступ к коллекциям расширения и свойствам среды выполнения операций клиента и операций службы соответственно. Однако из объекта среды выполнения операции, если это требуется, можно получить доступ к объекту среды выполнения с более широкой областью и наоборот.  
  
> [!NOTE]
>  Обсуждение типы расширений, которые можно использовать для изменения поведения выполнения клиента и свойствам среды выполнения см. в разделе [расширение клиентов](../../../../docs/framework/wcf/extending/extending-clients.md). Обсуждение типы расширений, которые можно использовать для изменения поведения выполнения диспетчера службы и свойствам среды выполнения см. в разделе [расширение диспетчеров](../../../../docs/framework/wcf/extending/extending-dispatchers.md).  
  
 Большинство пользователей [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не взаимодействуют со средой выполнения напрямую; вместо этого они используют элементы базовой модели программирования, например конечные точки, контракты, привязки, адреса и атрибуты поведений в классах или поведения в файлах конфигурации. Эти конструкции составляют *дерево описания*, который представляет собой полную спецификацию для создания среды выполнения для поддержки службы или клиента, описываемых деревом описания.  
  
 В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] имеется четыре типа поведений:  
  
-   поведения служб (типы <xref:System.ServiceModel.Description.IServiceBehavior>) позволяют настраивать среду выполнения службы целиком, включая <xref:System.ServiceModel.ServiceHostBase>;  
  
-   поведения конечных точек (типы <xref:System.ServiceModel.Description.IEndpointBehavior>) позволяют настраивать конечные точки служб и соответствующие объекты <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>;  
  
-   поведения контрактов (типы <xref:System.ServiceModel.Description.IContractBehavior>) позволяют настраивать классы <xref:System.ServiceModel.Dispatcher.ClientRuntime> и <xref:System.ServiceModel.Dispatcher.DispatchRuntime> в приложениях клиентов и служб соответственно;  
  
-   поведения операций (типы <xref:System.ServiceModel.Description.IOperationBehavior>) позволяют настраивать классы <xref:System.ServiceModel.Dispatcher.ClientOperation> и <xref:System.ServiceModel.Dispatcher.DispatchOperation> в приложениях клиентов и служб.  
  
 Эти поведения можно добавлять в различные объекты описания путем реализации пользовательских атрибутов, с помощью файлов конфигурации приложений или путем их непосредственного добавления в коллекцию поведений соответствующего объекта описания. Однако их обязательно необходимо добавлять в объекты описания службы или конечной точки службы до вызова метода <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> объектов <xref:System.ServiceModel.ServiceHost> и <xref:System.ServiceModel.ChannelFactory%601>.  
  
### <a name="behavior-scopes"></a>Области поведений  
 Каждый из четырех типов поведений соответствует определенной области доступа среды выполнения.  
  
#### <a name="service-behaviors"></a>Поведения служб  
 Поведения служб, реализующие интерфейс <xref:System.ServiceModel.Description.IServiceBehavior>, являются основным механизмом для изменения всей среды выполнения службы. Имеется три механизма добавления поведений служб к службам.  
  
1.  С помощью атрибута класса службы.  При создании объекта <xref:System.ServiceModel.ServiceHost> реализация класса <xref:System.ServiceModel.ServiceHost> использует отражение, чтобы обнаружить набор атрибутов типа службы. Все атрибуты, реализующие интерфейс <xref:System.ServiceModel.Description.IServiceBehavior>, добавляются в коллекцию поведений в объекте <xref:System.ServiceModel.Description.ServiceDescription>. Это позволяет таким поведениям участвовать в создании среды выполнения службы.  
  
2.  Добавление поведения в коллекцию поведений в объекте <xref:System.ServiceModel.Description.ServiceDescription> программным образом. Эту задачу можно решить с помощью следующего фрагмента кода:  
  
    ```  
    ServiceHost host = new ServiceHost(/* Parameters */);  
    host.Description.Behaviors.Add(/* Service Behavior */);  
    ```  
  
3.  Реализация пользовательского элемента <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>, который расширяет конфигурацию. Это позволяет использовать поведение службы в файлах конфигурации приложения.  
  
 К примерам поведений служб в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] относится атрибут <xref:System.ServiceModel.ServiceBehaviorAttribute>, а также поведения <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> и <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.  
  
#### <a name="contract-behaviors"></a>Поведения контрактов  
 Поведения контрактов, реализующие интерфейс <xref:System.ServiceModel.Description.IContractBehavior>, служат для расширения сред выполнения клиента и службы в рамках контракта.  
  
 Имеется два механизма добавления поведений контрактов к контрактам.  Первый механизм предполагает создание пользовательского атрибута, который будет использоваться в интерфейсе контракта. Когда интерфейс контракта передается объекту <xref:System.ServiceModel.ServiceHost> или <xref:System.ServiceModel.ChannelFactory%601>, среда [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] проверяет атрибуты этого интерфейса. Все атрибуты, реализующие интерфейс <xref:System.ServiceModel.Description.IContractBehavior>, добавляются в коллекцию поведений в объекте <xref:System.ServiceModel.Description.ContractDescription?displayProperty=nameWithType>, созданном для этого интерфейса.  
  
 Кроме того, можно реализовать интерфейс <xref:System.ServiceModel.Description.IContractBehaviorAttribute?displayProperty=nameWithType> в атрибуте поведения пользовательского контракта. В этом случае поведение, если оно применяется, выглядит следующим образом:  
  
 •Интерфейс контракта. В этом случае поведение применяется ко всем контрактам этого типа в любой конечной точке, а среда [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не учитывает значение свойства <xref:System.ServiceModel.Description.IContractBehaviorAttribute.TargetContract%2A?displayProperty=nameWithType>.  
  
 •Класс службы. В этом случае поведение применяется только к конечным точкам, контракт которых имеет значение, равное значению свойства <xref:System.ServiceModel.Description.IContractBehaviorAttribute.TargetContract%2A>.  
  
 •Класс обратного вызова. В этом случае поведение применяется к конечной точке дуплексного клиента, и среда [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не учитывает значение свойства <xref:System.ServiceModel.Description.IContractBehaviorAttribute.TargetContract%2A>.  
  
 Второй механизм предполагает добавление поведения в коллекцию поведений объекта <xref:System.ServiceModel.Description.ContractDescription>.  
  
 К примерам поведений контрактов в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] относится атрибут <xref:System.ServiceModel.DeliveryRequirementsAttribute?displayProperty=nameWithType>. Дополнительные сведения и пример см. в справочном разделе.  
  
#### <a name="endpoint-behaviors"></a>Поведения конечных точек  
 Поведения конечных точек, реализующие интерфейс <xref:System.ServiceModel.Description.IEndpointBehavior>, являются основным механизмом для изменения всей среды выполнения службы или клиента для конкретной конечной точки.  
  
 Имеется два механизма добавления поведений конечных точек к службам.  
  
1.  Добавьте поведение в свойство <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A>.  
  
2.  Реализуйте пользовательский элемент <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>, который расширяет конфигурацию.  
  
 Дополнительные сведения и пример см. в справочном разделе.  
  
#### <a name="operation-behaviors"></a>Поведения операций  
 Поведения операций, реализующие интерфейс <xref:System.ServiceModel.Description.IOperationBehavior>, служат для расширения сред выполнения клиента и службы для каждой из операций.  
  
 Имеется два механизма добавления поведений операций к операциям. Первый механизм предполагает создание пользовательского атрибута, который будет использоваться в методе, моделирующем операцию. При добавлении операции в объект <xref:System.ServiceModel.ServiceHost> или <xref:System.ServiceModel.ChannelFactory> среда [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] добавляет все атрибуты <xref:System.ServiceModel.Description.IOperationBehavior> в коллекцию поведений объекта <xref:System.ServiceModel.Description.OperationDescription>, созданного для данной операции.  
  
 Второй механизм предполагает непосредственное добавление поведения в коллекцию поведений объекта <xref:System.ServiceModel.Description.OperationDescription>.  
  
 К примерам поведений операций в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] относятся атрибуты <xref:System.ServiceModel.OperationBehaviorAttribute> и <xref:System.ServiceModel.TransactionFlowAttribute>.  
  
 Дополнительные сведения и пример см. в справочном разделе.  
  
### <a name="using-configuration-to-create-behaviors"></a>Создание поведений с помощью файла конфигурации  
 Поведения служб, конечных точек и контрактов можно разрабатывать таким образом, чтобы задавать их в коде с помощью атрибутов. Только поведения служб и конечных точек можно настраивать с помощью файлов конфигурации приложения и веб-службы. Предоставление доступа к поведениям с помощью атрибутов позволяет разработчикам задавать поведение во время компиляции; это значит, что такое поведение нельзя добавлять, удалять или изменять во время выполнения. Этот подход часто применяется для поведений, которые обязательно нужны для правильной работы службы (например, связанные с транзакциями параметры атрибута <xref:System.ServiceModel.ServiceBehaviorAttribute?displayProperty=nameWithType>). Предоставление доступа к поведениям с помощью файлов конфигурации позволяет разработчикам переложить обязанности по спецификации и настойке этих поведений на тех, кто будет развертывать службу. Такой подход удобно применять для поведений, которые являются необязательными компонентами, или для других конфигураций, которые зависят от развертывания, например, чтобы определить, нужно ли предоставлять метаданные всей службе или же только конкретной конфигурации авторизации службы.  
  
> [!NOTE]
>  Также можно использовать поведения, которые поддерживают файлы конфигурации, для реализации политик применения путем их вставки в файл конфигурации machine.config и блокировки соответствующих элементов от изменений. Описание и пример см. в разделе [как: блокировки работу конечных точек на предприятии](../../../../docs/framework/wcf/extending/how-to-lock-down-endpoints-in-the-enterprise.md).  
  
 Чтобы сделать поведение доступным с помощью файла конфигурации, разработчик должен создать производный класс для класса <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>, а затем зарегистрировать расширение в конфигурации.  
  
 В следующем примере кода показано, каким образом интерфейс <xref:System.ServiceModel.Description.IEndpointBehavior> реализует объект <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>.  
  
```  
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
  
 Где `Microsoft.WCF.Documentation.EndpointBehaviorMessageInspector` — тип расширения поведения и `HostApplication` является имя сборки, в которую был скомпилирован этот класс.  
  
### <a name="evaluation-order"></a>Порядок вычисления  
 Классы <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType> и <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType> отвечают за построение среды выполнения на основе модели программирования и описания. Как было сказано выше, поведения участвуют в этом процессе, оказывая влияние на службы, конечные точки, контракты и операции.  
  
 Объект <xref:System.ServiceModel.ServiceHost> применяет поведения в следующем порядке.  
  
1.  Служба  
  
2.  Контракт  
  
3.  Конечная точка  
  
4.  Операция  
  
 В рамках одной коллекции поведений порядок не гарантируется.  
  
 Объект <xref:System.ServiceModel.ChannelFactory%601> применяет поведения в следующем порядке.  
  
1.  Контракт  
  
2.  Конечная точка  
  
3.  Операция  
  
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
  
```  
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
