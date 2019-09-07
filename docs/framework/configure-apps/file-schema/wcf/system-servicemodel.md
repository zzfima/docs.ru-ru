---
title: <system.serviceModel>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.ServiceModel
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel
helpviewer_keywords:
- <system.serviceModel> element
- system.serviceModel element
ms.assetid: 78519531-ad7a-40d3-b3e7-42f1103d8854
ms.openlocfilehash: 2125ce00b0e23f2e93ff251549f9c1276892b16b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399443"
---
# <a name="systemservicemodel"></a><span data-ttu-id="1a11f-102">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="1a11f-102">\<system.serviceModel></span></span>
<span data-ttu-id="1a11f-103">Этот раздел конфигурации содержит все элементы конфигурации Windows Communication Foundation (WCF) ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="1a11f-103">This configuration section contains all the Windows Communication Foundation (WCF) ServiceModel configuration elements.</span></span>  

<span data-ttu-id="1a11f-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1a11f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1a11f-105">&nbsp;&nbsp; **\<> System. serviceModel**</span><span class="sxs-lookup"><span data-stu-id="1a11f-105">&nbsp;&nbsp;**\<system.serviceModel>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a11f-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1a11f-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1a11f-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1a11f-107">Attributes and Elements</span></span>  
 <span data-ttu-id="1a11f-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1a11f-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1a11f-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1a11f-109">Attributes</span></span>  
 <span data-ttu-id="1a11f-110">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="1a11f-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1a11f-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1a11f-111">Child Elements</span></span>  
  
