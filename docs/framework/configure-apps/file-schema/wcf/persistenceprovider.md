---
title: '&lt;persistenceProvider&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a37049c5-a7ea-4519-94f2-912eeb010380
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2d93a9ea8614f98c968d499c2f95dcd3962f0020
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltpersistenceprovidergt"></a><span data-ttu-id="be300-102">&lt;persistenceProvider&gt;</span><span class="sxs-lookup"><span data-stu-id="be300-102">&lt;persistenceProvider&gt;</span></span>
<span data-ttu-id="be300-103">Задает тип используемой реализации поставщика сохраняемости, а также время ожидания операций сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="be300-103">Specifies the type of the persistence provider implementation to use, as well as the time-out to use for persistence operations.</span></span>  
  
 <span data-ttu-id="be300-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="be300-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="be300-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="be300-105">\<behaviors></span></span>  
<span data-ttu-id="be300-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="be300-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="be300-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="be300-107">\<behavior></span></span>  
<span data-ttu-id="be300-108">\<persistenceProvider ></span><span class="sxs-lookup"><span data-stu-id="be300-108">\<persistenceProvider></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be300-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="be300-109">Syntax</span></span>  
  
```xml  
<persistenceProvider persistenceOperationTimeout="TimeSpan"  
   type="String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="be300-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="be300-110">Attributes and Elements</span></span>  
 <span data-ttu-id="be300-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="be300-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="be300-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="be300-112">Attributes</span></span>  
  
|<span data-ttu-id="be300-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="be300-113">Attribute</span></span>|<span data-ttu-id="be300-114">Описание</span><span class="sxs-lookup"><span data-stu-id="be300-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="be300-115">persistenceOperationTimeout</span><span class="sxs-lookup"><span data-stu-id="be300-115">persistenceOperationTimeout</span></span>|<span data-ttu-id="be300-116">Значение <xref:System.TimeSpan>, которое задает время ожидания, используемое для операций сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="be300-116">A <xref:System.TimeSpan> value that specifies the time-out used for persistence operations.</span></span> <span data-ttu-id="be300-117">Значение по умолчанию — «00: 00:30».</span><span class="sxs-lookup"><span data-stu-id="be300-117">The default is "00:00:30".</span></span>|  
|<span data-ttu-id="be300-118">type</span><span class="sxs-lookup"><span data-stu-id="be300-118">type</span></span>|<span data-ttu-id="be300-119">Строка, указывающая тип используемой фабрики поставщика сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="be300-119">A string that specifies the type of the persistence provider factory to use.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="be300-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="be300-120">Child Elements</span></span>  
 <span data-ttu-id="be300-121">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="be300-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="be300-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="be300-122">Parent Elements</span></span>  
  
|<span data-ttu-id="be300-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="be300-123">Element</span></span>|<span data-ttu-id="be300-124">Описание</span><span class="sxs-lookup"><span data-stu-id="be300-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="be300-125">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="be300-125">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="be300-126">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="be300-126">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="be300-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="be300-127">Remarks</span></span>  
 <span data-ttu-id="be300-128">Этот элемент задает поставщика сохраняемости, используемого для сериализации состояния службы WCF.</span><span class="sxs-lookup"><span data-stu-id="be300-128">This element specifies the persistence provider to be used to serialize the state of a WCF service.</span></span> <span data-ttu-id="be300-129">Он должен использоваться вместе с атрибутом `wsHttpContextBinding`, который передает сведения о состоянии в HTTP-заголовки.</span><span class="sxs-lookup"><span data-stu-id="be300-129">It should be used together with the `wsHttpContextBinding` which passes state information in HTTP headers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be300-130">См. также</span><span class="sxs-lookup"><span data-stu-id="be300-130">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PersistenceProviderElement>  
 <xref:System.ServiceModel.Persistence.PersistenceProvider>
