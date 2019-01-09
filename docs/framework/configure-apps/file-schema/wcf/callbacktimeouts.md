---
title: '&lt;callbackTimeouts&gt;'
ms.date: 03/30/2017
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
ms.openlocfilehash: 85e7b1f0d009e27cbacd9f69b381e4f05984bf56
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149115"
---
# <a name="ltcallbacktimeoutsgt"></a><span data-ttu-id="43577-102">&lt;callbackTimeouts&gt;</span><span class="sxs-lookup"><span data-stu-id="43577-102">&lt;callbackTimeouts&gt;</span></span>
<span data-ttu-id="43577-103">Задает значение времени ожидания при потоке транзакций от сервера к клиенту в сценарии с дуплексным контрактом обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="43577-103">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
 <span data-ttu-id="43577-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="43577-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="43577-105">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="43577-105">\<behaviors></span></span>  
<span data-ttu-id="43577-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="43577-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="43577-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="43577-107">\<behavior></span></span>  
<span data-ttu-id="43577-108">\<callbackTimeOuts ></span><span class="sxs-lookup"><span data-stu-id="43577-108">\<callbackTimeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43577-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="43577-109">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="43577-110">Тип</span><span class="sxs-lookup"><span data-stu-id="43577-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="43577-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="43577-111">Attributes and Elements</span></span>  
 <span data-ttu-id="43577-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="43577-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="43577-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="43577-113">Attributes</span></span>  
  
|<span data-ttu-id="43577-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="43577-114">Attribute</span></span>|<span data-ttu-id="43577-115">Описание</span><span class="sxs-lookup"><span data-stu-id="43577-115">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="43577-116">Значение <xref:System.TimeSpan>, задающее интервал времени, в течение которого транзакции должны завершаться или автоматически прерываться.</span><span class="sxs-lookup"><span data-stu-id="43577-116">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="43577-117">Значение по умолчанию — «00: 00:00».</span><span class="sxs-lookup"><span data-stu-id="43577-117">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="43577-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="43577-118">Child Elements</span></span>  
 <span data-ttu-id="43577-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="43577-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="43577-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="43577-120">Parent Elements</span></span>  
  
|<span data-ttu-id="43577-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="43577-121">Element</span></span>|<span data-ttu-id="43577-122">Описание</span><span class="sxs-lookup"><span data-stu-id="43577-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="43577-123">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="43577-123">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="43577-124">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="43577-124">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="43577-125">См. также</span><span class="sxs-lookup"><span data-stu-id="43577-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
