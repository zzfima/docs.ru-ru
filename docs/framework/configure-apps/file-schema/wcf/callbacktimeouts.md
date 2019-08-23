---
title: <callbackTimeouts>
ms.date: 03/30/2017
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
ms.openlocfilehash: d57a888a19e684ac13632c1ab2476e304667c3e3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919662"
---
# <a name="callbacktimeouts"></a><span data-ttu-id="11cb7-101">\<Каллбакктимеаутс ></span><span class="sxs-lookup"><span data-stu-id="11cb7-101">\<callbackTimeouts></span></span>
<span data-ttu-id="11cb7-102">Задает значение времени ожидания при потоке транзакций от сервера к клиенту в сценарии с дуплексным контрактом обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="11cb7-102">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
 <span data-ttu-id="11cb7-103">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="11cb7-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="11cb7-104">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="11cb7-104">\<behaviors></span></span>  
<span data-ttu-id="11cb7-105">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="11cb7-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="11cb7-106">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="11cb7-106">\<behavior></span></span>  
<span data-ttu-id="11cb7-107">\<Каллбакктимеаутс ></span><span class="sxs-lookup"><span data-stu-id="11cb7-107">\<callbackTimeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11cb7-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="11cb7-108">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="11cb7-109">Тип</span><span class="sxs-lookup"><span data-stu-id="11cb7-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="11cb7-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="11cb7-110">Attributes and Elements</span></span>  
 <span data-ttu-id="11cb7-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="11cb7-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="11cb7-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="11cb7-112">Attributes</span></span>  
  
|<span data-ttu-id="11cb7-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="11cb7-113">Attribute</span></span>|<span data-ttu-id="11cb7-114">Описание</span><span class="sxs-lookup"><span data-stu-id="11cb7-114">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="11cb7-115">Значение <xref:System.TimeSpan>, задающее интервал времени, в течение которого транзакции должны завершаться или автоматически прерываться.</span><span class="sxs-lookup"><span data-stu-id="11cb7-115">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="11cb7-116">Значение по умолчанию — "00:00:00".</span><span class="sxs-lookup"><span data-stu-id="11cb7-116">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="11cb7-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="11cb7-117">Child Elements</span></span>  
 <span data-ttu-id="11cb7-118">Нет.</span><span class="sxs-lookup"><span data-stu-id="11cb7-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="11cb7-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="11cb7-119">Parent Elements</span></span>  
  
|<span data-ttu-id="11cb7-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="11cb7-120">Element</span></span>|<span data-ttu-id="11cb7-121">Описание</span><span class="sxs-lookup"><span data-stu-id="11cb7-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="11cb7-122">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="11cb7-122">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="11cb7-123">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="11cb7-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="11cb7-124">См. также</span><span class="sxs-lookup"><span data-stu-id="11cb7-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
