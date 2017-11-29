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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e86b69b7d633fd99728936070e94da964e16de58
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ltcallbacktimeoutsgt"></a><span data-ttu-id="d6f40-102">&lt;callbackTimeouts&gt;</span><span class="sxs-lookup"><span data-stu-id="d6f40-102">&lt;callbackTimeouts&gt;</span></span>
<span data-ttu-id="d6f40-103">Задает значение времени ожидания при потоке транзакций от сервера к клиенту в сценарии с дуплексным контрактом обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="d6f40-103">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
 <span data-ttu-id="d6f40-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="d6f40-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d6f40-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="d6f40-105">\<behaviors></span></span>  
<span data-ttu-id="d6f40-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="d6f40-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="d6f40-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="d6f40-107">\<behavior></span></span>  
<span data-ttu-id="d6f40-108">\<callbackTimeOuts ></span><span class="sxs-lookup"><span data-stu-id="d6f40-108">\<callbackTimeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6f40-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d6f40-109">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />  
```  
  
## <a name="type"></a><span data-ttu-id="d6f40-110">Тип</span><span class="sxs-lookup"><span data-stu-id="d6f40-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d6f40-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d6f40-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d6f40-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d6f40-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d6f40-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d6f40-113">Attributes</span></span>  
  
|<span data-ttu-id="d6f40-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d6f40-114">Attribute</span></span>|<span data-ttu-id="d6f40-115">Описание</span><span class="sxs-lookup"><span data-stu-id="d6f40-115">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="d6f40-116">Значение <xref:System.TimeSpan>, задающее интервал времени, в течение которого транзакции должны завершаться или автоматически прерываться.</span><span class="sxs-lookup"><span data-stu-id="d6f40-116">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="d6f40-117">Значение по умолчанию — «00: 00:00».</span><span class="sxs-lookup"><span data-stu-id="d6f40-117">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d6f40-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d6f40-118">Child Elements</span></span>  
 <span data-ttu-id="d6f40-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d6f40-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d6f40-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d6f40-120">Parent Elements</span></span>  
  
|<span data-ttu-id="d6f40-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="d6f40-121">Element</span></span>|<span data-ttu-id="d6f40-122">Описание</span><span class="sxs-lookup"><span data-stu-id="d6f40-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d6f40-123">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="d6f40-123">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="d6f40-124">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="d6f40-124">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d6f40-125">См. также</span><span class="sxs-lookup"><span data-stu-id="d6f40-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
