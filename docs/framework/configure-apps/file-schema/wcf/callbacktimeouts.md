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
ms.workload: dotnet
ms.openlocfilehash: 71fc89a4b9735c13429b31d8cd7c5995f641afa8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltcallbacktimeoutsgt"></a><span data-ttu-id="aad2c-102">&lt;callbackTimeouts&gt;</span><span class="sxs-lookup"><span data-stu-id="aad2c-102">&lt;callbackTimeouts&gt;</span></span>
<span data-ttu-id="aad2c-103">Задает значение времени ожидания при потоке транзакций от сервера к клиенту в сценарии с дуплексным контрактом обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="aad2c-103">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
 <span data-ttu-id="aad2c-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="aad2c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="aad2c-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="aad2c-105">\<behaviors></span></span>  
<span data-ttu-id="aad2c-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="aad2c-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="aad2c-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="aad2c-107">\<behavior></span></span>  
<span data-ttu-id="aad2c-108">\<callbackTimeOuts ></span><span class="sxs-lookup"><span data-stu-id="aad2c-108">\<callbackTimeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aad2c-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aad2c-109">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />  
```  
  
## <a name="type"></a><span data-ttu-id="aad2c-110">Тип</span><span class="sxs-lookup"><span data-stu-id="aad2c-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aad2c-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="aad2c-111">Attributes and Elements</span></span>  
 <span data-ttu-id="aad2c-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="aad2c-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aad2c-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="aad2c-113">Attributes</span></span>  
  
|<span data-ttu-id="aad2c-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="aad2c-114">Attribute</span></span>|<span data-ttu-id="aad2c-115">Описание</span><span class="sxs-lookup"><span data-stu-id="aad2c-115">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="aad2c-116">Значение <xref:System.TimeSpan>, задающее интервал времени, в течение которого транзакции должны завершаться или автоматически прерываться.</span><span class="sxs-lookup"><span data-stu-id="aad2c-116">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="aad2c-117">Значение по умолчанию — «00: 00:00».</span><span class="sxs-lookup"><span data-stu-id="aad2c-117">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aad2c-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="aad2c-118">Child Elements</span></span>  
 <span data-ttu-id="aad2c-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="aad2c-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="aad2c-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="aad2c-120">Parent Elements</span></span>  
  
|<span data-ttu-id="aad2c-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="aad2c-121">Element</span></span>|<span data-ttu-id="aad2c-122">Описание:</span><span class="sxs-lookup"><span data-stu-id="aad2c-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aad2c-123">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="aad2c-123">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="aad2c-124">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="aad2c-124">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aad2c-125">См. также</span><span class="sxs-lookup"><span data-stu-id="aad2c-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
