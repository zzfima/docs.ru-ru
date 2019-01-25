---
title: '&lt;службы&gt;'
ms.date: 03/30/2017
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
ms.openlocfilehash: 7b26224f1217e7f73a529c082c2c9272ec189a5a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54573261"
---
# <a name="ltservicesgt"></a><span data-ttu-id="f83b4-102">&lt;службы&gt;</span><span class="sxs-lookup"><span data-stu-id="f83b4-102">&lt;services&gt;</span></span>
<span data-ttu-id="f83b4-103">Службы задаются в разделе `services` файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f83b4-103">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="f83b4-104">Для каждой службы используется собственный раздел конфигурации `service`.</span><span class="sxs-lookup"><span data-stu-id="f83b4-104">Each service has its own `service` configuration section.</span></span>  
  
 <span data-ttu-id="f83b4-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f83b4-105">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f83b4-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f83b4-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service>
    </service>
  </services>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f83b4-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f83b4-107">Attributes and Elements</span></span>  
 <span data-ttu-id="f83b4-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f83b4-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f83b4-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f83b4-109">Attributes</span></span>  
 <span data-ttu-id="f83b4-110">Нет</span><span class="sxs-lookup"><span data-stu-id="f83b4-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f83b4-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f83b4-111">Child Elements</span></span>  
  
|<span data-ttu-id="f83b4-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="f83b4-112">Element</span></span>|<span data-ttu-id="f83b4-113">Описание</span><span class="sxs-lookup"><span data-stu-id="f83b4-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f83b4-114">\<службы ></span><span class="sxs-lookup"><span data-stu-id="f83b4-114">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="f83b4-115">Определяет контракт службы, поведение и конечные точки конкретной службы.</span><span class="sxs-lookup"><span data-stu-id="f83b4-115">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f83b4-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f83b4-116">Parent Elements</span></span>  
  
|<span data-ttu-id="f83b4-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="f83b4-117">Element</span></span>|<span data-ttu-id="f83b4-118">Описание:</span><span class="sxs-lookup"><span data-stu-id="f83b4-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f83b4-119">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f83b4-119">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="f83b4-120">Корневой элемент всех элементов конфигурации Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="f83b4-120">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f83b4-121">См. также</span><span class="sxs-lookup"><span data-stu-id="f83b4-121">See also</span></span>
- <xref:System.ServiceModel.Configuration.ServicesSection>
