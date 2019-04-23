---
title: <endpoint> из <client>
ms.date: 03/30/2017
ms.assetid: de6238ae-bbf8-48e9-a1b5-e24c0bea8afa
ms.openlocfilehash: 3af41ad5b5681b08aac44d984372ab5ac66caf5e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59231205"
---
# <a name="endpoint-of-client"></a><span data-ttu-id="face3-102">\<Конечная точка > из \<клиента ></span><span class="sxs-lookup"><span data-stu-id="face3-102">\<endpoint> of \<client></span></span>
<span data-ttu-id="face3-103">Задает свойства контракта, привязки и адреса конечной точки канала, которая используется клиентами для подключения к конечным точкам службы на сервере.</span><span class="sxs-lookup"><span data-stu-id="face3-103">Specifies contract, binding, and address properties of the channel endpoint, which is used by clients to connect to service endpoints on the server.</span></span>  
  
 <span data-ttu-id="face3-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="face3-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="face3-105">\<Клиент ></span><span class="sxs-lookup"><span data-stu-id="face3-105">\<client></span></span>  
<span data-ttu-id="face3-106">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="face3-106">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="face3-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="face3-107">Syntax</span></span>  
  
```xml  
<endpoint address="String"
          behaviorConfiguration="String"
          binding="String"
          bindingConfiguration="String"
          contract="String"
          endpointConfiguration="String"
          kind="String"
          name="String">
</endpoint>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="face3-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="face3-108">Attributes and Elements</span></span>  
 <span data-ttu-id="face3-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="face3-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="face3-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="face3-110">Attributes</span></span>  
  
|<span data-ttu-id="face3-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="face3-111">Attribute</span></span>|<span data-ttu-id="face3-112">Описание</span><span class="sxs-lookup"><span data-stu-id="face3-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="face3-113">адрес</span><span class="sxs-lookup"><span data-stu-id="face3-113">address</span></span>|<span data-ttu-id="face3-114">Обязательный строковый атрибут.</span><span class="sxs-lookup"><span data-stu-id="face3-114">Required string attribute.</span></span><br /><br /> <span data-ttu-id="face3-115">Задает адрес конечной точки.</span><span class="sxs-lookup"><span data-stu-id="face3-115">Specifies the address of the endpoint.</span></span> <span data-ttu-id="face3-116">Значение по умолчанию - пустая строка.</span><span class="sxs-lookup"><span data-stu-id="face3-116">The default is an empty string.</span></span> <span data-ttu-id="face3-117">Адрес должен быть абсолютным универсальным кодом ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="face3-117">The address must be an absolute URI.</span></span>|  
|<span data-ttu-id="face3-118">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="face3-118">behaviorConfiguration</span></span>|<span data-ttu-id="face3-119">Строка, содержащая имя поведения, используемое для создания экземпляра конечной точки.</span><span class="sxs-lookup"><span data-stu-id="face3-119">A string that contains the behavior name of the behavior to be used to instantiate the endpoint.</span></span> <span data-ttu-id="face3-120">Имя поведения должно входить в область действия в точке определения службы.</span><span class="sxs-lookup"><span data-stu-id="face3-120">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="face3-121">Значение по умолчанию - пустая строка.</span><span class="sxs-lookup"><span data-stu-id="face3-121">The default is an empty string.</span></span>|  
|<span data-ttu-id="face3-122">привязка</span><span class="sxs-lookup"><span data-stu-id="face3-122">binding</span></span>|<span data-ttu-id="face3-123">Обязательный строковый атрибут.</span><span class="sxs-lookup"><span data-stu-id="face3-123">Required string attribute.</span></span><br /><br /> <span data-ttu-id="face3-124">Строка, указывающая тип привязки для использования.</span><span class="sxs-lookup"><span data-stu-id="face3-124">A string that indicates the type of binding to use.</span></span> <span data-ttu-id="face3-125">Чтобы на тип можно было ссылаться, он должен иметь зарегистрированный раздел конфигурации.</span><span class="sxs-lookup"><span data-stu-id="face3-125">The type must have a registered configuration section in order to be referenced.</span></span> <span data-ttu-id="face3-126">Тип регистрируется по имени раздела, а не по имени типа привязки.</span><span class="sxs-lookup"><span data-stu-id="face3-126">The type is registered by section name, instead of by the type name of the binding.</span></span>|  
|<span data-ttu-id="face3-127">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="face3-127">bindingConfiguration</span></span>|<span data-ttu-id="face3-128">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="face3-128">Optional.</span></span> <span data-ttu-id="face3-129">Строка, содержащая имя конфигурации привязки для использования при создании экземпляра конечной точки.</span><span class="sxs-lookup"><span data-stu-id="face3-129">A string that contains the name of the binding configuration to be used when the endpoint is instantiated.</span></span> <span data-ttu-id="face3-130">Конфигурация привязки должна входить в область действия в точке определения конечной точки.</span><span class="sxs-lookup"><span data-stu-id="face3-130">The binding configuration must be in scope at the point the endpoint is defined.</span></span> <span data-ttu-id="face3-131">Значение по умолчанию - пустая строка.</span><span class="sxs-lookup"><span data-stu-id="face3-131">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="face3-132">Этот атрибут используется вместе с атрибутом `binding` для ссылки на конкретную конфигурацию привязки в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="face3-132">This attribute is used in conjunction with `binding` to reference a specific binding configuration in the configuration file.</span></span> <span data-ttu-id="face3-133">Задайте этот атрибут, если выполняется попытка использовать пользовательскую привязку.</span><span class="sxs-lookup"><span data-stu-id="face3-133">Set this attribute if you are attempting to use a custom binding.</span></span> <span data-ttu-id="face3-134">В противном случае может быть создано исключение.</span><span class="sxs-lookup"><span data-stu-id="face3-134">Otherwise, an exception may be thrown.</span></span>|  
|<span data-ttu-id="face3-135">контракт</span><span class="sxs-lookup"><span data-stu-id="face3-135">contract</span></span>|<span data-ttu-id="face3-136">Обязательный строковый атрибут.</span><span class="sxs-lookup"><span data-stu-id="face3-136">Required string attribute.</span></span><br /><br /> <span data-ttu-id="face3-137">Строка, указывающая, к какому контракту предоставляется доступ этой конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="face3-137">A string that indicates which contract this endpoint is exposing.</span></span> <span data-ttu-id="face3-138">В сборке должен быть реализован данный тип контракта.</span><span class="sxs-lookup"><span data-stu-id="face3-138">The assembly must implement the contract type.</span></span>|  
|<span data-ttu-id="face3-139">endpointConfiguration</span><span class="sxs-lookup"><span data-stu-id="face3-139">endpointConfiguration</span></span>|<span data-ttu-id="face3-140">Строка, указывающая имя стандартной конечной точки, задаваемой атрибутом `kind`, который ссылается на дополнительные сведения конфигурации этой конечной точки.</span><span class="sxs-lookup"><span data-stu-id="face3-140">A string that specifies the name of the standard endpoint that is set by the `kind` attribute, which references to the additional configuration information of this standard endpoint.</span></span> <span data-ttu-id="face3-141">Такое же имя должно быть задано в разделе `<standardEndpoints>`.</span><span class="sxs-lookup"><span data-stu-id="face3-141">The same name must be defined in the `<standardEndpoints>` section.</span></span>|  
|<span data-ttu-id="face3-142">kind</span><span class="sxs-lookup"><span data-stu-id="face3-142">kind</span></span>|<span data-ttu-id="face3-143">Строка, указывающая тип применяемой стандартной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="face3-143">A string that specifies the type of standard endpoint applied.</span></span> <span data-ttu-id="face3-144">Этот тип должен быть зарегистрирован в разделе `<extensions>` или в файле machine.config. Если ничего не указано, будет создана обычная конечная точка канала.</span><span class="sxs-lookup"><span data-stu-id="face3-144">The type must be registered in the `<extensions>` section or in machine.config. If nothing is specified, a common channel endpoint is created.</span></span>|  
|<span data-ttu-id="face3-145">имя</span><span class="sxs-lookup"><span data-stu-id="face3-145">name</span></span>|<span data-ttu-id="face3-146">Необязательный строковый атрибут.</span><span class="sxs-lookup"><span data-stu-id="face3-146">Optional string attribute.</span></span> <span data-ttu-id="face3-147">Этот атрибут уникальным образом идентифицирует конечную точку для данного контракта.</span><span class="sxs-lookup"><span data-stu-id="face3-147">This attribute uniquely identifies an endpoint for a given contract.</span></span> <span data-ttu-id="face3-148">Для данного типа контракта можно определить несколько клиентов.</span><span class="sxs-lookup"><span data-stu-id="face3-148">You can define multiple clients for a given Contract type.</span></span> <span data-ttu-id="face3-149">Определения должны отличаться друг от друга уникальным именем конфигурации.</span><span class="sxs-lookup"><span data-stu-id="face3-149">Each definition must be differentiated by a unique configuration name.</span></span> <span data-ttu-id="face3-150">Если этот атрибут опущен, соответствующая конечная точка используется как конечная точка по умолчанию, связанная с заданным типом контракта.</span><span class="sxs-lookup"><span data-stu-id="face3-150">If this attribute is omitted, the corresponding endpoint is used as the default endpoint associated with the specified Contract type.</span></span> <span data-ttu-id="face3-151">Значение по умолчанию - пустая строка.</span><span class="sxs-lookup"><span data-stu-id="face3-151">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="face3-152">Атрибут `name` привязки используется для экспорта определения посредством языка WSDL.</span><span class="sxs-lookup"><span data-stu-id="face3-152">The `name` attribute of a binding is used for definition export through WSDL.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="face3-153">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="face3-153">Child Elements</span></span>  
  
|<span data-ttu-id="face3-154">Элемент</span><span class="sxs-lookup"><span data-stu-id="face3-154">Element</span></span>|<span data-ttu-id="face3-155">Описание</span><span class="sxs-lookup"><span data-stu-id="face3-155">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="face3-156">\<заголовки ></span><span class="sxs-lookup"><span data-stu-id="face3-156">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)|<span data-ttu-id="face3-157">Коллекция заголовков адреса.</span><span class="sxs-lookup"><span data-stu-id="face3-157">A collection of address headers.</span></span>|  
|[<span data-ttu-id="face3-158">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="face3-158">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="face3-159">Удостоверение, обеспечивающее проверку подлинности конечной точки другими конечными точками, которые обмениваются с ней сообщениями.</span><span class="sxs-lookup"><span data-stu-id="face3-159">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="face3-160">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="face3-160">Parent Elements</span></span>  
  
|<span data-ttu-id="face3-161">Элемент</span><span class="sxs-lookup"><span data-stu-id="face3-161">Element</span></span>|<span data-ttu-id="face3-162">Описание</span><span class="sxs-lookup"><span data-stu-id="face3-162">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="face3-163">\<Клиент ></span><span class="sxs-lookup"><span data-stu-id="face3-163">\<client></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/client.md)|<span data-ttu-id="face3-164">Раздел конфигурации, определяющий список конечных точек, к которым может подключаться клиент.</span><span class="sxs-lookup"><span data-stu-id="face3-164">A configuration section that defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="face3-165">Пример</span><span class="sxs-lookup"><span data-stu-id="face3-165">Example</span></span>  
 <span data-ttu-id="face3-166">Далее приведен пример конфигурации конечной точки канала.</span><span class="sxs-lookup"><span data-stu-id="face3-166">This is an example of a channel endpoint configuration.</span></span>  
  
```xml  
<endpoint address="/HelloWorld/"
          bindingConfiguration="usingDefaults"
          name="MyBinding"
          binding="customBinding"
          contract="HelloWorld">
</endpoint>
```  
  
## <a name="see-also"></a><span data-ttu-id="face3-167">См. также</span><span class="sxs-lookup"><span data-stu-id="face3-167">See also</span></span>

- <xref:System.ServiceModel.Configuration.ChannelEndpointElement>
- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.ChannelEndpointElementCollection>
- <xref:System.ServiceModel.Configuration.ClientSection.Endpoints%2A>
- <xref:System.ServiceModel.Configuration.ChannelEndpointElement>
- [<span data-ttu-id="face3-168">Конфигурация клиента WCF</span><span class="sxs-lookup"><span data-stu-id="face3-168">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="face3-169">Клиенты</span><span class="sxs-lookup"><span data-stu-id="face3-169">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
