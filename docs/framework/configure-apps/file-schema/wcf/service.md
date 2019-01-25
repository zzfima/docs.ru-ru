---
title: '&lt;Службы&gt;'
ms.date: 03/30/2017
ms.assetid: 13123dd6-c4a9-4a04-a984-df184b851788
ms.openlocfilehash: e91e04c602fd867e329477015fc0a8354ae26a05
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54535012"
---
# <a name="ltservicegt"></a><span data-ttu-id="50710-102">&lt;Службы&gt;</span><span class="sxs-lookup"><span data-stu-id="50710-102">&lt;service&gt;</span></span>
<span data-ttu-id="50710-103">Элемент `service` содержит параметры для службы Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="50710-103">The `service` element contains the settings for a Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="50710-104">Он также содержит конечные точки, предоставляющие доступ к службе.</span><span class="sxs-lookup"><span data-stu-id="50710-104">It also contains endpoints that expose the service.</span></span>  
  
 <span data-ttu-id="50710-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="50710-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="50710-106">\<Services ></span><span class="sxs-lookup"><span data-stu-id="50710-106">\<services></span></span>  
<span data-ttu-id="50710-107">\<службы ></span><span class="sxs-lookup"><span data-stu-id="50710-107">\<service></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50710-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="50710-108">Syntax</span></span>  
  
