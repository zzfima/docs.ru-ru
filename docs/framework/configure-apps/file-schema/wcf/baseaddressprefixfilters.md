---
title: '&lt;baseAddressPrefixFilters&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8cab2a9a-c51f-4283-bb60-2ad0c274fd46
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 39ceaf3377f1da7f3f953024e1207618df84bf1d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltbaseaddressprefixfiltersgt"></a><span data-ttu-id="4b3d3-102">&lt;baseAddressPrefixFilters&gt;</span><span class="sxs-lookup"><span data-stu-id="4b3d3-102">&lt;baseAddressPrefixFilters&gt;</span></span>
<span data-ttu-id="4b3d3-103">Представляет коллекцию элементов конфигурации, которые задают фильтры, предоставляющие механизм выбора соответствующих привязок служб IIS при размещении [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] в службе IIS.</span><span class="sxs-lookup"><span data-stu-id="4b3d3-103">Represents a collection of configuration elements that specify pass through filters, which provide a mechanism to pick the appropriate Internet Information Services (IIS) bindings when hosting the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] application in IIS.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="4b3d3-104">\<baseAddressPrefixFilters > не распознает «localhost», используйте полное имя компьютера.</span><span class="sxs-lookup"><span data-stu-id="4b3d3-104">\<baseAddressPrefixFilters> does not recognize "localhost", use the fully qualified machine name instead.</span></span>  
  
 <span data-ttu-id="4b3d3-105">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="4b3d3-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="4b3d3-106">\<ServiceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="4b3d3-106">\<ServiceHostingEnvironment></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b3d3-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4b3d3-107">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>  
     <baseAddressPrefixFilters>  
        <add prefix="string"/>  
     </baseAddressPrefixFilters>  
</serviceHostingEnvironment>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4b3d3-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4b3d3-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4b3d3-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4b3d3-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4b3d3-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4b3d3-110">Attributes</span></span>  
 <span data-ttu-id="4b3d3-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="4b3d3-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4b3d3-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4b3d3-112">Child Elements</span></span>  
  
|<span data-ttu-id="4b3d3-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="4b3d3-113">Element</span></span>|<span data-ttu-id="4b3d3-114">Описание</span><span class="sxs-lookup"><span data-stu-id="4b3d3-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4b3d3-115">\<add></span><span class="sxs-lookup"><span data-stu-id="4b3d3-115">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddressprefixfilter.md)|<span data-ttu-id="4b3d3-116">Добавляет элемент конфигурации, который задает префиксный фильтр для базовых адресов, используемых узлом службы.</span><span class="sxs-lookup"><span data-stu-id="4b3d3-116">Adds a configuration element that specifies a prefix filter for the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4b3d3-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4b3d3-117">Parent Elements</span></span>  
  
