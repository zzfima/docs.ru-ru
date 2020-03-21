---
title: Настройка привязок для служб Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- binding configuration [WCF]
ms.assetid: 99a85fd8-f7eb-4a84-a93e-7721b37d415c
ms.openlocfilehash: e7ee1a8ce358c77e46db39af67bd9dc20114fb3b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174827"
---
# <a name="configuring-bindings-for-windows-communication-foundation-services"></a><span data-ttu-id="9b721-102">Настройка привязок для служб Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="9b721-102">Configuring Bindings for Windows Communication Foundation Services</span></span>
<span data-ttu-id="9b721-103">При создании приложения часто нужно отложить решения для администратора после развертывания приложения.</span><span class="sxs-lookup"><span data-stu-id="9b721-103">When creating an application, you often want to defer decisions to the administrator after the deployment of the application.</span></span> <span data-ttu-id="9b721-104">Например, часто нет способа узнать заранее, какими будут адрес службы или универсальный код ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="9b721-104">For example, there is often no way of knowing in advance what a service address, or Uniform Resource Identifier (URI), will be.</span></span> <span data-ttu-id="9b721-105">Вместо жестко запрограммированного адреса желательно разрешить администратору ввести его после создания службы.</span><span class="sxs-lookup"><span data-stu-id="9b721-105">Instead of hard-coding an address, it is preferable to allow an administrator to do so after creating a service.</span></span> <span data-ttu-id="9b721-106">Такая гибкость достигается благодаря конфигурации.</span><span class="sxs-lookup"><span data-stu-id="9b721-106">This flexibility is accomplished through configuration.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9b721-107">Используйте [инструмент Utility Tool ServiceModel Metadata (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) с переходом `/config` для быстрого создания файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="9b721-107">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) with the `/config` switch to quickly create configuration files.</span></span>  
  
## <a name="major-sections"></a><span data-ttu-id="9b721-108">Основные разделы</span><span class="sxs-lookup"><span data-stu-id="9b721-108">Major Sections</span></span>  
 <span data-ttu-id="9b721-109">Схема конфигурации Windows Communication Foundation (WCF) включает`serviceModel` `bindings`в `services`себя следующие три основных раздела (, и):</span><span class="sxs-lookup"><span data-stu-id="9b721-109">The Windows Communication Foundation (WCF) configuration scheme includes the following three major sections (`serviceModel`, `bindings`, and `services`):</span></span>  
  
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
  
