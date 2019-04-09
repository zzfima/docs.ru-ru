---
title: <services>
ms.date: 03/30/2017
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
ms.openlocfilehash: 2db168d48e3959a7d80a10ca27134f58e3fcb2de
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59168081"
---
# <a name="services"></a><span data-ttu-id="87131-101">\<Services ></span><span class="sxs-lookup"><span data-stu-id="87131-101">\<services></span></span>
<span data-ttu-id="87131-102">Службы задаются в разделе `services` файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="87131-102">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="87131-103">Для каждой службы используется собственный раздел конфигурации `service`.</span><span class="sxs-lookup"><span data-stu-id="87131-103">Each service has its own `service` configuration section.</span></span>  
  
 <span data-ttu-id="87131-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="87131-104">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87131-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="87131-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service>
    </service>
  </services>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="87131-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="87131-106">Attributes and Elements</span></span>  
 <span data-ttu-id="87131-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="87131-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="87131-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="87131-108">Attributes</span></span>  
 <span data-ttu-id="87131-109">Нет</span><span class="sxs-lookup"><span data-stu-id="87131-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="87131-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="87131-110">Child Elements</span></span>  
  
|<span data-ttu-id="87131-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="87131-111">Element</span></span>|<span data-ttu-id="87131-112">Описание</span><span class="sxs-lookup"><span data-stu-id="87131-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="87131-113">\<службы ></span><span class="sxs-lookup"><span data-stu-id="87131-113">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="87131-114">Определяет контракт службы, поведение и конечные точки конкретной службы.</span><span class="sxs-lookup"><span data-stu-id="87131-114">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="87131-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="87131-115">Parent Elements</span></span>  
  
|<span data-ttu-id="87131-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="87131-116">Element</span></span>|<span data-ttu-id="87131-117">Описание</span><span class="sxs-lookup"><span data-stu-id="87131-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="87131-118">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="87131-118">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="87131-119">Корневой элемент всех элементов конфигурации Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="87131-119">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="87131-120">См. также</span><span class="sxs-lookup"><span data-stu-id="87131-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServicesSection>
