---
title: <clientVia>
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: b12a882d942555a24c145b243d2cea764ba106b1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919508"
---
# <a name="clientvia"></a><span data-ttu-id="c96b8-101">\<Клиентвиа ></span><span class="sxs-lookup"><span data-stu-id="c96b8-101">\<clientVia></span></span>
<span data-ttu-id="c96b8-102">Задает универсальный код ресурса (URI), для которого необходимо создать канал транспорта.</span><span class="sxs-lookup"><span data-stu-id="c96b8-102">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="c96b8-103">Дополнительные сведения см. в разделе <xref:System.ServiceModel.Description.ClientViaBehavior>.</span><span class="sxs-lookup"><span data-stu-id="c96b8-103">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
 <span data-ttu-id="c96b8-104">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="c96b8-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c96b8-105">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="c96b8-105">\<behaviors></span></span>  
<span data-ttu-id="c96b8-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="c96b8-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="c96b8-107">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="c96b8-107">\<behavior></span></span>  
<span data-ttu-id="c96b8-108">\<Клиентвиа ></span><span class="sxs-lookup"><span data-stu-id="c96b8-108">\<clientVia></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c96b8-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c96b8-109">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c96b8-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c96b8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c96b8-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c96b8-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c96b8-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c96b8-112">Attributes</span></span>  
  
|<span data-ttu-id="c96b8-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c96b8-113">Attribute</span></span>|<span data-ttu-id="c96b8-114">Описание</span><span class="sxs-lookup"><span data-stu-id="c96b8-114">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="c96b8-115">Строка, задающая универсальный код ресурса (URI), который указывает маршрут для сообщения.</span><span class="sxs-lookup"><span data-stu-id="c96b8-115">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c96b8-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c96b8-116">Child Elements</span></span>  
 <span data-ttu-id="c96b8-117">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="c96b8-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c96b8-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c96b8-118">Parent Elements</span></span>  
  
|<span data-ttu-id="c96b8-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="c96b8-119">Element</span></span>|<span data-ttu-id="c96b8-120">Описание</span><span class="sxs-lookup"><span data-stu-id="c96b8-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c96b8-121">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="c96b8-121">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="c96b8-122">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="c96b8-122">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c96b8-123">См. также</span><span class="sxs-lookup"><span data-stu-id="c96b8-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientViaElement>
- <xref:System.ServiceModel.Description.ClientViaBehavior>
