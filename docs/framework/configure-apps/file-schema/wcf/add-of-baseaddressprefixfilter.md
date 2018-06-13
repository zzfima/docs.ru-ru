---
title: '&lt;add&gt; для &lt;baseAddressPrefixFilter&gt;'
ms.date: 03/30/2017
ms.assetid: b226bede-8459-4de9-b2ac-3d39604ce2bc
ms.openlocfilehash: e4408488036be210e3a8b9cf8b8f8f8c2e669a1d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33365193"
---
# <a name="ltaddgt-of-ltbaseaddressprefixfiltergt"></a><span data-ttu-id="5319c-102">&lt;add&gt; для &lt;baseAddressPrefixFilter&gt;</span><span class="sxs-lookup"><span data-stu-id="5319c-102">&lt;add&gt; of &lt;baseAddressPrefixFilter&gt;</span></span>
<span data-ttu-id="5319c-103">Представляет элемент конфигурации, который задает проходной фильтр, предоставляющий механизм выбора соответствующих привязок служб Internet Information Services (IIS), при размещении приложения Windows Communication Foundation (WCF) в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="5319c-103">Represents a configuration element that specifies a pass-through filter, which provides a mechanism to pick the appropriate Internet Information Services (IIS) bindings when hosting a Windows Communication Foundation (WCF) application in IIS.</span></span>  
  
 <span data-ttu-id="5319c-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="5319c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="5319c-105">\<ServiceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="5319c-105">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="5319c-106">\<baseAddressPrefixFilters ></span><span class="sxs-lookup"><span data-stu-id="5319c-106">\<baseAddressPrefixFilters></span></span>  
<span data-ttu-id="5319c-107">\<add></span><span class="sxs-lookup"><span data-stu-id="5319c-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5319c-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5319c-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>  
     <baseAddressPrefixFilters>  
        <add prefix="string"/>  
     </baseAddressPrefixFilters>  
</serviceHostingEnvironment>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5319c-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5319c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="5319c-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5319c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5319c-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5319c-111">Attributes</span></span>  
  
|<span data-ttu-id="5319c-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5319c-112">Attribute</span></span>|<span data-ttu-id="5319c-113">Описание</span><span class="sxs-lookup"><span data-stu-id="5319c-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5319c-114">prefix</span><span class="sxs-lookup"><span data-stu-id="5319c-114">prefix</span></span>|<span data-ttu-id="5319c-115">Универсальный код ресурса (URI), совпадающий с частью базового адреса.</span><span class="sxs-lookup"><span data-stu-id="5319c-115">A URI that is used to match a part of a base address.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5319c-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5319c-116">Child Elements</span></span>  
 <span data-ttu-id="5319c-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5319c-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5319c-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5319c-118">Parent Elements</span></span>  
  
