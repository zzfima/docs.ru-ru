---
title: <services>
ms.date: 03/30/2017
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
ms.openlocfilehash: c00d5fe3e8b2ba05843e09aca6aaa79386541bad
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937192"
---
# <a name="services"></a><span data-ttu-id="0a5a6-101">\<службы ></span><span class="sxs-lookup"><span data-stu-id="0a5a6-101">\<services></span></span>
<span data-ttu-id="0a5a6-102">Службы задаются в разделе `services` файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0a5a6-102">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="0a5a6-103">Для каждой службы используется собственный раздел конфигурации `service`.</span><span class="sxs-lookup"><span data-stu-id="0a5a6-103">Each service has its own `service` configuration section.</span></span>  
  
 <span data-ttu-id="0a5a6-104">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="0a5a6-104">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a5a6-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0a5a6-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service>
    </service>
  </services>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0a5a6-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0a5a6-106">Attributes and Elements</span></span>  
 <span data-ttu-id="0a5a6-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0a5a6-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0a5a6-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0a5a6-108">Attributes</span></span>  
 <span data-ttu-id="0a5a6-109">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="0a5a6-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0a5a6-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0a5a6-110">Child Elements</span></span>  
  
|<span data-ttu-id="0a5a6-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="0a5a6-111">Element</span></span>|<span data-ttu-id="0a5a6-112">Описание</span><span class="sxs-lookup"><span data-stu-id="0a5a6-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0a5a6-113">\<> службы</span><span class="sxs-lookup"><span data-stu-id="0a5a6-113">\<service></span></span>](service.md)|<span data-ttu-id="0a5a6-114">Определяет контракт службы, поведение и конечные точки конкретной службы.</span><span class="sxs-lookup"><span data-stu-id="0a5a6-114">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0a5a6-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0a5a6-115">Parent Elements</span></span>  
  
|<span data-ttu-id="0a5a6-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="0a5a6-116">Element</span></span>|<span data-ttu-id="0a5a6-117">Описание</span><span class="sxs-lookup"><span data-stu-id="0a5a6-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0a5a6-118">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="0a5a6-118">\<system.serviceModel></span></span>](system-servicemodel.md)|<span data-ttu-id="0a5a6-119">Корневой элемент всех элементов конфигурации Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="0a5a6-119">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0a5a6-120">См. также</span><span class="sxs-lookup"><span data-stu-id="0a5a6-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServicesSection>
