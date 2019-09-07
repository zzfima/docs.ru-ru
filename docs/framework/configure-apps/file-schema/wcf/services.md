---
title: <services>
ms.date: 03/30/2017
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
ms.openlocfilehash: 1f9cb6c95fa14a5b8a55cc561699e2a07e1dc80c
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399588"
---
# <a name="services"></a><span data-ttu-id="69dd3-101">\<службы ></span><span class="sxs-lookup"><span data-stu-id="69dd3-101">\<services></span></span>
<span data-ttu-id="69dd3-102">Службы задаются в разделе `services` файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="69dd3-102">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="69dd3-103">Для каждой службы используется собственный раздел конфигурации `service`.</span><span class="sxs-lookup"><span data-stu-id="69dd3-103">Each service has its own `service` configuration section.</span></span>  
  
<span data-ttu-id="69dd3-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="69dd3-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="69dd3-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="69dd3-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="69dd3-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<службы >**</span><span class="sxs-lookup"><span data-stu-id="69dd3-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<services>**</span></span>  
## <a name="syntax"></a><span data-ttu-id="69dd3-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="69dd3-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service>
    </service>
  </services>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="69dd3-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="69dd3-108">Attributes and Elements</span></span>  
 <span data-ttu-id="69dd3-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="69dd3-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="69dd3-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="69dd3-110">Attributes</span></span>  
 <span data-ttu-id="69dd3-111">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="69dd3-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="69dd3-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="69dd3-112">Child Elements</span></span>  
  
|<span data-ttu-id="69dd3-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="69dd3-113">Element</span></span>|<span data-ttu-id="69dd3-114">Описание</span><span class="sxs-lookup"><span data-stu-id="69dd3-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="69dd3-115">\<> службы</span><span class="sxs-lookup"><span data-stu-id="69dd3-115">\<service></span></span>](service.md)|<span data-ttu-id="69dd3-116">Определяет контракт службы, поведение и конечные точки конкретной службы.</span><span class="sxs-lookup"><span data-stu-id="69dd3-116">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="69dd3-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="69dd3-117">Parent Elements</span></span>  
  
|<span data-ttu-id="69dd3-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="69dd3-118">Element</span></span>|<span data-ttu-id="69dd3-119">Описание</span><span class="sxs-lookup"><span data-stu-id="69dd3-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="69dd3-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="69dd3-120">\<system.serviceModel></span></span>](system-servicemodel.md)|<span data-ttu-id="69dd3-121">Корневой элемент всех элементов конфигурации Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="69dd3-121">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="69dd3-122">См. также</span><span class="sxs-lookup"><span data-stu-id="69dd3-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServicesSection>
