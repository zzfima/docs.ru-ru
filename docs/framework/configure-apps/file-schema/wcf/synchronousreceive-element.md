---
title: <synchronousReceive> - элемент
ms.date: 03/30/2017
ms.assetid: cc070387-3d11-4b02-a952-bc08ad2df05a
ms.openlocfilehash: f4a8868304ebae9a7ed5e6afbfb14fb2116afc49
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55278482"
---
# <a name="synchronousreceive-element"></a><span data-ttu-id="eb204-102">\<synchronousReceive > элемент</span><span class="sxs-lookup"><span data-stu-id="eb204-102">\<synchronousReceive> element</span></span>
<span data-ttu-id="eb204-103">Этот элемент конфигурации используется, чтобы задавать поведение времени выполнения при получении сообщений в службе или в клиентском приложении.</span><span class="sxs-lookup"><span data-stu-id="eb204-103">This configuration element is used to specify run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="eb204-104">Он не имеет атрибутов или дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="eb204-104">It does not have any attributes or child elements.</span></span>  
  
 <span data-ttu-id="eb204-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="eb204-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="eb204-106">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="eb204-106">\<behaviors></span></span>  
<span data-ttu-id="eb204-107">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="eb204-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="eb204-108">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="eb204-108">\<behavior></span></span>  
<span data-ttu-id="eb204-109">\<synchronousReceive ></span><span class="sxs-lookup"><span data-stu-id="eb204-109">\<synchronousReceive></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb204-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eb204-110">Syntax</span></span>  
  
```xml  
<synchronousReceive />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eb204-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="eb204-111">Attributes and Elements</span></span>  
 <span data-ttu-id="eb204-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="eb204-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eb204-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="eb204-113">Attributes</span></span>  
 <span data-ttu-id="eb204-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="eb204-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="eb204-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="eb204-115">Child Elements</span></span>  
 <span data-ttu-id="eb204-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="eb204-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eb204-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="eb204-117">Parent Elements</span></span>  
  
|<span data-ttu-id="eb204-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="eb204-118">Element</span></span>|<span data-ttu-id="eb204-119">Описание</span><span class="sxs-lookup"><span data-stu-id="eb204-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eb204-120">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="eb204-120">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="eb204-121">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="eb204-121">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eb204-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="eb204-122">Remarks</span></span>  
 <span data-ttu-id="eb204-123">Используйте это поведение, чтобы дать указание прослушивателю каналов использовать синхронное получение вместо асинхронного получения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="eb204-123">Use this behavior to instruct the channel listener to use a synchronous receive rather than the default, asynchronous.</span></span> <span data-ttu-id="eb204-124">Windows Communication Foundation (WCF) выдает новый поток для обработки каждого принятого канала.</span><span class="sxs-lookup"><span data-stu-id="eb204-124">Windows Communication Foundation (WCF) issues a new thread to pump for each accepted channel.</span></span> <span data-ttu-id="eb204-125">При наличии множества каналов существует вероятность недостатка потоков.</span><span class="sxs-lookup"><span data-stu-id="eb204-125">If there are a lot of channels, there is the possibility of running out of threads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb204-126">См. также</span><span class="sxs-lookup"><span data-stu-id="eb204-126">See also</span></span>
- <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>
- <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>
