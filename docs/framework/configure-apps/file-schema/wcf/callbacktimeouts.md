---
title: '&lt;callbackTimeouts&gt;'
ms.date: 03/30/2017
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
ms.openlocfilehash: 01932fe2b7b7e699311e2c65ec8adaf0aef82dc5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54557907"
---
# <a name="ltcallbacktimeoutsgt"></a><span data-ttu-id="574fb-102">&lt;callbackTimeouts&gt;</span><span class="sxs-lookup"><span data-stu-id="574fb-102">&lt;callbackTimeouts&gt;</span></span>
<span data-ttu-id="574fb-103">Задает значение времени ожидания при потоке транзакций от сервера к клиенту в сценарии с дуплексным контрактом обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="574fb-103">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
 <span data-ttu-id="574fb-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="574fb-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="574fb-105">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="574fb-105">\<behaviors></span></span>  
<span data-ttu-id="574fb-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="574fb-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="574fb-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="574fb-107">\<behavior></span></span>  
<span data-ttu-id="574fb-108">\<callbackTimeOuts></span><span class="sxs-lookup"><span data-stu-id="574fb-108">\<callbackTimeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="574fb-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="574fb-109">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="574fb-110">Тип</span><span class="sxs-lookup"><span data-stu-id="574fb-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="574fb-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="574fb-111">Attributes and Elements</span></span>  
 <span data-ttu-id="574fb-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="574fb-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="574fb-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="574fb-113">Attributes</span></span>  
  
|<span data-ttu-id="574fb-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="574fb-114">Attribute</span></span>|<span data-ttu-id="574fb-115">Описание</span><span class="sxs-lookup"><span data-stu-id="574fb-115">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="574fb-116">Значение <xref:System.TimeSpan>, задающее интервал времени, в течение которого транзакции должны завершаться или автоматически прерываться.</span><span class="sxs-lookup"><span data-stu-id="574fb-116">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="574fb-117">Значение по умолчанию — «00: 00:00».</span><span class="sxs-lookup"><span data-stu-id="574fb-117">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="574fb-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="574fb-118">Child Elements</span></span>  
 <span data-ttu-id="574fb-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="574fb-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="574fb-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="574fb-120">Parent Elements</span></span>  
  
|<span data-ttu-id="574fb-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="574fb-121">Element</span></span>|<span data-ttu-id="574fb-122">Описание:</span><span class="sxs-lookup"><span data-stu-id="574fb-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="574fb-123">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="574fb-123">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="574fb-124">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="574fb-124">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="574fb-125">См. также</span><span class="sxs-lookup"><span data-stu-id="574fb-125">See also</span></span>
- <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
