---
title: <callbackTimeouts>
ms.date: 03/30/2017
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
ms.openlocfilehash: e666bac0be772e417f140e1482649f82ea70e2f6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673424"
---
# <a name="callbacktimeouts"></a><span data-ttu-id="dc69e-101">\<callbackTimeouts></span><span class="sxs-lookup"><span data-stu-id="dc69e-101">\<callbackTimeouts></span></span>
<span data-ttu-id="dc69e-102">Задает значение времени ожидания при потоке транзакций от сервера к клиенту в сценарии с дуплексным контрактом обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="dc69e-102">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
 <span data-ttu-id="dc69e-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="dc69e-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="dc69e-104">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="dc69e-104">\<behaviors></span></span>  
<span data-ttu-id="dc69e-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="dc69e-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="dc69e-106">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="dc69e-106">\<behavior></span></span>  
<span data-ttu-id="dc69e-107">\<callbackTimeOuts></span><span class="sxs-lookup"><span data-stu-id="dc69e-107">\<callbackTimeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc69e-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dc69e-108">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="dc69e-109">Тип</span><span class="sxs-lookup"><span data-stu-id="dc69e-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dc69e-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="dc69e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="dc69e-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="dc69e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dc69e-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="dc69e-112">Attributes</span></span>  
  
|<span data-ttu-id="dc69e-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="dc69e-113">Attribute</span></span>|<span data-ttu-id="dc69e-114">Описание</span><span class="sxs-lookup"><span data-stu-id="dc69e-114">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="dc69e-115">Значение <xref:System.TimeSpan>, задающее интервал времени, в течение которого транзакции должны завершаться или автоматически прерываться.</span><span class="sxs-lookup"><span data-stu-id="dc69e-115">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="dc69e-116">Значение по умолчанию — «00: 00:00».</span><span class="sxs-lookup"><span data-stu-id="dc69e-116">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dc69e-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="dc69e-117">Child Elements</span></span>  
 <span data-ttu-id="dc69e-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="dc69e-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dc69e-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="dc69e-119">Parent Elements</span></span>  
  
|<span data-ttu-id="dc69e-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="dc69e-120">Element</span></span>|<span data-ttu-id="dc69e-121">Описание</span><span class="sxs-lookup"><span data-stu-id="dc69e-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dc69e-122">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="dc69e-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="dc69e-123">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="dc69e-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dc69e-124">См. также</span><span class="sxs-lookup"><span data-stu-id="dc69e-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
