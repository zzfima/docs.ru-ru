---
title: Элемент <endpoint>
ms.date: 03/30/2017
ms.assetid: 2fc8fedc-78d0-4e87-8142-fbfd26c15a4e
ms.openlocfilehash: fb9d3bf9b5f1a742abcc70d78af026c179ec4c4d
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855379"
---
# <a name="endpoint-element"></a><span data-ttu-id="bf677-102">\<Элемент > конечной точки</span><span class="sxs-lookup"><span data-stu-id="bf677-102">\<endpoint> element</span></span>
<span data-ttu-id="bf677-103">Задает свойства привязки, контракта и адреса для конечной точки службы, которая используется для предоставления доступа к службам.</span><span class="sxs-lookup"><span data-stu-id="bf677-103">Specifies binding, contract, and address properties for a service endpoint, which is used to expose services.</span></span>  
  
<span data-ttu-id="bf677-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="bf677-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="bf677-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="bf677-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="bf677-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<службы >** ](services.md)</span><span class="sxs-lookup"><span data-stu-id="bf677-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)</span></span>\
<span data-ttu-id="bf677-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> службы**](service.md)</span><span class="sxs-lookup"><span data-stu-id="bf677-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)</span></span>\
<span data-ttu-id="bf677-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> конечной точки**</span><span class="sxs-lookup"><span data-stu-id="bf677-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf677-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bf677-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bf677-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="bf677-110">Attributes and Elements</span></span>  
 <span data-ttu-id="bf677-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="bf677-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bf677-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bf677-112">Attributes</span></span>  
  
