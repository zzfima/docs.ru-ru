---
title: '&lt;system.serviceModel&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.ServiceModel
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel
helpviewer_keywords:
- <system.serviceModel> element
- system.serviceModel element
ms.assetid: 78519531-ad7a-40d3-b3e7-42f1103d8854
caps.latest.revision: "26"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 563825a92dbdeb90cd17d107795525686b7b4080
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ltsystemservicemodelgt"></a><span data-ttu-id="56f4a-102">&lt;system.serviceModel&gt;</span><span class="sxs-lookup"><span data-stu-id="56f4a-102">&lt;system.serviceModel&gt;</span></span>
<span data-ttu-id="56f4a-103">Данный раздел конфигурации содержит все элементы конфигурации ServiceModel для [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="56f4a-103">This configuration section contains all the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] ServiceModel configuration elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56f4a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="56f4a-104">Syntax</span></span>  
  
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
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="56f4a-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="56f4a-105">Attributes and Elements</span></span>  
 <span data-ttu-id="56f4a-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="56f4a-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="56f4a-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="56f4a-107">Attributes</span></span>  
 <span data-ttu-id="56f4a-108">Нет</span><span class="sxs-lookup"><span data-stu-id="56f4a-108">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="56f4a-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="56f4a-109">Child Elements</span></span>  
  
