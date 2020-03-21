---
title: <baseAddressPrefixFilters>
ms.date: 03/30/2017
ms.assetid: 8cab2a9a-c51f-4283-bb60-2ad0c274fd46
ms.openlocfilehash: 0673507b72690c3a5c7dcc35442c05e378dba43c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153039"
---
# <a name="baseaddressprefixfilters"></a><span data-ttu-id="cb130-101">\<baseAddressPrefixФильтрs></span><span class="sxs-lookup"><span data-stu-id="cb130-101">\<baseAddressPrefixFilters></span></span>
<span data-ttu-id="cb130-102">Представляет собой набор элементов конфигурации, которые указывают пройти через фильтры, которые обеспечивают механизм для выбора соответствующих Интернет-информационных услуг (IIS) привязки при хостинге Windows Communication Foundation (WCF) приложение в IIS.</span><span class="sxs-lookup"><span data-stu-id="cb130-102">Represents a collection of configuration elements that specify pass through filters, which provide a mechanism to pick the appropriate Internet Information Services (IIS) bindings when hosting the Windows Communication Foundation (WCF) application in IIS.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="cb130-103">\<baseAddressPrefixFilters> не признает "местный хозяин"; использовать полностью квалифицированное название машины вместо.</span><span class="sxs-lookup"><span data-stu-id="cb130-103">\<baseAddressPrefixFilters> does not recognize "localhost"; use the fully qualified machine name instead.</span></span>  
  
<span data-ttu-id="cb130-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="cb130-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="cb130-105">&nbsp;&nbsp;[**\<system.serviceМодель>**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="cb130-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="cb130-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)</span><span class="sxs-lookup"><span data-stu-id="cb130-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)</span></span>\
<span data-ttu-id="cb130-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<baseAddressPrefixФильтрs>**</span><span class="sxs-lookup"><span data-stu-id="cb130-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<baseAddressPrefixFilters>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb130-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cb130-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <baseAddressPrefixFilters>
    <add prefix="String" />
   </baseAddressPrefixFilters>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cb130-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="cb130-109">Attributes and Elements</span></span>  
 <span data-ttu-id="cb130-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="cb130-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cb130-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="cb130-111">Attributes</span></span>  
 <span data-ttu-id="cb130-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="cb130-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cb130-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="cb130-113">Child Elements</span></span>  
  
|<span data-ttu-id="cb130-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="cb130-114">Element</span></span>|<span data-ttu-id="cb130-115">Описание</span><span class="sxs-lookup"><span data-stu-id="cb130-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cb130-116">\<добавить></span><span class="sxs-lookup"><span data-stu-id="cb130-116">\<add></span></span>](add-of-baseaddressprefixfilter.md)|<span data-ttu-id="cb130-117">Добавляет элемент конфигурации, который задает префиксный фильтр для базовых адресов, используемых узлом службы.</span><span class="sxs-lookup"><span data-stu-id="cb130-117">Adds a configuration element that specifies a prefix filter for the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cb130-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="cb130-118">Parent Elements</span></span>  
  
