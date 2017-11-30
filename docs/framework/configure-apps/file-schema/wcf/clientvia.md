---
title: '&lt;clientVia&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7cdc85c23202154728610ab4721bf830004928c8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltclientviagt"></a><span data-ttu-id="b9566-102">&lt;clientVia&gt;</span><span class="sxs-lookup"><span data-stu-id="b9566-102">&lt;clientVia&gt;</span></span>
<span data-ttu-id="b9566-103">Задает универсальный код ресурса (URI), для которого необходимо создать канал транспорта.</span><span class="sxs-lookup"><span data-stu-id="b9566-103">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="b9566-104">Для получения дополнительной информации см. <xref:System.ServiceModel.Description.ClientViaBehavior>.</span><span class="sxs-lookup"><span data-stu-id="b9566-104">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
 <span data-ttu-id="b9566-105">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="b9566-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="b9566-106">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="b9566-106">\<behaviors></span></span>  
<span data-ttu-id="b9566-107">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="b9566-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="b9566-108">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="b9566-108">\<behavior></span></span>  
<span data-ttu-id="b9566-109">\<clientVia ></span><span class="sxs-lookup"><span data-stu-id="b9566-109">\<clientVia></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9566-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b9566-110">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b9566-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b9566-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b9566-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b9566-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b9566-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b9566-113">Attributes</span></span>  
  
|<span data-ttu-id="b9566-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b9566-114">Attribute</span></span>|<span data-ttu-id="b9566-115">Описание</span><span class="sxs-lookup"><span data-stu-id="b9566-115">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="b9566-116">Строка, задающая универсальный код ресурса (URI), который указывает маршрут для сообщения.</span><span class="sxs-lookup"><span data-stu-id="b9566-116">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b9566-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b9566-117">Child Elements</span></span>  
 <span data-ttu-id="b9566-118">Нет</span><span class="sxs-lookup"><span data-stu-id="b9566-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b9566-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b9566-119">Parent Elements</span></span>  
  
|<span data-ttu-id="b9566-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="b9566-120">Element</span></span>|<span data-ttu-id="b9566-121">Описание</span><span class="sxs-lookup"><span data-stu-id="b9566-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b9566-122">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="b9566-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="b9566-123">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="b9566-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b9566-124">См. также</span><span class="sxs-lookup"><span data-stu-id="b9566-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientViaElement>  
 <xref:System.ServiceModel.Description.ClientViaBehavior>
