---
title: <add> из <baseAddressPrefixFilter>
ms.date: 03/30/2017
ms.assetid: b226bede-8459-4de9-b2ac-3d39604ce2bc
ms.openlocfilehash: 809e6d5504b56f86eb09a5d57931f922e1c18348
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73973813"
---
# <a name="add-of-baseaddressprefixfilter"></a><span data-ttu-id="dbdd0-102">\<Добавить > \<Басеаддресспрефиксфилтер ></span><span class="sxs-lookup"><span data-stu-id="dbdd0-102">\<add> of \<baseAddressPrefixFilter></span></span>
<span data-ttu-id="dbdd0-103">Представляет элемент конфигурации, указывающий сквозной фильтр, который предоставляет механизм для выбора соответствующих привязок службы IIS (IIS) при размещении приложения Windows Communication Foundation (WCF) в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="dbdd0-103">Represents a configuration element that specifies a pass-through filter, which provides a mechanism to pick the appropriate Internet Information Services (IIS) bindings when hosting a Windows Communication Foundation (WCF) application in IIS.</span></span>  
  
<span data-ttu-id="dbdd0-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="dbdd0-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="dbdd0-105">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="dbdd0-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="dbdd0-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceHostingEnvironment >** ](servicehostingenvironment.md)</span><span class="sxs-lookup"><span data-stu-id="dbdd0-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)</span></span>\
<span data-ttu-id="dbdd0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<baseAddressPrefixFilters >** ](baseaddressprefixfilters.md)</span><span class="sxs-lookup"><span data-stu-id="dbdd0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<baseAddressPrefixFilters>**](baseaddressprefixfilters.md)</span></span>\
<span data-ttu-id="dbdd0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<добавить >**</span><span class="sxs-lookup"><span data-stu-id="dbdd0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbdd0-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dbdd0-109">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <baseAddressPrefixFilters>
    <add prefix="String" />
  </baseAddressPrefixFilters>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dbdd0-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="dbdd0-110">Attributes and Elements</span></span>  
 <span data-ttu-id="dbdd0-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="dbdd0-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dbdd0-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="dbdd0-112">Attributes</span></span>  
  
|<span data-ttu-id="dbdd0-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="dbdd0-113">Attribute</span></span>|<span data-ttu-id="dbdd0-114">Описание</span><span class="sxs-lookup"><span data-stu-id="dbdd0-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dbdd0-115">prefix</span><span class="sxs-lookup"><span data-stu-id="dbdd0-115">prefix</span></span>|<span data-ttu-id="dbdd0-116">Универсальный код ресурса (URI), совпадающий с частью базового адреса.</span><span class="sxs-lookup"><span data-stu-id="dbdd0-116">A URI that is used to match a part of a base address.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dbdd0-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="dbdd0-117">Child Elements</span></span>  
 <span data-ttu-id="dbdd0-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="dbdd0-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dbdd0-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="dbdd0-119">Parent Elements</span></span>  
  
