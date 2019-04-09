---
title: <serviceTimeouts>
ms.date: 03/30/2017
ms.assetid: ada536cf-97dc-4cd7-89ec-ed1466c1c557
ms.openlocfilehash: 5c2f0ef7ad509eb5d6c686802c3fe5a75ea1a258
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59075526"
---
# <a name="servicetimeouts"></a><span data-ttu-id="fb0a2-101">\<serviceTimeouts></span><span class="sxs-lookup"><span data-stu-id="fb0a2-101">\<serviceTimeouts></span></span>
<span data-ttu-id="fb0a2-102">Задает время ожидания для службы.</span><span class="sxs-lookup"><span data-stu-id="fb0a2-102">Specifies the timeout for a service.</span></span>  
  
 <span data-ttu-id="fb0a2-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="fb0a2-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="fb0a2-104">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="fb0a2-104">\<behaviors></span></span>  
<span data-ttu-id="fb0a2-105">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="fb0a2-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="fb0a2-106">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="fb0a2-106">\<behavior></span></span>  
<span data-ttu-id="fb0a2-107">\<serviceTimeouts></span><span class="sxs-lookup"><span data-stu-id="fb0a2-107">\<serviceTimeouts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb0a2-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fb0a2-108">Syntax</span></span>  
  
```xml  
<serviceTimeouts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="fb0a2-109">Тип</span><span class="sxs-lookup"><span data-stu-id="fb0a2-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fb0a2-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="fb0a2-110">Attributes and Elements</span></span>  
 <span data-ttu-id="fb0a2-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="fb0a2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fb0a2-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="fb0a2-112">Attributes</span></span>  
  
|<span data-ttu-id="fb0a2-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="fb0a2-113">Attribute</span></span>|<span data-ttu-id="fb0a2-114">Описание</span><span class="sxs-lookup"><span data-stu-id="fb0a2-114">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="fb0a2-115">Значение <xref:System.TimeSpan>, задающее интервал времени, в течение которого транзакция должна дойти от клиента до сервера.</span><span class="sxs-lookup"><span data-stu-id="fb0a2-115">A <xref:System.TimeSpan> value that specifies the interval of time a transaction must flow from client to server.</span></span> <span data-ttu-id="fb0a2-116">Значение по умолчанию — «00: 00:00».</span><span class="sxs-lookup"><span data-stu-id="fb0a2-116">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fb0a2-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="fb0a2-117">Child Elements</span></span>  
 <span data-ttu-id="fb0a2-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="fb0a2-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fb0a2-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="fb0a2-119">Parent Elements</span></span>  
  
|<span data-ttu-id="fb0a2-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="fb0a2-120">Element</span></span>|<span data-ttu-id="fb0a2-121">Описание</span><span class="sxs-lookup"><span data-stu-id="fb0a2-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fb0a2-122">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="fb0a2-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="fb0a2-123">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="fb0a2-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fb0a2-124">См. также</span><span class="sxs-lookup"><span data-stu-id="fb0a2-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