```xml  
<service behaviorConfiguration="String"
         name="String">
</service>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="50710-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="50710-109">Attributes and Elements</span></span>  
 <span data-ttu-id="50710-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="50710-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="50710-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="50710-111">Attributes</span></span>  
  
|<span data-ttu-id="50710-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="50710-112">Attribute</span></span>|<span data-ttu-id="50710-113">Описание</span><span class="sxs-lookup"><span data-stu-id="50710-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="50710-114">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="50710-114">behaviorConfiguration</span></span>|<span data-ttu-id="50710-115">Строка, содержащая имя поведения, которое следует использовать для создания экземпляра службы.</span><span class="sxs-lookup"><span data-stu-id="50710-115">A string that contains the behavior name of the behavior to be used to instantiate the service.</span></span> <span data-ttu-id="50710-116">Имя поведения должно входить в область действия в точке определения службы.</span><span class="sxs-lookup"><span data-stu-id="50710-116">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="50710-117">Значение по умолчанию - пустая строка.</span><span class="sxs-lookup"><span data-stu-id="50710-117">The default value is an empty string.</span></span>|  
|<span data-ttu-id="50710-118">имя</span><span class="sxs-lookup"><span data-stu-id="50710-118">name</span></span>|<span data-ttu-id="50710-119">Требуемый строковый атрибут, указывающий тип службы, экземпляр которой создается.</span><span class="sxs-lookup"><span data-stu-id="50710-119">Required String attribute that specifies the type of the service to be instantiated.</span></span> <span data-ttu-id="50710-120">Этот параметр должен иметь значение допустимого типа.</span><span class="sxs-lookup"><span data-stu-id="50710-120">This setting must equate to a valid type.</span></span> <span data-ttu-id="50710-121">Формат должен быть `Namespace.Class.`.</span><span class="sxs-lookup"><span data-stu-id="50710-121">The format should be `Namespace.Class.`</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="50710-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="50710-122">Child Elements</span></span>  
  
|<span data-ttu-id="50710-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="50710-123">Element</span></span>|<span data-ttu-id="50710-124">Описание:</span><span class="sxs-lookup"><span data-stu-id="50710-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="50710-125">\<Конечная точка ></span><span class="sxs-lookup"><span data-stu-id="50710-125">\<endpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md)|<span data-ttu-id="50710-126">Коллекция элементов `endpoint`, которые обеспечивают доступ к данной службе.</span><span class="sxs-lookup"><span data-stu-id="50710-126">A collection of `endpoint` elements that expose this service.</span></span>|  
|[<span data-ttu-id="50710-127">\<узел ></span><span class="sxs-lookup"><span data-stu-id="50710-127">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="50710-128">Задает узел данного экземпляра службы.</span><span class="sxs-lookup"><span data-stu-id="50710-128">Specifies the host of this service instance.</span></span> <span data-ttu-id="50710-129">Это элемент типа <xref:System.ServiceModel.Configuration.HostElement>.</span><span class="sxs-lookup"><span data-stu-id="50710-129">This element is of type <xref:System.ServiceModel.Configuration.HostElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="50710-130">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="50710-130">Parent Elements</span></span>  
  
|<span data-ttu-id="50710-131">Элемент</span><span class="sxs-lookup"><span data-stu-id="50710-131">Element</span></span>|<span data-ttu-id="50710-132">Описание</span><span class="sxs-lookup"><span data-stu-id="50710-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="50710-133">\<Services ></span><span class="sxs-lookup"><span data-stu-id="50710-133">\<services></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md)|<span data-ttu-id="50710-134">Корневой элемент всех элементов конфигурации WCF.</span><span class="sxs-lookup"><span data-stu-id="50710-134">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50710-135">Примечания</span><span class="sxs-lookup"><span data-stu-id="50710-135">Remarks</span></span>  
 <span data-ttu-id="50710-136">Службы задаются в разделе `services` файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="50710-136">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="50710-137">Сборка может содержать любое число служб.</span><span class="sxs-lookup"><span data-stu-id="50710-137">An assembly can contain any number of services.</span></span> <span data-ttu-id="50710-138">Для каждой службы используется собственный раздел конфигурации `service`.</span><span class="sxs-lookup"><span data-stu-id="50710-138">Each service has its own `service` configuration section.</span></span> <span data-ttu-id="50710-139">В этом разделе определяются контракт, поведение и конечные точки конкретной службы.</span><span class="sxs-lookup"><span data-stu-id="50710-139">This section and its content define the service contract, behavior, and endpoints of the particular service.</span></span>  
  
 <span data-ttu-id="50710-140">Элемент `behaviorConfiguration` также является необязательным.</span><span class="sxs-lookup"><span data-stu-id="50710-140">The `behaviorConfiguration` element is also optional.</span></span> <span data-ttu-id="50710-141">Он указывает поведение, используемое службой.</span><span class="sxs-lookup"><span data-stu-id="50710-141">It identifies the behavior the service uses.</span></span> <span data-ttu-id="50710-142">Поведение, заданное в данном атрибуте, должно быть связано с поведением в области в том же файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="50710-142">The behavior specified in this attribute must link to a behavior in scope in the same configuration file.</span></span>  
  
 <span data-ttu-id="50710-143">Каждая служба предоставляет доступ к одной или нескольким конечным точкам, которые имеют собственные адреса и привязки.</span><span class="sxs-lookup"><span data-stu-id="50710-143">Each service exposes one or more endpoints, which has its own address and binding.</span></span> <span data-ttu-id="50710-144">Все привязки в файле конфигурации должны быть определены в области файла.</span><span class="sxs-lookup"><span data-stu-id="50710-144">All bindings used within the configuration file must be defined in the scope of the file.</span></span> <span data-ttu-id="50710-145">Привязки связаны с конечными точками с помощью сочетания атрибутов `name` и `bindingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="50710-145">Binding are linked to endpoints through the combination of the attributes `name` and `bindingConfiguration`.</span></span> <span data-ttu-id="50710-146">Атрибут `name` описывает раздел, в котором определена привязка.</span><span class="sxs-lookup"><span data-stu-id="50710-146">The `name` attribute describes the section the binding is defined in.</span></span> <span data-ttu-id="50710-147">Атрибут `bindingConfiguration` указывает, какая конфигурация из раздела привязок используется.</span><span class="sxs-lookup"><span data-stu-id="50710-147">The `bindingConfiguration` attribute defines which configuration within the binding section is used.</span></span> <span data-ttu-id="50710-148">В разделе привязки может определяться несколько конфигураций.</span><span class="sxs-lookup"><span data-stu-id="50710-148">A binding section can define several configurations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="50710-149">Пример</span><span class="sxs-lookup"><span data-stu-id="50710-149">Example</span></span>  
 <span data-ttu-id="50710-150">Ниже приведен пример конфигурации службы.</span><span class="sxs-lookup"><span data-stu-id="50710-150">This is an example of a service configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="50710-151">См. также</span><span class="sxs-lookup"><span data-stu-id="50710-151">See also</span></span>
- <xref:System.ServiceModel.Configuration.ServiceElement>
- [<span data-ttu-id="50710-152">Настройка служб</span><span class="sxs-lookup"><span data-stu-id="50710-152">Configuring Services</span></span>](../../../../../docs/framework/wcf/configuring-services.md)
