---
title: "Элемент &lt;synchronousReceive&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc070387-3d11-4b02-a952-bc08ad2df05a
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b630f5ad2fbf5e3f20667e0bd1b7ae711992dc18
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltsynchronousreceivegt-element"></a><span data-ttu-id="d2c6b-102">Элемент &lt;synchronousReceive&gt;</span><span class="sxs-lookup"><span data-stu-id="d2c6b-102">&lt;synchronousReceive&gt; element</span></span>
<span data-ttu-id="d2c6b-103">Этот элемент конфигурации используется, чтобы задавать поведение времени выполнения при получении сообщений в службе или в клиентском приложении.</span><span class="sxs-lookup"><span data-stu-id="d2c6b-103">This configuration element is used to specify run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="d2c6b-104">Он не имеет атрибутов или дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="d2c6b-104">It does not have any attributes or child elements.</span></span>  
  
 <span data-ttu-id="d2c6b-105">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="d2c6b-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="d2c6b-106">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="d2c6b-106">\<behaviors></span></span>  
<span data-ttu-id="d2c6b-107">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="d2c6b-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="d2c6b-108">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="d2c6b-108">\<behavior></span></span>  
<span data-ttu-id="d2c6b-109">\<synchronousReceive ></span><span class="sxs-lookup"><span data-stu-id="d2c6b-109">\<synchronousReceive></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2c6b-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d2c6b-110">Syntax</span></span>  
  
```xml  
<synchronousReceive />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d2c6b-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d2c6b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d2c6b-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d2c6b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d2c6b-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d2c6b-113">Attributes</span></span>  
 <span data-ttu-id="d2c6b-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d2c6b-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d2c6b-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d2c6b-115">Child Elements</span></span>  
 <span data-ttu-id="d2c6b-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d2c6b-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d2c6b-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d2c6b-117">Parent Elements</span></span>  
  
|<span data-ttu-id="d2c6b-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="d2c6b-118">Element</span></span>|<span data-ttu-id="d2c6b-119">Описание</span><span class="sxs-lookup"><span data-stu-id="d2c6b-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d2c6b-120">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="d2c6b-120">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="d2c6b-121">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="d2c6b-121">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d2c6b-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="d2c6b-122">Remarks</span></span>  
 <span data-ttu-id="d2c6b-123">Используйте это поведение, чтобы дать указание прослушивателю каналов использовать синхронное получение вместо асинхронного получения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d2c6b-123">Use this behavior to instruct the channel listener to use a synchronous receive rather than the default, asynchronous.</span></span> [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<span data-ttu-id="d2c6b-124"> создает новый поток переноса сообщений для каждого принятого канала.</span><span class="sxs-lookup"><span data-stu-id="d2c6b-124"> issues a new thread to pump for each accepted channel.</span></span> <span data-ttu-id="d2c6b-125">При наличии множества каналов существует вероятность недостатка потоков.</span><span class="sxs-lookup"><span data-stu-id="d2c6b-125">If there are a lot of channels, there is the possibility of running out of threads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2c6b-126">См. также</span><span class="sxs-lookup"><span data-stu-id="d2c6b-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>  
 <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>
