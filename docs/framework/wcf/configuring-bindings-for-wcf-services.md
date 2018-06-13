---
title: Настройка привязок для служб Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- binding configuration [WCF]
ms.assetid: 99a85fd8-f7eb-4a84-a93e-7721b37d415c
ms.openlocfilehash: b91c8ff5a78ef2b2b2db5ea26ae7a1733a97ffd0
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33806062"
---
# <a name="configuring-bindings-for-windows-communication-foundation-services"></a><span data-ttu-id="ea6f1-102">Настройка привязок для служб Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="ea6f1-102">Configuring Bindings for Windows Communication Foundation Services</span></span>
<span data-ttu-id="ea6f1-103">При создании приложения часто нужно отложить решения для администратора после развертывания приложения.</span><span class="sxs-lookup"><span data-stu-id="ea6f1-103">When creating an application, you often want to defer decisions to the administrator after the deployment of the application.</span></span> <span data-ttu-id="ea6f1-104">Например, часто нет способа узнать заранее, какими будут адрес службы или универсальный код ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="ea6f1-104">For example, there is often no way of knowing in advance what a service address, or Uniform Resource Identifier (URI), will be.</span></span> <span data-ttu-id="ea6f1-105">Вместо жестко запрограммированного адреса желательно разрешить администратору ввести его после создания службы.</span><span class="sxs-lookup"><span data-stu-id="ea6f1-105">Instead of hard-coding an address, it is preferable to allow an administrator to do so after creating a service.</span></span> <span data-ttu-id="ea6f1-106">Такая гибкость достигается благодаря конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ea6f1-106">This flexibility is accomplished through configuration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ea6f1-107">Используйте [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) с `/config` коммутатора для быстрого создания файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ea6f1-107">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) with the `/config` switch to quickly create configuration files.</span></span>  
  
## <a name="major-sections"></a><span data-ttu-id="ea6f1-108">Основные разделы</span><span class="sxs-lookup"><span data-stu-id="ea6f1-108">Major Sections</span></span>  
 <span data-ttu-id="ea6f1-109">Схема конфигурации Windows Communication Foundation (WCF) включает три основных раздела (`serviceModel`, `bindings`, и `services`):</span><span class="sxs-lookup"><span data-stu-id="ea6f1-109">The Windows Communication Foundation (WCF) configuration scheme includes the following three major sections (`serviceModel`, `bindings`, and `services`):</span></span>  
  
```xml  
<configuration>  
    <system.serviceModel>  
        <bindings>  
        </bindings>  
        <services>  
        </services>  
        <behaviors>  
        </behaviors>  
    </system.serviceModel>  
</configuration>  
```  
  
