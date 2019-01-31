---
title: <callbackTimeouts>
ms.date: 03/30/2017
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
ms.openlocfilehash: 269500324ad1beaa0b519fa17d251ee942276faa
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269072"
---
# <a name="callbacktimeouts"></a><span data-ttu-id="f8d86-101">\<callbackTimeouts></span><span class="sxs-lookup"><span data-stu-id="f8d86-101">\<callbackTimeouts></span></span>
<span data-ttu-id="f8d86-102">Задает значение времени ожидания при потоке транзакций от сервера к клиенту в сценарии с дуплексным контрактом обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="f8d86-102">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
 <span data-ttu-id="f8d86-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f8d86-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="f8d86-104">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="f8d86-104">\<behaviors></span></span>  
<span data-ttu-id="f8d86-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="f8d86-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="f8d86-106">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="f8d86-106">\<behavior></span></span>  
<span data-ttu-id="f8d86-107">\<callbackTimeOuts></span><span class="sxs-lookup"><span data-stu-id="f8d86-107">\<callbackTimeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8d86-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f8d86-108">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="f8d86-109">Тип</span><span class="sxs-lookup"><span data-stu-id="f8d86-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f8d86-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f8d86-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f8d86-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f8d86-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f8d86-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f8d86-112">Attributes</span></span>  
  
|<span data-ttu-id="f8d86-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f8d86-113">Attribute</span></span>|<span data-ttu-id="f8d86-114">Описание</span><span class="sxs-lookup"><span data-stu-id="f8d86-114">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="f8d86-115">Значение <xref:System.TimeSpan>, задающее интервал времени, в течение которого транзакции должны завершаться или автоматически прерываться.</span><span class="sxs-lookup"><span data-stu-id="f8d86-115">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="f8d86-116">Значение по умолчанию — «00: 00:00».</span><span class="sxs-lookup"><span data-stu-id="f8d86-116">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f8d86-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f8d86-117">Child Elements</span></span>  
 <span data-ttu-id="f8d86-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f8d86-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f8d86-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f8d86-119">Parent Elements</span></span>  
  
|<span data-ttu-id="f8d86-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="f8d86-120">Element</span></span>|<span data-ttu-id="f8d86-121">Описание:</span><span class="sxs-lookup"><span data-stu-id="f8d86-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f8d86-122">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="f8d86-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="f8d86-123">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="f8d86-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f8d86-124">См. также</span><span class="sxs-lookup"><span data-stu-id="f8d86-124">See also</span></span>
- <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
