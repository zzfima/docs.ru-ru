---
title: Элемент <synchronousReceive>
ms.date: 03/30/2017
ms.assetid: cc070387-3d11-4b02-a952-bc08ad2df05a
ms.openlocfilehash: b3f4860be6b7edac776a1c30611271b2eb36968e
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399501"
---
# <a name="synchronousreceive-element"></a><span data-ttu-id="0a02b-102">\<Элемент > Синчронаусрецеиве</span><span class="sxs-lookup"><span data-stu-id="0a02b-102">\<synchronousReceive> element</span></span>
<span data-ttu-id="0a02b-103">Этот элемент конфигурации используется, чтобы задавать поведение времени выполнения при получении сообщений в службе или в клиентском приложении.</span><span class="sxs-lookup"><span data-stu-id="0a02b-103">This configuration element is used to specify run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="0a02b-104">Он не имеет атрибутов или дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="0a02b-104">It does not have any attributes or child elements.</span></span>  
  
<span data-ttu-id="0a02b-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0a02b-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0a02b-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="0a02b-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="0a02b-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="0a02b-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="0a02b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="0a02b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="0a02b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="0a02b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="0a02b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Синчронаусрецеиве >**</span><span class="sxs-lookup"><span data-stu-id="0a02b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<synchronousReceive>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a02b-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0a02b-111">Syntax</span></span>  
  
```xml  
<synchronousReceive />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0a02b-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0a02b-112">Attributes and Elements</span></span>  
 <span data-ttu-id="0a02b-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0a02b-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0a02b-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0a02b-114">Attributes</span></span>  
 <span data-ttu-id="0a02b-115">Нет.</span><span class="sxs-lookup"><span data-stu-id="0a02b-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0a02b-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0a02b-116">Child Elements</span></span>  
 <span data-ttu-id="0a02b-117">Нет.</span><span class="sxs-lookup"><span data-stu-id="0a02b-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0a02b-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0a02b-118">Parent Elements</span></span>  
  
|<span data-ttu-id="0a02b-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="0a02b-119">Element</span></span>|<span data-ttu-id="0a02b-120">Описание</span><span class="sxs-lookup"><span data-stu-id="0a02b-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0a02b-121">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="0a02b-121">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="0a02b-122">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="0a02b-122">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0a02b-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="0a02b-123">Remarks</span></span>  
 <span data-ttu-id="0a02b-124">Используйте это поведение, чтобы дать указание прослушивателю каналов использовать синхронное получение вместо асинхронного получения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0a02b-124">Use this behavior to instruct the channel listener to use a synchronous receive rather than the default, asynchronous.</span></span> <span data-ttu-id="0a02b-125">Windows Communication Foundation (WCF) выдает новый поток для приема для каждого принятого канала.</span><span class="sxs-lookup"><span data-stu-id="0a02b-125">Windows Communication Foundation (WCF) issues a new thread to pump for each accepted channel.</span></span> <span data-ttu-id="0a02b-126">При наличии множества каналов существует вероятность недостатка потоков.</span><span class="sxs-lookup"><span data-stu-id="0a02b-126">If there are a lot of channels, there is the possibility of running out of threads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a02b-127">См. также</span><span class="sxs-lookup"><span data-stu-id="0a02b-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>
- <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>
