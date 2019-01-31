---
title: <services>
ms.date: 03/30/2017
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
ms.openlocfilehash: 4dc425fa97eaf99664f0d9bbbbc851c462cbf373
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55274967"
---
# <a name="services"></a><span data-ttu-id="d6c3c-101">\<Services ></span><span class="sxs-lookup"><span data-stu-id="d6c3c-101">\<services></span></span>
<span data-ttu-id="d6c3c-102">Службы задаются в разделе `services` файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d6c3c-102">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="d6c3c-103">Для каждой службы используется собственный раздел конфигурации `service`.</span><span class="sxs-lookup"><span data-stu-id="d6c3c-103">Each service has its own `service` configuration section.</span></span>  
  
 <span data-ttu-id="d6c3c-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d6c3c-104">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6c3c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d6c3c-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service>
    </service>
  </services>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d6c3c-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d6c3c-106">Attributes and Elements</span></span>  
 <span data-ttu-id="d6c3c-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d6c3c-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d6c3c-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d6c3c-108">Attributes</span></span>  
 <span data-ttu-id="d6c3c-109">Нет</span><span class="sxs-lookup"><span data-stu-id="d6c3c-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d6c3c-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d6c3c-110">Child Elements</span></span>  
  
|<span data-ttu-id="d6c3c-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="d6c3c-111">Element</span></span>|<span data-ttu-id="d6c3c-112">Описание:</span><span class="sxs-lookup"><span data-stu-id="d6c3c-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d6c3c-113">\<службы ></span><span class="sxs-lookup"><span data-stu-id="d6c3c-113">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="d6c3c-114">Определяет контракт службы, поведение и конечные точки конкретной службы.</span><span class="sxs-lookup"><span data-stu-id="d6c3c-114">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d6c3c-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d6c3c-115">Parent Elements</span></span>  
  
|<span data-ttu-id="d6c3c-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="d6c3c-116">Element</span></span>|<span data-ttu-id="d6c3c-117">Описание:</span><span class="sxs-lookup"><span data-stu-id="d6c3c-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d6c3c-118">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d6c3c-118">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="d6c3c-119">Корневой элемент всех элементов конфигурации Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="d6c3c-119">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d6c3c-120">См. также</span><span class="sxs-lookup"><span data-stu-id="d6c3c-120">See also</span></span>
- <xref:System.ServiceModel.Configuration.ServicesSection>
