---
title: <serviceTimeouts>
ms.date: 03/30/2017
ms.assetid: ada536cf-97dc-4cd7-89ec-ed1466c1c557
ms.openlocfilehash: a1792fec4f86c9ac31107c043b976cfafcfa4c13
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937096"
---
# <a name="servicetimeouts"></a><span data-ttu-id="ed88d-101">\<Сервицетимеаутс ></span><span class="sxs-lookup"><span data-stu-id="ed88d-101">\<serviceTimeouts></span></span>
<span data-ttu-id="ed88d-102">Задает время ожидания для службы.</span><span class="sxs-lookup"><span data-stu-id="ed88d-102">Specifies the timeout for a service.</span></span>  
  
 <span data-ttu-id="ed88d-103">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ed88d-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="ed88d-104">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="ed88d-104">\<behaviors></span></span>  
<span data-ttu-id="ed88d-105">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="ed88d-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="ed88d-106">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="ed88d-106">\<behavior></span></span>  
<span data-ttu-id="ed88d-107">\<Сервицетимеаутс ></span><span class="sxs-lookup"><span data-stu-id="ed88d-107">\<serviceTimeouts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed88d-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ed88d-108">Syntax</span></span>  
  
```xml  
<serviceTimeouts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="ed88d-109">Тип</span><span class="sxs-lookup"><span data-stu-id="ed88d-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ed88d-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ed88d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ed88d-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ed88d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ed88d-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ed88d-112">Attributes</span></span>  
  
|<span data-ttu-id="ed88d-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ed88d-113">Attribute</span></span>|<span data-ttu-id="ed88d-114">Описание</span><span class="sxs-lookup"><span data-stu-id="ed88d-114">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="ed88d-115">Значение <xref:System.TimeSpan>, задающее интервал времени, в течение которого транзакция должна дойти от клиента до сервера.</span><span class="sxs-lookup"><span data-stu-id="ed88d-115">A <xref:System.TimeSpan> value that specifies the interval of time a transaction must flow from client to server.</span></span> <span data-ttu-id="ed88d-116">Значение по умолчанию — "00:00:00".</span><span class="sxs-lookup"><span data-stu-id="ed88d-116">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ed88d-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ed88d-117">Child Elements</span></span>  
 <span data-ttu-id="ed88d-118">Нет.</span><span class="sxs-lookup"><span data-stu-id="ed88d-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ed88d-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ed88d-119">Parent Elements</span></span>  
  
|<span data-ttu-id="ed88d-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="ed88d-120">Element</span></span>|<span data-ttu-id="ed88d-121">Описание</span><span class="sxs-lookup"><span data-stu-id="ed88d-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ed88d-122">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="ed88d-122">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="ed88d-123">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="ed88d-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ed88d-124">См. также</span><span class="sxs-lookup"><span data-stu-id="ed88d-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