|<span data-ttu-id="56f4a-110">Элемент</span><span class="sxs-lookup"><span data-stu-id="56f4a-110">Element</span></span>|<span data-ttu-id="56f4a-111">Описание</span><span class="sxs-lookup"><span data-stu-id="56f4a-111">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="56f4a-112">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="56f4a-112">\<behaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)|<span data-ttu-id="56f4a-113">Данный раздел определяет две дочерние коллекции с именами `endpointBehaviors` и `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="56f4a-113">This section defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="56f4a-114">Каждая коллекция определяет элементы поведений, используемые конечными точками и службами соответственно.</span><span class="sxs-lookup"><span data-stu-id="56f4a-114">Each collection defines behavior elements consumed by endpoints and services respectively.</span></span> <span data-ttu-id="56f4a-115">Каждый элемент поведения идентифицируется по уникальному атрибуту `name`.</span><span class="sxs-lookup"><span data-stu-id="56f4a-115">Each behavior element is identified by its unique `name` attribute.</span></span>|  
|[<span data-ttu-id="56f4a-116">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="56f4a-116">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="56f4a-117">В этом разделе содержится коллекция стандартных и пользовательских привязок.</span><span class="sxs-lookup"><span data-stu-id="56f4a-117">This section holds a collection of standard and custom bindings.</span></span> <span data-ttu-id="56f4a-118">Каждая запись идентифицируется по уникальному свойству `name`.</span><span class="sxs-lookup"><span data-stu-id="56f4a-118">Each entry is identified by its unique `name`.</span></span> <span data-ttu-id="56f4a-119">Службы используют привязки, связывая их с помощью параметра `name`.</span><span class="sxs-lookup"><span data-stu-id="56f4a-119">Services use bindings by linking them using the `name`.</span></span>|  
|[<span data-ttu-id="56f4a-120">\<Клиент ></span><span class="sxs-lookup"><span data-stu-id="56f4a-120">\<client></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/client.md)|<span data-ttu-id="56f4a-121">Данный раздел содержит список конечных точек, которые клиент использует для подключения к службе.</span><span class="sxs-lookup"><span data-stu-id="56f4a-121">This section contains a list of endpoints a client uses to connect to a service.</span></span>|  
|[<span data-ttu-id="56f4a-122">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="56f4a-122">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)|<span data-ttu-id="56f4a-123">В данном разделе определяются контракты COM, которые разрешены для обеспечения взаимодействия WCF и COM.</span><span class="sxs-lookup"><span data-stu-id="56f4a-123">This section defines COM contracts enabled for WCF and COM interop.</span></span>|  
|[<span data-ttu-id="56f4a-124">\<commonBehaviors ></span><span class="sxs-lookup"><span data-stu-id="56f4a-124">\<commonBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md)|<span data-ttu-id="56f4a-125">Этот раздел может быть определен только в файле machine.config.</span><span class="sxs-lookup"><span data-stu-id="56f4a-125">This section can only be defined in the machine.config file.</span></span> <span data-ttu-id="56f4a-126">В нем определяются две дочерние коллекции с именами `endpointBehaviors` и `serviceBehaviors`.</span><span class="sxs-lookup"><span data-stu-id="56f4a-126">It defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="56f4a-127">Каждая коллекция определяет элементы поведения, используемые соответственно всеми конечными точками [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] и службами на компьютере.</span><span class="sxs-lookup"><span data-stu-id="56f4a-127">Each collection defines behavior elements consumed by all [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] endpoints and services on the machine respectively.</span></span>  <span data-ttu-id="56f4a-128">Если поведение определено как `<commonBehaviors>` и `<behaviors>` разделах, в \<поведения > отдается поведениям из раздела.</span><span class="sxs-lookup"><span data-stu-id="56f4a-128">If a behavior is defined in both `<commonBehaviors>` and `<behaviors>` sections, the behavior in the \<behaviors> section is given preference.</span></span>|  
|[<span data-ttu-id="56f4a-129">\<расширения ></span><span class="sxs-lookup"><span data-stu-id="56f4a-129">\<extensions></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions-section.md)|<span data-ttu-id="56f4a-130">Данный раздел содержит коллекцию расширений, которые позволяют пользователю создавать определяемые пользователем привязки, поведения и другие виды расширений.</span><span class="sxs-lookup"><span data-stu-id="56f4a-130">This section contains a collection of extensions, which enable the user to create user-defined bindings, behaviors, and other aspects of extensions.</span></span>|  
|[<span data-ttu-id="56f4a-131">\<Диагностика ></span><span class="sxs-lookup"><span data-stu-id="56f4a-131">\<diagnostics></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md)|<span data-ttu-id="56f4a-132">В этом разделе содержатся параметры возможностей диагностики WCF.</span><span class="sxs-lookup"><span data-stu-id="56f4a-132">This section contains settings for the diagnostics features of WCF.</span></span> <span data-ttu-id="56f4a-133">Пользователь может включить или отключить трассировку, счетчики производительности и провайдер инструментария WMI, а также может добавлять специальные фильтры сообщений.</span><span class="sxs-lookup"><span data-stu-id="56f4a-133">The user can enable/disable tracing, performance counters, and the WMI provider, and can add custom message filters.</span></span>|  
|[<span data-ttu-id="56f4a-134">\<protocolMapping ></span><span class="sxs-lookup"><span data-stu-id="56f4a-134">\<protocolMapping></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/protocolmapping.md)|<span data-ttu-id="56f4a-135">Этот раздел определяет набор сопоставления протоколов по умолчанию между схемами транспортных протоколов (например, http, net.tcp, net.pipe, т. д.) и привязками WCF.</span><span class="sxs-lookup"><span data-stu-id="56f4a-135">This section defines a set of default protocol mapping between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and WCF bindings.</span></span>|  
|[<span data-ttu-id="56f4a-136">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="56f4a-136">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="56f4a-137">Этот раздел определяет набор фильтров маршрутизации, которые определяют тип [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter>, используемый при оценке входящих сообщений, а также таблиц маршрутизации, которые определяют целевые конечные точки для отправки сообщений (в случае если фильтр срабатывает).</span><span class="sxs-lookup"><span data-stu-id="56f4a-137">This section defines a set of routing filters, which determine the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
|[<span data-ttu-id="56f4a-138">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="56f4a-138">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="56f4a-139">Этот раздел определяет тип, который среда размещения служб создает для определенного транспорта.</span><span class="sxs-lookup"><span data-stu-id="56f4a-139">This section defines what type the service hosting environment instantiates for a particular transport.</span></span> <span data-ttu-id="56f4a-140">Если данный раздел пуст, то используется тип, заданный по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="56f4a-140">If this section is empty, the default type is used.</span></span>|  
|[<span data-ttu-id="56f4a-141">\<службы ></span><span class="sxs-lookup"><span data-stu-id="56f4a-141">\<services></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md)|<span data-ttu-id="56f4a-142">Раздел содержит коллекцию служб.</span><span class="sxs-lookup"><span data-stu-id="56f4a-142">The section contains a collection of services.</span></span> <span data-ttu-id="56f4a-143">Для каждой службы, определенной в сборке, данный элемент содержит элемент `service`, который задает параметры для данной службы.</span><span class="sxs-lookup"><span data-stu-id="56f4a-143">For each service defined in the assembly, this element contains a `service` element specifying settings for the service.</span></span>|  
|[<span data-ttu-id="56f4a-144">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="56f4a-144">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="56f4a-145">В этом разделе определяется коллекция конечных точек, которые являются пригодными для многократного использования стандартными конечными точками.</span><span class="sxs-lookup"><span data-stu-id="56f4a-145">This section defines a collection of standard endpoints, which are reusable preconfigured endpoints.</span></span> <span data-ttu-id="56f4a-146">Значение одного или нескольких атрибутов стандартной конечной точки, обозначающих адрес, привязку или контракт, является фиксированным.</span><span class="sxs-lookup"><span data-stu-id="56f4a-146">A standard endpoint will have one or more of the address, binding and contract attributes set to a fixed value.</span></span> <span data-ttu-id="56f4a-147">Например, в конечной точке обнаружения фиксированным является контракт.</span><span class="sxs-lookup"><span data-stu-id="56f4a-147">For example, in the discovery endpoint the contract is fixed.</span></span> <span data-ttu-id="56f4a-148">По аналогии с определением пользовательских привязок можно также использовать стандартные конечные точки для расширения конечной точки службы за счет новых свойств.</span><span class="sxs-lookup"><span data-stu-id="56f4a-148">You can also use standard endpoints to extend service endpoint with new properties similar to defining custom bindings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="56f4a-149">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="56f4a-149">Parent Elements</span></span>  
  
|<span data-ttu-id="56f4a-150">Элемент</span><span class="sxs-lookup"><span data-stu-id="56f4a-150">Element</span></span>|<span data-ttu-id="56f4a-151">Описание</span><span class="sxs-lookup"><span data-stu-id="56f4a-151">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="56f4a-152">\<configuration></span><span class="sxs-lookup"><span data-stu-id="56f4a-152">\<configuration></span></span>|<span data-ttu-id="56f4a-153">Корневой элемент для всех элементов конфигурации в файле конфигурации .NET.</span><span class="sxs-lookup"><span data-stu-id="56f4a-153">The root element for all configuration elements in a .NET configuration file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="56f4a-154">Примечания</span><span class="sxs-lookup"><span data-stu-id="56f4a-154">Remarks</span></span>  
 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]<span data-ttu-id="56f4a-155"> не добавляет элементы к разделам конфигурации других продуктов.</span><span class="sxs-lookup"><span data-stu-id="56f4a-155"> does not add elements to the configuration sections of other products.</span></span>  
  
 <span data-ttu-id="56f4a-156">Службы [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] определяются в разделе `services` файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="56f4a-156">[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="56f4a-157">Сборка может содержать любое число служб.</span><span class="sxs-lookup"><span data-stu-id="56f4a-157">An assembly can contain any number of services.</span></span> <span data-ttu-id="56f4a-158">Для каждой службы используется собственный раздел конфигурации `service`.</span><span class="sxs-lookup"><span data-stu-id="56f4a-158">Each service has its own `service` configuration section.</span></span> <span data-ttu-id="56f4a-159">Этот раздел и его содержимое определяют контракт, поведение и конечные точки конкретной службы.</span><span class="sxs-lookup"><span data-stu-id="56f4a-159">The section and its content define the service contract, behavior, and endpoints of the particular service.</span></span>  
  
 <span data-ttu-id="56f4a-160">Обязательным является только атрибут `name`.</span><span class="sxs-lookup"><span data-stu-id="56f4a-160">Only a service's `name` attribute is required.</span></span>  <span data-ttu-id="56f4a-161">По умолчанию имя службы описывает базовый тип CLR, который используется для реализации службы, однако можно изменить свойство ConfigurationName в классе <xref:System.ServiceModel.ServiceContractAttribute>, чтобы изменить требования к типу CLR.</span><span class="sxs-lookup"><span data-stu-id="56f4a-161">By default, a service's name describes the underlying CLR type used to implement a service; however, you may change the ConfigurationName property on a <xref:System.ServiceModel.ServiceContractAttribute> to override the CLR type requirement.</span></span>  
  
 <span data-ttu-id="56f4a-162">Атрибут `behaviorConfiguration` является необязательным.</span><span class="sxs-lookup"><span data-stu-id="56f4a-162">The `behaviorConfiguration` attribute is optional.</span></span> <span data-ttu-id="56f4a-163">Он указывает поведение, используемое службой.</span><span class="sxs-lookup"><span data-stu-id="56f4a-163">It identifies the service behavior used by a service.</span></span> <span data-ttu-id="56f4a-164">Поведение, которое определяется данным атрибутом, должно быть связано с поведением службы, которое определяется в области того же файла конфигурации (то есть в том же файле или в родительском файле).</span><span class="sxs-lookup"><span data-stu-id="56f4a-164">The behavior specified by this attribute must link to a service behavior defined in the scope of the same configuration file (i.e. the same file or a parent file).</span></span>  
  
 <span data-ttu-id="56f4a-165">Каждая служба предоставляет одну или несколько конечных точек, которые определяются в элементе `endpoint`.</span><span class="sxs-lookup"><span data-stu-id="56f4a-165">Each service exposes one or more endpoints defined in an `endpoint` element.</span></span> <span data-ttu-id="56f4a-166">Каждая конечная точка имеет свой адрес и привязку.</span><span class="sxs-lookup"><span data-stu-id="56f4a-166">Each endpoint has its own address and binding.</span></span> <span data-ttu-id="56f4a-167">Все привязки в файле конфигурации должны быть определены в области файла.</span><span class="sxs-lookup"><span data-stu-id="56f4a-167">All bindings used within the configuration file must be defined in the scope of the file.</span></span>  
  
 <span data-ttu-id="56f4a-168">Привязки связаны с конечными точками через сочетание атрибутов `name` и `bindingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="56f4a-168">Bindings are linked to endpoints through the combination of the attributes `name` and `bindingConfiguration`.</span></span> <span data-ttu-id="56f4a-169">Атрибут `binding` указывает, в каком разделе определяется привязка.</span><span class="sxs-lookup"><span data-stu-id="56f4a-169">The `binding` attribute defines in which section the binding is defined.</span></span> <span data-ttu-id="56f4a-170">Атрибут `bindingConfiguration` указывает, какая из настроенных привязок используется в разделе привязки.</span><span class="sxs-lookup"><span data-stu-id="56f4a-170">The `bindingConfiguration` attribute defines which configured binding within the binding section is used.</span></span> <span data-ttu-id="56f4a-171">В разделе привязки может определяться несколько настроенных привязок.</span><span class="sxs-lookup"><span data-stu-id="56f4a-171">A binding section can define several configured bindings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="56f4a-172">Пример</span><span class="sxs-lookup"><span data-stu-id="56f4a-172">Example</span></span>  
 <span data-ttu-id="56f4a-173">Ниже приведен пример файла конфигурации WCF.</span><span class="sxs-lookup"><span data-stu-id="56f4a-173">This is an example of a WCF configuration file.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="56f4a-174">См. также</span><span class="sxs-lookup"><span data-stu-id="56f4a-174">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceModelSectionGroup>
