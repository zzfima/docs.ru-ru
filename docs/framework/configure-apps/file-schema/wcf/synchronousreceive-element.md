---
title: Элемент &lt;synchronousReceive&gt;
ms.date: 03/30/2017
ms.assetid: cc070387-3d11-4b02-a952-bc08ad2df05a
ms.openlocfilehash: bc89470900e50e4d3e522682b39b20e21a66b284
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147386"
---
# <a name="ltsynchronousreceivegt-element"></a><span data-ttu-id="88642-102">Элемент &lt;synchronousReceive&gt;</span><span class="sxs-lookup"><span data-stu-id="88642-102">&lt;synchronousReceive&gt; element</span></span>
<span data-ttu-id="88642-103">Этот элемент конфигурации используется, чтобы задавать поведение времени выполнения при получении сообщений в службе или в клиентском приложении.</span><span class="sxs-lookup"><span data-stu-id="88642-103">This configuration element is used to specify run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="88642-104">Он не имеет атрибутов или дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="88642-104">It does not have any attributes or child elements.</span></span>  
  
 <span data-ttu-id="88642-105">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="88642-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="88642-106">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="88642-106">\<behaviors></span></span>  
<span data-ttu-id="88642-107">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="88642-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="88642-108">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="88642-108">\<behavior></span></span>  
<span data-ttu-id="88642-109">\<synchronousReceive ></span><span class="sxs-lookup"><span data-stu-id="88642-109">\<synchronousReceive></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88642-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="88642-110">Syntax</span></span>  
  
```xml  
<synchronousReceive />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="88642-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="88642-111">Attributes and Elements</span></span>  
 <span data-ttu-id="88642-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="88642-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="88642-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="88642-113">Attributes</span></span>  
 <span data-ttu-id="88642-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="88642-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="88642-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="88642-115">Child Elements</span></span>  
 <span data-ttu-id="88642-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="88642-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="88642-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="88642-117">Parent Elements</span></span>  
  
|<span data-ttu-id="88642-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="88642-118">Element</span></span>|<span data-ttu-id="88642-119">Описание</span><span class="sxs-lookup"><span data-stu-id="88642-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="88642-120">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="88642-120">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="88642-121">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="88642-121">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="88642-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="88642-122">Remarks</span></span>  
 <span data-ttu-id="88642-123">Используйте это поведение, чтобы дать указание прослушивателю каналов использовать синхронное получение вместо асинхронного получения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="88642-123">Use this behavior to instruct the channel listener to use a synchronous receive rather than the default, asynchronous.</span></span> <span data-ttu-id="88642-124">Windows Communication Foundation (WCF) выдает новый поток для обработки каждого принятого канала.</span><span class="sxs-lookup"><span data-stu-id="88642-124">Windows Communication Foundation (WCF) issues a new thread to pump for each accepted channel.</span></span> <span data-ttu-id="88642-125">При наличии множества каналов существует вероятность недостатка потоков.</span><span class="sxs-lookup"><span data-stu-id="88642-125">If there are a lot of channels, there is the possibility of running out of threads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88642-126">См. также</span><span class="sxs-lookup"><span data-stu-id="88642-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>  
 <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>
