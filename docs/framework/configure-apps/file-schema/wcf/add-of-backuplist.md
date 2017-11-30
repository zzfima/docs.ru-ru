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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1475983f7dc54a597198d48a2a404e431ce9c0a0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ltaddgt-of-ltbackuplistgt"></a><span data-ttu-id="0337c-102">&lt;add&gt; для &lt;backupList&gt;</span><span class="sxs-lookup"><span data-stu-id="0337c-102">&lt;add&gt; of &lt;backupList&gt;</span></span>
<span data-ttu-id="0337c-103">Представляет элемент конфигурации, в котором задается элемент резервной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="0337c-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
 <span data-ttu-id="0337c-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="0337c-104">\<system.serviceModel></span></span>  
<span data-ttu-id="0337c-105">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="0337c-105">\<routing></span></span>  
<span data-ttu-id="0337c-106">\<backupLists ></span><span class="sxs-lookup"><span data-stu-id="0337c-106">\<backupLists></span></span>  
<span data-ttu-id="0337c-107">\<backupList ></span><span class="sxs-lookup"><span data-stu-id="0337c-107">\<backupList></span></span>  
<span data-ttu-id="0337c-108">\<add></span><span class="sxs-lookup"><span data-stu-id="0337c-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0337c-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0337c-109">Syntax</span></span>  
  
```xml  
   <routing>  <backupLists>    <backupList name="String">      <add endpointName="String" />    </backupList>    </backupLists></routing>  
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0337c-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0337c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="0337c-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0337c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0337c-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0337c-112">Attributes</span></span>  
  
|<span data-ttu-id="0337c-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="0337c-113">Attribute</span></span>|<span data-ttu-id="0337c-114">Описание</span><span class="sxs-lookup"><span data-stu-id="0337c-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0337c-115">имя</span><span class="sxs-lookup"><span data-stu-id="0337c-115">name</span></span>|<span data-ttu-id="0337c-116">Строка, задающая имя резервной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="0337c-116">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0337c-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0337c-117">Child Elements</span></span>  
 <span data-ttu-id="0337c-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0337c-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0337c-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0337c-119">Parent Elements</span></span>  
  
|<span data-ttu-id="0337c-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="0337c-120">Element</span></span>|<span data-ttu-id="0337c-121">Описание</span><span class="sxs-lookup"><span data-stu-id="0337c-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0337c-122">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="0337c-122">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="0337c-123">Содержит список конечных точек, которые вы будете службе маршрутизации в случае, если основная конечная точка становится недоступной.</span><span class="sxs-lookup"><span data-stu-id="0337c-123">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0337c-124">См. также</span><span class="sxs-lookup"><span data-stu-id="0337c-124">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType> 
