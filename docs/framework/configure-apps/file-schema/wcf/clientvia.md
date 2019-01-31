---
title: <clientVia>
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: 063dbee71a91e098e26026ea78c74642115c7955
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55266667"
---
# <a name="clientvia"></a><span data-ttu-id="83ed9-101">\<clientVia ></span><span class="sxs-lookup"><span data-stu-id="83ed9-101">\<clientVia></span></span>
<span data-ttu-id="83ed9-102">Задает универсальный код ресурса (URI), для которого необходимо создать канал транспорта.</span><span class="sxs-lookup"><span data-stu-id="83ed9-102">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="83ed9-103">Дополнительные сведения см. в разделе <xref:System.ServiceModel.Description.ClientViaBehavior>.</span><span class="sxs-lookup"><span data-stu-id="83ed9-103">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
 <span data-ttu-id="83ed9-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="83ed9-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="83ed9-105">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="83ed9-105">\<behaviors></span></span>  
<span data-ttu-id="83ed9-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="83ed9-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="83ed9-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="83ed9-107">\<behavior></span></span>  
<span data-ttu-id="83ed9-108">\<clientVia ></span><span class="sxs-lookup"><span data-stu-id="83ed9-108">\<clientVia></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83ed9-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="83ed9-109">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="83ed9-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="83ed9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="83ed9-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="83ed9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="83ed9-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="83ed9-112">Attributes</span></span>  
  
|<span data-ttu-id="83ed9-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="83ed9-113">Attribute</span></span>|<span data-ttu-id="83ed9-114">Описание</span><span class="sxs-lookup"><span data-stu-id="83ed9-114">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="83ed9-115">Строка, задающая универсальный код ресурса (URI), который указывает маршрут для сообщения.</span><span class="sxs-lookup"><span data-stu-id="83ed9-115">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="83ed9-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="83ed9-116">Child Elements</span></span>  
 <span data-ttu-id="83ed9-117">Нет</span><span class="sxs-lookup"><span data-stu-id="83ed9-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="83ed9-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="83ed9-118">Parent Elements</span></span>  
  
|<span data-ttu-id="83ed9-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="83ed9-119">Element</span></span>|<span data-ttu-id="83ed9-120">Описание:</span><span class="sxs-lookup"><span data-stu-id="83ed9-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="83ed9-121">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="83ed9-121">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="83ed9-122">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="83ed9-122">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="83ed9-123">См. также</span><span class="sxs-lookup"><span data-stu-id="83ed9-123">See also</span></span>
- <xref:System.ServiceModel.Configuration.ClientViaElement>
- <xref:System.ServiceModel.Description.ClientViaBehavior>
