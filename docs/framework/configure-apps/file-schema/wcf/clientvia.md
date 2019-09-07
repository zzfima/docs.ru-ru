---
title: <clientVia>
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: a1c2ee68fb039e24e1462148cb52daf1bb57f8ed
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398112"
---
# <a name="clientvia"></a><span data-ttu-id="577b6-101">\<Клиентвиа ></span><span class="sxs-lookup"><span data-stu-id="577b6-101">\<clientVia></span></span>
<span data-ttu-id="577b6-102">Задает универсальный код ресурса (URI), для которого необходимо создать канал транспорта.</span><span class="sxs-lookup"><span data-stu-id="577b6-102">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="577b6-103">Дополнительные сведения см. в разделе <xref:System.ServiceModel.Description.ClientViaBehavior>.</span><span class="sxs-lookup"><span data-stu-id="577b6-103">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
<span data-ttu-id="577b6-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="577b6-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="577b6-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="577b6-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="577b6-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="577b6-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="577b6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="577b6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="577b6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="577b6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="577b6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Клиентвиа >**</span><span class="sxs-lookup"><span data-stu-id="577b6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientVia>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="577b6-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="577b6-110">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="577b6-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="577b6-111">Attributes and Elements</span></span>  
 <span data-ttu-id="577b6-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="577b6-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="577b6-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="577b6-113">Attributes</span></span>  
  
|<span data-ttu-id="577b6-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="577b6-114">Attribute</span></span>|<span data-ttu-id="577b6-115">Описание</span><span class="sxs-lookup"><span data-stu-id="577b6-115">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="577b6-116">Строка, задающая универсальный код ресурса (URI), который указывает маршрут для сообщения.</span><span class="sxs-lookup"><span data-stu-id="577b6-116">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="577b6-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="577b6-117">Child Elements</span></span>  
 <span data-ttu-id="577b6-118">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="577b6-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="577b6-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="577b6-119">Parent Elements</span></span>  
  
|<span data-ttu-id="577b6-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="577b6-120">Element</span></span>|<span data-ttu-id="577b6-121">Описание</span><span class="sxs-lookup"><span data-stu-id="577b6-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="577b6-122">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="577b6-122">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="577b6-123">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="577b6-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="577b6-124">См. также</span><span class="sxs-lookup"><span data-stu-id="577b6-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientViaElement>
- <xref:System.ServiceModel.Description.ClientViaBehavior>
