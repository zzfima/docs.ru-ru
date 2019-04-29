---
title: <endpointDiscovery>
ms.date: 03/30/2017
ms.assetid: 70812717-888a-4748-9640-0df6715ff029
ms.openlocfilehash: 125baba917a49135aaa426df2cfa1a4dbe8ac1e8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61700914"
---
# <a name="endpointdiscovery"></a><span data-ttu-id="d6fce-101">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="d6fce-101">\<endpointDiscovery></span></span>
<span data-ttu-id="d6fce-102">Указывает различные параметры обнаружения для конечной точки, такие как возможность обнаружения, области и любые пользовательские модули для ее метаданных.</span><span class="sxs-lookup"><span data-stu-id="d6fce-102">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>  
  
<span data-ttu-id="d6fce-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d6fce-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="d6fce-104">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="d6fce-104">\<behaviors></span></span>  
<span data-ttu-id="d6fce-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="d6fce-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="d6fce-106">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="d6fce-106">\<behavior></span></span>  
<span data-ttu-id="d6fce-107">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="d6fce-107">\<endpointDiscovery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6fce-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d6fce-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d6fce-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d6fce-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d6fce-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d6fce-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d6fce-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d6fce-111">Attributes</span></span>  
  
|<span data-ttu-id="d6fce-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d6fce-112">Attribute</span></span>|<span data-ttu-id="d6fce-113">Описание</span><span class="sxs-lookup"><span data-stu-id="d6fce-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d6fce-114">enabled</span><span class="sxs-lookup"><span data-stu-id="d6fce-114">enabled</span></span>|<span data-ttu-id="d6fce-115">Логическое значение, указывающее, включена ли возможность обнаружения этой конечной точки.</span><span class="sxs-lookup"><span data-stu-id="d6fce-115">A Boolean value that specifies whether discoverability is enabled on this endpoint.</span></span> <span data-ttu-id="d6fce-116">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="d6fce-116">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d6fce-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d6fce-117">Child Elements</span></span>  
  
|<span data-ttu-id="d6fce-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="d6fce-118">Element</span></span>|<span data-ttu-id="d6fce-119">Описание</span><span class="sxs-lookup"><span data-stu-id="d6fce-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d6fce-120">\<области ></span><span class="sxs-lookup"><span data-stu-id="d6fce-120">\<scopes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|<span data-ttu-id="d6fce-121">Коллекция URI областей для этой конечной точки.</span><span class="sxs-lookup"><span data-stu-id="d6fce-121">A collection of scope URIs for the endpoint.</span></span> <span data-ttu-id="d6fce-122">С одной конечной точкой можно связать несколько URI областей.</span><span class="sxs-lookup"><span data-stu-id="d6fce-122">More than one scope Uris can be associated with a single endpoint.</span></span>|  
|<span data-ttu-id="d6fce-123">[\<расширения >](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) [из \<endpointDiscovery >]</span><span class="sxs-lookup"><span data-stu-id="d6fce-123">[\<extensions>](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) [of \<endpointDiscovery>]</span></span>|<span data-ttu-id="d6fce-124">Коллекция элементов XML, позволяющая указывать пользовательские метаданные, публикуемые для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="d6fce-124">A collection of XML elements that allows you to specify custom metadata to be published for an endpoint.</span></span>|  
|<span data-ttu-id="d6fce-125">\<типы ></span><span class="sxs-lookup"><span data-stu-id="d6fce-125">\<types></span></span>|<span data-ttu-id="d6fce-126">Коллекция интерфейсов, которые нужно найти.</span><span class="sxs-lookup"><span data-stu-id="d6fce-126">A collection of interfaces to search for.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d6fce-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d6fce-127">Parent Elements</span></span>  
  
|<span data-ttu-id="d6fce-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="d6fce-128">Element</span></span>|<span data-ttu-id="d6fce-129">Описание</span><span class="sxs-lookup"><span data-stu-id="d6fce-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d6fce-130">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="d6fce-130">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="d6fce-131">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="d6fce-131">Specifies a behavior element.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="d6fce-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="d6fce-132">Remarks</span></span>  
 <span data-ttu-id="d6fce-133">Если добавить этот элемент конфигурации в конфигурацию поведения конечной точки и присвоить атрибуту `enabled` значение `true`, то будет включена возможность обнаружения.</span><span class="sxs-lookup"><span data-stu-id="d6fce-133">When added to the endpoint’s behavior configuration and with the `enabled` attribute set to `true`, this configuration element enables its discoverability.</span></span> <span data-ttu-id="d6fce-134">Кроме того, можно использовать [ \<области >](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)дочерний элемент для указания пользовательских областей URI, который может использоваться для фильтрации конечных точек службы во время выполнения запроса, а также [ \<расширения >](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) дочерний элемент для указания пользовательских метаданных, которые требуется опубликовать вместе со стандартными обнаруживаемыми метаданными (EPR, ContractTypeName, BindingName, Scope и ListenURI).</span><span class="sxs-lookup"><span data-stu-id="d6fce-134">In addition, you can use the [\<scopes>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)child element to specifying custom scope Uris that can be used to filter service endpoints during query, as well as the [\<extensions>](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) child element to specify custom metadata that should be published along with the standard discoverable metadata (EPR, ContractTypeName, BindingName, Scope and ListenURI).</span></span>  
  
 <span data-ttu-id="d6fce-135">Этот элемент конфигурации зависит от [ \<serviceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) элемент, который управляет уровнем обслуживания для обнаружения.</span><span class="sxs-lookup"><span data-stu-id="d6fce-135">This configuration element is dependent on the [\<serviceDiscovery>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) element that provides the service level control of discoverability.</span></span> <span data-ttu-id="d6fce-136">Это означает, что параметры этого элемента пропускаются, если [ \<serviceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) не присутствует в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d6fce-136">This means that this element’s settings are ignored if [\<serviceDiscovery>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) is not present in the configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6fce-137">Пример</span><span class="sxs-lookup"><span data-stu-id="d6fce-137">Example</span></span>  
 <span data-ttu-id="d6fce-138">В следующем примере конфигурации определены области фильтрации и метаданные расширения, которые будут опубликованы для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="d6fce-138">The following configuration example specifies filtering scopes and extension metadata to be published for an endpoint.</span></span>  
  
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
          <add scope="http://contoso/test1" />
          <add scope="http://contoso/test2" />
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
  
## <a name="see-also"></a><span data-ttu-id="d6fce-139">См. также</span><span class="sxs-lookup"><span data-stu-id="d6fce-139">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
