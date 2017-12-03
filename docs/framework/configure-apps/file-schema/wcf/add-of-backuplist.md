---
title: "&lt;add&gt; для &lt;backupList&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b93b442d21d34eea5031cea565bdcf62139abc81
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltaddgt-of-ltbackuplistgt"></a><span data-ttu-id="6c0a8-102">&lt;add&gt; для &lt;backupList&gt;</span><span class="sxs-lookup"><span data-stu-id="6c0a8-102">&lt;add&gt; of &lt;backupList&gt;</span></span>
<span data-ttu-id="6c0a8-103">Представляет элемент конфигурации, в котором задается элемент резервной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="6c0a8-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
 <span data-ttu-id="6c0a8-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="6c0a8-104">\<system.serviceModel></span></span>  
<span data-ttu-id="6c0a8-105">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="6c0a8-105">\<routing></span></span>  
<span data-ttu-id="6c0a8-106">\<backupLists ></span><span class="sxs-lookup"><span data-stu-id="6c0a8-106">\<backupLists></span></span>  
<span data-ttu-id="6c0a8-107">\<backupList ></span><span class="sxs-lookup"><span data-stu-id="6c0a8-107">\<backupList></span></span>  
<span data-ttu-id="6c0a8-108">\<add></span><span class="sxs-lookup"><span data-stu-id="6c0a8-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c0a8-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6c0a8-109">Syntax</span></span>  
  
```xml  
   <routing>  <backupLists>    <backupList name="String">      <add endpointName="String" />    </backupList>    </backupLists></routing>  
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6c0a8-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6c0a8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="6c0a8-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6c0a8-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6c0a8-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6c0a8-112">Attributes</span></span>  
  
|<span data-ttu-id="6c0a8-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="6c0a8-113">Attribute</span></span>|<span data-ttu-id="6c0a8-114">Описание</span><span class="sxs-lookup"><span data-stu-id="6c0a8-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6c0a8-115">имя</span><span class="sxs-lookup"><span data-stu-id="6c0a8-115">name</span></span>|<span data-ttu-id="6c0a8-116">Строка, задающая имя резервной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="6c0a8-116">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6c0a8-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6c0a8-117">Child Elements</span></span>  
 <span data-ttu-id="6c0a8-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="6c0a8-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6c0a8-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6c0a8-119">Parent Elements</span></span>  
  
|<span data-ttu-id="6c0a8-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="6c0a8-120">Element</span></span>|<span data-ttu-id="6c0a8-121">Описание</span><span class="sxs-lookup"><span data-stu-id="6c0a8-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6c0a8-122">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="6c0a8-122">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="6c0a8-123">Содержит список конечных точек, которые вы будете службе маршрутизации в случае, если основная конечная точка становится недоступной.</span><span class="sxs-lookup"><span data-stu-id="6c0a8-123">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6c0a8-124">См. также</span><span class="sxs-lookup"><span data-stu-id="6c0a8-124">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType> 