|<span data-ttu-id="cb130-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="cb130-119">Element</span></span>|<span data-ttu-id="cb130-120">Описание</span><span class="sxs-lookup"><span data-stu-id="cb130-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cb130-121">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="cb130-121">\<serviceHostingEnvironment></span></span>](servicehostingenvironment.md)|<span data-ttu-id="cb130-122">Определяет, какой тип среда размещения служб создает для конкретного транспорта.</span><span class="sxs-lookup"><span data-stu-id="cb130-122">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cb130-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="cb130-123">Remarks</span></span>  
 <span data-ttu-id="cb130-124">Префиксный фильтр предоставляет способ для общих поставщиков услуг размещения задать, какие URI должны использоваться службой.</span><span class="sxs-lookup"><span data-stu-id="cb130-124">A prefix filter provides a way for shared hosting providers to specify which URIs are to be used by the service.</span></span> <span data-ttu-id="cb130-125">Это дает возможность общим узлам размещать несколько приложений с разными базовыми адресами для одной схемы на одном узле.</span><span class="sxs-lookup"><span data-stu-id="cb130-125">It enables shared hosts to host multiple applications with different base addresses for the same scheme on the same site.</span></span>  
  
 <span data-ttu-id="cb130-126">Веб-узлы IIS являются контейнерами виртуальных приложений, содержащими виртуальные каталоги.</span><span class="sxs-lookup"><span data-stu-id="cb130-126">IIS Web sites are containers for virtual applications which contain virtual directories.</span></span> <span data-ttu-id="cb130-127">Доступ к приложению на узле можно осуществлять через одну или несколько привязок службы IIS.</span><span class="sxs-lookup"><span data-stu-id="cb130-127">The application in a site can be accessed through one or more IIS bindings.</span></span> <span data-ttu-id="cb130-128">Привязки IIS предоставляют два блока данных: протокол привязки и данные привязки.</span><span class="sxs-lookup"><span data-stu-id="cb130-128">IIS bindings provide two pieces of information: binding protocol and binding information.</span></span> <span data-ttu-id="cb130-129">Протокол привязки (например, HTTP) определяет схему, посредством которой осуществляется связь, а данные привязки (например, IP-адрес, порт, заголовок узла) содержат сведения, используемые для доступа к узлу.</span><span class="sxs-lookup"><span data-stu-id="cb130-129">Binding protocol (for example, HTTP) defines the scheme over which communication occurs, and binding information (for example, IP Address, Port, Hostheader) contains data used to access the site.</span></span>  
  
 <span data-ttu-id="cb130-130">IIS поддерживает задание нескольких привязок IIS для каждого узла, что позволяет использовать несколько базовых адресов для каждой схемы.</span><span class="sxs-lookup"><span data-stu-id="cb130-130">IIS supports specifying multiple IIS bindings for each site, which results in multiple base addresses for each scheme.</span></span> <span data-ttu-id="cb130-131">Поскольку служба WCF, размещенная под сайтом, позволяет связываться только с одним базовым адресом для каждой схемы, можно использовать функцию фильтра префикса для выбора необходимого базового адреса размещенной службы.</span><span class="sxs-lookup"><span data-stu-id="cb130-131">Because a WCF service hosted under a site allows binding to only one base address for each scheme, you can use the prefix filter feature to pick the required base address of the hosted service.</span></span> <span data-ttu-id="cb130-132">Входящие базовые адреса, предоставляемые IIS, фильтруются с использованием дополнительного фильтра списка префиксов.</span><span class="sxs-lookup"><span data-stu-id="cb130-132">The incoming base addresses, supplied by IIS, are filtered based on the optional prefix list filter.</span></span>  
  
 <span data-ttu-id="cb130-133">Например, ваш сайт может содержать следующие базовые адреса:</span><span class="sxs-lookup"><span data-stu-id="cb130-133">For example, your site can contain the following base addresses:</span></span>
  
```
http://testl.fabrikam.com/Service.svc  
http://test2.fabrikam.com/Service.svc  
```  
  
 <span data-ttu-id="cb130-134">Для задания префиксного фильтра на уровне домена приложений можно использовать следующий файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="cb130-134">You can use the following configuration file to specify a prefix filter at the appdomain level.</span></span>  
  
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
  
 <span data-ttu-id="cb130-135">В этом примере `net.tcp://test1.fabrikam.com:8000` и `http://test2.fabrikam.com:9000` являются единственными базовыми адресами для соответствующих схем, которые могут пропускаться.</span><span class="sxs-lookup"><span data-stu-id="cb130-135">In this example, `net.tcp://test1.fabrikam.com:8000` and `http://test2.fabrikam.com:9000` are the only base addresses for their respective schemes, which are allowed to be passed through.</span></span>  
  
 <span data-ttu-id="cb130-136">Если префикс не задан, по умолчанию пропускаются все адреса.</span><span class="sxs-lookup"><span data-stu-id="cb130-136">By default, when prefix is not specified, all addresses are passed through.</span></span> <span data-ttu-id="cb130-137">При задании префикса разрешается прохождение данных только с соответствующего базового адреса для данной схемы.</span><span class="sxs-lookup"><span data-stu-id="cb130-137">Specifying the prefix only allows the matching base address for that scheme to be passed through.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cb130-138">Фильтр не поддерживает какие-либо подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="cb130-138">The filter does not support any wildcards.</span></span> <span data-ttu-id="cb130-139">Кроме того, среди базовых адресов, предоставляемых IIS, могут присутствовать адреса, привязанные к другим схемам, не представленным в списке `baseAddressPrefixFilters`.</span><span class="sxs-lookup"><span data-stu-id="cb130-139">In addition, the baseAddresses supplied by IIS may have addresses bound to other schemes not present in the `baseAddressPrefixFilters` list.</span></span> <span data-ttu-id="cb130-140">Эти адреса не фильтруются.</span><span class="sxs-lookup"><span data-stu-id="cb130-140">These addresses are not filtered out.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb130-141">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cb130-141">See also</span></span>

- <xref:System.ServiceModel.Configuration.BaseAddressPrefixFilterElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="cb130-142">Размещение</span><span class="sxs-lookup"><span data-stu-id="cb130-142">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
