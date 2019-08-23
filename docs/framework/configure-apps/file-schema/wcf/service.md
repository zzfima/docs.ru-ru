---
title: <service>
ms.date: 03/30/2017
ms.assetid: 13123dd6-c4a9-4a04-a984-df184b851788
ms.openlocfilehash: 69f3c70514fc2bcab1b4ef6a45036de98d1af7b7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936523"
---
# <a name="service"></a><span data-ttu-id="dd2b1-101">\<> службы</span><span class="sxs-lookup"><span data-stu-id="dd2b1-101">\<service></span></span>
<span data-ttu-id="dd2b1-102">Элемент `service` содержит параметры для службы Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="dd2b1-102">The `service` element contains the settings for a Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="dd2b1-103">Он также содержит конечные точки, предоставляющие доступ к службе.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-103">It also contains endpoints that expose the service.</span></span>  
  
 <span data-ttu-id="dd2b1-104">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="dd2b1-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="dd2b1-105">\<службы ></span><span class="sxs-lookup"><span data-stu-id="dd2b1-105">\<services></span></span>  
<span data-ttu-id="dd2b1-106">\<> службы</span><span class="sxs-lookup"><span data-stu-id="dd2b1-106">\<service></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd2b1-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dd2b1-107">Syntax</span></span>  
  
