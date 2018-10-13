---
title: '&lt;system.serviceModel&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.ServiceModel
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel
helpviewer_keywords:
- <system.serviceModel> element
- system.serviceModel element
ms.assetid: 78519531-ad7a-40d3-b3e7-42f1103d8854
ms.openlocfilehash: 50cc8fdbf175a7148795078e4d243df21d34a40e
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2018
ms.locfileid: "49308517"
---
# <a name="ltsystemservicemodelgt"></a><span data-ttu-id="46fdb-102">&lt;system.serviceModel&gt;</span><span class="sxs-lookup"><span data-stu-id="46fdb-102">&lt;system.serviceModel&gt;</span></span>
<span data-ttu-id="46fdb-103">Этот раздел конфигурации содержит все элементы конфигурации ServiceModel службы Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="46fdb-103">This configuration section contains all the Windows Communication Foundation (WCF) ServiceModel configuration elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46fdb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="46fdb-104">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <behaviors>  
  </behaviors>  
  <bindings>  
  </bindings>  
  <client>  
  </client>  
  <comContracts>  
  </comContracts>  
  <commonBehaviors>  
  </commonBehaviors>  
  <diagnostics>  
  </diagnostics>  
  <extensions>  
  </extensions>
  <protocolMapping>
  </protocolMapping>
  <routing>
  </routing>  
  <serviceHostingEnvironment>  
  </serviceHostingEnvironment>  
  <services>  
  </services>
  <standardEndpoints>  
  </standardEndpoints>
  <tracking>
  </tracking>
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="46fdb-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="46fdb-105">Attributes and Elements</span></span>  
 <span data-ttu-id="46fdb-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="46fdb-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="46fdb-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="46fdb-107">Attributes</span></span>  
 <span data-ttu-id="46fdb-108">Нет</span><span class="sxs-lookup"><span data-stu-id="46fdb-108">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="46fdb-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="46fdb-109">Child Elements</span></span>  
  