|<span data-ttu-id="5319c-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="5319c-119">Element</span></span>|<span data-ttu-id="5319c-120">Описание</span><span class="sxs-lookup"><span data-stu-id="5319c-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5319c-121">\<baseAddressPrefixFilters ></span><span class="sxs-lookup"><span data-stu-id="5319c-121">\<baseAddressPrefixFilters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddressprefixfilters.md)|<span data-ttu-id="5319c-122">Коллекция элементов конфигурации, которые задают проходные фильтры, предоставляющие механизм выбора необходимых привязок служб IIS при размещении приложения Windows Communication Foundation (WCF) в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="5319c-122">A collection of configuration elements that specify pass-through filters, which provide a mechanism to pick the appropriate IIS bindings when hosting a Windows Communication Foundation (WCF) application in IIS.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5319c-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="5319c-123">Remarks</span></span>  
 <span data-ttu-id="5319c-124">Префиксный фильтр предоставляет способ для общих поставщиков услуг размещения задать, какие URI должны использоваться службой.</span><span class="sxs-lookup"><span data-stu-id="5319c-124">A prefix filter provides a way for shared hosting providers to specify which URIs are to be used by the service.</span></span> <span data-ttu-id="5319c-125">Это дает возможность общим узлам размещать несколько приложений с разными базовыми адресами для одной схемы на одном узле.</span><span class="sxs-lookup"><span data-stu-id="5319c-125">It enables shared hosts to host multiple applications with different base addresses for the same scheme on the same site.</span></span>  
  
 <span data-ttu-id="5319c-126">Веб-узлы IIS являются контейнерами виртуальных приложений, содержащими виртуальные каталоги.</span><span class="sxs-lookup"><span data-stu-id="5319c-126">IIS Web sites are containers for virtual applications which contain virtual directories.</span></span> <span data-ttu-id="5319c-127">Доступ к приложению на узле можно осуществлять через одну или несколько привязок IIS.</span><span class="sxs-lookup"><span data-stu-id="5319c-127">The application in a site can be accessed through one or more IIS binding.</span></span> <span data-ttu-id="5319c-128">Привязки IIS предоставляют два блока данных: протокол привязки и данные привязки.</span><span class="sxs-lookup"><span data-stu-id="5319c-128">IIS bindings provide two pieces of information: binding protocol and binding information.</span></span> <span data-ttu-id="5319c-129">Протокол привязки (например, HTTP) определяет схему, посредством которой осуществляется связь, а данные привязки (например, IP-адрес, порт, заголовок узла) содержат сведения, используемые для доступа к узлу.</span><span class="sxs-lookup"><span data-stu-id="5319c-129">Binding protocol (for example, HTTP) defines the scheme over which communication occurs, and binding information (for example, IP Address, Port, Hostheader) contains data used to access the site.</span></span>  
  
 <span data-ttu-id="5319c-130">IIS поддерживает задание нескольких привязок IIS для каждого узла, что позволяет использовать несколько базовых адресов для каждой схемы.</span><span class="sxs-lookup"><span data-stu-id="5319c-130">IIS supports specifying multiple IIS bindings for each site, which results in multiple base addresses for each scheme.</span></span> <span data-ttu-id="5319c-131">Поскольку размещаемая на узле службы WCF допускает привязку только к одному базовому адресу для каждой схемы, можно использовать функцию префиксного фильтра, чтобы выбирать необходимые базовые адреса размещенной службы.</span><span class="sxs-lookup"><span data-stu-id="5319c-131">Because a WCF service hosted under a site allows binding to only one base address for each scheme, you can use the prefix filter feature to pick the required base address of the hosted service.</span></span> <span data-ttu-id="5319c-132">Входящие базовые адреса, предоставляемые IIS, фильтруются с использованием дополнительного фильтра списка префиксов.</span><span class="sxs-lookup"><span data-stu-id="5319c-132">The incoming base addresses, supplied by IIS, are filtered based on the optional prefix list filter.</span></span>  
  
 <span data-ttu-id="5319c-133">Например, узел может содержать следующие базовые адреса.</span><span class="sxs-lookup"><span data-stu-id="5319c-133">For example, your site can contain the following base addresses.</span></span>  
  
```  
http://testl.fabrikam.com/Service.svc  
http://test2.fabrikam.com/Service.svc  
```  
  
 <span data-ttu-id="5319c-134">Для задания префиксного фильтра на уровне домена приложений можно использовать следующий файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="5319c-134">You can use the following configuration file to specify a prefix filter at the appdomain level.</span></span>  
  
```xml  
<system.serviceModel>  
  <serviceHostingEnvironment>  
     <baseAddressPrefixFilters>  
        <add prefix="net.tcp://test1.fabrikam.com:8000"/>  
        <add prefix="http://test2.fabrikam.com:9000"/>  
    </baseAddressPrefixFilters>  
  </serviceHostingEnvironment>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="5319c-135">В этом примере `net.tcp://test1.fabrikam.com:8000` и `http://test2.fabrikam.com:9000` являются единственными базовыми адресами соответствующих схем, для которых разрешено прохождение данных.</span><span class="sxs-lookup"><span data-stu-id="5319c-135">In this example, `net.tcp://test1.fabrikam.com:8000` and `http://test2.fabrikam.com:9000` are the only base addresses for their respective schemes which are allowed to be passed through.</span></span>  
  
 <span data-ttu-id="5319c-136">Если префикс не задан, по умолчанию пропускаются все адреса.</span><span class="sxs-lookup"><span data-stu-id="5319c-136">By default, when prefix is not specified, all addresses are passed through.</span></span> <span data-ttu-id="5319c-137">При задании префикса разрешается прохождение данных только с соответствующего базового адреса для данной схемы.</span><span class="sxs-lookup"><span data-stu-id="5319c-137">Specifying the prefix only allows the matching base address for that scheme to be passed through.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5319c-138">Фильтр не поддерживает какие-либо подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="5319c-138">The filter does not support any wildcards.</span></span> <span data-ttu-id="5319c-139">Кроме того, среди базовых адресов, предоставляемых IIS, могут присутствовать адреса, привязанные к другим схемам, не представленным в списке `baseAddressPrefixFilters`.</span><span class="sxs-lookup"><span data-stu-id="5319c-139">In addition, the baseAddresses supplied by IIS may have addresses bound to other schemes not present in the `baseAddressPrefixFilters` list.</span></span> <span data-ttu-id="5319c-140">Эти адреса не фильтруются.</span><span class="sxs-lookup"><span data-stu-id="5319c-140">These addresses are not filtered out.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5319c-141">См. также</span><span class="sxs-lookup"><span data-stu-id="5319c-141">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BaseAddressPrefixFilterElement>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>  
 [<span data-ttu-id="5319c-142">Размещение</span><span class="sxs-lookup"><span data-stu-id="5319c-142">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
