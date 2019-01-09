---
title: '&lt;clientVia&gt;'
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: 48e56b79f47e84122ddd4d7f55d50044510bfa66
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149063"
---
# <a name="ltclientviagt"></a><span data-ttu-id="08878-102">&lt;clientVia&gt;</span><span class="sxs-lookup"><span data-stu-id="08878-102">&lt;clientVia&gt;</span></span>
<span data-ttu-id="08878-103">Задает универсальный код ресурса (URI), для которого необходимо создать канал транспорта.</span><span class="sxs-lookup"><span data-stu-id="08878-103">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="08878-104">Дополнительные сведения см. в разделе <xref:System.ServiceModel.Description.ClientViaBehavior>.</span><span class="sxs-lookup"><span data-stu-id="08878-104">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
 <span data-ttu-id="08878-105">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="08878-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="08878-106">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="08878-106">\<behaviors></span></span>  
<span data-ttu-id="08878-107">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="08878-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="08878-108">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="08878-108">\<behavior></span></span>  
<span data-ttu-id="08878-109">\<clientVia ></span><span class="sxs-lookup"><span data-stu-id="08878-109">\<clientVia></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08878-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="08878-110">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="08878-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="08878-111">Attributes and Elements</span></span>  
 <span data-ttu-id="08878-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="08878-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="08878-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="08878-113">Attributes</span></span>  
  
|<span data-ttu-id="08878-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="08878-114">Attribute</span></span>|<span data-ttu-id="08878-115">Описание</span><span class="sxs-lookup"><span data-stu-id="08878-115">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="08878-116">Строка, задающая универсальный код ресурса (URI), который указывает маршрут для сообщения.</span><span class="sxs-lookup"><span data-stu-id="08878-116">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="08878-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="08878-117">Child Elements</span></span>  
 <span data-ttu-id="08878-118">Нет</span><span class="sxs-lookup"><span data-stu-id="08878-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="08878-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="08878-119">Parent Elements</span></span>  
  
|<span data-ttu-id="08878-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="08878-120">Element</span></span>|<span data-ttu-id="08878-121">Описание</span><span class="sxs-lookup"><span data-stu-id="08878-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="08878-122">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="08878-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="08878-123">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="08878-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="08878-124">См. также</span><span class="sxs-lookup"><span data-stu-id="08878-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientViaElement>  
 <xref:System.ServiceModel.Description.ClientViaBehavior>
