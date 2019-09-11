---
title: <endpoint> из <client>
ms.date: 03/30/2017
ms.assetid: de6238ae-bbf8-48e9-a1b5-e24c0bea8afa
ms.openlocfilehash: f1ffbc1e8efac70523d7f631c8cf9ba9a1622bfc
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855320"
---
# <a name="endpoint-of-client"></a><span data-ttu-id="46808-102">\<Конечная точка \<> клиента ></span><span class="sxs-lookup"><span data-stu-id="46808-102">\<endpoint> of \<client></span></span>
<span data-ttu-id="46808-103">Задает свойства контракта, привязки и адреса конечной точки канала, которая используется клиентами для подключения к конечным точкам службы на сервере.</span><span class="sxs-lookup"><span data-stu-id="46808-103">Specifies contract, binding, and address properties of the channel endpoint, which is used by clients to connect to service endpoints on the server.</span></span>  
  
<span data-ttu-id="46808-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="46808-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="46808-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="46808-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="46808-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> клиента**](client.md)</span><span class="sxs-lookup"><span data-stu-id="46808-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="46808-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> конечной точки**</span><span class="sxs-lookup"><span data-stu-id="46808-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46808-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="46808-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="46808-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="46808-109">Attributes and Elements</span></span>  
 <span data-ttu-id="46808-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="46808-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="46808-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="46808-111">Attributes</span></span>  
  
