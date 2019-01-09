---
title: '&lt;serviceTimeouts&gt;'
ms.date: 03/30/2017
ms.assetid: ada536cf-97dc-4cd7-89ec-ed1466c1c557
ms.openlocfilehash: 4cb4b4ae6fe01430989d9ee5f3d94b16778595aa
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54148478"
---
# <a name="ltservicetimeoutsgt"></a><span data-ttu-id="7bd6f-102">&lt;serviceTimeouts&gt;</span><span class="sxs-lookup"><span data-stu-id="7bd6f-102">&lt;serviceTimeouts&gt;</span></span>
<span data-ttu-id="7bd6f-103">Задает время ожидания для службы.</span><span class="sxs-lookup"><span data-stu-id="7bd6f-103">Specifies the timeout for a service.</span></span>  
  
 <span data-ttu-id="7bd6f-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="7bd6f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="7bd6f-105">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="7bd6f-105">\<behaviors></span></span>  
<span data-ttu-id="7bd6f-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="7bd6f-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="7bd6f-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="7bd6f-107">\<behavior></span></span>  
<span data-ttu-id="7bd6f-108">\<serviceTimeouts ></span><span class="sxs-lookup"><span data-stu-id="7bd6f-108">\<serviceTimeouts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bd6f-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7bd6f-109">Syntax</span></span>  
  
```xml  
<serviceTimeouts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="7bd6f-110">Тип</span><span class="sxs-lookup"><span data-stu-id="7bd6f-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7bd6f-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7bd6f-111">Attributes and Elements</span></span>  
 <span data-ttu-id="7bd6f-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7bd6f-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7bd6f-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7bd6f-113">Attributes</span></span>  
  
|<span data-ttu-id="7bd6f-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="7bd6f-114">Attribute</span></span>|<span data-ttu-id="7bd6f-115">Описание</span><span class="sxs-lookup"><span data-stu-id="7bd6f-115">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="7bd6f-116">Значение <xref:System.TimeSpan>, задающее интервал времени, в течение которого транзакция должна дойти от клиента до сервера.</span><span class="sxs-lookup"><span data-stu-id="7bd6f-116">A <xref:System.TimeSpan> value that specifies the interval of time a transaction must flow from client to server.</span></span> <span data-ttu-id="7bd6f-117">Значение по умолчанию — «00: 00:00».</span><span class="sxs-lookup"><span data-stu-id="7bd6f-117">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7bd6f-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7bd6f-118">Child Elements</span></span>  
 <span data-ttu-id="7bd6f-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="7bd6f-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7bd6f-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7bd6f-120">Parent Elements</span></span>  
  
|<span data-ttu-id="7bd6f-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="7bd6f-121">Element</span></span>|<span data-ttu-id="7bd6f-122">Описание:</span><span class="sxs-lookup"><span data-stu-id="7bd6f-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7bd6f-123">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="7bd6f-123">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="7bd6f-124">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="7bd6f-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7bd6f-125">См. также</span><span class="sxs-lookup"><span data-stu-id="7bd6f-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
