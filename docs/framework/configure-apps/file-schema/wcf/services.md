---
title: "&lt;службы&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: eb292a62c2b042c387799164ff4cec88bd2ca482
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ltservicesgt"></a><span data-ttu-id="48089-102">&lt;службы&gt;</span><span class="sxs-lookup"><span data-stu-id="48089-102">&lt;services&gt;</span></span>
<span data-ttu-id="48089-103">Службы задаются в разделе `services` файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="48089-103">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="48089-104">Для каждой службы используется собственный раздел конфигурации `service`.</span><span class="sxs-lookup"><span data-stu-id="48089-104">Each service has its own `service` configuration section.</span></span>  
  
 <span data-ttu-id="48089-105">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="48089-105">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48089-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="48089-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
        <services>  
        <service>  
        </service>  
        </services>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="48089-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="48089-107">Attributes and Elements</span></span>  
 <span data-ttu-id="48089-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="48089-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="48089-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="48089-109">Attributes</span></span>  
 <span data-ttu-id="48089-110">Нет</span><span class="sxs-lookup"><span data-stu-id="48089-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="48089-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="48089-111">Child Elements</span></span>  
  
|<span data-ttu-id="48089-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="48089-112">Element</span></span>|<span data-ttu-id="48089-113">Описание</span><span class="sxs-lookup"><span data-stu-id="48089-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="48089-114">\<Служба ></span><span class="sxs-lookup"><span data-stu-id="48089-114">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="48089-115">Определяет контракт службы, поведение и конечные точки конкретной службы.</span><span class="sxs-lookup"><span data-stu-id="48089-115">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="48089-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="48089-116">Parent Elements</span></span>  
  
|<span data-ttu-id="48089-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="48089-117">Element</span></span>|<span data-ttu-id="48089-118">Описание</span><span class="sxs-lookup"><span data-stu-id="48089-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="48089-119">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="48089-119">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="48089-120">Корневой элемент всех элементов конфигурации Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="48089-120">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="48089-121">См. также</span><span class="sxs-lookup"><span data-stu-id="48089-121">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServicesSection>