|<span data-ttu-id="46808-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="46808-112">Attribute</span></span>|<span data-ttu-id="46808-113">Описание</span><span class="sxs-lookup"><span data-stu-id="46808-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="46808-114">адрес</span><span class="sxs-lookup"><span data-stu-id="46808-114">address</span></span>|<span data-ttu-id="46808-115">Обязательный строковый атрибут.</span><span class="sxs-lookup"><span data-stu-id="46808-115">Required string attribute.</span></span><br /><br /> <span data-ttu-id="46808-116">Задает адрес конечной точки.</span><span class="sxs-lookup"><span data-stu-id="46808-116">Specifies the address of the endpoint.</span></span> <span data-ttu-id="46808-117">Значение по умолчанию — пустая строка.</span><span class="sxs-lookup"><span data-stu-id="46808-117">The default is an empty string.</span></span> <span data-ttu-id="46808-118">Адрес должен быть абсолютным универсальным кодом ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="46808-118">The address must be an absolute URI.</span></span>|  
|<span data-ttu-id="46808-119">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="46808-119">behaviorConfiguration</span></span>|<span data-ttu-id="46808-120">Строка, содержащая имя поведения, используемое для создания экземпляра конечной точки.</span><span class="sxs-lookup"><span data-stu-id="46808-120">A string that contains the behavior name of the behavior to be used to instantiate the endpoint.</span></span> <span data-ttu-id="46808-121">Имя поведения должно входить в область действия в точке определения службы.</span><span class="sxs-lookup"><span data-stu-id="46808-121">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="46808-122">Значение по умолчанию — пустая строка.</span><span class="sxs-lookup"><span data-stu-id="46808-122">The default is an empty string.</span></span>|  
|<span data-ttu-id="46808-123">привязка</span><span class="sxs-lookup"><span data-stu-id="46808-123">binding</span></span>|<span data-ttu-id="46808-124">Обязательный строковый атрибут.</span><span class="sxs-lookup"><span data-stu-id="46808-124">Required string attribute.</span></span><br /><br /> <span data-ttu-id="46808-125">Строка, указывающая тип привязки для использования.</span><span class="sxs-lookup"><span data-stu-id="46808-125">A string that indicates the type of binding to use.</span></span> <span data-ttu-id="46808-126">Чтобы на тип можно было ссылаться, он должен иметь зарегистрированный раздел конфигурации.</span><span class="sxs-lookup"><span data-stu-id="46808-126">The type must have a registered configuration section in order to be referenced.</span></span> <span data-ttu-id="46808-127">Тип регистрируется по имени раздела, а не по имени типа привязки.</span><span class="sxs-lookup"><span data-stu-id="46808-127">The type is registered by section name, instead of by the type name of the binding.</span></span>|  
|<span data-ttu-id="46808-128">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="46808-128">bindingConfiguration</span></span>|<span data-ttu-id="46808-129">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="46808-129">Optional.</span></span> <span data-ttu-id="46808-130">Строка, содержащая имя конфигурации привязки для использования при создании экземпляра конечной точки.</span><span class="sxs-lookup"><span data-stu-id="46808-130">A string that contains the name of the binding configuration to be used when the endpoint is instantiated.</span></span> <span data-ttu-id="46808-131">Конфигурация привязки должна входить в область действия в точке определения конечной точки.</span><span class="sxs-lookup"><span data-stu-id="46808-131">The binding configuration must be in scope at the point the endpoint is defined.</span></span> <span data-ttu-id="46808-132">Значение по умолчанию — пустая строка.</span><span class="sxs-lookup"><span data-stu-id="46808-132">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="46808-133">Этот атрибут используется вместе с атрибутом `binding` для ссылки на конкретную конфигурацию привязки в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="46808-133">This attribute is used in conjunction with `binding` to reference a specific binding configuration in the configuration file.</span></span> <span data-ttu-id="46808-134">Задайте этот атрибут, если выполняется попытка использовать пользовательскую привязку.</span><span class="sxs-lookup"><span data-stu-id="46808-134">Set this attribute if you are attempting to use a custom binding.</span></span> <span data-ttu-id="46808-135">В противном случае может быть создано исключение.</span><span class="sxs-lookup"><span data-stu-id="46808-135">Otherwise, an exception may be thrown.</span></span>|  
|<span data-ttu-id="46808-136">контракт</span><span class="sxs-lookup"><span data-stu-id="46808-136">contract</span></span>|<span data-ttu-id="46808-137">Обязательный строковый атрибут.</span><span class="sxs-lookup"><span data-stu-id="46808-137">Required string attribute.</span></span><br /><br /> <span data-ttu-id="46808-138">Строка, указывающая, к какому контракту предоставляется доступ этой конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="46808-138">A string that indicates which contract this endpoint is exposing.</span></span> <span data-ttu-id="46808-139">В сборке должен быть реализован данный тип контракта.</span><span class="sxs-lookup"><span data-stu-id="46808-139">The assembly must implement the contract type.</span></span>|  
|<span data-ttu-id="46808-140">endpointConfiguration</span><span class="sxs-lookup"><span data-stu-id="46808-140">endpointConfiguration</span></span>|<span data-ttu-id="46808-141">Строка, указывающая имя стандартной конечной точки, задаваемой атрибутом `kind`, который ссылается на дополнительные сведения конфигурации этой конечной точки.</span><span class="sxs-lookup"><span data-stu-id="46808-141">A string that specifies the name of the standard endpoint that is set by the `kind` attribute, which references to the additional configuration information of this standard endpoint.</span></span> <span data-ttu-id="46808-142">Такое же имя должно быть задано в разделе `<standardEndpoints>`.</span><span class="sxs-lookup"><span data-stu-id="46808-142">The same name must be defined in the `<standardEndpoints>` section.</span></span>|  
|<span data-ttu-id="46808-143">kind</span><span class="sxs-lookup"><span data-stu-id="46808-143">kind</span></span>|<span data-ttu-id="46808-144">Строка, указывающая тип применяемой стандартной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="46808-144">A string that specifies the type of standard endpoint applied.</span></span> <span data-ttu-id="46808-145">Этот тип должен быть зарегистрирован в разделе `<extensions>` или в файле machine.config. Если ничего не указано, будет создана обычная конечная точка канала.</span><span class="sxs-lookup"><span data-stu-id="46808-145">The type must be registered in the `<extensions>` section or in machine.config. If nothing is specified, a common channel endpoint is created.</span></span>|  
|<span data-ttu-id="46808-146">имя</span><span class="sxs-lookup"><span data-stu-id="46808-146">name</span></span>|<span data-ttu-id="46808-147">Необязательный строковый атрибут.</span><span class="sxs-lookup"><span data-stu-id="46808-147">Optional string attribute.</span></span> <span data-ttu-id="46808-148">Этот атрибут уникальным образом идентифицирует конечную точку для данного контракта.</span><span class="sxs-lookup"><span data-stu-id="46808-148">This attribute uniquely identifies an endpoint for a given contract.</span></span> <span data-ttu-id="46808-149">Для данного типа контракта можно определить несколько клиентов.</span><span class="sxs-lookup"><span data-stu-id="46808-149">You can define multiple clients for a given Contract type.</span></span> <span data-ttu-id="46808-150">Определения должны отличаться друг от друга уникальным именем конфигурации.</span><span class="sxs-lookup"><span data-stu-id="46808-150">Each definition must be differentiated by a unique configuration name.</span></span> <span data-ttu-id="46808-151">Если этот атрибут опущен, соответствующая конечная точка используется как конечная точка по умолчанию, связанная с заданным типом контракта.</span><span class="sxs-lookup"><span data-stu-id="46808-151">If this attribute is omitted, the corresponding endpoint is used as the default endpoint associated with the specified Contract type.</span></span> <span data-ttu-id="46808-152">Значение по умолчанию — пустая строка.</span><span class="sxs-lookup"><span data-stu-id="46808-152">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="46808-153">Атрибут `name` привязки используется для экспорта определения посредством языка WSDL.</span><span class="sxs-lookup"><span data-stu-id="46808-153">The `name` attribute of a binding is used for definition export through WSDL.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="46808-154">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="46808-154">Child Elements</span></span>  
  
