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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ca55770da8da0fe91a12aeb5fa72e61d6dcd67ae
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltservicesgt"></a><span data-ttu-id="79589-102">&lt;службы&gt;</span><span class="sxs-lookup"><span data-stu-id="79589-102">&lt;services&gt;</span></span>
<span data-ttu-id="79589-103">Службы задаются в разделе `services` файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="79589-103">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="79589-104">Для каждой службы используется собственный раздел конфигурации `service`.</span><span class="sxs-lookup"><span data-stu-id="79589-104">Each service has its own `service` configuration section.</span></span>  
  
 <span data-ttu-id="79589-105">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="79589-105">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79589-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="79589-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
        <services>  
        <service>  
        </service>  
        </services>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="79589-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="79589-107">Attributes and Elements</span></span>  
 <span data-ttu-id="79589-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="79589-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="79589-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="79589-109">Attributes</span></span>  
 <span data-ttu-id="79589-110">Нет</span><span class="sxs-lookup"><span data-stu-id="79589-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="79589-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="79589-111">Child Elements</span></span>  
  
|<span data-ttu-id="79589-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="79589-112">Element</span></span>|<span data-ttu-id="79589-113">Описание</span><span class="sxs-lookup"><span data-stu-id="79589-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="79589-114">\<Служба ></span><span class="sxs-lookup"><span data-stu-id="79589-114">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="79589-115">Определяет контракт службы, поведение и конечные точки конкретной службы.</span><span class="sxs-lookup"><span data-stu-id="79589-115">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="79589-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="79589-116">Parent Elements</span></span>  
  
|<span data-ttu-id="79589-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="79589-117">Element</span></span>|<span data-ttu-id="79589-118">Описание</span><span class="sxs-lookup"><span data-stu-id="79589-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="79589-119">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="79589-119">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="79589-120">Корневой элемент всех элементов конфигурации Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="79589-120">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="79589-121">См. также</span><span class="sxs-lookup"><span data-stu-id="79589-121">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServicesSection>
