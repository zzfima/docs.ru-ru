---
title: '&lt;callbackTimeouts&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5a030a615aae0159e1426bdf4c640ddfab7287dd
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltcallbacktimeoutsgt"></a><span data-ttu-id="bda83-102">&lt;callbackTimeouts&gt;</span><span class="sxs-lookup"><span data-stu-id="bda83-102">&lt;callbackTimeouts&gt;</span></span>
<span data-ttu-id="bda83-103">Задает значение времени ожидания при потоке транзакций от сервера к клиенту в сценарии с дуплексным контрактом обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="bda83-103">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
 <span data-ttu-id="bda83-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="bda83-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="bda83-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="bda83-105">\<behaviors></span></span>  
<span data-ttu-id="bda83-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="bda83-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="bda83-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="bda83-107">\<behavior></span></span>  
<span data-ttu-id="bda83-108">\<callbackTimeOuts ></span><span class="sxs-lookup"><span data-stu-id="bda83-108">\<callbackTimeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bda83-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bda83-109">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />  
```  
  
## <a name="type"></a><span data-ttu-id="bda83-110">Тип</span><span class="sxs-lookup"><span data-stu-id="bda83-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bda83-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="bda83-111">Attributes and Elements</span></span>  
 <span data-ttu-id="bda83-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="bda83-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bda83-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bda83-113">Attributes</span></span>  
  
|<span data-ttu-id="bda83-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="bda83-114">Attribute</span></span>|<span data-ttu-id="bda83-115">Описание</span><span class="sxs-lookup"><span data-stu-id="bda83-115">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="bda83-116">Значение <xref:System.TimeSpan>, задающее интервал времени, в течение которого транзакции должны завершаться или автоматически прерываться.</span><span class="sxs-lookup"><span data-stu-id="bda83-116">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="bda83-117">Значение по умолчанию — «00: 00:00».</span><span class="sxs-lookup"><span data-stu-id="bda83-117">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bda83-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bda83-118">Child Elements</span></span>  
 <span data-ttu-id="bda83-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="bda83-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bda83-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bda83-120">Parent Elements</span></span>  
  
|<span data-ttu-id="bda83-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="bda83-121">Element</span></span>|<span data-ttu-id="bda83-122">Описание</span><span class="sxs-lookup"><span data-stu-id="bda83-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bda83-123">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="bda83-123">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="bda83-124">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="bda83-124">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bda83-125">См. также</span><span class="sxs-lookup"><span data-stu-id="bda83-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
