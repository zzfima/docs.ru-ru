---
title: <host>
ms.date: 03/30/2017
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
ms.openlocfilehash: b764bc21e9c4555b39c3d096212b6e6bcabb62ff
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855209"
---
# <a name="host"></a><span data-ttu-id="82b20-101">\<> узла</span><span class="sxs-lookup"><span data-stu-id="82b20-101">\<host></span></span>
<span data-ttu-id="82b20-102">Задает параметры узла службы.</span><span class="sxs-lookup"><span data-stu-id="82b20-102">Specifies settings for a service host.</span></span>  
  
<span data-ttu-id="82b20-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="82b20-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="82b20-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="82b20-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="82b20-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<службы >** ](services.md)</span><span class="sxs-lookup"><span data-stu-id="82b20-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)</span></span>\
<span data-ttu-id="82b20-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> службы**](service.md)</span><span class="sxs-lookup"><span data-stu-id="82b20-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)</span></span>\
<span data-ttu-id="82b20-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> узла**</span><span class="sxs-lookup"><span data-stu-id="82b20-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<host>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82b20-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="82b20-108">Syntax</span></span>  
  
```xml  
<host>
  <baseAddresses>
    <add baseAddress="string" />
  </baseAddresses>
  <timeOuts closeTimeout="TimeSpan"
            openTimeout="TimeSpan" />
</host>
```  
  
## <a name="type"></a><span data-ttu-id="82b20-109">Тип</span><span class="sxs-lookup"><span data-stu-id="82b20-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="82b20-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="82b20-110">Attributes and Elements</span></span>  
 <span data-ttu-id="82b20-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="82b20-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="82b20-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="82b20-112">Attributes</span></span>  
 <span data-ttu-id="82b20-113">Нет.</span><span class="sxs-lookup"><span data-stu-id="82b20-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="82b20-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="82b20-114">Child Elements</span></span>  
  
|<span data-ttu-id="82b20-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="82b20-115">Element</span></span>|<span data-ttu-id="82b20-116">Описание</span><span class="sxs-lookup"><span data-stu-id="82b20-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="82b20-117">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="82b20-117">\<baseAddresses></span></span>](baseaddresses.md)|<span data-ttu-id="82b20-118">Коллекция элементов`baseAddress`, которая задает базовые адреса, используемые узлом службы.</span><span class="sxs-lookup"><span data-stu-id="82b20-118">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[<span data-ttu-id="82b20-119">\<> времени ожидания</span><span class="sxs-lookup"><span data-stu-id="82b20-119">\<timeOuts></span></span>](timeouts.md)|<span data-ttu-id="82b20-120">Элемент конфигурации, задающий допустимый интервал времени для открытия или закрытия узла службы.</span><span class="sxs-lookup"><span data-stu-id="82b20-120">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="82b20-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="82b20-121">Parent Elements</span></span>  
  
|<span data-ttu-id="82b20-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="82b20-122">Element</span></span>|<span data-ttu-id="82b20-123">Описание</span><span class="sxs-lookup"><span data-stu-id="82b20-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="82b20-124">\<> службы</span><span class="sxs-lookup"><span data-stu-id="82b20-124">\<service></span></span>](service.md)|<span data-ttu-id="82b20-125">Задает параметры для службы Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="82b20-125">Specifies the settings for a Windows Communication Foundation (WCF) service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="82b20-126">См. также</span><span class="sxs-lookup"><span data-stu-id="82b20-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="82b20-127">Размещение</span><span class="sxs-lookup"><span data-stu-id="82b20-127">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