### <a name="servicemodel-elements"></a><span data-ttu-id="ea6f1-110">Элементы ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ea6f1-110">ServiceModel Elements</span></span>  
 <span data-ttu-id="ea6f1-111">Можно использовать раздел, связанный с `system.ServiceModel` элемент, чтобы настроить тип службы с одной или несколькими конечными точками, а также параметры службы.</span><span class="sxs-lookup"><span data-stu-id="ea6f1-111">You can use the section bounded by the `system.ServiceModel` element to configure a service type with one or more endpoints, as well as settings for a service.</span></span> <span data-ttu-id="ea6f1-112">После этого каждая конечная точка может быть настроена с адресом, контрактом и привязкой.</span><span class="sxs-lookup"><span data-stu-id="ea6f1-112">Each endpoint can then be configured with an address, a contract, and a binding.</span></span> <span data-ttu-id="ea6f1-113">Дополнительные сведения о конечных точках см. в разделе [Общие сведения о создании конечной точки](../../../docs/framework/wcf/endpoint-creation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ea6f1-113">For more information about endpoints, see [Endpoint Creation Overview](../../../docs/framework/wcf/endpoint-creation-overview.md).</span></span> <span data-ttu-id="ea6f1-114">Если конечные точки не указаны, то среда выполнения добавит конечные точки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ea6f1-114">If no endpoints are specified, the runtime adds default endpoints.</span></span> <span data-ttu-id="ea6f1-115">Дополнительные сведения о конечных точек по умолчанию, привязок и поведений см. в разделе [упрощенной конфигурации](../../../docs/framework/wcf/simplified-configuration.md) и [упрощенной конфигурации для служб WCF](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="ea6f1-115">For more information about default endpoints, bindings, and behaviors, see [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
 <span data-ttu-id="ea6f1-116">Привязка задает транспорт (HTTP, TCP, каналы, очередь сообщений) и протоколы (безопасность, надежность, потоки транзакций) и состоит из элементов привязки, каждый из которых задает определенный аспект способа связи конечной точки с миром.</span><span class="sxs-lookup"><span data-stu-id="ea6f1-116">A binding specifies transports (HTTP, TCP, pipes, Message Queuing) and protocols (Security, Reliability, Transaction flows) and consists of binding elements, each of which specifies an aspect of how an endpoint communicates with the world.</span></span>  
  
 <span data-ttu-id="ea6f1-117">Например, при указании [ \<basicHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) элемент указывает на использование протокола HTTP для транспорта для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="ea6f1-117">For example, specifying the [\<basicHttpBinding>](../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) element indicates to use HTTP as the transport for an endpoint.</span></span> <span data-ttu-id="ea6f1-118">Это используется для подключения конечной точки во время выполнения, когда открыта служба, использующая данную конечную точку.</span><span class="sxs-lookup"><span data-stu-id="ea6f1-118">This is used to wire up the endpoint at run time when the service using this endpoint is opened.</span></span>  
  
 <span data-ttu-id="ea6f1-119">Существует два вида привязок: предопределенная и пользовательская.</span><span class="sxs-lookup"><span data-stu-id="ea6f1-119">There are two kinds of bindings: predefined and custom.</span></span> <span data-ttu-id="ea6f1-120">Предопределенные привязки содержат полезные комбинации элементов, которые используются в общих сценариях.</span><span class="sxs-lookup"><span data-stu-id="ea6f1-120">Predefined bindings contain useful combinations of elements that are used in common scenarios.</span></span> <span data-ttu-id="ea6f1-121">Список типов предварительно определенные привязки, предоставляемые WCF см. в разделе [привязка, предоставляемая системой](../../../docs/framework/wcf/system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="ea6f1-121">For a list of predefined binding types that WCF provides, see [System-Provided Bindings](../../../docs/framework/wcf/system-provided-bindings.md).</span></span> <span data-ttu-id="ea6f1-122">Если ни одна из стандартных коллекций привязок не имеет нужного для приложения службы сочетания возможностей, для соответствия требованиям приложения можно создать специальные привязки.</span><span class="sxs-lookup"><span data-stu-id="ea6f1-122">If no predefined binding collection has the correct combination of features that a service application needs, you can construct custom bindings to meet the application's requirements.</span></span> <span data-ttu-id="ea6f1-123">Дополнительные сведения о пользовательских привязок см. в разделе [ \<customBinding >](../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span><span class="sxs-lookup"><span data-stu-id="ea6f1-123">For more information about custom bindings, see [\<customBinding>](../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span></span>  
  
 <span data-ttu-id="ea6f1-124">В следующих четырех примерах проиллюстрированы наиболее общие конфигурации привязок, используемые для настройки службы WCF.</span><span class="sxs-lookup"><span data-stu-id="ea6f1-124">The following four examples illustrate the most common binding configurations used for setting up a WCF service.</span></span>  
  
#### <a name="specifying-an-endpoint-to-use-a-binding-type"></a><span data-ttu-id="ea6f1-125">Указание конечной точки для использования типа привязки</span><span class="sxs-lookup"><span data-stu-id="ea6f1-125">Specifying an Endpoint to Use a Binding Type</span></span>  
 <span data-ttu-id="ea6f1-126">В первом примере показано, как указать конечную точку, настроенную по адресу, контракту и привязке.</span><span class="sxs-lookup"><span data-stu-id="ea6f1-126">The first example illustrates how to specify an endpoint configured with an address, a contract, and a binding.</span></span>  
  
```xml  
<service name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">  
  <!—- This section is optional with the default configuration introduced  
       in .NET Framework 4. -->  
  <endpoint   
      address="/HelloWorld2/"  
      contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
      binding="basicHttpBinding" />
</service>  
```  
  
 <span data-ttu-id="ea6f1-127">В данном примере атрибут `name` указывает на тип службы, для которой предназначена конфигурация.</span><span class="sxs-lookup"><span data-stu-id="ea6f1-127">In this example, the `name` attribute indicates which service type the configuration is for.</span></span> <span data-ttu-id="ea6f1-128">При создании в коде при помощи контракта `HelloWorld` служба инициализируется со всеми конечными точками, указанными в конфигурации примера.</span><span class="sxs-lookup"><span data-stu-id="ea6f1-128">When you create a service in your code with the `HelloWorld` contract, it is initialized with all of the endpoints defined in the example configuration.</span></span> <span data-ttu-id="ea6f1-129">Если сборка реализует только один контракт службы, `name` атрибута может быть опущено, поскольку служба использует единственный имеющийся тип.</span><span class="sxs-lookup"><span data-stu-id="ea6f1-129">If the assembly implements only one service contract, the `name` attribute can be omitted because the service uses the only available type.</span></span> <span data-ttu-id="ea6f1-130">Атрибут принимает строку, которая должна иметь формат `Namespace.Class, AssemblyName, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null`</span><span class="sxs-lookup"><span data-stu-id="ea6f1-130">The attribute takes a string, which must be in the format `Namespace.Class, AssemblyName, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null`</span></span>  
  
 <span data-ttu-id="ea6f1-131">Атрибут `address` указывает универсальный код ресурса (URI), который другие конечные точки используют для связи со службой.</span><span class="sxs-lookup"><span data-stu-id="ea6f1-131">The `address` attribute specifies the URI that other endpoints use to communicate to the service.</span></span> <span data-ttu-id="ea6f1-132">Универсальный код ресурса (URI) может быть как абсолютным, так и относительным путем.</span><span class="sxs-lookup"><span data-stu-id="ea6f1-132">The URI can be either an absolute or relative path.</span></span> <span data-ttu-id="ea6f1-133">Если указан относительный адрес, от узла ожидается предоставление базового адреса, подходящего для используемой в привязке схемы транспорта.</span><span class="sxs-lookup"><span data-stu-id="ea6f1-133">If a relative address is provided, the host is expected to provide a base address that is appropriate for the transport scheme used in the binding.</span></span> <span data-ttu-id="ea6f1-134">Если адрес не настроен, в качестве базового адреса используется адрес соответствующей конечной точки.</span><span class="sxs-lookup"><span data-stu-id="ea6f1-134">If an address is not configured, the base address is assumed to be the address for that endpoint.</span></span>  
  
 <span data-ttu-id="ea6f1-135">Атрибут `contract` задает контракт, который предоставляет данная конечная точка.</span><span class="sxs-lookup"><span data-stu-id="ea6f1-135">The `contract` attribute specifies the contract this endpoint is exposing.</span></span> <span data-ttu-id="ea6f1-136">Тип реализации службы должен реализовывать тип контракта.</span><span class="sxs-lookup"><span data-stu-id="ea6f1-136">The service implementation type must implement the contract type.</span></span> <span data-ttu-id="ea6f1-137">Если реализация службы реализует один тип контракта, это свойство может быть опущено.</span><span class="sxs-lookup"><span data-stu-id="ea6f1-137">If a service implementation implements a single contract type, then this property can be omitted.</span></span>  
  
 <span data-ttu-id="ea6f1-138">Атрибут `binding` выбирает предопределенную или специальную привязку для использования в данной конкретной конечной точке.</span><span class="sxs-lookup"><span data-stu-id="ea6f1-138">The `binding` attribute selects a predefined or custom binding to use for this specific endpoint.</span></span> <span data-ttu-id="ea6f1-139">Конечная точка, которая не выбирает привязку явным образом, использует выбор привязки по умолчанию, т. е. `BasicHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="ea6f1-139">An endpoint that does not explicitly select a binding uses the default binding selection, which is `BasicHttpBinding`.</span></span>  
  
#### <a name="modifying-a-predefined-binding"></a><span data-ttu-id="ea6f1-140">Изменение предопределенной привязки</span><span class="sxs-lookup"><span data-stu-id="ea6f1-140">Modifying a Predefined Binding</span></span>  
 <span data-ttu-id="ea6f1-141">В следующем примере изменяется заранее заданная привязка.</span><span class="sxs-lookup"><span data-stu-id="ea6f1-141">In the following example, a predefined binding is modified.</span></span> <span data-ttu-id="ea6f1-142">После этого ее можно использовать для настройки любой конечной точки в службе.</span><span class="sxs-lookup"><span data-stu-id="ea6f1-142">It can then be used to configure any endpoint in the service.</span></span> <span data-ttu-id="ea6f1-143">Привязка изменяется настройкой значения <xref:System.ServiceModel.Configuration.IBindingConfigurationElement.ReceiveTimeout%2A> на 1 секунду.</span><span class="sxs-lookup"><span data-stu-id="ea6f1-143">The binding is modified by setting the <xref:System.ServiceModel.Configuration.IBindingConfigurationElement.ReceiveTimeout%2A> value to 1 second.</span></span> <span data-ttu-id="ea6f1-144">Обратите внимание, что свойство возвращает объект <xref:System.TimeSpan>.</span><span class="sxs-lookup"><span data-stu-id="ea6f1-144">Note that the property returns a <xref:System.TimeSpan> object.</span></span>  
  
 <span data-ttu-id="ea6f1-145">Эта измененная привязка находится в разделе привязок.</span><span class="sxs-lookup"><span data-stu-id="ea6f1-145">That altered binding is found in the bindings section.</span></span> <span data-ttu-id="ea6f1-146">Теперь эта измененная привязка может использоваться при создании любой конечной точки путем установки атрибута `binding` в элементе `endpoint`.</span><span class="sxs-lookup"><span data-stu-id="ea6f1-146">This altered binding can now be used when creating any endpoint by setting the `binding` attribute in the `endpoint` element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ea6f1-147">Если задать определенное имя для привязки, то значение `bindingConfiguration`, указанное в конечной точке службы, должно совпадать с этим именем.</span><span class="sxs-lookup"><span data-stu-id="ea6f1-147">If you give a particular name to the binding, the `bindingConfiguration` specified in the service endpoint must match with it.</span></span>  
  
```xml  
<service name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">  
  <endpoint   
      address="/HelloWorld2/"  
      contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
      binding="basicHttpBinding" />
</service>  
<bindings>  
    <basicHttpBinding   
        receiveTimeout="00:00:01"  
    />  
</bindings>  
```  
  
## <a name="configuring-a-behavior-to-apply-to-a-service"></a><span data-ttu-id="ea6f1-148">Настройка поведения для применения к службе</span><span class="sxs-lookup"><span data-stu-id="ea6f1-148">Configuring a Behavior to Apply to a Service</span></span>  
 <span data-ttu-id="ea6f1-149">В следующем примере специальное поведение настраивается для типа службы.</span><span class="sxs-lookup"><span data-stu-id="ea6f1-149">In the following example, a specific behavior is configured for the service type.</span></span> <span data-ttu-id="ea6f1-150">`ServiceMetadataBehavior` Элемент используется для включения [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для запроса к службе и создания документов языка описания веб-служб (WSDL) из метаданных.</span><span class="sxs-lookup"><span data-stu-id="ea6f1-150">The `ServiceMetadataBehavior` element is used to enable the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to query the service and generate Web Services Description Language (WSDL) documents from the metadata.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ea6f1-151">Если задать определенное имя для поведения, то значение `behaviorConfiguration`, указанное в разделе службы или конечной точки, должно совпадать с этим именем.</span><span class="sxs-lookup"><span data-stu-id="ea6f1-151">If you give a particular name to the behavior, the `behaviorConfiguration` specified in the service or endpoint section must match it.</span></span>  
  
```xml  
<behaviors>  
    <behavior>  
        <ServiceMetadata httpGetEnabled="true" />   
    </behavior>  
</behaviors>  
<services>  
    <service   
       name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">
       <endpoint   
          address="http://computer:8080/Hello"  
          contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
          binding="basicHttpBinding" />
    </service>  
</services>  
```  
  
 <span data-ttu-id="ea6f1-152">Предыдущая конфигурация позволяет клиенту вызывать и получать метаданные типизированной службы HelloWorld.</span><span class="sxs-lookup"><span data-stu-id="ea6f1-152">The preceding configuration enables a client to call and get the metadata of the "HelloWorld" typed service.</span></span>  
  
 `svcutil /config:Client.exe.config http://computer:8080/Hello?wsdl`  
  
## <a name="specifying-a-service-with-two-endpoints-using-different-binding-values"></a><span data-ttu-id="ea6f1-153">Указание службы с двумя конечными точками при помощи различных значений привязки</span><span class="sxs-lookup"><span data-stu-id="ea6f1-153">Specifying a Service with Two Endpoints Using Different Binding Values</span></span>  
 <span data-ttu-id="ea6f1-154">В последнем примере две конечные точки настраиваются для типа службы `HelloWorld`.</span><span class="sxs-lookup"><span data-stu-id="ea6f1-154">In this last example, two endpoints are configured for the `HelloWorld` service type.</span></span> <span data-ttu-id="ea6f1-155">Каждая конечная точка использует другой настроенные `bindingConfiguration` атрибут того же типа привязки (каждый изменяет `basicHttpBinding`).</span><span class="sxs-lookup"><span data-stu-id="ea6f1-155">Each endpoint uses a different customized  `bindingConfiguration` attribute of the same binding type (each modifies the `basicHttpBinding`).</span></span>  
  
```xml  
<service name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">  
    <endpoint  
        address="http://computer:8080/Hello1"  
        contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
        binding="basicHttpBinding"  
        bindingConfiguration="shortTimeout" />
    <endpoint  
        address="http://computer:8080/Hello2"  
        contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
        binding="basicHttpBinding"  
        bindingConfiguration="Secure" />
</service>  
<bindings>  
    <basicHttpBinding   
        name="shortTimeout"  
        timeout="00:00:00:01"   
     />  
     <basicHttpBinding   
        name="Secure">  
        <Security mode="Transport" />  
     </basicHttpBinding>
</bindings>  
```  
  
 <span data-ttu-id="ea6f1-156">Можно добиться того же поведения с помощью конфигурации по умолчанию, добавив раздел `protocolMapping` и настроив привязки, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="ea6f1-156">You can get the same behavior using the default configuration by adding a `protocolMapping` section and configuring the bindings as demonstrated in the following example.</span></span>  
  
```xml  
<protocolMapping>  
    <add scheme="http" binding="basicHttpBinding" bindingConfiguration="shortTimeout" />  
    <add scheme="https" binding="basicHttpBinding" bindingConfiguration="Secure" />  
</protocolMapping>  
<bindings>  
    <basicHttpBinding   
        name="shortTimeout"  
        timeout="00:00:00:01"   
     />  
     <basicHttpBinding   
        name="Secure" />  
        <Security mode="Transport" />  
</bindings>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ea6f1-157">См. также</span><span class="sxs-lookup"><span data-stu-id="ea6f1-157">See Also</span></span>  
 [<span data-ttu-id="ea6f1-158">Упрощенная конфигурация</span><span class="sxs-lookup"><span data-stu-id="ea6f1-158">Simplified Configuration</span></span>](../../../docs/framework/wcf/simplified-configuration.md)  
 [<span data-ttu-id="ea6f1-159">Привязки, предоставляемые системой</span><span class="sxs-lookup"><span data-stu-id="ea6f1-159">System-Provided Bindings</span></span>](../../../docs/framework/wcf/system-provided-bindings.md)  
 [<span data-ttu-id="ea6f1-160">Общие сведения о создании конечных точек</span><span class="sxs-lookup"><span data-stu-id="ea6f1-160">Endpoint Creation Overview</span></span>](../../../docs/framework/wcf/endpoint-creation-overview.md)  
 [<span data-ttu-id="ea6f1-161">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="ea6f1-161">Using Bindings to Configure Services and Clients</span></span>](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