|<span data-ttu-id="4b3d3-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="4b3d3-118">Element</span></span>|<span data-ttu-id="4b3d3-119">Описание</span><span class="sxs-lookup"><span data-stu-id="4b3d3-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4b3d3-120">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="4b3d3-120">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="4b3d3-121">Определяет, какой тип среда размещения служб создает для конкретного транспорта.</span><span class="sxs-lookup"><span data-stu-id="4b3d3-121">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4b3d3-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="4b3d3-122">Remarks</span></span>  
 <span data-ttu-id="4b3d3-123">Префиксный фильтр предоставляет способ для общих поставщиков услуг размещения задать, какие URI должны использоваться службой.</span><span class="sxs-lookup"><span data-stu-id="4b3d3-123">A prefix filter provides a way for shared hosting providers to specify which URIs are to be used by the service.</span></span> <span data-ttu-id="4b3d3-124">Это дает возможность общим узлам размещать несколько приложений с разными базовыми адресами для одной схемы на одном узле.</span><span class="sxs-lookup"><span data-stu-id="4b3d3-124">It enables shared hosts to host multiple applications with different base addresses for the same scheme on the same site.</span></span>  
  
 <span data-ttu-id="4b3d3-125">Веб-узлы IIS являются контейнерами виртуальных приложений, содержащими виртуальные каталоги.</span><span class="sxs-lookup"><span data-stu-id="4b3d3-125">IIS Web sites are containers for virtual applications which contain virtual directories.</span></span> <span data-ttu-id="4b3d3-126">Доступ к приложению на узле можно осуществлять через одну или несколько привязок службы IIS.</span><span class="sxs-lookup"><span data-stu-id="4b3d3-126">The application in a site can be accessed through one or more IIS bindings.</span></span> <span data-ttu-id="4b3d3-127">Привязки IIS предоставляют два блока данных: протокол привязки и данные привязки.</span><span class="sxs-lookup"><span data-stu-id="4b3d3-127">IIS bindings provide two pieces of information: binding protocol and binding information.</span></span> <span data-ttu-id="4b3d3-128">Протокол привязки (например, HTTP) определяет схему, посредством которой осуществляется связь, а данные привязки (например, IP-адрес, порт, заголовок узла) содержат сведения, используемые для доступа к узлу.</span><span class="sxs-lookup"><span data-stu-id="4b3d3-128">Binding protocol (for example, HTTP) defines the scheme over which communication occurs, and binding information (for example, IP Address, Port, Hostheader) contains data used to access the site.</span></span>  
  
 <span data-ttu-id="4b3d3-129">IIS поддерживает задание нескольких привязок IIS для каждого узла, что позволяет использовать несколько базовых адресов для каждой схемы.</span><span class="sxs-lookup"><span data-stu-id="4b3d3-129">IIS supports specifying multiple IIS bindings for each site, which results in multiple base addresses for each scheme.</span></span> <span data-ttu-id="4b3d3-130">Поскольку размещаемая на узле служба [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] разрешает привязку только к одному базовому адресу для каждой схемы, можно использовать функцию префиксного фильтра, чтобы выбирать необходимый базовый адрес размещенной службы.</span><span class="sxs-lookup"><span data-stu-id="4b3d3-130">Because a [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] service hosted under a site allows binding to only one base address for each scheme, you can use the prefix filter feature to pick the required base address of the hosted service.</span></span> <span data-ttu-id="4b3d3-131">Входящие базовые адреса, предоставляемые IIS, фильтруются с использованием дополнительного фильтра списка префиксов.</span><span class="sxs-lookup"><span data-stu-id="4b3d3-131">The incoming base addresses, supplied by IIS, are filtered based on the optional prefix list filter.</span></span>  
  
 <span data-ttu-id="4b3d3-132">Например, узел может содержать следующие базовые адреса.</span><span class="sxs-lookup"><span data-stu-id="4b3d3-132">For example, your site can contain the following base addresses.</span></span>  
  
```  
http://testl.fabrikam.com/Service.svc  
http://test2.fabrikam.com/Service.svc  
```  
  
 <span data-ttu-id="4b3d3-133">Для задания префиксного фильтра на уровне домена приложений можно использовать следующий файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="4b3d3-133">You can use the following configuration file to specify a prefix filter at the appdomain level.</span></span>  
  
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
  
 <span data-ttu-id="4b3d3-134">В этом примере `net.tcp://test1.fabrikam.com:8000` и `http://test2.fabrikam.com:9000` являются единственными базовыми адресами для соответствующих схем, которые могут пропускаться.</span><span class="sxs-lookup"><span data-stu-id="4b3d3-134">In this example, `net.tcp://test1.fabrikam.com:8000` and `http://test2.fabrikam.com:9000` are the only base addresses for their respective schemes, which are allowed to be passed through.</span></span>  
  
 <span data-ttu-id="4b3d3-135">Если префикс не задан, по умолчанию пропускаются все адреса.</span><span class="sxs-lookup"><span data-stu-id="4b3d3-135">By default, when prefix is not specified, all addresses are passed through.</span></span> <span data-ttu-id="4b3d3-136">При задании префикса разрешается прохождение данных только с соответствующего базового адреса для данной схемы.</span><span class="sxs-lookup"><span data-stu-id="4b3d3-136">Specifying the prefix only allows the matching base address for that scheme to be passed through.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4b3d3-137">Фильтр не поддерживает какие-либо подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="4b3d3-137">The filter does not support any wildcards.</span></span> <span data-ttu-id="4b3d3-138">Кроме того, среди базовых адресов, предоставляемых IIS, могут присутствовать адреса, привязанные к другим схемам, не представленным в списке `baseAddressPrefixFilters`.</span><span class="sxs-lookup"><span data-stu-id="4b3d3-138">In addition, the baseAddresses supplied by IIS may have addresses bound to other schemes not present in the `baseAddressPrefixFilters` list.</span></span> <span data-ttu-id="4b3d3-139">Эти адреса не фильтруются.</span><span class="sxs-lookup"><span data-stu-id="4b3d3-139">These addresses are not filtered out.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b3d3-140">См. также</span><span class="sxs-lookup"><span data-stu-id="4b3d3-140">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BaseAddressPrefixFilterElementCollection>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>  
 [<span data-ttu-id="4b3d3-141">Размещение</span><span class="sxs-lookup"><span data-stu-id="4b3d3-141">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