### <a name="servicemodel-elements"></a><span data-ttu-id="9b721-110">Элементы ServiceModel</span><span class="sxs-lookup"><span data-stu-id="9b721-110">ServiceModel Elements</span></span>  
 <span data-ttu-id="9b721-111">Раздел, ограниченный `system.ServiceModel` элементом, можно настроить тип службы с одной или более конечными точками, а также настройками службы.</span><span class="sxs-lookup"><span data-stu-id="9b721-111">You can use the section bounded by the `system.ServiceModel` element to configure a service type with one or more endpoints, as well as settings for a service.</span></span> <span data-ttu-id="9b721-112">После этого каждая конечная точка может быть настроена с адресом, контрактом и привязкой.</span><span class="sxs-lookup"><span data-stu-id="9b721-112">Each endpoint can then be configured with an address, a contract, and a binding.</span></span> <span data-ttu-id="9b721-113">Для получения дополнительной информации о конечных точках, см [Endpoint Создание Обзор](endpoint-creation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9b721-113">For more information about endpoints, see [Endpoint Creation Overview](endpoint-creation-overview.md).</span></span> <span data-ttu-id="9b721-114">Если конечные точки не указаны, то среда выполнения добавит конечные точки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9b721-114">If no endpoints are specified, the runtime adds default endpoints.</span></span> <span data-ttu-id="9b721-115">Дополнительные сведения о конечных точках по умолчанию, привязках и режимах работы см. в разделах [Упрощенная конфигурация](simplified-configuration.md) и [Упрощенная конфигурация служб WCF](./samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="9b721-115">For more information about default endpoints, bindings, and behaviors, see [Simplified Configuration](simplified-configuration.md) and [Simplified Configuration for WCF Services](./samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
 <span data-ttu-id="9b721-116">Привязка задает транспорт (HTTP, TCP, каналы, очередь сообщений) и протоколы (безопасность, надежность, потоки транзакций) и состоит из элементов привязки, каждый из которых задает определенный аспект способа связи конечной точки с миром.</span><span class="sxs-lookup"><span data-stu-id="9b721-116">A binding specifies transports (HTTP, TCP, pipes, Message Queuing) and protocols (Security, Reliability, Transaction flows) and consists of binding elements, each of which specifies an aspect of how an endpoint communicates with the world.</span></span>  
  
 <span data-ttu-id="9b721-117">Например, указание [ \<элемента basicHttpBinding>](../configure-apps/file-schema/wcf/basichttpbinding.md) указывает на использование HTTP в качестве переноса для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="9b721-117">For example, specifying the [\<basicHttpBinding>](../configure-apps/file-schema/wcf/basichttpbinding.md) element indicates to use HTTP as the transport for an endpoint.</span></span> <span data-ttu-id="9b721-118">Это используется для подключения конечной точки во время выполнения, когда открыта служба, использующая данную конечную точку.</span><span class="sxs-lookup"><span data-stu-id="9b721-118">This is used to wire up the endpoint at run time when the service using this endpoint is opened.</span></span>  
  
 <span data-ttu-id="9b721-119">Существует два вида привязок: предопределенная и пользовательская.</span><span class="sxs-lookup"><span data-stu-id="9b721-119">There are two kinds of bindings: predefined and custom.</span></span> <span data-ttu-id="9b721-120">Предопределенные привязки содержат полезные комбинации элементов, которые используются в общих сценариях.</span><span class="sxs-lookup"><span data-stu-id="9b721-120">Predefined bindings contain useful combinations of elements that are used in common scenarios.</span></span> <span data-ttu-id="9b721-121">Для списка предопределенных типов связывания, [System-Provided Bindings](system-provided-bindings.md)которые предоставляет WCF, см.</span><span class="sxs-lookup"><span data-stu-id="9b721-121">For a list of predefined binding types that WCF provides, see [System-Provided Bindings](system-provided-bindings.md).</span></span> <span data-ttu-id="9b721-122">Если ни одна из стандартных коллекций привязок не имеет нужного для приложения службы сочетания возможностей, для соответствия требованиям приложения можно создать специальные привязки.</span><span class="sxs-lookup"><span data-stu-id="9b721-122">If no predefined binding collection has the correct combination of features that a service application needs, you can construct custom bindings to meet the application's requirements.</span></span> <span data-ttu-id="9b721-123">Для получения дополнительной информации о пользовательских привязок, см [ \<пользовательскихОбязательные>](../configure-apps/file-schema/wcf/custombinding.md).</span><span class="sxs-lookup"><span data-stu-id="9b721-123">For more information about custom bindings, see [\<customBinding>](../configure-apps/file-schema/wcf/custombinding.md).</span></span>  
  
 <span data-ttu-id="9b721-124">Следующие четыре примера иллюстрируют наиболее распространенные обязательные конфигурации, используемые для настройки службы WCF.</span><span class="sxs-lookup"><span data-stu-id="9b721-124">The following four examples illustrate the most common binding configurations used for setting up a WCF service.</span></span>  
  
#### <a name="specifying-an-endpoint-to-use-a-binding-type"></a><span data-ttu-id="9b721-125">Указание конечной точки для использования типа привязки</span><span class="sxs-lookup"><span data-stu-id="9b721-125">Specifying an Endpoint to Use a Binding Type</span></span>  
 <span data-ttu-id="9b721-126">В первом примере показано, как указать конечную точку, настроенную по адресу, контракту и привязке.</span><span class="sxs-lookup"><span data-stu-id="9b721-126">The first example illustrates how to specify an endpoint configured with an address, a contract, and a binding.</span></span>  
  
```xml  
<service name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">  
  <!-- This section is optional with the default configuration introduced  
       in .NET Framework 4. -->  
  <endpoint
      address="/HelloWorld2/"  
      contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
      binding="basicHttpBinding" />
</service>  
```  
  
 <span data-ttu-id="9b721-127">В данном примере атрибут `name` указывает на тип службы, для которой предназначена конфигурация.</span><span class="sxs-lookup"><span data-stu-id="9b721-127">In this example, the `name` attribute indicates which service type the configuration is for.</span></span> <span data-ttu-id="9b721-128">При создании в коде при помощи контракта `HelloWorld` служба инициализируется со всеми конечными точками, указанными в конфигурации примера.</span><span class="sxs-lookup"><span data-stu-id="9b721-128">When you create a service in your code with the `HelloWorld` contract, it is initialized with all of the endpoints defined in the example configuration.</span></span> <span data-ttu-id="9b721-129">Если сборка выполняет только один `name` контракт службы, атрибут может быть опущен, поскольку служба использует единственный доступный тип.</span><span class="sxs-lookup"><span data-stu-id="9b721-129">If the assembly implements only one service contract, the `name` attribute can be omitted because the service uses the only available type.</span></span> <span data-ttu-id="9b721-130">Атрибут принимает строку, которая должна иметь формат `Namespace.Class, AssemblyName, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null`</span><span class="sxs-lookup"><span data-stu-id="9b721-130">The attribute takes a string, which must be in the format `Namespace.Class, AssemblyName, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null`</span></span>  
  
 <span data-ttu-id="9b721-131">Атрибут `address` указывает универсальный код ресурса (URI), который другие конечные точки используют для связи со службой.</span><span class="sxs-lookup"><span data-stu-id="9b721-131">The `address` attribute specifies the URI that other endpoints use to communicate to the service.</span></span> <span data-ttu-id="9b721-132">Универсальный код ресурса (URI) может быть как абсолютным, так и относительным путем.</span><span class="sxs-lookup"><span data-stu-id="9b721-132">The URI can be either an absolute or relative path.</span></span> <span data-ttu-id="9b721-133">Если указан относительный адрес, от узла ожидается предоставление базового адреса, подходящего для используемой в привязке схемы транспорта.</span><span class="sxs-lookup"><span data-stu-id="9b721-133">If a relative address is provided, the host is expected to provide a base address that is appropriate for the transport scheme used in the binding.</span></span> <span data-ttu-id="9b721-134">Если адрес не настроен, в качестве базового адреса используется адрес соответствующей конечной точки.</span><span class="sxs-lookup"><span data-stu-id="9b721-134">If an address is not configured, the base address is assumed to be the address for that endpoint.</span></span>  
  
 <span data-ttu-id="9b721-135">Атрибут `contract` задает контракт, который предоставляет данная конечная точка.</span><span class="sxs-lookup"><span data-stu-id="9b721-135">The `contract` attribute specifies the contract this endpoint is exposing.</span></span> <span data-ttu-id="9b721-136">Тип реализации службы должен реализовывать тип контракта.</span><span class="sxs-lookup"><span data-stu-id="9b721-136">The service implementation type must implement the contract type.</span></span> <span data-ttu-id="9b721-137">Если реализация службы реализует один тип контракта, это свойство может быть опущено.</span><span class="sxs-lookup"><span data-stu-id="9b721-137">If a service implementation implements a single contract type, then this property can be omitted.</span></span>  
  
 <span data-ttu-id="9b721-138">Атрибут `binding` выбирает предопределенную или специальную привязку для использования в данной конкретной конечной точке.</span><span class="sxs-lookup"><span data-stu-id="9b721-138">The `binding` attribute selects a predefined or custom binding to use for this specific endpoint.</span></span> <span data-ttu-id="9b721-139">Конечная точка, которая не выбирает привязку явным образом, использует выбор привязки по умолчанию, т. е. `BasicHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="9b721-139">An endpoint that does not explicitly select a binding uses the default binding selection, which is `BasicHttpBinding`.</span></span>  
  
#### <a name="modifying-a-predefined-binding"></a><span data-ttu-id="9b721-140">Изменение предопределенной привязки</span><span class="sxs-lookup"><span data-stu-id="9b721-140">Modifying a Predefined Binding</span></span>  
 <span data-ttu-id="9b721-141">В следующем примере изменяется заранее заданная привязка.</span><span class="sxs-lookup"><span data-stu-id="9b721-141">In the following example, a predefined binding is modified.</span></span> <span data-ttu-id="9b721-142">После этого ее можно использовать для настройки любой конечной точки в службе.</span><span class="sxs-lookup"><span data-stu-id="9b721-142">It can then be used to configure any endpoint in the service.</span></span> <span data-ttu-id="9b721-143">Привязка изменяется настройкой значения <xref:System.ServiceModel.Configuration.IBindingConfigurationElement.ReceiveTimeout%2A> на 1 секунду.</span><span class="sxs-lookup"><span data-stu-id="9b721-143">The binding is modified by setting the <xref:System.ServiceModel.Configuration.IBindingConfigurationElement.ReceiveTimeout%2A> value to 1 second.</span></span> <span data-ttu-id="9b721-144">Обратите внимание, что свойство возвращает объект <xref:System.TimeSpan>.</span><span class="sxs-lookup"><span data-stu-id="9b721-144">Note that the property returns a <xref:System.TimeSpan> object.</span></span>  
  
 <span data-ttu-id="9b721-145">Эта измененная привязка находится в разделе привязок.</span><span class="sxs-lookup"><span data-stu-id="9b721-145">That altered binding is found in the bindings section.</span></span> <span data-ttu-id="9b721-146">Теперь эта измененная привязка может использоваться при создании любой конечной точки путем установки атрибута `binding` в элементе `endpoint`.</span><span class="sxs-lookup"><span data-stu-id="9b721-146">This altered binding can now be used when creating any endpoint by setting the `binding` attribute in the `endpoint` element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9b721-147">Если задать определенное имя для привязки, то значение `bindingConfiguration`, указанное в конечной точке службы, должно совпадать с этим именем.</span><span class="sxs-lookup"><span data-stu-id="9b721-147">If you give a particular name to the binding, the `bindingConfiguration` specified in the service endpoint must match with it.</span></span>  
  
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
  
## <a name="configuring-a-behavior-to-apply-to-a-service"></a><span data-ttu-id="9b721-148">Настройка поведения для применения к службе</span><span class="sxs-lookup"><span data-stu-id="9b721-148">Configuring a Behavior to Apply to a Service</span></span>  
 <span data-ttu-id="9b721-149">В следующем примере специальное поведение настраивается для типа службы.</span><span class="sxs-lookup"><span data-stu-id="9b721-149">In the following example, a specific behavior is configured for the service type.</span></span> <span data-ttu-id="9b721-150">Элемент `ServiceMetadataBehavior` используется для того, чтобы позволить [Utility Tool ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) задать запрос службы и создать документы языка описания web-сервисов (WSDL) из метаданных.</span><span class="sxs-lookup"><span data-stu-id="9b721-150">The `ServiceMetadataBehavior` element is used to enable the [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) to query the service and generate Web Services Description Language (WSDL) documents from the metadata.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9b721-151">Если задать определенное имя для поведения, то значение `behaviorConfiguration`, указанное в разделе службы или конечной точки, должно совпадать с этим именем.</span><span class="sxs-lookup"><span data-stu-id="9b721-151">If you give a particular name to the behavior, the `behaviorConfiguration` specified in the service or endpoint section must match it.</span></span>  
  
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
  
 <span data-ttu-id="9b721-152">Предыдущая конфигурация позволяет клиенту вызывать и получать метаданные типизированной службы HelloWorld.</span><span class="sxs-lookup"><span data-stu-id="9b721-152">The preceding configuration enables a client to call and get the metadata of the "HelloWorld" typed service.</span></span>  
  
 `svcutil /config:Client.exe.config http://computer:8080/Hello?wsdl`  
  
## <a name="specifying-a-service-with-two-endpoints-using-different-binding-values"></a><span data-ttu-id="9b721-153">Указание службы с двумя конечными точками при помощи различных значений привязки</span><span class="sxs-lookup"><span data-stu-id="9b721-153">Specifying a Service with Two Endpoints Using Different Binding Values</span></span>  
 <span data-ttu-id="9b721-154">В последнем примере две конечные точки настраиваются для типа службы `HelloWorld`.</span><span class="sxs-lookup"><span data-stu-id="9b721-154">In this last example, two endpoints are configured for the `HelloWorld` service type.</span></span> <span data-ttu-id="9b721-155">Каждая конечная точка `bindingConfiguration` использует различные индивидуальные атрибуты `basicHttpBinding`одного и того же типа связывания (каждая изменяет).</span><span class="sxs-lookup"><span data-stu-id="9b721-155">Each endpoint uses a different customized  `bindingConfiguration` attribute of the same binding type (each modifies the `basicHttpBinding`).</span></span>  
  
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
  
 <span data-ttu-id="9b721-156">Можно добиться того же поведения с помощью конфигурации по умолчанию, добавив раздел `protocolMapping` и настроив привязки, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="9b721-156">You can get the same behavior using the default configuration by adding a `protocolMapping` section and configuring the bindings as demonstrated in the following example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9b721-157">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9b721-157">See also</span></span>

- [<span data-ttu-id="9b721-158">Упрощенная конфигурация</span><span class="sxs-lookup"><span data-stu-id="9b721-158">Simplified Configuration</span></span>](simplified-configuration.md)
- [<span data-ttu-id="9b721-159">Привязки, предоставляемые системой</span><span class="sxs-lookup"><span data-stu-id="9b721-159">System-Provided Bindings</span></span>](system-provided-bindings.md)
- [<span data-ttu-id="9b721-160">Общие сведения о создании конечных точек</span><span class="sxs-lookup"><span data-stu-id="9b721-160">Endpoint Creation Overview</span></span>](endpoint-creation-overview.md)
- [<span data-ttu-id="9b721-161">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="9b721-161">Using Bindings to Configure Services and Clients</span></span>](using-bindings-to-configure-services-and-clients.md)
