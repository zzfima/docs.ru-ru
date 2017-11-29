---
title: '&lt;serviceTimeouts&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ada536cf-97dc-4cd7-89ec-ed1466c1c557
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ecefda0a3447aa029079fbb3633b05054f42195a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ltservicetimeoutsgt"></a><span data-ttu-id="5b73d-102">&lt;serviceTimeouts&gt;</span><span class="sxs-lookup"><span data-stu-id="5b73d-102">&lt;serviceTimeouts&gt;</span></span>
<span data-ttu-id="5b73d-103">Задает время ожидания для службы.</span><span class="sxs-lookup"><span data-stu-id="5b73d-103">Specifies the timeout for a service.</span></span>  
  
 <span data-ttu-id="5b73d-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="5b73d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="5b73d-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="5b73d-105">\<behaviors></span></span>  
<span data-ttu-id="5b73d-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="5b73d-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="5b73d-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="5b73d-107">\<behavior></span></span>  
<span data-ttu-id="5b73d-108">\<serviceTimeouts ></span><span class="sxs-lookup"><span data-stu-id="5b73d-108">\<serviceTimeouts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b73d-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5b73d-109">Syntax</span></span>  
  
```xml  
<serviceTimeouts transactionTimeout="TimeSpan" />  
```  
  
## <a name="type"></a><span data-ttu-id="5b73d-110">Тип</span><span class="sxs-lookup"><span data-stu-id="5b73d-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5b73d-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5b73d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="5b73d-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5b73d-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5b73d-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5b73d-113">Attributes</span></span>  
  
|<span data-ttu-id="5b73d-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5b73d-114">Attribute</span></span>|<span data-ttu-id="5b73d-115">Описание</span><span class="sxs-lookup"><span data-stu-id="5b73d-115">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="5b73d-116">Значение <xref:System.TimeSpan>, задающее интервал времени, в течение которого транзакция должна дойти от клиента до сервера.</span><span class="sxs-lookup"><span data-stu-id="5b73d-116">A <xref:System.TimeSpan> value that specifies the interval of time a transaction must flow from client to server.</span></span> <span data-ttu-id="5b73d-117">Значение по умолчанию — «00: 00:00».</span><span class="sxs-lookup"><span data-stu-id="5b73d-117">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5b73d-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5b73d-118">Child Elements</span></span>  
 <span data-ttu-id="5b73d-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5b73d-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5b73d-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5b73d-120">Parent Elements</span></span>  
  
|<span data-ttu-id="5b73d-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="5b73d-121">Element</span></span>|<span data-ttu-id="5b73d-122">Описание</span><span class="sxs-lookup"><span data-stu-id="5b73d-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5b73d-123">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="5b73d-123">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="5b73d-124">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="5b73d-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5b73d-125">См. также</span><span class="sxs-lookup"><span data-stu-id="5b73d-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
