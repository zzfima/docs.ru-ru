---
title: <endpoint> элемент
ms.date: 03/30/2017
ms.assetid: 2fc8fedc-78d0-4e87-8142-fbfd26c15a4e
ms.openlocfilehash: 667086cda010daf51cb92116d636b9b526b4b34b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59163414"
---
# <a name="endpoint-element"></a><span data-ttu-id="bce0a-102">\<Конечная точка > элемент</span><span class="sxs-lookup"><span data-stu-id="bce0a-102">\<endpoint> element</span></span>
<span data-ttu-id="bce0a-103">Задает свойства привязки, контракта и адреса для конечной точки службы, которая используется для предоставления доступа к службам.</span><span class="sxs-lookup"><span data-stu-id="bce0a-103">Specifies binding, contract, and address properties for a service endpoint, which is used to expose services.</span></span>  
  
 <span data-ttu-id="bce0a-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="bce0a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="bce0a-105">\<службы ></span><span class="sxs-lookup"><span data-stu-id="bce0a-105">\<service></span></span>  
<span data-ttu-id="bce0a-106">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="bce0a-106">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bce0a-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bce0a-107">Syntax</span></span>  
  
```xml  
<endpoint address="String"
          behaviorConfiguration="String"
          binding="String"
          bindingConfiguration="String"
          bindingName="String"
          bindingNamespace="String"
          contract="String"
          endpointConfiguration="String"
          isSystemEndpoint="Boolean"
          kind="String"
          listenUriMode="Explicit/Unique"
          listenUri="Uri">
</endpoint>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bce0a-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="bce0a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="bce0a-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="bce0a-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bce0a-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bce0a-110">Attributes</span></span>  
  
|<span data-ttu-id="bce0a-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="bce0a-111">Attribute</span></span>|<span data-ttu-id="bce0a-112">Описание</span><span class="sxs-lookup"><span data-stu-id="bce0a-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bce0a-113">адрес</span><span class="sxs-lookup"><span data-stu-id="bce0a-113">address</span></span>|<span data-ttu-id="bce0a-114">Строка, содержащая адрес конечной точки.</span><span class="sxs-lookup"><span data-stu-id="bce0a-114">A string that contains the address of the endpoint.</span></span> <span data-ttu-id="bce0a-115">Адрес может быть указан как абсолютный или относительный адрес.</span><span class="sxs-lookup"><span data-stu-id="bce0a-115">The address can be specified as an absolute or relative address.</span></span> <span data-ttu-id="bce0a-116">Если указан относительный адрес, от соответствующего узла ожидается предоставление базового адреса, подходящего для схемы транспорта, используемой в привязке.</span><span class="sxs-lookup"><span data-stu-id="bce0a-116">If a relative address is provided, the host is expected to provide a base address appropriate for the transport scheme used in the binding.</span></span> <span data-ttu-id="bce0a-117">Если адрес не настроен, в качестве базового адреса используется адрес соответствующей конечной точки.</span><span class="sxs-lookup"><span data-stu-id="bce0a-117">If an address is not configured, the base address is assumed to be the address for that endpoint.</span></span><br /><br /> <span data-ttu-id="bce0a-118">Значение по умолчанию - пустая строка.</span><span class="sxs-lookup"><span data-stu-id="bce0a-118">The default is an empty string.</span></span>|  
|<span data-ttu-id="bce0a-119">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="bce0a-119">behaviorConfiguration</span></span>|<span data-ttu-id="bce0a-120">Строка, содержащая имя поведения для использования в конечной точке.</span><span class="sxs-lookup"><span data-stu-id="bce0a-120">A string that contains the name of the behavior to be used in the endpoint.</span></span>|  
|<span data-ttu-id="bce0a-121">привязка</span><span class="sxs-lookup"><span data-stu-id="bce0a-121">binding</span></span>|<span data-ttu-id="bce0a-122">Требуемый строковый атрибут, указывающий тип используемой привязки.</span><span class="sxs-lookup"><span data-stu-id="bce0a-122">Required string attribute that specifies the type of binding to use.</span></span> <span data-ttu-id="bce0a-123">Чтобы на тип можно было ссылаться, он должен иметь зарегистрированный раздел конфигурации.</span><span class="sxs-lookup"><span data-stu-id="bce0a-123">The type must have a registered configuration section in order to be referenced.</span></span> <span data-ttu-id="bce0a-124">Тип регистрируется по имени раздела, а не по имени типа привязки.</span><span class="sxs-lookup"><span data-stu-id="bce0a-124">The type is the registered by section name, rather than by the type name of the binding.</span></span>|  
|<span data-ttu-id="bce0a-125">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="bce0a-125">bindingConfiguration</span></span>|<span data-ttu-id="bce0a-126">Строка, указывающая имя привязки для использования при создании экземпляра конечной точки.</span><span class="sxs-lookup"><span data-stu-id="bce0a-126">A string that specifies the binding name of the binding to use when the endpoint is instantiated.</span></span> <span data-ttu-id="bce0a-127">Имя привязки должно входить в область в точке определения конечной точки.</span><span class="sxs-lookup"><span data-stu-id="bce0a-127">The binding name must be in scope at the point the endpoint is defined.</span></span> <span data-ttu-id="bce0a-128">Значение по умолчанию - пустая строка.</span><span class="sxs-lookup"><span data-stu-id="bce0a-128">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="bce0a-129">Этот атрибут используется вместе с атрибутом `binding` для ссылки на конкретную конфигурацию привязки в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="bce0a-129">This attribute is used in conjunction with `binding` to reference a specific binding configuration in the configuration file.</span></span> <span data-ttu-id="bce0a-130">Задайте этот атрибут, если выполняется попытка использовать пользовательскую привязку.</span><span class="sxs-lookup"><span data-stu-id="bce0a-130">Set this attribute if you are attempting to use a custom binding.</span></span> <span data-ttu-id="bce0a-131">В противном случае может быть создано исключение.</span><span class="sxs-lookup"><span data-stu-id="bce0a-131">Otherwise, an exception may be thrown.</span></span>|  
|<span data-ttu-id="bce0a-132">bindingName</span><span class="sxs-lookup"><span data-stu-id="bce0a-132">bindingName</span></span>|<span data-ttu-id="bce0a-133">Строка, указывающая уникальное полное имя привязки для экспорта определения посредством WSDL.</span><span class="sxs-lookup"><span data-stu-id="bce0a-133">A string that specifies the unique qualified name of the binding for definition export through WSDL.</span></span> <span data-ttu-id="bce0a-134">Значение по умолчанию - пустая строка.</span><span class="sxs-lookup"><span data-stu-id="bce0a-134">The default is an empty string.</span></span>|  
|<span data-ttu-id="bce0a-135">bindingNamespace</span><span class="sxs-lookup"><span data-stu-id="bce0a-135">bindingNamespace</span></span>|<span data-ttu-id="bce0a-136">Строка, указывающая уникальное полное имя пространства имен привязки для экспорта определения посредством WSDL.</span><span class="sxs-lookup"><span data-stu-id="bce0a-136">A string that specifies the qualified name of the namespace of the binding for definition export through WSDL.</span></span> <span data-ttu-id="bce0a-137">Значение по умолчанию - пустая строка.</span><span class="sxs-lookup"><span data-stu-id="bce0a-137">The default is an empty string.</span></span>|  
|<span data-ttu-id="bce0a-138">контракт</span><span class="sxs-lookup"><span data-stu-id="bce0a-138">contract</span></span>|<span data-ttu-id="bce0a-139">Строка, указывающая, к какому контракту предоставляется доступ этой конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="bce0a-139">A string that indicates which contract this endpoint is exposing.</span></span> <span data-ttu-id="bce0a-140">В сборке должен быть реализован данный тип контракта.</span><span class="sxs-lookup"><span data-stu-id="bce0a-140">The assembly must implement the contract type.</span></span> <span data-ttu-id="bce0a-141">Если реализация службы реализует один тип контракта, это свойство может быть опущено.</span><span class="sxs-lookup"><span data-stu-id="bce0a-141">If a service implementation implements a single contract type, then this property can be omitted.</span></span> <span data-ttu-id="bce0a-142">Значение по умолчанию - пустая строка.</span><span class="sxs-lookup"><span data-stu-id="bce0a-142">The default is an empty string.</span></span>|  
|<span data-ttu-id="bce0a-143">endpointConfiguration</span><span class="sxs-lookup"><span data-stu-id="bce0a-143">endpointConfiguration</span></span>|<span data-ttu-id="bce0a-144">Строка, указывающая имя стандартной конечной точки, задаваемой атрибутом `kind`, который ссылается на дополнительные сведения конфигурации этой конечной точки.</span><span class="sxs-lookup"><span data-stu-id="bce0a-144">A string that specifies the name of the standard endpoint that is set by the `kind` attribute, which references to the additional configuration information of this standard endpoint.</span></span> <span data-ttu-id="bce0a-145">Такое же имя должно быть задано в разделе `<standardEndpoints>`.</span><span class="sxs-lookup"><span data-stu-id="bce0a-145">The same name must be defined in the `<standardEndpoints>` section.</span></span>|  
|<span data-ttu-id="bce0a-146">isSystemEndpoint</span><span class="sxs-lookup"><span data-stu-id="bce0a-146">isSystemEndpoint</span></span>|<span data-ttu-id="bce0a-147">Логическое значение, указывающее, является ли конечная точка конечной точкой инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="bce0a-147">A Boolean value that specifies whether an endpoint is an infrastructure endpoint.</span></span>|  
|<span data-ttu-id="bce0a-148">kind</span><span class="sxs-lookup"><span data-stu-id="bce0a-148">kind</span></span>|<span data-ttu-id="bce0a-149">Строка, указывающая тип применяемой стандартной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="bce0a-149">A string that specifies the type of standard endpoint applied.</span></span> <span data-ttu-id="bce0a-150">Этот тип должен быть зарегистрирован в разделе `<extensions>` или в файле machine.config. Если ничего не указано, будет создана обычная конечная точка службы.</span><span class="sxs-lookup"><span data-stu-id="bce0a-150">The type must be registered in the `<extensions>` section or in machine.config. If nothing is specified, a common service endpoint is created.</span></span>|  
|<span data-ttu-id="bce0a-151">listenUriMode</span><span class="sxs-lookup"><span data-stu-id="bce0a-151">listenUriMode</span></span>|<span data-ttu-id="bce0a-152">Указывает способ обработки транспортом значения `ListenUri`, предоставленного для ожидания передачи данных службой.</span><span class="sxs-lookup"><span data-stu-id="bce0a-152">Specifies how the transport treats the `ListenUri` provided for the service to listen on.</span></span> <span data-ttu-id="bce0a-153">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="bce0a-153">Valid values are</span></span><br /><br /> <span data-ttu-id="bce0a-154">-Явные</span><span class="sxs-lookup"><span data-stu-id="bce0a-154">-   Explicit</span></span><br /><span data-ttu-id="bce0a-155">-Unique</span><span class="sxs-lookup"><span data-stu-id="bce0a-155">-   Unique</span></span><br /><br /> <span data-ttu-id="bce0a-156">Значение по умолчанию - Explicit.</span><span class="sxs-lookup"><span data-stu-id="bce0a-156">The default value is Explicit.</span></span>|  
|<span data-ttu-id="bce0a-157">listenUri</span><span class="sxs-lookup"><span data-stu-id="bce0a-157">listenUri</span></span>|<span data-ttu-id="bce0a-158">Строка, указывающая URI, по которому конечная точка службы ожидает передачи данных.</span><span class="sxs-lookup"><span data-stu-id="bce0a-158">A string that specifies the URI at which the service endpoint listens.</span></span> <span data-ttu-id="bce0a-159">Значение по умолчанию - пустая строка.</span><span class="sxs-lookup"><span data-stu-id="bce0a-159">The default is an empty string.</span></span>|  
|<span data-ttu-id="bce0a-160">имя</span><span class="sxs-lookup"><span data-stu-id="bce0a-160">name</span></span>|<span data-ttu-id="bce0a-161">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="bce0a-161">Optional attribute.</span></span> <span data-ttu-id="bce0a-162">Строка, указывающая имя конечной точки службы.</span><span class="sxs-lookup"><span data-stu-id="bce0a-162">A string that specifies the name the service endpoint.</span></span> <span data-ttu-id="bce0a-163">По умолчанию используется объединение имени привязки и имя описания контракта.</span><span class="sxs-lookup"><span data-stu-id="bce0a-163">The default value is the concatenation of the binding name and the contract description name.</span></span> <span data-ttu-id="bce0a-164">Службы могут иметь несколько конечных точек, поэтому атрибут конечной точки `name` отличается от имени службы.</span><span class="sxs-lookup"><span data-stu-id="bce0a-164">Services may have multiple endpoints, so the endpoint’s `name` attribute is distinct from the name of the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bce0a-165">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bce0a-165">Child Elements</span></span>  
  
|<span data-ttu-id="bce0a-166">Элемент</span><span class="sxs-lookup"><span data-stu-id="bce0a-166">Element</span></span>|<span data-ttu-id="bce0a-167">Описание</span><span class="sxs-lookup"><span data-stu-id="bce0a-167">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bce0a-168">\<headers></span><span class="sxs-lookup"><span data-stu-id="bce0a-168">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)|<span data-ttu-id="bce0a-169">Коллекция заголовков адреса.</span><span class="sxs-lookup"><span data-stu-id="bce0a-169">A collection of address headers.</span></span>|  
|[<span data-ttu-id="bce0a-170">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="bce0a-170">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="bce0a-171">Удостоверение, обеспечивающее проверку подлинности конечной точки другими конечными точками, которые обмениваются с ней сообщениями.</span><span class="sxs-lookup"><span data-stu-id="bce0a-171">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bce0a-172">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bce0a-172">Parent Elements</span></span>  
  
|<span data-ttu-id="bce0a-173">Элемент</span><span class="sxs-lookup"><span data-stu-id="bce0a-173">Element</span></span>|<span data-ttu-id="bce0a-174">Описание</span><span class="sxs-lookup"><span data-stu-id="bce0a-174">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bce0a-175">\<службы ></span><span class="sxs-lookup"><span data-stu-id="bce0a-175">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="bce0a-176">Раздел конфигурации, определяющий список конечных точек, к которым может подключаться клиент.</span><span class="sxs-lookup"><span data-stu-id="bce0a-176">A configuration section that defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="bce0a-177">Пример</span><span class="sxs-lookup"><span data-stu-id="bce0a-177">Example</span></span>  
 <span data-ttu-id="bce0a-178">Ниже приведен пример конфигурации конечной точки службы.</span><span class="sxs-lookup"><span data-stu-id="bce0a-178">This is an example of a service endpoint configuration.</span></span>  
  
```xml  
<endpoint address="/HelloWorld/"
          bindingConfiguration="usingDefaults"
          bindingName="MyBinding"
          binding="customBinding"
          contract="HelloWorld">
  <headers>
    <region xmlns="http://tempuri.org/">EastCoast</region>
    <member xmlns="http://tempuri.org/">Gold</member>
  </headers>
</endpoint>
```  
  
## <a name="see-also"></a><span data-ttu-id="bce0a-179">См. также</span><span class="sxs-lookup"><span data-stu-id="bce0a-179">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceEndpointElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.Description.ServiceEndpoint>
- [<span data-ttu-id="bce0a-180">Конечные точки: адреса, привязки и контракты</span><span class="sxs-lookup"><span data-stu-id="bce0a-180">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
- [<span data-ttu-id="bce0a-181">Практическое руководство. Создание конечной точки службы в конфигурации</span><span class="sxs-lookup"><span data-stu-id="bce0a-181">How to: Create a Service Endpoint in Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)