|<span data-ttu-id="46fdb-110">Элемент</span><span class="sxs-lookup"><span data-stu-id="46fdb-110">Element</span></span>|<span data-ttu-id="46fdb-111">Описание</span><span class="sxs-lookup"><span data-stu-id="46fdb-111">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="46fdb-112">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="46fdb-112">\<behaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)|<span data-ttu-id="46fdb-113">Данный раздел определяет две дочерние коллекции с именами `endpointBehaviors` и `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="46fdb-113">This section defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="46fdb-114">Каждая коллекция определяет элементы поведений, используемые конечными точками и службами соответственно.</span><span class="sxs-lookup"><span data-stu-id="46fdb-114">Each collection defines behavior elements consumed by endpoints and services respectively.</span></span> <span data-ttu-id="46fdb-115">Каждый элемент поведения идентифицируется по уникальному атрибуту `name`.</span><span class="sxs-lookup"><span data-stu-id="46fdb-115">Each behavior element is identified by its unique `name` attribute.</span></span>|  
|[<span data-ttu-id="46fdb-116">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="46fdb-116">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="46fdb-117">В этом разделе содержится коллекция стандартных и пользовательских привязок.</span><span class="sxs-lookup"><span data-stu-id="46fdb-117">This section holds a collection of standard and custom bindings.</span></span> <span data-ttu-id="46fdb-118">Каждая запись идентифицируется по уникальному свойству `name`.</span><span class="sxs-lookup"><span data-stu-id="46fdb-118">Each entry is identified by its unique `name`.</span></span> <span data-ttu-id="46fdb-119">Службы используют привязки, связывая их с помощью параметра `name`.</span><span class="sxs-lookup"><span data-stu-id="46fdb-119">Services use bindings by linking them using the `name`.</span></span>|  
|[<span data-ttu-id="46fdb-120">\<Клиент ></span><span class="sxs-lookup"><span data-stu-id="46fdb-120">\<client></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/client.md)|<span data-ttu-id="46fdb-121">Данный раздел содержит список конечных точек, которые клиент использует для подключения к службе.</span><span class="sxs-lookup"><span data-stu-id="46fdb-121">This section contains a list of endpoints a client uses to connect to a service.</span></span>|  
|[<span data-ttu-id="46fdb-122">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="46fdb-122">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)|<span data-ttu-id="46fdb-123">В данном разделе определяются контракты COM, которые разрешены для обеспечения взаимодействия WCF и COM.</span><span class="sxs-lookup"><span data-stu-id="46fdb-123">This section defines COM contracts enabled for WCF and COM interop.</span></span>|  
|[<span data-ttu-id="46fdb-124">\<commonBehaviors ></span><span class="sxs-lookup"><span data-stu-id="46fdb-124">\<commonBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md)|<span data-ttu-id="46fdb-125">Этот раздел может быть определен только в файле machine.config.</span><span class="sxs-lookup"><span data-stu-id="46fdb-125">This section can only be defined in the machine.config file.</span></span> <span data-ttu-id="46fdb-126">В нем определяются две дочерние коллекции с именами `endpointBehaviors` и `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="46fdb-126">It defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="46fdb-127">Каждая коллекция определяет элементы поведения, используемые соответственно всеми конечными точками WCF и службы на компьютере.</span><span class="sxs-lookup"><span data-stu-id="46fdb-127">Each collection defines behavior elements consumed by all WCF endpoints and services on the machine respectively.</span></span>  <span data-ttu-id="46fdb-128">Если поведение задано в обоих `<commonBehaviors>` и `<behaviors>` разделах, в \<поведения > отдается поведениям из раздела.</span><span class="sxs-lookup"><span data-stu-id="46fdb-128">If a behavior is defined in both `<commonBehaviors>` and `<behaviors>` sections, the behavior in the \<behaviors> section is given preference.</span></span>|  
|[<span data-ttu-id="46fdb-129">\<Диагностика ></span><span class="sxs-lookup"><span data-stu-id="46fdb-129">\<diagnostics></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md)|<span data-ttu-id="46fdb-130">В этом разделе содержатся параметры возможностей диагностики WCF.</span><span class="sxs-lookup"><span data-stu-id="46fdb-130">This section contains settings for the diagnostics features of WCF.</span></span> <span data-ttu-id="46fdb-131">Пользователь может включить или отключить трассировку, счетчики производительности и провайдер инструментария WMI, а также может добавлять специальные фильтры сообщений.</span><span class="sxs-lookup"><span data-stu-id="46fdb-131">The user can enable/disable tracing, performance counters, and the WMI provider, and can add custom message filters.</span></span>|  
|[<span data-ttu-id="46fdb-132">\<расширения ></span><span class="sxs-lookup"><span data-stu-id="46fdb-132">\<extensions></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions-section.md)|<span data-ttu-id="46fdb-133">Данный раздел содержит коллекцию расширений, которые позволяют пользователю создавать определяемые пользователем привязки, поведения и другие виды расширений.</span><span class="sxs-lookup"><span data-stu-id="46fdb-133">This section contains a collection of extensions, which enable the user to create user-defined bindings, behaviors, and other aspects of extensions.</span></span>|  
|[<span data-ttu-id="46fdb-134">\<protocolMapping ></span><span class="sxs-lookup"><span data-stu-id="46fdb-134">\<protocolMapping></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/protocolmapping.md)|<span data-ttu-id="46fdb-135">В этом разделе определяет набор сопоставления протоколов по умолчанию между схемами транспортных протоколов (например, http, net.tcp, net.pipe, и т.д.) и привязками WCF.</span><span class="sxs-lookup"><span data-stu-id="46fdb-135">This section defines a set of default protocol mapping between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and WCF bindings.</span></span>|  
|[<span data-ttu-id="46fdb-136">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="46fdb-136">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="46fdb-137">В этом разделе определяет набор фильтров маршрутизации, которые определяют тип Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> для использования при вычислении входящих сообщений, а также маршрутизацию таблиц, которые определяют целевые конечные точки для отправки сообщений в случае Фильтр соответствует.</span><span class="sxs-lookup"><span data-stu-id="46fdb-137">This section defines a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
|[<span data-ttu-id="46fdb-138">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="46fdb-138">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="46fdb-139">Этот раздел определяет тип, который среда размещения служб создает для определенного транспорта.</span><span class="sxs-lookup"><span data-stu-id="46fdb-139">This section defines what type the service hosting environment instantiates for a particular transport.</span></span> <span data-ttu-id="46fdb-140">Если данный раздел пуст, то используется тип, заданный по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="46fdb-140">If this section is empty, the default type is used.</span></span>|  
|[<span data-ttu-id="46fdb-141">\<Services ></span><span class="sxs-lookup"><span data-stu-id="46fdb-141">\<services></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md)|<span data-ttu-id="46fdb-142">Раздел содержит коллекцию служб.</span><span class="sxs-lookup"><span data-stu-id="46fdb-142">The section contains a collection of services.</span></span> <span data-ttu-id="46fdb-143">Для каждой службы, определенной в сборке, данный элемент содержит элемент `service`, который задает параметры для данной службы.</span><span class="sxs-lookup"><span data-stu-id="46fdb-143">For each service defined in the assembly, this element contains a `service` element specifying settings for the service.</span></span>|  
|[<span data-ttu-id="46fdb-144">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="46fdb-144">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="46fdb-145">В этом разделе определяется коллекция конечных точек, которые являются пригодными для многократного использования стандартными конечными точками.</span><span class="sxs-lookup"><span data-stu-id="46fdb-145">This section defines a collection of standard endpoints, which are reusable preconfigured endpoints.</span></span> <span data-ttu-id="46fdb-146">Значение одного или нескольких атрибутов стандартной конечной точки, обозначающих адрес, привязку или контракт, является фиксированным.</span><span class="sxs-lookup"><span data-stu-id="46fdb-146">A standard endpoint will have one or more of the address, binding and contract attributes set to a fixed value.</span></span> <span data-ttu-id="46fdb-147">Например, в конечной точке обнаружения фиксированным является контракт.</span><span class="sxs-lookup"><span data-stu-id="46fdb-147">For example, in the discovery endpoint the contract is fixed.</span></span> <span data-ttu-id="46fdb-148">По аналогии с определением пользовательских привязок можно также использовать стандартные конечные точки для расширения конечной точки службы за счет новых свойств.</span><span class="sxs-lookup"><span data-stu-id="46fdb-148">You can also use standard endpoints to extend service endpoint with new properties similar to defining custom bindings.</span></span>|
|[<span data-ttu-id="46fdb-149">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="46fdb-149">\<tracking></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tracking-of-wcf.md)|<span data-ttu-id="46fdb-150">В этом разделе определяет параметры отслеживания для службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="46fdb-150">This section defines tracking settings for a workflow service.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="46fdb-151">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="46fdb-151">Parent Elements</span></span>  
  
|<span data-ttu-id="46fdb-152">Элемент</span><span class="sxs-lookup"><span data-stu-id="46fdb-152">Element</span></span>|<span data-ttu-id="46fdb-153">Описание</span><span class="sxs-lookup"><span data-stu-id="46fdb-153">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="46fdb-154">\<configuration></span><span class="sxs-lookup"><span data-stu-id="46fdb-154">\<configuration></span></span>|<span data-ttu-id="46fdb-155">Корневой элемент для всех элементов конфигурации в файле конфигурации .NET.</span><span class="sxs-lookup"><span data-stu-id="46fdb-155">The root element for all configuration elements in a .NET configuration file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="46fdb-156">Примечания</span><span class="sxs-lookup"><span data-stu-id="46fdb-156">Remarks</span></span>  
 <span data-ttu-id="46fdb-157">WCF не добавляет элементы к разделам конфигурации других продуктов.</span><span class="sxs-lookup"><span data-stu-id="46fdb-157">WCF does not add elements to the configuration sections of other products.</span></span>  
  
 <span data-ttu-id="46fdb-158">Службы WCF определены в `services` раздел файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="46fdb-158">WCF services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="46fdb-159">Сборка может содержать любое число служб.</span><span class="sxs-lookup"><span data-stu-id="46fdb-159">An assembly can contain any number of services.</span></span> <span data-ttu-id="46fdb-160">Для каждой службы используется собственный раздел конфигурации `service`.</span><span class="sxs-lookup"><span data-stu-id="46fdb-160">Each service has its own `service` configuration section.</span></span> <span data-ttu-id="46fdb-161">Этот раздел и его содержимое определяют контракт, поведение и конечные точки конкретной службы.</span><span class="sxs-lookup"><span data-stu-id="46fdb-161">The section and its content define the service contract, behavior, and endpoints of the particular service.</span></span>  
  
 <span data-ttu-id="46fdb-162">Обязательным является только атрибут `name`.</span><span class="sxs-lookup"><span data-stu-id="46fdb-162">Only a service's `name` attribute is required.</span></span>  <span data-ttu-id="46fdb-163">По умолчанию имя службы описывает базовый тип CLR, который используется для реализации службы, однако можно изменить свойство ConfigurationName в классе <xref:System.ServiceModel.ServiceContractAttribute>, чтобы изменить требования к типу CLR.</span><span class="sxs-lookup"><span data-stu-id="46fdb-163">By default, a service's name describes the underlying CLR type used to implement a service; however, you may change the ConfigurationName property on a <xref:System.ServiceModel.ServiceContractAttribute> to override the CLR type requirement.</span></span>  
  
 <span data-ttu-id="46fdb-164">Атрибут `behaviorConfiguration` является необязательным.</span><span class="sxs-lookup"><span data-stu-id="46fdb-164">The `behaviorConfiguration` attribute is optional.</span></span> <span data-ttu-id="46fdb-165">Он указывает поведение, используемое службой.</span><span class="sxs-lookup"><span data-stu-id="46fdb-165">It identifies the service behavior used by a service.</span></span> <span data-ttu-id="46fdb-166">Поведение, которое определяется данным атрибутом, должно быть связано с поведением службы, которое определяется в области того же файла конфигурации (то есть в том же файле или в родительском файле).</span><span class="sxs-lookup"><span data-stu-id="46fdb-166">The behavior specified by this attribute must link to a service behavior defined in the scope of the same configuration file (i.e. the same file or a parent file).</span></span>  
  
 <span data-ttu-id="46fdb-167">Каждая служба предоставляет одну или несколько конечных точек, которые определяются в элементе `endpoint`.</span><span class="sxs-lookup"><span data-stu-id="46fdb-167">Each service exposes one or more endpoints defined in an `endpoint` element.</span></span> <span data-ttu-id="46fdb-168">Каждая конечная точка имеет свой адрес и привязку.</span><span class="sxs-lookup"><span data-stu-id="46fdb-168">Each endpoint has its own address and binding.</span></span> <span data-ttu-id="46fdb-169">Все привязки в файле конфигурации должны быть определены в области файла.</span><span class="sxs-lookup"><span data-stu-id="46fdb-169">All bindings used within the configuration file must be defined in the scope of the file.</span></span>  
  
 <span data-ttu-id="46fdb-170">Привязки связаны с конечными точками через сочетание атрибутов `name` и `bindingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="46fdb-170">Bindings are linked to endpoints through the combination of the attributes `name` and `bindingConfiguration`.</span></span> <span data-ttu-id="46fdb-171">Атрибут `binding` указывает, в каком разделе определяется привязка.</span><span class="sxs-lookup"><span data-stu-id="46fdb-171">The `binding` attribute defines in which section the binding is defined.</span></span> <span data-ttu-id="46fdb-172">Атрибут `bindingConfiguration` указывает, какая из настроенных привязок используется в разделе привязки.</span><span class="sxs-lookup"><span data-stu-id="46fdb-172">The `bindingConfiguration` attribute defines which configured binding within the binding section is used.</span></span> <span data-ttu-id="46fdb-173">В разделе привязки может определяться несколько настроенных привязок.</span><span class="sxs-lookup"><span data-stu-id="46fdb-173">A binding section can define several configured bindings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46fdb-174">Пример</span><span class="sxs-lookup"><span data-stu-id="46fdb-174">Example</span></span>  
 <span data-ttu-id="46fdb-175">Ниже приведен пример файла конфигурации WCF.</span><span class="sxs-lookup"><span data-stu-id="46fdb-175">This is an example of a WCF configuration file.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
    <system.serviceModel>  
        <behaviors>  
           <!-- List of Behaviors -->  
        </behaviors>  
        <client>  
           <!-- List of Endpoints -->  
        </client>  
        <diagnostics wmiProviderEnabled="false" performanceCountersEnabled="false" tracingEnabled="false">  
        </diagnostics>  
        <serviceHostingEnvironment>  
           <!-- List of entries -->  
        </serviceHostingEnvironment>  
        <comContracts>  
           <!-- List of COM+ Contracts -->  
        </comContracts>          
        <services>  
           <!-- List of Services -->  
        </services>  
        <bindings>  
           <!-- List of Bindings -->  
        </bindings>  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="46fdb-176">См. также</span><span class="sxs-lookup"><span data-stu-id="46fdb-176">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceModelSectionGroup>
