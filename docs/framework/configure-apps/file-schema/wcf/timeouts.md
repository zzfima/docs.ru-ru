---
title: "&lt;время ожидания&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 04003584cf12355116d32cccffdcb2b9990b1b85
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="lttimeoutsgt"></a><span data-ttu-id="c8638-102">&lt;время ожидания&gt;</span><span class="sxs-lookup"><span data-stu-id="c8638-102">&lt;timeOuts&gt;</span></span>
<span data-ttu-id="c8638-103">Элемент конфигурации, который задает допустимый интервал времени для открытия или закрытия узла службы.</span><span class="sxs-lookup"><span data-stu-id="c8638-103">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
 <span data-ttu-id="c8638-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="c8638-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c8638-105">\<Клиент ></span><span class="sxs-lookup"><span data-stu-id="c8638-105">\<client></span></span>  
<span data-ttu-id="c8638-106">\<Конечная точка ></span><span class="sxs-lookup"><span data-stu-id="c8638-106">\<endpoint></span></span>  
<span data-ttu-id="c8638-107">\<узел ></span><span class="sxs-lookup"><span data-stu-id="c8638-107">\<host></span></span>  
<span data-ttu-id="c8638-108">\<время ожидания ></span><span class="sxs-lookup"><span data-stu-id="c8638-108">\<timeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8638-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c8638-109">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"  
   openTimeout="TimeSpan" >  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c8638-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c8638-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c8638-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c8638-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c8638-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c8638-112">Attributes</span></span>  
  
|<span data-ttu-id="c8638-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c8638-113">Attribute</span></span>|<span data-ttu-id="c8638-114">Описание</span><span class="sxs-lookup"><span data-stu-id="c8638-114">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="c8638-115">Значение <xref:System.TimeSpan>, которое задает временной интервал, выделенный для операции закрытия узла службы.</span><span class="sxs-lookup"><span data-stu-id="c8638-115">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="c8638-116">Значение <xref:System.TimeSpan>, которое задает временной интервал, выделенный для операции открытия узла службы.</span><span class="sxs-lookup"><span data-stu-id="c8638-116">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c8638-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c8638-117">Child Elements</span></span>  
 <span data-ttu-id="c8638-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="c8638-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c8638-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c8638-119">Parent Elements</span></span>  
  
|<span data-ttu-id="c8638-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="c8638-120">Element</span></span>|<span data-ttu-id="c8638-121">Описание:</span><span class="sxs-lookup"><span data-stu-id="c8638-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c8638-122">\<узел ></span><span class="sxs-lookup"><span data-stu-id="c8638-122">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="c8638-123">Элемент конфигурации, который задает параметры узла службы.</span><span class="sxs-lookup"><span data-stu-id="c8638-123">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c8638-124">См. также</span><span class="sxs-lookup"><span data-stu-id="c8638-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 [<span data-ttu-id="c8638-125">Размещение</span><span class="sxs-lookup"><span data-stu-id="c8638-125">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