|<span data-ttu-id="bf677-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="bf677-113">Attribute</span></span>|<span data-ttu-id="bf677-114">Описание</span><span class="sxs-lookup"><span data-stu-id="bf677-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bf677-115">адрес</span><span class="sxs-lookup"><span data-stu-id="bf677-115">address</span></span>|<span data-ttu-id="bf677-116">Строка, содержащая адрес конечной точки.</span><span class="sxs-lookup"><span data-stu-id="bf677-116">A string that contains the address of the endpoint.</span></span> <span data-ttu-id="bf677-117">Адрес может быть указан как абсолютный или относительный адрес.</span><span class="sxs-lookup"><span data-stu-id="bf677-117">The address can be specified as an absolute or relative address.</span></span> <span data-ttu-id="bf677-118">Если указан относительный адрес, от соответствующего узла ожидается предоставление базового адреса, подходящего для схемы транспорта, используемой в привязке.</span><span class="sxs-lookup"><span data-stu-id="bf677-118">If a relative address is provided, the host is expected to provide a base address appropriate for the transport scheme used in the binding.</span></span> <span data-ttu-id="bf677-119">Если адрес не настроен, в качестве базового адреса используется адрес соответствующей конечной точки.</span><span class="sxs-lookup"><span data-stu-id="bf677-119">If an address is not configured, the base address is assumed to be the address for that endpoint.</span></span><br /><br /> <span data-ttu-id="bf677-120">Значение по умолчанию — пустая строка.</span><span class="sxs-lookup"><span data-stu-id="bf677-120">The default is an empty string.</span></span>|  
|<span data-ttu-id="bf677-121">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="bf677-121">behaviorConfiguration</span></span>|<span data-ttu-id="bf677-122">Строка, содержащая имя поведения для использования в конечной точке.</span><span class="sxs-lookup"><span data-stu-id="bf677-122">A string that contains the name of the behavior to be used in the endpoint.</span></span>|  
|<span data-ttu-id="bf677-123">привязка</span><span class="sxs-lookup"><span data-stu-id="bf677-123">binding</span></span>|<span data-ttu-id="bf677-124">Требуемый строковый атрибут, указывающий тип используемой привязки.</span><span class="sxs-lookup"><span data-stu-id="bf677-124">Required string attribute that specifies the type of binding to use.</span></span> <span data-ttu-id="bf677-125">Чтобы на тип можно было ссылаться, он должен иметь зарегистрированный раздел конфигурации.</span><span class="sxs-lookup"><span data-stu-id="bf677-125">The type must have a registered configuration section in order to be referenced.</span></span> <span data-ttu-id="bf677-126">Тип регистрируется по имени раздела, а не по имени типа привязки.</span><span class="sxs-lookup"><span data-stu-id="bf677-126">The type is the registered by section name, rather than by the type name of the binding.</span></span>|  
|<span data-ttu-id="bf677-127">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="bf677-127">bindingConfiguration</span></span>|<span data-ttu-id="bf677-128">Строка, указывающая имя привязки для использования при создании экземпляра конечной точки.</span><span class="sxs-lookup"><span data-stu-id="bf677-128">A string that specifies the binding name of the binding to use when the endpoint is instantiated.</span></span> <span data-ttu-id="bf677-129">Имя привязки должно входить в область в точке определения конечной точки.</span><span class="sxs-lookup"><span data-stu-id="bf677-129">The binding name must be in scope at the point the endpoint is defined.</span></span> <span data-ttu-id="bf677-130">Значение по умолчанию — пустая строка.</span><span class="sxs-lookup"><span data-stu-id="bf677-130">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="bf677-131">Этот атрибут используется вместе с атрибутом `binding` для ссылки на конкретную конфигурацию привязки в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="bf677-131">This attribute is used in conjunction with `binding` to reference a specific binding configuration in the configuration file.</span></span> <span data-ttu-id="bf677-132">Задайте этот атрибут, если выполняется попытка использовать пользовательскую привязку.</span><span class="sxs-lookup"><span data-stu-id="bf677-132">Set this attribute if you are attempting to use a custom binding.</span></span> <span data-ttu-id="bf677-133">В противном случае может быть создано исключение.</span><span class="sxs-lookup"><span data-stu-id="bf677-133">Otherwise, an exception may be thrown.</span></span>|  
|<span data-ttu-id="bf677-134">bindingName</span><span class="sxs-lookup"><span data-stu-id="bf677-134">bindingName</span></span>|<span data-ttu-id="bf677-135">Строка, указывающая уникальное полное имя привязки для экспорта определения посредством WSDL.</span><span class="sxs-lookup"><span data-stu-id="bf677-135">A string that specifies the unique qualified name of the binding for definition export through WSDL.</span></span> <span data-ttu-id="bf677-136">Значение по умолчанию — пустая строка.</span><span class="sxs-lookup"><span data-stu-id="bf677-136">The default is an empty string.</span></span>|  
|<span data-ttu-id="bf677-137">bindingNamespace</span><span class="sxs-lookup"><span data-stu-id="bf677-137">bindingNamespace</span></span>|<span data-ttu-id="bf677-138">Строка, указывающая уникальное полное имя пространства имен привязки для экспорта определения посредством WSDL.</span><span class="sxs-lookup"><span data-stu-id="bf677-138">A string that specifies the qualified name of the namespace of the binding for definition export through WSDL.</span></span> <span data-ttu-id="bf677-139">Значение по умолчанию — пустая строка.</span><span class="sxs-lookup"><span data-stu-id="bf677-139">The default is an empty string.</span></span>|  
|<span data-ttu-id="bf677-140">контракт</span><span class="sxs-lookup"><span data-stu-id="bf677-140">contract</span></span>|<span data-ttu-id="bf677-141">Строка, указывающая, к какому контракту предоставляется доступ этой конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="bf677-141">A string that indicates which contract this endpoint is exposing.</span></span> <span data-ttu-id="bf677-142">В сборке должен быть реализован данный тип контракта.</span><span class="sxs-lookup"><span data-stu-id="bf677-142">The assembly must implement the contract type.</span></span> <span data-ttu-id="bf677-143">Если реализация службы реализует один тип контракта, это свойство может быть опущено.</span><span class="sxs-lookup"><span data-stu-id="bf677-143">If a service implementation implements a single contract type, then this property can be omitted.</span></span> <span data-ttu-id="bf677-144">Значение по умолчанию — пустая строка.</span><span class="sxs-lookup"><span data-stu-id="bf677-144">The default is an empty string.</span></span>|  
|<span data-ttu-id="bf677-145">endpointConfiguration</span><span class="sxs-lookup"><span data-stu-id="bf677-145">endpointConfiguration</span></span>|<span data-ttu-id="bf677-146">Строка, указывающая имя стандартной конечной точки, задаваемой атрибутом `kind`, который ссылается на дополнительные сведения конфигурации этой конечной точки.</span><span class="sxs-lookup"><span data-stu-id="bf677-146">A string that specifies the name of the standard endpoint that is set by the `kind` attribute, which references to the additional configuration information of this standard endpoint.</span></span> <span data-ttu-id="bf677-147">Такое же имя должно быть задано в разделе `<standardEndpoints>`.</span><span class="sxs-lookup"><span data-stu-id="bf677-147">The same name must be defined in the `<standardEndpoints>` section.</span></span>|  
|<span data-ttu-id="bf677-148">isSystemEndpoint</span><span class="sxs-lookup"><span data-stu-id="bf677-148">isSystemEndpoint</span></span>|<span data-ttu-id="bf677-149">Логическое значение, указывающее, является ли конечная точка конечной точкой инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="bf677-149">A Boolean value that specifies whether an endpoint is an infrastructure endpoint.</span></span>|  
|<span data-ttu-id="bf677-150">kind</span><span class="sxs-lookup"><span data-stu-id="bf677-150">kind</span></span>|<span data-ttu-id="bf677-151">Строка, указывающая тип применяемой стандартной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="bf677-151">A string that specifies the type of standard endpoint applied.</span></span> <span data-ttu-id="bf677-152">Этот тип должен быть зарегистрирован в разделе `<extensions>` или в файле machine.config. Если ничего не указано, будет создана обычная конечная точка службы.</span><span class="sxs-lookup"><span data-stu-id="bf677-152">The type must be registered in the `<extensions>` section or in machine.config. If nothing is specified, a common service endpoint is created.</span></span>|  
|<span data-ttu-id="bf677-153">listenUriMode</span><span class="sxs-lookup"><span data-stu-id="bf677-153">listenUriMode</span></span>|<span data-ttu-id="bf677-154">Указывает способ обработки транспортом значения `ListenUri`, предоставленного для ожидания передачи данных службой.</span><span class="sxs-lookup"><span data-stu-id="bf677-154">Specifies how the transport treats the `ListenUri` provided for the service to listen on.</span></span> <span data-ttu-id="bf677-155">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="bf677-155">Valid values are</span></span><br /><br /> <span data-ttu-id="bf677-156">-Explicit</span><span class="sxs-lookup"><span data-stu-id="bf677-156">-   Explicit</span></span><br /><span data-ttu-id="bf677-157">— Уникальный</span><span class="sxs-lookup"><span data-stu-id="bf677-157">-   Unique</span></span><br /><br /> <span data-ttu-id="bf677-158">Значение по умолчанию - Explicit.</span><span class="sxs-lookup"><span data-stu-id="bf677-158">The default value is Explicit.</span></span>|  
|<span data-ttu-id="bf677-159">listenUri</span><span class="sxs-lookup"><span data-stu-id="bf677-159">listenUri</span></span>|<span data-ttu-id="bf677-160">Строка, указывающая URI, по которому конечная точка службы ожидает передачи данных.</span><span class="sxs-lookup"><span data-stu-id="bf677-160">A string that specifies the URI at which the service endpoint listens.</span></span> <span data-ttu-id="bf677-161">Значение по умолчанию — пустая строка.</span><span class="sxs-lookup"><span data-stu-id="bf677-161">The default is an empty string.</span></span>|  
|<span data-ttu-id="bf677-162">имя</span><span class="sxs-lookup"><span data-stu-id="bf677-162">name</span></span>|<span data-ttu-id="bf677-163">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="bf677-163">Optional attribute.</span></span> <span data-ttu-id="bf677-164">Строка, указывающая имя конечной точки службы.</span><span class="sxs-lookup"><span data-stu-id="bf677-164">A string that specifies the name the service endpoint.</span></span> <span data-ttu-id="bf677-165">По умолчанию используется объединение имени привязки и имя описания контракта.</span><span class="sxs-lookup"><span data-stu-id="bf677-165">The default value is the concatenation of the binding name and the contract description name.</span></span> <span data-ttu-id="bf677-166">Службы могут иметь несколько конечных точек, поэтому атрибут конечной точки `name` отличается от имени службы.</span><span class="sxs-lookup"><span data-stu-id="bf677-166">Services may have multiple endpoints, so the endpoint’s `name` attribute is distinct from the name of the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bf677-167">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bf677-167">Child Elements</span></span>  
  
