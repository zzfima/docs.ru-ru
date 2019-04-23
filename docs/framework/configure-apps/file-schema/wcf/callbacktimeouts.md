---
title: <callbackTimeouts>
ms.date: 03/30/2017
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
ms.openlocfilehash: e666bac0be772e417f140e1482649f82ea70e2f6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59173645"
---
# <a name="callbacktimeouts"></a><span data-ttu-id="09abd-101">\<callbackTimeouts></span><span class="sxs-lookup"><span data-stu-id="09abd-101">\<callbackTimeouts></span></span>
<span data-ttu-id="09abd-102">Задает значение времени ожидания при потоке транзакций от сервера к клиенту в сценарии с дуплексным контрактом обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="09abd-102">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
 <span data-ttu-id="09abd-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="09abd-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="09abd-104">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="09abd-104">\<behaviors></span></span>  
<span data-ttu-id="09abd-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="09abd-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="09abd-106">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="09abd-106">\<behavior></span></span>  
<span data-ttu-id="09abd-107">\<callbackTimeOuts></span><span class="sxs-lookup"><span data-stu-id="09abd-107">\<callbackTimeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09abd-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="09abd-108">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="09abd-109">Тип</span><span class="sxs-lookup"><span data-stu-id="09abd-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="09abd-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="09abd-110">Attributes and Elements</span></span>  
 <span data-ttu-id="09abd-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="09abd-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="09abd-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="09abd-112">Attributes</span></span>  
  
|<span data-ttu-id="09abd-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="09abd-113">Attribute</span></span>|<span data-ttu-id="09abd-114">Описание</span><span class="sxs-lookup"><span data-stu-id="09abd-114">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="09abd-115">Значение <xref:System.TimeSpan>, задающее интервал времени, в течение которого транзакции должны завершаться или автоматически прерываться.</span><span class="sxs-lookup"><span data-stu-id="09abd-115">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="09abd-116">Значение по умолчанию — «00: 00:00».</span><span class="sxs-lookup"><span data-stu-id="09abd-116">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="09abd-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="09abd-117">Child Elements</span></span>  
 <span data-ttu-id="09abd-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="09abd-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="09abd-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="09abd-119">Parent Elements</span></span>  
  
|<span data-ttu-id="09abd-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="09abd-120">Element</span></span>|<span data-ttu-id="09abd-121">Описание</span><span class="sxs-lookup"><span data-stu-id="09abd-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="09abd-122">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="09abd-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="09abd-123">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="09abd-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="09abd-124">См. также</span><span class="sxs-lookup"><span data-stu-id="09abd-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
