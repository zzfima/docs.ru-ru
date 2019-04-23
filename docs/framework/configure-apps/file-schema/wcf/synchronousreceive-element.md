---
title: Элемент <synchronousReceive>
ms.date: 03/30/2017
ms.assetid: cc070387-3d11-4b02-a952-bc08ad2df05a
ms.openlocfilehash: 20390f747c8beaccba1cfea7a9ea0ed366037ecb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59166547"
---
# <a name="synchronousreceive-element"></a><span data-ttu-id="5e529-102">\<synchronousReceive > элемент</span><span class="sxs-lookup"><span data-stu-id="5e529-102">\<synchronousReceive> element</span></span>
<span data-ttu-id="5e529-103">Этот элемент конфигурации используется, чтобы задавать поведение времени выполнения при получении сообщений в службе или в клиентском приложении.</span><span class="sxs-lookup"><span data-stu-id="5e529-103">This configuration element is used to specify run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="5e529-104">Он не имеет атрибутов или дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="5e529-104">It does not have any attributes or child elements.</span></span>  
  
 <span data-ttu-id="5e529-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5e529-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="5e529-106">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="5e529-106">\<behaviors></span></span>  
<span data-ttu-id="5e529-107">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="5e529-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="5e529-108">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="5e529-108">\<behavior></span></span>  
<span data-ttu-id="5e529-109">\<synchronousReceive ></span><span class="sxs-lookup"><span data-stu-id="5e529-109">\<synchronousReceive></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e529-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5e529-110">Syntax</span></span>  
  
```xml  
<synchronousReceive />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5e529-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5e529-111">Attributes and Elements</span></span>  
 <span data-ttu-id="5e529-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5e529-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5e529-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5e529-113">Attributes</span></span>  
 <span data-ttu-id="5e529-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5e529-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5e529-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5e529-115">Child Elements</span></span>  
 <span data-ttu-id="5e529-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5e529-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5e529-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5e529-117">Parent Elements</span></span>  
  
|<span data-ttu-id="5e529-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="5e529-118">Element</span></span>|<span data-ttu-id="5e529-119">Описание</span><span class="sxs-lookup"><span data-stu-id="5e529-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5e529-120">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="5e529-120">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="5e529-121">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="5e529-121">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5e529-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="5e529-122">Remarks</span></span>  
 <span data-ttu-id="5e529-123">Используйте это поведение, чтобы дать указание прослушивателю каналов использовать синхронное получение вместо асинхронного получения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5e529-123">Use this behavior to instruct the channel listener to use a synchronous receive rather than the default, asynchronous.</span></span> <span data-ttu-id="5e529-124">Windows Communication Foundation (WCF) выдает новый поток для обработки каждого принятого канала.</span><span class="sxs-lookup"><span data-stu-id="5e529-124">Windows Communication Foundation (WCF) issues a new thread to pump for each accepted channel.</span></span> <span data-ttu-id="5e529-125">При наличии множества каналов существует вероятность недостатка потоков.</span><span class="sxs-lookup"><span data-stu-id="5e529-125">If there are a lot of channels, there is the possibility of running out of threads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e529-126">См. также</span><span class="sxs-lookup"><span data-stu-id="5e529-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>
- <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>
