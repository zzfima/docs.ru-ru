---
title: Элемент <synchronousReceive>
ms.date: 03/30/2017
ms.assetid: cc070387-3d11-4b02-a952-bc08ad2df05a
ms.openlocfilehash: fa14d4606303b2d67cf5ef845d428bb086680204
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69938970"
---
# <a name="synchronousreceive-element"></a><span data-ttu-id="cbca5-102">\<Элемент > Синчронаусрецеиве</span><span class="sxs-lookup"><span data-stu-id="cbca5-102">\<synchronousReceive> element</span></span>
<span data-ttu-id="cbca5-103">Этот элемент конфигурации используется, чтобы задавать поведение времени выполнения при получении сообщений в службе или в клиентском приложении.</span><span class="sxs-lookup"><span data-stu-id="cbca5-103">This configuration element is used to specify run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="cbca5-104">Он не имеет атрибутов или дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="cbca5-104">It does not have any attributes or child elements.</span></span>  
  
 <span data-ttu-id="cbca5-105">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="cbca5-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="cbca5-106">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="cbca5-106">\<behaviors></span></span>  
<span data-ttu-id="cbca5-107">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="cbca5-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="cbca5-108">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="cbca5-108">\<behavior></span></span>  
<span data-ttu-id="cbca5-109">\<Синчронаусрецеиве ></span><span class="sxs-lookup"><span data-stu-id="cbca5-109">\<synchronousReceive></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbca5-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cbca5-110">Syntax</span></span>  
  
```xml  
<synchronousReceive />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cbca5-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="cbca5-111">Attributes and Elements</span></span>  
 <span data-ttu-id="cbca5-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="cbca5-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cbca5-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="cbca5-113">Attributes</span></span>  
 <span data-ttu-id="cbca5-114">Нет.</span><span class="sxs-lookup"><span data-stu-id="cbca5-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cbca5-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="cbca5-115">Child Elements</span></span>  
 <span data-ttu-id="cbca5-116">Нет.</span><span class="sxs-lookup"><span data-stu-id="cbca5-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cbca5-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="cbca5-117">Parent Elements</span></span>  
  
|<span data-ttu-id="cbca5-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="cbca5-118">Element</span></span>|<span data-ttu-id="cbca5-119">Описание</span><span class="sxs-lookup"><span data-stu-id="cbca5-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cbca5-120">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="cbca5-120">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="cbca5-121">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="cbca5-121">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cbca5-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="cbca5-122">Remarks</span></span>  
 <span data-ttu-id="cbca5-123">Используйте это поведение, чтобы дать указание прослушивателю каналов использовать синхронное получение вместо асинхронного получения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cbca5-123">Use this behavior to instruct the channel listener to use a synchronous receive rather than the default, asynchronous.</span></span> <span data-ttu-id="cbca5-124">Windows Communication Foundation (WCF) выдает новый поток для приема для каждого принятого канала.</span><span class="sxs-lookup"><span data-stu-id="cbca5-124">Windows Communication Foundation (WCF) issues a new thread to pump for each accepted channel.</span></span> <span data-ttu-id="cbca5-125">При наличии множества каналов существует вероятность недостатка потоков.</span><span class="sxs-lookup"><span data-stu-id="cbca5-125">If there are a lot of channels, there is the possibility of running out of threads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbca5-126">См. также</span><span class="sxs-lookup"><span data-stu-id="cbca5-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>
- <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>
