---
title: '&lt;persistenceProvider&gt;'
ms.date: 03/30/2017
ms.assetid: a37049c5-a7ea-4519-94f2-912eeb010380
ms.openlocfilehash: ba02977a7df44931ae195040949e9a8eb0c141b5
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54152025"
---
# <a name="ltpersistenceprovidergt"></a><span data-ttu-id="2f562-102">&lt;persistenceProvider&gt;</span><span class="sxs-lookup"><span data-stu-id="2f562-102">&lt;persistenceProvider&gt;</span></span>
<span data-ttu-id="2f562-103">Задает тип используемой реализации поставщика сохраняемости, а также время ожидания операций сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="2f562-103">Specifies the type of the persistence provider implementation to use, as well as the time-out to use for persistence operations.</span></span>  
  
 <span data-ttu-id="2f562-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="2f562-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="2f562-105">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="2f562-105">\<behaviors></span></span>  
<span data-ttu-id="2f562-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="2f562-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="2f562-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="2f562-107">\<behavior></span></span>  
<span data-ttu-id="2f562-108">\<persistenceProvider ></span><span class="sxs-lookup"><span data-stu-id="2f562-108">\<persistenceProvider></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f562-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2f562-109">Syntax</span></span>  
  
```xml  
<persistenceProvider persistenceOperationTimeout="TimeSpan"
                     type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2f562-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2f562-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2f562-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2f562-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2f562-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2f562-112">Attributes</span></span>  
  
|<span data-ttu-id="2f562-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="2f562-113">Attribute</span></span>|<span data-ttu-id="2f562-114">Описание</span><span class="sxs-lookup"><span data-stu-id="2f562-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2f562-115">persistenceOperationTimeout</span><span class="sxs-lookup"><span data-stu-id="2f562-115">persistenceOperationTimeout</span></span>|<span data-ttu-id="2f562-116">Значение <xref:System.TimeSpan>, которое задает время ожидания, используемое для операций сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="2f562-116">A <xref:System.TimeSpan> value that specifies the time-out used for persistence operations.</span></span> <span data-ttu-id="2f562-117">Значение по умолчанию — «00: 00:30».</span><span class="sxs-lookup"><span data-stu-id="2f562-117">The default is "00:00:30".</span></span>|  
|<span data-ttu-id="2f562-118">type</span><span class="sxs-lookup"><span data-stu-id="2f562-118">type</span></span>|<span data-ttu-id="2f562-119">Строка, указывающая тип используемой фабрики поставщика сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="2f562-119">A string that specifies the type of the persistence provider factory to use.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2f562-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2f562-120">Child Elements</span></span>  
 <span data-ttu-id="2f562-121">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="2f562-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2f562-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2f562-122">Parent Elements</span></span>  
  
|<span data-ttu-id="2f562-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="2f562-123">Element</span></span>|<span data-ttu-id="2f562-124">Описание</span><span class="sxs-lookup"><span data-stu-id="2f562-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2f562-125">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="2f562-125">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="2f562-126">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="2f562-126">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f562-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="2f562-127">Remarks</span></span>  
 <span data-ttu-id="2f562-128">Этот элемент задает поставщика сохраняемости, используемого для сериализации состояния службы WCF.</span><span class="sxs-lookup"><span data-stu-id="2f562-128">This element specifies the persistence provider to be used to serialize the state of a WCF service.</span></span> <span data-ttu-id="2f562-129">Он должен использоваться вместе с атрибутом `wsHttpContextBinding`, который передает сведения о состоянии в HTTP-заголовки.</span><span class="sxs-lookup"><span data-stu-id="2f562-129">It should be used together with the `wsHttpContextBinding` which passes state information in HTTP headers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f562-130">См. также</span><span class="sxs-lookup"><span data-stu-id="2f562-130">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PersistenceProviderElement>  
 <xref:System.ServiceModel.Persistence.PersistenceProvider>