|<span data-ttu-id="46808-155">Элемент</span><span class="sxs-lookup"><span data-stu-id="46808-155">Element</span></span>|<span data-ttu-id="46808-156">Описание</span><span class="sxs-lookup"><span data-stu-id="46808-156">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="46808-157">\<заголовки ></span><span class="sxs-lookup"><span data-stu-id="46808-157">\<headers></span></span>](headers.md)|<span data-ttu-id="46808-158">Коллекция заголовков адреса.</span><span class="sxs-lookup"><span data-stu-id="46808-158">A collection of address headers.</span></span>|  
|[<span data-ttu-id="46808-159">\<> удостоверений</span><span class="sxs-lookup"><span data-stu-id="46808-159">\<identity></span></span>](identity.md)|<span data-ttu-id="46808-160">Удостоверение, обеспечивающее проверку подлинности конечной точки другими конечными точками, которые обмениваются с ней сообщениями.</span><span class="sxs-lookup"><span data-stu-id="46808-160">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="46808-161">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="46808-161">Parent Elements</span></span>  
  
|<span data-ttu-id="46808-162">Элемент</span><span class="sxs-lookup"><span data-stu-id="46808-162">Element</span></span>|<span data-ttu-id="46808-163">Описание</span><span class="sxs-lookup"><span data-stu-id="46808-163">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="46808-164">\<> клиента</span><span class="sxs-lookup"><span data-stu-id="46808-164">\<client></span></span>](client.md)|<span data-ttu-id="46808-165">Раздел конфигурации, определяющий список конечных точек, к которым может подключаться клиент.</span><span class="sxs-lookup"><span data-stu-id="46808-165">A configuration section that defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="46808-166">Пример</span><span class="sxs-lookup"><span data-stu-id="46808-166">Example</span></span>  
 <span data-ttu-id="46808-167">Далее приведен пример конфигурации конечной точки канала.</span><span class="sxs-lookup"><span data-stu-id="46808-167">This is an example of a channel endpoint configuration.</span></span>  
  
```xml  
<endpoint address="/HelloWorld/"
          bindingConfiguration="usingDefaults"
          name="MyBinding"
          binding="customBinding"
          contract="HelloWorld">
</endpoint>
```  
  
## <a name="see-also"></a><span data-ttu-id="46808-168">См. также</span><span class="sxs-lookup"><span data-stu-id="46808-168">See also</span></span>

- <xref:System.ServiceModel.Configuration.ChannelEndpointElement>
- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.ChannelEndpointElementCollection>
- <xref:System.ServiceModel.Configuration.ClientSection.Endpoints%2A>
- <xref:System.ServiceModel.Configuration.ChannelEndpointElement>
- [<span data-ttu-id="46808-169">Конфигурация клиента WCF</span><span class="sxs-lookup"><span data-stu-id="46808-169">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="46808-170">Клиенты</span><span class="sxs-lookup"><span data-stu-id="46808-170">Clients</span></span>](../../../wcf/feature-details/clients.md)
