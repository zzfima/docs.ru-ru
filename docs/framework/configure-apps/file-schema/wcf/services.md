---
title: <services>
ms.date: 03/30/2017
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
ms.openlocfilehash: 02d1d530f37f5082153c9aa6b9993fc4009917f5
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854976"
---
# <a name="services"></a><span data-ttu-id="265f5-101">\<службы ></span><span class="sxs-lookup"><span data-stu-id="265f5-101">\<services></span></span>
<span data-ttu-id="265f5-102">Службы задаются в разделе `services` файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="265f5-102">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="265f5-103">Для каждой службы используется собственный раздел конфигурации `service`.</span><span class="sxs-lookup"><span data-stu-id="265f5-103">Each service has its own `service` configuration section.</span></span>  
  
<span data-ttu-id="265f5-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="265f5-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="265f5-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="265f5-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="265f5-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<службы >**</span><span class="sxs-lookup"><span data-stu-id="265f5-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<services>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="265f5-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="265f5-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service>
    </service>
  </services>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="265f5-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="265f5-108">Attributes and Elements</span></span>  
 <span data-ttu-id="265f5-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="265f5-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="265f5-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="265f5-110">Attributes</span></span>  
 <span data-ttu-id="265f5-111">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="265f5-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="265f5-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="265f5-112">Child Elements</span></span>  
  
|<span data-ttu-id="265f5-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="265f5-113">Element</span></span>|<span data-ttu-id="265f5-114">Описание</span><span class="sxs-lookup"><span data-stu-id="265f5-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="265f5-115">\<> службы</span><span class="sxs-lookup"><span data-stu-id="265f5-115">\<service></span></span>](service.md)|<span data-ttu-id="265f5-116">Определяет контракт службы, поведение и конечные точки конкретной службы.</span><span class="sxs-lookup"><span data-stu-id="265f5-116">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="265f5-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="265f5-117">Parent Elements</span></span>  
  
|<span data-ttu-id="265f5-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="265f5-118">Element</span></span>|<span data-ttu-id="265f5-119">Описание</span><span class="sxs-lookup"><span data-stu-id="265f5-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="265f5-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="265f5-120">\<system.serviceModel></span></span>](system-servicemodel.md)|<span data-ttu-id="265f5-121">Корневой элемент всех элементов конфигурации Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="265f5-121">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="265f5-122">См. также</span><span class="sxs-lookup"><span data-stu-id="265f5-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServicesSection>
