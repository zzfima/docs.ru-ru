---
title: '&lt;add&gt; для &lt;baseAddressPrefixFilter&gt;'
ms.date: 03/30/2017
ms.assetid: b226bede-8459-4de9-b2ac-3d39604ce2bc
ms.openlocfilehash: ece3178c48c84c609ab959a5cfc426062de9255f
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145605"
---
# <a name="ltaddgt-of-ltbaseaddressprefixfiltergt"></a><span data-ttu-id="fb504-102">&lt;add&gt; для &lt;baseAddressPrefixFilter&gt;</span><span class="sxs-lookup"><span data-stu-id="fb504-102">&lt;add&gt; of &lt;baseAddressPrefixFilter&gt;</span></span>
<span data-ttu-id="fb504-103">Представляет элемент конфигурации, в котором указывается сквозной фильтр, который предоставляет механизм для выбора необходимых привязок служб Internet Information Services (IIS), при размещении приложения Windows Communication Foundation (WCF) в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="fb504-103">Represents a configuration element that specifies a pass-through filter, which provides a mechanism to pick the appropriate Internet Information Services (IIS) bindings when hosting a Windows Communication Foundation (WCF) application in IIS.</span></span>  
  
 <span data-ttu-id="fb504-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="fb504-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="fb504-105">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="fb504-105">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="fb504-106">\<baseAddressPrefixFilters ></span><span class="sxs-lookup"><span data-stu-id="fb504-106">\<baseAddressPrefixFilters></span></span>  
<span data-ttu-id="fb504-107">\<add></span><span class="sxs-lookup"><span data-stu-id="fb504-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb504-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fb504-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <baseAddressPrefixFilters>
    <add prefix="String" />
  </baseAddressPrefixFilters>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fb504-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="fb504-109">Attributes and Elements</span></span>  
 <span data-ttu-id="fb504-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="fb504-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fb504-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="fb504-111">Attributes</span></span>  
  
|<span data-ttu-id="fb504-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="fb504-112">Attribute</span></span>|<span data-ttu-id="fb504-113">Описание</span><span class="sxs-lookup"><span data-stu-id="fb504-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fb504-114">prefix</span><span class="sxs-lookup"><span data-stu-id="fb504-114">prefix</span></span>|<span data-ttu-id="fb504-115">Универсальный код ресурса (URI), совпадающий с частью базового адреса.</span><span class="sxs-lookup"><span data-stu-id="fb504-115">A URI that is used to match a part of a base address.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fb504-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="fb504-116">Child Elements</span></span>  
 <span data-ttu-id="fb504-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="fb504-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fb504-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="fb504-118">Parent Elements</span></span>  
  
|<span data-ttu-id="fb504-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="fb504-119">Element</span></span>|<span data-ttu-id="fb504-120">Описание:</span><span class="sxs-lookup"><span data-stu-id="fb504-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fb504-121">\<baseAddressPrefixFilters ></span><span class="sxs-lookup"><span data-stu-id="fb504-121">\<baseAddressPrefixFilters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddressprefixfilters.md)|<span data-ttu-id="fb504-122">Коллекция элементов конфигурации, которые задают проходные фильтры, которые предоставляют механизм выбора необходимых привязок служб IIS при размещении приложения Windows Communication Foundation (WCF) в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="fb504-122">A collection of configuration elements that specify pass-through filters, which provide a mechanism to pick the appropriate IIS bindings when hosting a Windows Communication Foundation (WCF) application in IIS.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fb504-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="fb504-123">Remarks</span></span>  
 <span data-ttu-id="fb504-124">Префиксный фильтр предоставляет способ для общих поставщиков услуг размещения задать, какие URI должны использоваться службой.</span><span class="sxs-lookup"><span data-stu-id="fb504-124">A prefix filter provides a way for shared hosting providers to specify which URIs are to be used by the service.</span></span> <span data-ttu-id="fb504-125">Это дает возможность общим узлам размещать несколько приложений с разными базовыми адресами для одной схемы на одном узле.</span><span class="sxs-lookup"><span data-stu-id="fb504-125">It enables shared hosts to host multiple applications with different base addresses for the same scheme on the same site.</span></span>  
  
 <span data-ttu-id="fb504-126">Веб-узлы IIS являются контейнерами виртуальных приложений, содержащими виртуальные каталоги.</span><span class="sxs-lookup"><span data-stu-id="fb504-126">IIS Web sites are containers for virtual applications which contain virtual directories.</span></span> <span data-ttu-id="fb504-127">Доступ к приложению на узле можно осуществлять через одну или несколько привязок IIS.</span><span class="sxs-lookup"><span data-stu-id="fb504-127">The application in a site can be accessed through one or more IIS binding.</span></span> <span data-ttu-id="fb504-128">Привязки IIS предоставляют два блока данных: протокол привязки и данные привязки.</span><span class="sxs-lookup"><span data-stu-id="fb504-128">IIS bindings provide two pieces of information: binding protocol and binding information.</span></span> <span data-ttu-id="fb504-129">Протокол привязки (например, HTTP) определяет схему, посредством которой осуществляется связь, а данные привязки (например, IP-адрес, порт, заголовок узла) содержат сведения, используемые для доступа к узлу.</span><span class="sxs-lookup"><span data-stu-id="fb504-129">Binding protocol (for example, HTTP) defines the scheme over which communication occurs, and binding information (for example, IP Address, Port, Hostheader) contains data used to access the site.</span></span>  
  
 <span data-ttu-id="fb504-130">IIS поддерживает задание нескольких привязок IIS для каждого узла, что позволяет использовать несколько базовых адресов для каждой схемы.</span><span class="sxs-lookup"><span data-stu-id="fb504-130">IIS supports specifying multiple IIS bindings for each site, which results in multiple base addresses for each scheme.</span></span> <span data-ttu-id="fb504-131">Так как служба WCF, размещаемая на узле разрешает привязку только к одному базовому адресу для каждой схемы, чтобы выбрать необходимый базовый адрес размещенной службы можно использовать возможность префиксного фильтра.</span><span class="sxs-lookup"><span data-stu-id="fb504-131">Because a WCF service hosted under a site allows binding to only one base address for each scheme, you can use the prefix filter feature to pick the required base address of the hosted service.</span></span> <span data-ttu-id="fb504-132">Входящие базовые адреса, предоставляемые IIS, фильтруются с использованием дополнительного фильтра списка префиксов.</span><span class="sxs-lookup"><span data-stu-id="fb504-132">The incoming base addresses, supplied by IIS, are filtered based on the optional prefix list filter.</span></span>  
  
 <span data-ttu-id="fb504-133">Например, узел может содержать следующие базовые адреса.</span><span class="sxs-lookup"><span data-stu-id="fb504-133">For example, your site can contain the following base addresses.</span></span>  
  
