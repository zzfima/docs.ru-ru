---
title: '&lt;Службы&gt;'
ms.date: 03/30/2017
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
ms.openlocfilehash: 789fc52f628174ef61a9c7169cb0cae0f1ba8e31
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32749235"
---
# <a name="ltservicesgt"></a><span data-ttu-id="b9b2b-102">&lt;Службы&gt;</span><span class="sxs-lookup"><span data-stu-id="b9b2b-102">&lt;services&gt;</span></span>
<span data-ttu-id="b9b2b-103">Службы задаются в разделе `services` файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b9b2b-103">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="b9b2b-104">Для каждой службы используется собственный раздел конфигурации `service`.</span><span class="sxs-lookup"><span data-stu-id="b9b2b-104">Each service has its own `service` configuration section.</span></span>  
  
 <span data-ttu-id="b9b2b-105">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="b9b2b-105">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9b2b-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b9b2b-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
        <services>  
        <service>  
        </service>  
        </services>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b9b2b-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b9b2b-107">Attributes and Elements</span></span>  
 <span data-ttu-id="b9b2b-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b9b2b-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b9b2b-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b9b2b-109">Attributes</span></span>  
 <span data-ttu-id="b9b2b-110">Нет</span><span class="sxs-lookup"><span data-stu-id="b9b2b-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b9b2b-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b9b2b-111">Child Elements</span></span>  
  
|<span data-ttu-id="b9b2b-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="b9b2b-112">Element</span></span>|<span data-ttu-id="b9b2b-113">Описание</span><span class="sxs-lookup"><span data-stu-id="b9b2b-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b9b2b-114">\<Служба ></span><span class="sxs-lookup"><span data-stu-id="b9b2b-114">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="b9b2b-115">Определяет контракт службы, поведение и конечные точки конкретной службы.</span><span class="sxs-lookup"><span data-stu-id="b9b2b-115">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b9b2b-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b9b2b-116">Parent Elements</span></span>  
  
|<span data-ttu-id="b9b2b-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="b9b2b-117">Element</span></span>|<span data-ttu-id="b9b2b-118">Описание</span><span class="sxs-lookup"><span data-stu-id="b9b2b-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b9b2b-119">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b9b2b-119">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="b9b2b-120">Корневой элемент всех элементов конфигурации Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="b9b2b-120">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b9b2b-121">См. также</span><span class="sxs-lookup"><span data-stu-id="b9b2b-121">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServicesSection>