|<span data-ttu-id="bf677-168">Элемент</span><span class="sxs-lookup"><span data-stu-id="bf677-168">Element</span></span>|<span data-ttu-id="bf677-169">Описание</span><span class="sxs-lookup"><span data-stu-id="bf677-169">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bf677-170">\<заголовки ></span><span class="sxs-lookup"><span data-stu-id="bf677-170">\<headers></span></span>](headers.md)|<span data-ttu-id="bf677-171">Коллекция заголовков адреса.</span><span class="sxs-lookup"><span data-stu-id="bf677-171">A collection of address headers.</span></span>|  
|[<span data-ttu-id="bf677-172">\<> удостоверений</span><span class="sxs-lookup"><span data-stu-id="bf677-172">\<identity></span></span>](identity.md)|<span data-ttu-id="bf677-173">Удостоверение, обеспечивающее проверку подлинности конечной точки другими конечными точками, которые обмениваются с ней сообщениями.</span><span class="sxs-lookup"><span data-stu-id="bf677-173">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bf677-174">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bf677-174">Parent Elements</span></span>  
  
|<span data-ttu-id="bf677-175">Элемент</span><span class="sxs-lookup"><span data-stu-id="bf677-175">Element</span></span>|<span data-ttu-id="bf677-176">Описание</span><span class="sxs-lookup"><span data-stu-id="bf677-176">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bf677-177">\<> службы</span><span class="sxs-lookup"><span data-stu-id="bf677-177">\<service></span></span>](service.md)|<span data-ttu-id="bf677-178">Раздел конфигурации, определяющий список конечных точек, к которым может подключаться клиент.</span><span class="sxs-lookup"><span data-stu-id="bf677-178">A configuration section that defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="bf677-179">Пример</span><span class="sxs-lookup"><span data-stu-id="bf677-179">Example</span></span>  
 <span data-ttu-id="bf677-180">Ниже приведен пример конфигурации конечной точки службы.</span><span class="sxs-lookup"><span data-stu-id="bf677-180">This is an example of a service endpoint configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bf677-181">См. также</span><span class="sxs-lookup"><span data-stu-id="bf677-181">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceEndpointElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.Description.ServiceEndpoint>
- [<span data-ttu-id="bf677-182">Конеч Адреса, привязки и контракты</span><span class="sxs-lookup"><span data-stu-id="bf677-182">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
- [<span data-ttu-id="bf677-183">Практическое руководство. Создание конечной точки службы в конфигурации</span><span class="sxs-lookup"><span data-stu-id="bf677-183">How to: Create a Service Endpoint in Configuration</span></span>](../../../wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)