```  
http://testl.fabrikam.com/Service.svc  
http://test2.fabrikam.com/Service.svc  
```  
  
 <span data-ttu-id="fb504-134">Для задания префиксного фильтра на уровне домена приложений можно использовать следующий файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="fb504-134">You can use the following configuration file to specify a prefix filter at the appdomain level.</span></span>  
  
```xml  
<system.serviceModel>
  <serviceHostingEnvironment>
    <baseAddressPrefixFilters>
      <add prefix="net.tcp://test1.fabrikam.com:8000" />
      <add prefix="http://test2.fabrikam.com:9000" />
    </baseAddressPrefixFilters>
  </serviceHostingEnvironment>
</system.serviceModel>
```  
  
 <span data-ttu-id="fb504-135">В этом примере `net.tcp://test1.fabrikam.com:8000` и `http://test2.fabrikam.com:9000` являются единственными базовыми адресами соответствующих схем, для которых разрешено прохождение данных.</span><span class="sxs-lookup"><span data-stu-id="fb504-135">In this example, `net.tcp://test1.fabrikam.com:8000` and `http://test2.fabrikam.com:9000` are the only base addresses for their respective schemes which are allowed to be passed through.</span></span>  
  
 <span data-ttu-id="fb504-136">Если префикс не задан, по умолчанию пропускаются все адреса.</span><span class="sxs-lookup"><span data-stu-id="fb504-136">By default, when prefix is not specified, all addresses are passed through.</span></span> <span data-ttu-id="fb504-137">При задании префикса разрешается прохождение данных только с соответствующего базового адреса для данной схемы.</span><span class="sxs-lookup"><span data-stu-id="fb504-137">Specifying the prefix only allows the matching base address for that scheme to be passed through.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fb504-138">Фильтр не поддерживает какие-либо подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="fb504-138">The filter does not support any wildcards.</span></span> <span data-ttu-id="fb504-139">Кроме того, среди базовых адресов, предоставляемых IIS, могут присутствовать адреса, привязанные к другим схемам, не представленным в списке `baseAddressPrefixFilters`.</span><span class="sxs-lookup"><span data-stu-id="fb504-139">In addition, the baseAddresses supplied by IIS may have addresses bound to other schemes not present in the `baseAddressPrefixFilters` list.</span></span> <span data-ttu-id="fb504-140">Эти адреса не фильтруются.</span><span class="sxs-lookup"><span data-stu-id="fb504-140">These addresses are not filtered out.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb504-141">См. также</span><span class="sxs-lookup"><span data-stu-id="fb504-141">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BaseAddressPrefixFilterElement>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>  
 [<span data-ttu-id="fb504-142">Размещение</span><span class="sxs-lookup"><span data-stu-id="fb504-142">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
