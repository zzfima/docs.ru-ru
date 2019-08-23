---
title: <persistenceProvider>
ms.date: 03/30/2017
ms.assetid: a37049c5-a7ea-4519-94f2-912eeb010380
ms.openlocfilehash: 4fc9e1332effc51e183a84cf2d3653357277d2ad
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934143"
---
# <a name="persistenceprovider"></a><span data-ttu-id="08da5-101">\<persistenceProvider ></span><span class="sxs-lookup"><span data-stu-id="08da5-101">\<persistenceProvider></span></span>
<span data-ttu-id="08da5-102">Задает тип используемой реализации поставщика сохраняемости, а также время ожидания операций сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="08da5-102">Specifies the type of the persistence provider implementation to use, as well as the time-out to use for persistence operations.</span></span>  
  
 <span data-ttu-id="08da5-103">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="08da5-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="08da5-104">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="08da5-104">\<behaviors></span></span>  
<span data-ttu-id="08da5-105">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="08da5-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="08da5-106">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="08da5-106">\<behavior></span></span>  
<span data-ttu-id="08da5-107">\<persistenceProvider ></span><span class="sxs-lookup"><span data-stu-id="08da5-107">\<persistenceProvider></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08da5-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="08da5-108">Syntax</span></span>  
  
```xml  
<persistenceProvider persistenceOperationTimeout="TimeSpan"
                     type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="08da5-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="08da5-109">Attributes and Elements</span></span>  
 <span data-ttu-id="08da5-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="08da5-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="08da5-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="08da5-111">Attributes</span></span>  
  
|<span data-ttu-id="08da5-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="08da5-112">Attribute</span></span>|<span data-ttu-id="08da5-113">Описание</span><span class="sxs-lookup"><span data-stu-id="08da5-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="08da5-114">persistenceOperationTimeout</span><span class="sxs-lookup"><span data-stu-id="08da5-114">persistenceOperationTimeout</span></span>|<span data-ttu-id="08da5-115">Значение <xref:System.TimeSpan>, которое задает время ожидания, используемое для операций сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="08da5-115">A <xref:System.TimeSpan> value that specifies the time-out used for persistence operations.</span></span> <span data-ttu-id="08da5-116">Значение по умолчанию — "00:00:30".</span><span class="sxs-lookup"><span data-stu-id="08da5-116">The default is "00:00:30".</span></span>|  
|<span data-ttu-id="08da5-117">type</span><span class="sxs-lookup"><span data-stu-id="08da5-117">type</span></span>|<span data-ttu-id="08da5-118">Строка, указывающая тип используемой фабрики поставщика сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="08da5-118">A string that specifies the type of the persistence provider factory to use.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="08da5-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="08da5-119">Child Elements</span></span>  
 <span data-ttu-id="08da5-120">Нет.</span><span class="sxs-lookup"><span data-stu-id="08da5-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="08da5-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="08da5-121">Parent Elements</span></span>  
  
|<span data-ttu-id="08da5-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="08da5-122">Element</span></span>|<span data-ttu-id="08da5-123">Описание</span><span class="sxs-lookup"><span data-stu-id="08da5-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="08da5-124">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="08da5-124">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="08da5-125">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="08da5-125">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08da5-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="08da5-126">Remarks</span></span>  
 <span data-ttu-id="08da5-127">Этот элемент задает поставщика сохраняемости, используемого для сериализации состояния службы WCF.</span><span class="sxs-lookup"><span data-stu-id="08da5-127">This element specifies the persistence provider to be used to serialize the state of a WCF service.</span></span> <span data-ttu-id="08da5-128">Он должен использоваться вместе с атрибутом `wsHttpContextBinding`, который передает сведения о состоянии в HTTP-заголовки.</span><span class="sxs-lookup"><span data-stu-id="08da5-128">It should be used together with the `wsHttpContextBinding` which passes state information in HTTP headers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08da5-129">См. также</span><span class="sxs-lookup"><span data-stu-id="08da5-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.PersistenceProviderElement>
- <xref:System.ServiceModel.Persistence.PersistenceProvider>