```xml  
<service behaviorConfiguration="String"
         name="String">
</service>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dd2b1-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="dd2b1-108">Attributes and Elements</span></span>  
 <span data-ttu-id="dd2b1-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dd2b1-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="dd2b1-110">Attributes</span></span>  
  
|<span data-ttu-id="dd2b1-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="dd2b1-111">Attribute</span></span>|<span data-ttu-id="dd2b1-112">Описание</span><span class="sxs-lookup"><span data-stu-id="dd2b1-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dd2b1-113">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="dd2b1-113">behaviorConfiguration</span></span>|<span data-ttu-id="dd2b1-114">Строка, содержащая имя поведения, которое следует использовать для создания экземпляра службы.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-114">A string that contains the behavior name of the behavior to be used to instantiate the service.</span></span> <span data-ttu-id="dd2b1-115">Имя поведения должно входить в область действия в точке определения службы.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-115">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="dd2b1-116">Значение по умолчанию - пустая строка.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-116">The default value is an empty string.</span></span>|  
|<span data-ttu-id="dd2b1-117">имя</span><span class="sxs-lookup"><span data-stu-id="dd2b1-117">name</span></span>|<span data-ttu-id="dd2b1-118">Требуемый строковый атрибут, указывающий тип службы, экземпляр которой создается.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-118">Required String attribute that specifies the type of the service to be instantiated.</span></span> <span data-ttu-id="dd2b1-119">Этот параметр должен иметь значение допустимого типа.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-119">This setting must equate to a valid type.</span></span> <span data-ttu-id="dd2b1-120">Формат должен быть `Namespace.Class.`.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-120">The format should be `Namespace.Class.`</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dd2b1-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="dd2b1-121">Child Elements</span></span>  
  
|<span data-ttu-id="dd2b1-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="dd2b1-122">Element</span></span>|<span data-ttu-id="dd2b1-123">Описание</span><span class="sxs-lookup"><span data-stu-id="dd2b1-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dd2b1-124">\<> конечной точки</span><span class="sxs-lookup"><span data-stu-id="dd2b1-124">\<endpoint></span></span>](endpoint-element.md)|<span data-ttu-id="dd2b1-125">Коллекция элементов `endpoint`, которые обеспечивают доступ к данной службе.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-125">A collection of `endpoint` elements that expose this service.</span></span>|  
|[<span data-ttu-id="dd2b1-126">\<> узла</span><span class="sxs-lookup"><span data-stu-id="dd2b1-126">\<host></span></span>](host.md)|<span data-ttu-id="dd2b1-127">Задает узел данного экземпляра службы.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-127">Specifies the host of this service instance.</span></span> <span data-ttu-id="dd2b1-128">Это элемент типа <xref:System.ServiceModel.Configuration.HostElement>.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-128">This element is of type <xref:System.ServiceModel.Configuration.HostElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dd2b1-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="dd2b1-129">Parent Elements</span></span>  
  
|<span data-ttu-id="dd2b1-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="dd2b1-130">Element</span></span>|<span data-ttu-id="dd2b1-131">Описание</span><span class="sxs-lookup"><span data-stu-id="dd2b1-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dd2b1-132">\<службы ></span><span class="sxs-lookup"><span data-stu-id="dd2b1-132">\<services></span></span>](services.md)|<span data-ttu-id="dd2b1-133">Корневой элемент всех элементов конфигурации WCF.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-133">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dd2b1-134">Примечания</span><span class="sxs-lookup"><span data-stu-id="dd2b1-134">Remarks</span></span>  
 <span data-ttu-id="dd2b1-135">Службы задаются в разделе `services` файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-135">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="dd2b1-136">Сборка может содержать любое число служб.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-136">An assembly can contain any number of services.</span></span> <span data-ttu-id="dd2b1-137">Для каждой службы используется собственный раздел конфигурации `service`.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-137">Each service has its own `service` configuration section.</span></span> <span data-ttu-id="dd2b1-138">В этом разделе определяются контракт, поведение и конечные точки конкретной службы.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-138">This section and its content define the service contract, behavior, and endpoints of the particular service.</span></span>  
  
 <span data-ttu-id="dd2b1-139">Элемент `behaviorConfiguration` также является необязательным.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-139">The `behaviorConfiguration` element is also optional.</span></span> <span data-ttu-id="dd2b1-140">Он указывает поведение, используемое службой.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-140">It identifies the behavior the service uses.</span></span> <span data-ttu-id="dd2b1-141">Поведение, заданное в данном атрибуте, должно быть связано с поведением в области в том же файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-141">The behavior specified in this attribute must link to a behavior in scope in the same configuration file.</span></span>  
  
 <span data-ttu-id="dd2b1-142">Каждая служба предоставляет доступ к одной или нескольким конечным точкам, которые имеют собственные адреса и привязки.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-142">Each service exposes one or more endpoints, which has its own address and binding.</span></span> <span data-ttu-id="dd2b1-143">Все привязки в файле конфигурации должны быть определены в области файла.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-143">All bindings used within the configuration file must be defined in the scope of the file.</span></span> <span data-ttu-id="dd2b1-144">Привязки связаны с конечными точками с помощью сочетания атрибутов `name` и `bindingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-144">Binding are linked to endpoints through the combination of the attributes `name` and `bindingConfiguration`.</span></span> <span data-ttu-id="dd2b1-145">Атрибут `name` описывает раздел, в котором определена привязка.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-145">The `name` attribute describes the section the binding is defined in.</span></span> <span data-ttu-id="dd2b1-146">Атрибут `bindingConfiguration` указывает, какая конфигурация из раздела привязок используется.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-146">The `bindingConfiguration` attribute defines which configuration within the binding section is used.</span></span> <span data-ttu-id="dd2b1-147">В разделе привязки может определяться несколько конфигураций.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-147">A binding section can define several configurations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd2b1-148">Пример</span><span class="sxs-lookup"><span data-stu-id="dd2b1-148">Example</span></span>  
 <span data-ttu-id="dd2b1-149">Ниже приведен пример конфигурации службы.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-149">This is an example of a service configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="dd2b1-150">См. также</span><span class="sxs-lookup"><span data-stu-id="dd2b1-150">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceElement>
- [<span data-ttu-id="dd2b1-151">Настройка служб</span><span class="sxs-lookup"><span data-stu-id="dd2b1-151">Configuring Services</span></span>](../../../wcf/configuring-services.md)
