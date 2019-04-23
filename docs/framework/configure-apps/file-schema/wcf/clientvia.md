---
title: <clientVia>
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: b8864760c1700cd785922b922346204d194f56cc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59176817"
---
# <a name="clientvia"></a><span data-ttu-id="1ad22-101">\<clientVia ></span><span class="sxs-lookup"><span data-stu-id="1ad22-101">\<clientVia></span></span>
<span data-ttu-id="1ad22-102">Задает универсальный код ресурса (URI), для которого необходимо создать канал транспорта.</span><span class="sxs-lookup"><span data-stu-id="1ad22-102">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="1ad22-103">Дополнительные сведения см. в разделе <xref:System.ServiceModel.Description.ClientViaBehavior>.</span><span class="sxs-lookup"><span data-stu-id="1ad22-103">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
 <span data-ttu-id="1ad22-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="1ad22-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="1ad22-105">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="1ad22-105">\<behaviors></span></span>  
<span data-ttu-id="1ad22-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="1ad22-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="1ad22-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="1ad22-107">\<behavior></span></span>  
<span data-ttu-id="1ad22-108">\<clientVia ></span><span class="sxs-lookup"><span data-stu-id="1ad22-108">\<clientVia></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ad22-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1ad22-109">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1ad22-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1ad22-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1ad22-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1ad22-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1ad22-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1ad22-112">Attributes</span></span>  
  
|<span data-ttu-id="1ad22-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="1ad22-113">Attribute</span></span>|<span data-ttu-id="1ad22-114">Описание</span><span class="sxs-lookup"><span data-stu-id="1ad22-114">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="1ad22-115">Строка, задающая универсальный код ресурса (URI), который указывает маршрут для сообщения.</span><span class="sxs-lookup"><span data-stu-id="1ad22-115">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1ad22-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1ad22-116">Child Elements</span></span>  
 <span data-ttu-id="1ad22-117">Нет</span><span class="sxs-lookup"><span data-stu-id="1ad22-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1ad22-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1ad22-118">Parent Elements</span></span>  
  
|<span data-ttu-id="1ad22-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="1ad22-119">Element</span></span>|<span data-ttu-id="1ad22-120">Описание</span><span class="sxs-lookup"><span data-stu-id="1ad22-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1ad22-121">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="1ad22-121">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="1ad22-122">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="1ad22-122">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1ad22-123">См. также</span><span class="sxs-lookup"><span data-stu-id="1ad22-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientViaElement>
- <xref:System.ServiceModel.Description.ClientViaBehavior>
