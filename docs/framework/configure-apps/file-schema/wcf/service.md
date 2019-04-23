---
title: <service>
ms.date: 03/30/2017
ms.assetid: 13123dd6-c4a9-4a04-a984-df184b851788
ms.openlocfilehash: 68bddc01b02d9885b3f0fc4c2cbc5c3249de03f4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59197962"
---
# <a name="service"></a><span data-ttu-id="98ca0-101">\<службы ></span><span class="sxs-lookup"><span data-stu-id="98ca0-101">\<service></span></span>
<span data-ttu-id="98ca0-102">Элемент `service` содержит параметры для службы Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="98ca0-102">The `service` element contains the settings for a Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="98ca0-103">Он также содержит конечные точки, предоставляющие доступ к службе.</span><span class="sxs-lookup"><span data-stu-id="98ca0-103">It also contains endpoints that expose the service.</span></span>  
  
 <span data-ttu-id="98ca0-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="98ca0-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="98ca0-105">\<Services ></span><span class="sxs-lookup"><span data-stu-id="98ca0-105">\<services></span></span>  
<span data-ttu-id="98ca0-106">\<службы ></span><span class="sxs-lookup"><span data-stu-id="98ca0-106">\<service></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98ca0-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="98ca0-107">Syntax</span></span>  
  
