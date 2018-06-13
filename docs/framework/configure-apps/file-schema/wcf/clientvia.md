---
title: '&lt;clientVia&gt;'
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: 6218bb3f205f2825eb3f10fabf834cfd0396ac87
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32754136"
---
# <a name="ltclientviagt"></a><span data-ttu-id="00e85-102">&lt;clientVia&gt;</span><span class="sxs-lookup"><span data-stu-id="00e85-102">&lt;clientVia&gt;</span></span>
<span data-ttu-id="00e85-103">Задает универсальный код ресурса (URI), для которого необходимо создать канал транспорта.</span><span class="sxs-lookup"><span data-stu-id="00e85-103">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="00e85-104">Дополнительные сведения см. в разделе <xref:System.ServiceModel.Description.ClientViaBehavior>.</span><span class="sxs-lookup"><span data-stu-id="00e85-104">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
 <span data-ttu-id="00e85-105">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="00e85-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="00e85-106">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="00e85-106">\<behaviors></span></span>  
<span data-ttu-id="00e85-107">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="00e85-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="00e85-108">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="00e85-108">\<behavior></span></span>  
<span data-ttu-id="00e85-109">\<clientVia ></span><span class="sxs-lookup"><span data-stu-id="00e85-109">\<clientVia></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00e85-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="00e85-110">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="00e85-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="00e85-111">Attributes and Elements</span></span>  
 <span data-ttu-id="00e85-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="00e85-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="00e85-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="00e85-113">Attributes</span></span>  
  
|<span data-ttu-id="00e85-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="00e85-114">Attribute</span></span>|<span data-ttu-id="00e85-115">Описание</span><span class="sxs-lookup"><span data-stu-id="00e85-115">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="00e85-116">Строка, задающая универсальный код ресурса (URI), который указывает маршрут для сообщения.</span><span class="sxs-lookup"><span data-stu-id="00e85-116">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="00e85-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="00e85-117">Child Elements</span></span>  
 <span data-ttu-id="00e85-118">Нет</span><span class="sxs-lookup"><span data-stu-id="00e85-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="00e85-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="00e85-119">Parent Elements</span></span>  
  
|<span data-ttu-id="00e85-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="00e85-120">Element</span></span>|<span data-ttu-id="00e85-121">Описание</span><span class="sxs-lookup"><span data-stu-id="00e85-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="00e85-122">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="00e85-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="00e85-123">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="00e85-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="00e85-124">См. также</span><span class="sxs-lookup"><span data-stu-id="00e85-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientViaElement>  
 <xref:System.ServiceModel.Description.ClientViaBehavior>