|<span data-ttu-id="dbdd0-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="dbdd0-120">Element</span></span>|<span data-ttu-id="dbdd0-121">Описание</span><span class="sxs-lookup"><span data-stu-id="dbdd0-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dbdd0-122">\<baseAddressPrefixFilters ></span><span class="sxs-lookup"><span data-stu-id="dbdd0-122">\<baseAddressPrefixFilters></span></span>](baseaddressprefixfilters.md)|<span data-ttu-id="dbdd0-123">Коллекция элементов конфигурации, задающих сквозные фильтры, которые предоставляют механизм для выбора соответствующих привязок IIS при размещении приложения Windows Communication Foundation (WCF) в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="dbdd0-123">A collection of configuration elements that specify pass-through filters, which provide a mechanism to pick the appropriate IIS bindings when hosting a Windows Communication Foundation (WCF) application in IIS.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dbdd0-124">Заметки</span><span class="sxs-lookup"><span data-stu-id="dbdd0-124">Remarks</span></span>  
 <span data-ttu-id="dbdd0-125">Префиксный фильтр предоставляет способ для общих поставщиков услуг размещения задать, какие URI должны использоваться службой.</span><span class="sxs-lookup"><span data-stu-id="dbdd0-125">A prefix filter provides a way for shared hosting providers to specify which URIs are to be used by the service.</span></span> <span data-ttu-id="dbdd0-126">Это дает возможность общим узлам размещать несколько приложений с разными базовыми адресами для одной схемы на одном узле.</span><span class="sxs-lookup"><span data-stu-id="dbdd0-126">It enables shared hosts to host multiple applications with different base addresses for the same scheme on the same site.</span></span>  
  
 <span data-ttu-id="dbdd0-127">Веб-узлы IIS являются контейнерами виртуальных приложений, содержащими виртуальные каталоги.</span><span class="sxs-lookup"><span data-stu-id="dbdd0-127">IIS Web sites are containers for virtual applications which contain virtual directories.</span></span> <span data-ttu-id="dbdd0-128">Доступ к приложению на узле можно осуществлять через одну или несколько привязок IIS.</span><span class="sxs-lookup"><span data-stu-id="dbdd0-128">The application in a site can be accessed through one or more IIS binding.</span></span> <span data-ttu-id="dbdd0-129">Привязки IIS предоставляют два блока данных: протокол привязки и данные привязки.</span><span class="sxs-lookup"><span data-stu-id="dbdd0-129">IIS bindings provide two pieces of information: binding protocol and binding information.</span></span> <span data-ttu-id="dbdd0-130">Протокол привязки (например, HTTP) определяет схему, посредством которой осуществляется связь, а данные привязки (например, IP-адрес, порт, заголовок узла) содержат сведения, используемые для доступа к узлу.</span><span class="sxs-lookup"><span data-stu-id="dbdd0-130">Binding protocol (for example, HTTP) defines the scheme over which communication occurs, and binding information (for example, IP Address, Port, Hostheader) contains data used to access the site.</span></span>  
  
 <span data-ttu-id="dbdd0-131">IIS поддерживает задание нескольких привязок IIS для каждого узла, что позволяет использовать несколько базовых адресов для каждой схемы.</span><span class="sxs-lookup"><span data-stu-id="dbdd0-131">IIS supports specifying multiple IIS bindings for each site, which results in multiple base addresses for each scheme.</span></span> <span data-ttu-id="dbdd0-132">Так как служба WCF, размещенная на сайте, допускает привязку только к одному базовому адресу для каждой схемы, можно использовать функцию фильтрации префиксов, чтобы выбрать необходимый базовый адрес размещенной службы.</span><span class="sxs-lookup"><span data-stu-id="dbdd0-132">Because a WCF service hosted under a site allows binding to only one base address for each scheme, you can use the prefix filter feature to pick the required base address of the hosted service.</span></span> <span data-ttu-id="dbdd0-133">Входящие базовые адреса, предоставляемые IIS, фильтруются с использованием дополнительного фильтра списка префиксов.</span><span class="sxs-lookup"><span data-stu-id="dbdd0-133">The incoming base addresses, supplied by IIS, are filtered based on the optional prefix list filter.</span></span>  
  
 <span data-ttu-id="dbdd0-134">Например, сайт может содержать следующие базовые адреса:</span><span class="sxs-lookup"><span data-stu-id="dbdd0-134">For example, your site can contain the following base addresses:</span></span>
  
``` 
http://testl.fabrikam.com/Service.svc  
http://test2.fabrikam.com/Service.svc  
```  
  
 <span data-ttu-id="dbdd0-135">Для задания префиксного фильтра на уровне домена приложений можно использовать следующий файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="dbdd0-135">You can use the following configuration file to specify a prefix filter at the appdomain level.</span></span>  
  
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
  
 <span data-ttu-id="dbdd0-136">В этом примере `net.tcp://test1.fabrikam.com:8000` и `http://test2.fabrikam.com:9000` являются единственными базовыми адресами соответствующих схем, для которых разрешено прохождение данных.</span><span class="sxs-lookup"><span data-stu-id="dbdd0-136">In this example, `net.tcp://test1.fabrikam.com:8000` and `http://test2.fabrikam.com:9000` are the only base addresses for their respective schemes which are allowed to be passed through.</span></span>  
  
 <span data-ttu-id="dbdd0-137">Если префикс не задан, по умолчанию пропускаются все адреса.</span><span class="sxs-lookup"><span data-stu-id="dbdd0-137">By default, when prefix is not specified, all addresses are passed through.</span></span> <span data-ttu-id="dbdd0-138">При задании префикса разрешается прохождение данных только с соответствующего базового адреса для данной схемы.</span><span class="sxs-lookup"><span data-stu-id="dbdd0-138">Specifying the prefix only allows the matching base address for that scheme to be passed through.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dbdd0-139">Фильтр не поддерживает какие-либо подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="dbdd0-139">The filter does not support any wildcards.</span></span> <span data-ttu-id="dbdd0-140">Кроме того, среди базовых адресов, предоставляемых IIS, могут присутствовать адреса, привязанные к другим схемам, не представленным в списке `baseAddressPrefixFilters`.</span><span class="sxs-lookup"><span data-stu-id="dbdd0-140">In addition, the baseAddresses supplied by IIS may have addresses bound to other schemes not present in the `baseAddressPrefixFilters` list.</span></span> <span data-ttu-id="dbdd0-141">Эти адреса не фильтруются.</span><span class="sxs-lookup"><span data-stu-id="dbdd0-141">These addresses are not filtered out.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbdd0-142">См. также</span><span class="sxs-lookup"><span data-stu-id="dbdd0-142">See also</span></span>

- <xref:System.ServiceModel.Configuration.BaseAddressPrefixFilterElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="dbdd0-143">Размещение</span><span class="sxs-lookup"><span data-stu-id="dbdd0-143">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