```xml  
<service behaviorConfiguration="String"
         name="String">
</service>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="98ca0-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="98ca0-108">Attributes and Elements</span></span>  
 <span data-ttu-id="98ca0-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="98ca0-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="98ca0-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="98ca0-110">Attributes</span></span>  
  
|<span data-ttu-id="98ca0-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="98ca0-111">Attribute</span></span>|<span data-ttu-id="98ca0-112">Описание</span><span class="sxs-lookup"><span data-stu-id="98ca0-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="98ca0-113">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="98ca0-113">behaviorConfiguration</span></span>|<span data-ttu-id="98ca0-114">Строка, содержащая имя поведения, которое следует использовать для создания экземпляра службы.</span><span class="sxs-lookup"><span data-stu-id="98ca0-114">A string that contains the behavior name of the behavior to be used to instantiate the service.</span></span> <span data-ttu-id="98ca0-115">Имя поведения должно входить в область действия в точке определения службы.</span><span class="sxs-lookup"><span data-stu-id="98ca0-115">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="98ca0-116">Значение по умолчанию - пустая строка.</span><span class="sxs-lookup"><span data-stu-id="98ca0-116">The default value is an empty string.</span></span>|  
|<span data-ttu-id="98ca0-117">имя</span><span class="sxs-lookup"><span data-stu-id="98ca0-117">name</span></span>|<span data-ttu-id="98ca0-118">Требуемый строковый атрибут, указывающий тип службы, экземпляр которой создается.</span><span class="sxs-lookup"><span data-stu-id="98ca0-118">Required String attribute that specifies the type of the service to be instantiated.</span></span> <span data-ttu-id="98ca0-119">Этот параметр должен иметь значение допустимого типа.</span><span class="sxs-lookup"><span data-stu-id="98ca0-119">This setting must equate to a valid type.</span></span> <span data-ttu-id="98ca0-120">Формат должен быть `Namespace.Class.`.</span><span class="sxs-lookup"><span data-stu-id="98ca0-120">The format should be `Namespace.Class.`</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="98ca0-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="98ca0-121">Child Elements</span></span>  
  
|<span data-ttu-id="98ca0-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="98ca0-122">Element</span></span>|<span data-ttu-id="98ca0-123">Описание</span><span class="sxs-lookup"><span data-stu-id="98ca0-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="98ca0-124">\<Конечная точка ></span><span class="sxs-lookup"><span data-stu-id="98ca0-124">\<endpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md)|<span data-ttu-id="98ca0-125">Коллекция элементов `endpoint`, которые обеспечивают доступ к данной службе.</span><span class="sxs-lookup"><span data-stu-id="98ca0-125">A collection of `endpoint` elements that expose this service.</span></span>|  
|[<span data-ttu-id="98ca0-126">\<узел ></span><span class="sxs-lookup"><span data-stu-id="98ca0-126">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="98ca0-127">Задает узел данного экземпляра службы.</span><span class="sxs-lookup"><span data-stu-id="98ca0-127">Specifies the host of this service instance.</span></span> <span data-ttu-id="98ca0-128">Это элемент типа <xref:System.ServiceModel.Configuration.HostElement>.</span><span class="sxs-lookup"><span data-stu-id="98ca0-128">This element is of type <xref:System.ServiceModel.Configuration.HostElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="98ca0-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="98ca0-129">Parent Elements</span></span>  
  
|<span data-ttu-id="98ca0-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="98ca0-130">Element</span></span>|<span data-ttu-id="98ca0-131">Описание</span><span class="sxs-lookup"><span data-stu-id="98ca0-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="98ca0-132">\<Services ></span><span class="sxs-lookup"><span data-stu-id="98ca0-132">\<services></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md)|<span data-ttu-id="98ca0-133">Корневой элемент всех элементов конфигурации WCF.</span><span class="sxs-lookup"><span data-stu-id="98ca0-133">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="98ca0-134">Примечания</span><span class="sxs-lookup"><span data-stu-id="98ca0-134">Remarks</span></span>  
 <span data-ttu-id="98ca0-135">Службы задаются в разделе `services` файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="98ca0-135">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="98ca0-136">Сборка может содержать любое число служб.</span><span class="sxs-lookup"><span data-stu-id="98ca0-136">An assembly can contain any number of services.</span></span> <span data-ttu-id="98ca0-137">Для каждой службы используется собственный раздел конфигурации `service`.</span><span class="sxs-lookup"><span data-stu-id="98ca0-137">Each service has its own `service` configuration section.</span></span> <span data-ttu-id="98ca0-138">В этом разделе определяются контракт, поведение и конечные точки конкретной службы.</span><span class="sxs-lookup"><span data-stu-id="98ca0-138">This section and its content define the service contract, behavior, and endpoints of the particular service.</span></span>  
  
 <span data-ttu-id="98ca0-139">Элемент `behaviorConfiguration` также является необязательным.</span><span class="sxs-lookup"><span data-stu-id="98ca0-139">The `behaviorConfiguration` element is also optional.</span></span> <span data-ttu-id="98ca0-140">Он указывает поведение, используемое службой.</span><span class="sxs-lookup"><span data-stu-id="98ca0-140">It identifies the behavior the service uses.</span></span> <span data-ttu-id="98ca0-141">Поведение, заданное в данном атрибуте, должно быть связано с поведением в области в том же файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="98ca0-141">The behavior specified in this attribute must link to a behavior in scope in the same configuration file.</span></span>  
  
 <span data-ttu-id="98ca0-142">Каждая служба предоставляет доступ к одной или нескольким конечным точкам, которые имеют собственные адреса и привязки.</span><span class="sxs-lookup"><span data-stu-id="98ca0-142">Each service exposes one or more endpoints, which has its own address and binding.</span></span> <span data-ttu-id="98ca0-143">Все привязки в файле конфигурации должны быть определены в области файла.</span><span class="sxs-lookup"><span data-stu-id="98ca0-143">All bindings used within the configuration file must be defined in the scope of the file.</span></span> <span data-ttu-id="98ca0-144">Привязки связаны с конечными точками с помощью сочетания атрибутов `name` и `bindingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="98ca0-144">Binding are linked to endpoints through the combination of the attributes `name` and `bindingConfiguration`.</span></span> <span data-ttu-id="98ca0-145">Атрибут `name` описывает раздел, в котором определена привязка.</span><span class="sxs-lookup"><span data-stu-id="98ca0-145">The `name` attribute describes the section the binding is defined in.</span></span> <span data-ttu-id="98ca0-146">Атрибут `bindingConfiguration` указывает, какая конфигурация из раздела привязок используется.</span><span class="sxs-lookup"><span data-stu-id="98ca0-146">The `bindingConfiguration` attribute defines which configuration within the binding section is used.</span></span> <span data-ttu-id="98ca0-147">В разделе привязки может определяться несколько конфигураций.</span><span class="sxs-lookup"><span data-stu-id="98ca0-147">A binding section can define several configurations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="98ca0-148">Пример</span><span class="sxs-lookup"><span data-stu-id="98ca0-148">Example</span></span>  
 <span data-ttu-id="98ca0-149">Ниже приведен пример конфигурации службы.</span><span class="sxs-lookup"><span data-stu-id="98ca0-149">This is an example of a service configuration.</span></span>  
  
```xml  
<service behaviorConfiguration="testChannelBehavior"
         name="HelloWorld">
  <endpoint address="/HelloWorld2/"
            name="test"
            bindingNamespace="http://www.cohowinery.com/"
            binding="basicHttpBinding"
            contract="IHelloWorld" />
</service>
```  
  
## <a name="see-also"></a><span data-ttu-id="98ca0-150">См. также</span><span class="sxs-lookup"><span data-stu-id="98ca0-150">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceElement>
- [<span data-ttu-id="98ca0-151">Настройка служб</span><span class="sxs-lookup"><span data-stu-id="98ca0-151">Configuring Services</span></span>](../../../../../docs/framework/wcf/configuring-services.md)