|<span data-ttu-id="1a11f-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="1a11f-112">Element</span></span>|<span data-ttu-id="1a11f-113">Описание</span><span class="sxs-lookup"><span data-stu-id="1a11f-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1a11f-114">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="1a11f-114">\<behaviors></span></span>](behaviors.md)|<span data-ttu-id="1a11f-115">Данный раздел определяет две дочерние коллекции с именами `endpointBehaviors` и `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="1a11f-115">This section defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="1a11f-116">Каждая коллекция определяет элементы поведений, используемые конечными точками и службами соответственно.</span><span class="sxs-lookup"><span data-stu-id="1a11f-116">Each collection defines behavior elements consumed by endpoints and services respectively.</span></span> <span data-ttu-id="1a11f-117">Каждый элемент поведения идентифицируется по уникальному атрибуту `name`.</span><span class="sxs-lookup"><span data-stu-id="1a11f-117">Each behavior element is identified by its unique `name` attribute.</span></span>|  
|[<span data-ttu-id="1a11f-118">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="1a11f-118">\<bindings></span></span>](bindings.md)|<span data-ttu-id="1a11f-119">В этом разделе содержится коллекция стандартных и пользовательских привязок.</span><span class="sxs-lookup"><span data-stu-id="1a11f-119">This section holds a collection of standard and custom bindings.</span></span> <span data-ttu-id="1a11f-120">Каждая запись идентифицируется по уникальному свойству `name`.</span><span class="sxs-lookup"><span data-stu-id="1a11f-120">Each entry is identified by its unique `name`.</span></span> <span data-ttu-id="1a11f-121">Службы используют привязки, связывая их с помощью параметра `name`.</span><span class="sxs-lookup"><span data-stu-id="1a11f-121">Services use bindings by linking them using the `name`.</span></span>|  
|[<span data-ttu-id="1a11f-122">\<> клиента</span><span class="sxs-lookup"><span data-stu-id="1a11f-122">\<client></span></span>](client.md)|<span data-ttu-id="1a11f-123">Данный раздел содержит список конечных точек, которые клиент использует для подключения к службе.</span><span class="sxs-lookup"><span data-stu-id="1a11f-123">This section contains a list of endpoints a client uses to connect to a service.</span></span>|  
|[<span data-ttu-id="1a11f-124">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="1a11f-124">\<comContracts></span></span>](comcontracts.md)|<span data-ttu-id="1a11f-125">В данном разделе определяются контракты COM, которые разрешены для обеспечения взаимодействия WCF и COM.</span><span class="sxs-lookup"><span data-stu-id="1a11f-125">This section defines COM contracts enabled for WCF and COM interop.</span></span>|  
|[<span data-ttu-id="1a11f-126">\<commonBehaviors ></span><span class="sxs-lookup"><span data-stu-id="1a11f-126">\<commonBehaviors></span></span>](commonbehaviors.md)|<span data-ttu-id="1a11f-127">Этот раздел может быть определен только в файле machine.config.</span><span class="sxs-lookup"><span data-stu-id="1a11f-127">This section can only be defined in the machine.config file.</span></span> <span data-ttu-id="1a11f-128">В нем определяются две дочерние коллекции с именами `endpointBehaviors` и `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="1a11f-128">It defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="1a11f-129">Каждая коллекция определяет элементы поведения, используемые всеми конечными точками и службами WCF на компьютере соответственно.</span><span class="sxs-lookup"><span data-stu-id="1a11f-129">Each collection defines behavior elements consumed by all WCF endpoints and services on the machine respectively.</span></span>  <span data-ttu-id="1a11f-130">Если поведение определено в обоих `<commonBehaviors>` разделах и `<behaviors>` \<, то поведение в разделе «behaviors >» задается предпочтением.</span><span class="sxs-lookup"><span data-stu-id="1a11f-130">If a behavior is defined in both `<commonBehaviors>` and `<behaviors>` sections, the behavior in the \<behaviors> section is given preference.</span></span>|  
|[<span data-ttu-id="1a11f-131">\<Диагностика ></span><span class="sxs-lookup"><span data-stu-id="1a11f-131">\<diagnostics></span></span>](diagnostics.md)|<span data-ttu-id="1a11f-132">В этом разделе содержатся параметры возможностей диагностики WCF.</span><span class="sxs-lookup"><span data-stu-id="1a11f-132">This section contains settings for the diagnostics features of WCF.</span></span> <span data-ttu-id="1a11f-133">Пользователь может включить или отключить трассировку, счетчики производительности и провайдер инструментария WMI, а также может добавлять специальные фильтры сообщений.</span><span class="sxs-lookup"><span data-stu-id="1a11f-133">The user can enable/disable tracing, performance counters, and the WMI provider, and can add custom message filters.</span></span>|  
|[<span data-ttu-id="1a11f-134">\<расширения ></span><span class="sxs-lookup"><span data-stu-id="1a11f-134">\<extensions></span></span>](extensions-section.md)|<span data-ttu-id="1a11f-135">Данный раздел содержит коллекцию расширений, которые позволяют пользователю создавать определяемые пользователем привязки, поведения и другие виды расширений.</span><span class="sxs-lookup"><span data-stu-id="1a11f-135">This section contains a collection of extensions, which enable the user to create user-defined bindings, behaviors, and other aspects of extensions.</span></span>|  
|[<span data-ttu-id="1a11f-136">\<Протоколмаппинг ></span><span class="sxs-lookup"><span data-stu-id="1a11f-136">\<protocolMapping></span></span>](protocolmapping.md)|<span data-ttu-id="1a11f-137">В этом разделе определяется набор протоколов по умолчанию между схемами транспортного протокола (например, HTTP, net. TCP, net. pipe и т. д.) и привязками WCF.</span><span class="sxs-lookup"><span data-stu-id="1a11f-137">This section defines a set of default protocol mapping between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and WCF bindings.</span></span>|  
|[<span data-ttu-id="1a11f-138">\<> маршрутизации</span><span class="sxs-lookup"><span data-stu-id="1a11f-138">\<routing></span></span>](routing.md)|<span data-ttu-id="1a11f-139">В этом разделе определяется набор фильтров маршрутизации, которые определяют тип Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> , используемый при оценке входящих сообщений, а также таблицы маршрутизации, которые определяют целевые конечные точки для отправки сообщений, когда Фильтрация совпадений.</span><span class="sxs-lookup"><span data-stu-id="1a11f-139">This section defines a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
|[<span data-ttu-id="1a11f-140">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="1a11f-140">\<serviceHostingEnvironment></span></span>](servicehostingenvironment.md)|<span data-ttu-id="1a11f-141">Этот раздел определяет тип, который среда размещения служб создает для определенного транспорта.</span><span class="sxs-lookup"><span data-stu-id="1a11f-141">This section defines what type the service hosting environment instantiates for a particular transport.</span></span> <span data-ttu-id="1a11f-142">Если данный раздел пуст, то используется тип, заданный по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1a11f-142">If this section is empty, the default type is used.</span></span>|  
|[<span data-ttu-id="1a11f-143">\<службы ></span><span class="sxs-lookup"><span data-stu-id="1a11f-143">\<services></span></span>](services.md)|<span data-ttu-id="1a11f-144">Раздел содержит коллекцию служб.</span><span class="sxs-lookup"><span data-stu-id="1a11f-144">The section contains a collection of services.</span></span> <span data-ttu-id="1a11f-145">Для каждой службы, определенной в сборке, данный элемент содержит элемент `service`, который задает параметры для данной службы.</span><span class="sxs-lookup"><span data-stu-id="1a11f-145">For each service defined in the assembly, this element contains a `service` element specifying settings for the service.</span></span>|  
|[<span data-ttu-id="1a11f-146">\<Стандардендпоинтс ></span><span class="sxs-lookup"><span data-stu-id="1a11f-146">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="1a11f-147">В этом разделе определяется коллекция конечных точек, которые являются пригодными для многократного использования стандартными конечными точками.</span><span class="sxs-lookup"><span data-stu-id="1a11f-147">This section defines a collection of standard endpoints, which are reusable preconfigured endpoints.</span></span> <span data-ttu-id="1a11f-148">Значение одного или нескольких атрибутов стандартной конечной точки, обозначающих адрес, привязку или контракт, является фиксированным.</span><span class="sxs-lookup"><span data-stu-id="1a11f-148">A standard endpoint will have one or more of the address, binding and contract attributes set to a fixed value.</span></span> <span data-ttu-id="1a11f-149">Например, в конечной точке обнаружения фиксированным является контракт.</span><span class="sxs-lookup"><span data-stu-id="1a11f-149">For example, in the discovery endpoint the contract is fixed.</span></span> <span data-ttu-id="1a11f-150">По аналогии с определением пользовательских привязок можно также использовать стандартные конечные точки для расширения конечной точки службы за счет новых свойств.</span><span class="sxs-lookup"><span data-stu-id="1a11f-150">You can also use standard endpoints to extend service endpoint with new properties similar to defining custom bindings.</span></span>|
|[<span data-ttu-id="1a11f-151">\<Отслеживание ></span><span class="sxs-lookup"><span data-stu-id="1a11f-151">\<tracking></span></span>](tracking-of-wcf.md)|<span data-ttu-id="1a11f-152">В этом разделе определяются параметры отслеживания для службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="1a11f-152">This section defines tracking settings for a workflow service.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="1a11f-153">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1a11f-153">Parent Elements</span></span>  
  
|<span data-ttu-id="1a11f-154">Элемент</span><span class="sxs-lookup"><span data-stu-id="1a11f-154">Element</span></span>|<span data-ttu-id="1a11f-155">Описание</span><span class="sxs-lookup"><span data-stu-id="1a11f-155">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1a11f-156">\<configuration></span><span class="sxs-lookup"><span data-stu-id="1a11f-156">\<configuration></span></span>|<span data-ttu-id="1a11f-157">Корневой элемент для всех элементов конфигурации в файле конфигурации .NET.</span><span class="sxs-lookup"><span data-stu-id="1a11f-157">The root element for all configuration elements in a .NET configuration file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1a11f-158">Примечания</span><span class="sxs-lookup"><span data-stu-id="1a11f-158">Remarks</span></span>  
 <span data-ttu-id="1a11f-159">WCF не добавляет элементы в разделы конфигурации других продуктов.</span><span class="sxs-lookup"><span data-stu-id="1a11f-159">WCF does not add elements to the configuration sections of other products.</span></span>  
  
 <span data-ttu-id="1a11f-160">Службы WCF определяются в `services` разделе файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1a11f-160">WCF services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="1a11f-161">Сборка может содержать любое число служб.</span><span class="sxs-lookup"><span data-stu-id="1a11f-161">An assembly can contain any number of services.</span></span> <span data-ttu-id="1a11f-162">Для каждой службы используется собственный раздел конфигурации `service`.</span><span class="sxs-lookup"><span data-stu-id="1a11f-162">Each service has its own `service` configuration section.</span></span> <span data-ttu-id="1a11f-163">Этот раздел и его содержимое определяют контракт, поведение и конечные точки конкретной службы.</span><span class="sxs-lookup"><span data-stu-id="1a11f-163">The section and its content define the service contract, behavior, and endpoints of the particular service.</span></span>  
  
 <span data-ttu-id="1a11f-164">Обязательным является только атрибут `name`.</span><span class="sxs-lookup"><span data-stu-id="1a11f-164">Only a service's `name` attribute is required.</span></span>  <span data-ttu-id="1a11f-165">По умолчанию имя службы описывает базовый тип CLR, который используется для реализации службы, однако можно изменить свойство ConfigurationName в классе <xref:System.ServiceModel.ServiceContractAttribute>, чтобы изменить требования к типу CLR.</span><span class="sxs-lookup"><span data-stu-id="1a11f-165">By default, a service's name describes the underlying CLR type used to implement a service; however, you may change the ConfigurationName property on a <xref:System.ServiceModel.ServiceContractAttribute> to override the CLR type requirement.</span></span>  
  
 <span data-ttu-id="1a11f-166">Атрибут `behaviorConfiguration` является необязательным.</span><span class="sxs-lookup"><span data-stu-id="1a11f-166">The `behaviorConfiguration` attribute is optional.</span></span> <span data-ttu-id="1a11f-167">Он указывает поведение, используемое службой.</span><span class="sxs-lookup"><span data-stu-id="1a11f-167">It identifies the service behavior used by a service.</span></span> <span data-ttu-id="1a11f-168">Поведение, которое определяется данным атрибутом, должно быть связано с поведением службы, которое определяется в области того же файла конфигурации (то есть в том же файле или в родительском файле).</span><span class="sxs-lookup"><span data-stu-id="1a11f-168">The behavior specified by this attribute must link to a service behavior defined in the scope of the same configuration file (i.e. the same file or a parent file).</span></span>  
  
 <span data-ttu-id="1a11f-169">Каждая служба предоставляет одну или несколько конечных точек, которые определяются в элементе `endpoint`.</span><span class="sxs-lookup"><span data-stu-id="1a11f-169">Each service exposes one or more endpoints defined in an `endpoint` element.</span></span> <span data-ttu-id="1a11f-170">Каждая конечная точка имеет свой адрес и привязку.</span><span class="sxs-lookup"><span data-stu-id="1a11f-170">Each endpoint has its own address and binding.</span></span> <span data-ttu-id="1a11f-171">Все привязки в файле конфигурации должны быть определены в области файла.</span><span class="sxs-lookup"><span data-stu-id="1a11f-171">All bindings used within the configuration file must be defined in the scope of the file.</span></span>  
  
 <span data-ttu-id="1a11f-172">Привязки связаны с конечными точками через сочетание атрибутов `name` и `bindingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="1a11f-172">Bindings are linked to endpoints through the combination of the attributes `name` and `bindingConfiguration`.</span></span> <span data-ttu-id="1a11f-173">Атрибут `binding` указывает, в каком разделе определяется привязка.</span><span class="sxs-lookup"><span data-stu-id="1a11f-173">The `binding` attribute defines in which section the binding is defined.</span></span> <span data-ttu-id="1a11f-174">Атрибут `bindingConfiguration` указывает, какая из настроенных привязок используется в разделе привязки.</span><span class="sxs-lookup"><span data-stu-id="1a11f-174">The `bindingConfiguration` attribute defines which configured binding within the binding section is used.</span></span> <span data-ttu-id="1a11f-175">В разделе привязки может определяться несколько настроенных привязок.</span><span class="sxs-lookup"><span data-stu-id="1a11f-175">A binding section can define several configured bindings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a11f-176">Пример</span><span class="sxs-lookup"><span data-stu-id="1a11f-176">Example</span></span>  
 <span data-ttu-id="1a11f-177">Ниже приведен пример файла конфигурации WCF.</span><span class="sxs-lookup"><span data-stu-id="1a11f-177">This is an example of a WCF configuration file.</span></span>  
  
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
    <diagnostics wmiProviderEnabled="false"
                 performanceCountersEnabled="false"
                 tracingEnabled="false">
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
  
## <a name="see-also"></a><span data-ttu-id="1a11f-178">См. также</span><span class="sxs-lookup"><span data-stu-id="1a11f-178">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceModelSectionGroup>
