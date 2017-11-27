---
title: '&lt;endpointDiscovery&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 70812717-888a-4748-9640-0df6715ff029
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1716955748c481236a5d23c0592702855356e9e0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ltendpointdiscoverygt"></a><span data-ttu-id="9175a-102">&lt;endpointDiscovery&gt;</span><span class="sxs-lookup"><span data-stu-id="9175a-102">&lt;endpointDiscovery&gt;</span></span>
<span data-ttu-id="9175a-103">Указывает различные параметры обнаружения для конечной точки, такие как возможность обнаружения, области и любые пользовательские модули для ее метаданных.</span><span class="sxs-lookup"><span data-stu-id="9175a-103">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>  
  
<span data-ttu-id="9175a-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="9175a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="9175a-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="9175a-105">\<behaviors></span></span>  
<span data-ttu-id="9175a-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="9175a-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="9175a-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="9175a-107">\<behavior></span></span>  
<span data-ttu-id="9175a-108">\<endpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="9175a-108">\<endpointDiscovery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9175a-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9175a-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="String">
      <endpointDiscovery enabled="Boolean">
        <scopes>
          <add scope="URI"/>
        </scopes>
        <extensions />
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9175a-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9175a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9175a-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9175a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9175a-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9175a-112">Attributes</span></span>  
  
|<span data-ttu-id="9175a-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="9175a-113">Attribute</span></span>|<span data-ttu-id="9175a-114">Описание</span><span class="sxs-lookup"><span data-stu-id="9175a-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9175a-115">enabled</span><span class="sxs-lookup"><span data-stu-id="9175a-115">enabled</span></span>|<span data-ttu-id="9175a-116">Логическое значение, указывающее, включена ли для этой конечной точки возможность обнаружения.</span><span class="sxs-lookup"><span data-stu-id="9175a-116">A Boolean value that that specifies whether discoverability is enabled on this endpoint.</span></span> <span data-ttu-id="9175a-117">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="9175a-117">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9175a-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9175a-118">Child Elements</span></span>  
  
|<span data-ttu-id="9175a-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="9175a-119">Element</span></span>|<span data-ttu-id="9175a-120">Описание</span><span class="sxs-lookup"><span data-stu-id="9175a-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9175a-121">\<области ></span><span class="sxs-lookup"><span data-stu-id="9175a-121">\<scopes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|<span data-ttu-id="9175a-122">Коллекция URI областей для этой конечной точки.</span><span class="sxs-lookup"><span data-stu-id="9175a-122">A collection of scope URIs for the endpoint.</span></span> <span data-ttu-id="9175a-123">С одной конечной точкой можно связать несколько URI областей.</span><span class="sxs-lookup"><span data-stu-id="9175a-123">More than one scope Uris can be associated with a single endpoint.</span></span>|  
|<span data-ttu-id="9175a-124">[\<расширения >](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) [из \<endpointDiscovery >]</span><span class="sxs-lookup"><span data-stu-id="9175a-124">[\<extensions>](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) [of \<endpointDiscovery>]</span></span>|<span data-ttu-id="9175a-125">Коллекция элементов XML, позволяющая указывать пользовательские метаданные, публикуемые для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="9175a-125">A collection of XML elements that allows you to specify custom metadata to be published for an endpoint.</span></span>|  
|<span data-ttu-id="9175a-126">\<типы ></span><span class="sxs-lookup"><span data-stu-id="9175a-126">\<types></span></span>|<span data-ttu-id="9175a-127">Коллекция интерфейсов, которые нужно найти.</span><span class="sxs-lookup"><span data-stu-id="9175a-127">A collection of interfaces to search for.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9175a-128">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9175a-128">Parent Elements</span></span>  
  
|<span data-ttu-id="9175a-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="9175a-129">Element</span></span>|<span data-ttu-id="9175a-130">Описание</span><span class="sxs-lookup"><span data-stu-id="9175a-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9175a-131">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="9175a-131">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="9175a-132">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="9175a-132">Specifies a behavior element.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="9175a-133">Примечания</span><span class="sxs-lookup"><span data-stu-id="9175a-133">Remarks</span></span>  
 <span data-ttu-id="9175a-134">Если добавить этот элемент конфигурации в конфигурацию поведения конечной точки и присвоить атрибуту `enabled` значение `true`, то будет включена возможность обнаружения.</span><span class="sxs-lookup"><span data-stu-id="9175a-134">When added to the endpoint’s behavior configuration and with the `enabled` attribute set to `true`, this configuration element enables its discoverability.</span></span> <span data-ttu-id="9175a-135">Кроме того, можно использовать [ \<области >](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)дочернего элемента к указанию пользовательских областей URI, которые можно использовать для фильтрации конечных точек службы во время выполнения запроса, а также [ \<расширения >](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) дочерний элемент, чтобы указать пользовательские метаданные, которые должны быть опубликованы вместе со стандартными обнаруживаемыми метаданными (EPR, ContractTypeName, BindingName, области и ListenURI).</span><span class="sxs-lookup"><span data-stu-id="9175a-135">In addition, you can use the [\<scopes>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)child element to specifying custom scope Uris that can be used to filter service endpoints during query, as well as the [\<extensions>](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) child element to specify custom metadata that should be published along with the standard discoverable metadata (EPR, ContractTypeName, BindingName, Scope and ListenURI).</span></span>  
  
 <span data-ttu-id="9175a-136">Этот элемент конфигурации зависит от [ \<serviceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) элемент, который управляет уровнем обслуживания для обнаружения.</span><span class="sxs-lookup"><span data-stu-id="9175a-136">This configuration element is dependent on the [\<serviceDiscovery>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) element that provides the service level control of discoverability.</span></span> <span data-ttu-id="9175a-137">Это означает, что параметры этого элемента учитываются, если [ \<serviceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) не присутствует в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="9175a-137">This means that this element’s settings are ignored if [\<serviceDiscovery>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) is not present in the configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9175a-138">Пример</span><span class="sxs-lookup"><span data-stu-id="9175a-138">Example</span></span>  
 <span data-ttu-id="9175a-139">В следующем примере конфигурации определены области фильтрации и метаданные расширения, которые будут опубликованы для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="9175a-139">The following configuration example specifies filtering scopes and extension metadata to be published for an endpoint.</span></span>  
  
```xml  
<services>  
  <service name="CalculatorService"  
           behaviorConfiguration="CalculatorServiceBehavior">  
     <endpoint binding="basicHttpBinding"  
              address="calculator"  
              contract="ICalculatorService"  
              behaviorConfiguration="calculatorEndpointBehavior" />  
  </service>  
</services>  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <serviceDiscovery />  
    </behavior>  
  </serviceBehaviors>  
  <endpointBehaviors>  
    <behavior name="calculatorEndpointBehavior">  
      <endpointDiscovery enabled="true">  
        <scopes>  
          <add scope="http://contoso/test1"/>  
          <add scope="http://contoso/test2"/>  
        </scopes>  
        <extensions>  
          <e:Publisher xmlns:e="http://example.org">  
            <e:Name>The Example Organization</e:Name>  
            <e:Address>One Example Way, ExampleTown, EX 12345</e:Address>  
            <e:Contact>support@example.org</e:Contact>  
          </e:Publisher>  
          <AnotherCustomMetadata>Custom Metadata</AnotherCustomMetadata>  
        </extensions>  
      </endpointDiscovery>  
    </behavior>  
  </endpointBehaviors>  
</behaviors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9175a-140">См. также</span><span class="sxs-lookup"><span data-stu-id="9175a-140">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
