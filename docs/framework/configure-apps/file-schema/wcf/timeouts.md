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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 41ebd88f64b001b577342562c9c3010b307aaccc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="lttimeoutsgt"></a><span data-ttu-id="70971-102">&lt;время ожидания&gt;</span><span class="sxs-lookup"><span data-stu-id="70971-102">&lt;timeOuts&gt;</span></span>
<span data-ttu-id="70971-103">Элемент конфигурации, который задает допустимый интервал времени для открытия или закрытия узла службы.</span><span class="sxs-lookup"><span data-stu-id="70971-103">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
 <span data-ttu-id="70971-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="70971-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="70971-105">\<Клиент ></span><span class="sxs-lookup"><span data-stu-id="70971-105">\<client></span></span>  
<span data-ttu-id="70971-106">\<Конечная точка ></span><span class="sxs-lookup"><span data-stu-id="70971-106">\<endpoint></span></span>  
<span data-ttu-id="70971-107">\<узел ></span><span class="sxs-lookup"><span data-stu-id="70971-107">\<host></span></span>  
<span data-ttu-id="70971-108">\<время ожидания ></span><span class="sxs-lookup"><span data-stu-id="70971-108">\<timeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70971-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="70971-109">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"  
   openTimeout="TimeSpan" >  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="70971-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="70971-110">Attributes and Elements</span></span>  
 <span data-ttu-id="70971-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="70971-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="70971-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="70971-112">Attributes</span></span>  
  
|<span data-ttu-id="70971-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="70971-113">Attribute</span></span>|<span data-ttu-id="70971-114">Описание</span><span class="sxs-lookup"><span data-stu-id="70971-114">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="70971-115">Значение <xref:System.TimeSpan>, которое задает временной интервал, выделенный для операции закрытия узла службы.</span><span class="sxs-lookup"><span data-stu-id="70971-115">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="70971-116">Значение <xref:System.TimeSpan>, которое задает временной интервал, выделенный для операции открытия узла службы.</span><span class="sxs-lookup"><span data-stu-id="70971-116">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="70971-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="70971-117">Child Elements</span></span>  
 <span data-ttu-id="70971-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="70971-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="70971-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="70971-119">Parent Elements</span></span>  
  
|<span data-ttu-id="70971-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="70971-120">Element</span></span>|<span data-ttu-id="70971-121">Описание</span><span class="sxs-lookup"><span data-stu-id="70971-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="70971-122">\<узел ></span><span class="sxs-lookup"><span data-stu-id="70971-122">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="70971-123">Элемент конфигурации, который задает параметры узла службы.</span><span class="sxs-lookup"><span data-stu-id="70971-123">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="70971-124">См. также</span><span class="sxs-lookup"><span data-stu-id="70971-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 [<span data-ttu-id="70971-125">Размещение</span><span class="sxs-lookup"><span data-stu-id="70971-125">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
