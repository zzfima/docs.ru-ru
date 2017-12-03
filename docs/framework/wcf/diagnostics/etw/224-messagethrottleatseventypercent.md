---
title: 224 - MessageThrottleAtSeventyPercent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 82bbbfd7-10d2-41fd-805d-2443b0c1b96b
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e2f96aea0df629c24eb9d795a4409cae6a9c9aa9
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="224---messagethrottleatseventypercent"></a><span data-ttu-id="98d71-102">224 - MessageThrottleAtSeventyPercent</span><span class="sxs-lookup"><span data-stu-id="98d71-102">224 - MessageThrottleAtSeventyPercent</span></span>
## <a name="properties"></a><span data-ttu-id="98d71-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="98d71-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="98d71-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="98d71-104">ID</span></span>|<span data-ttu-id="98d71-105">224</span><span class="sxs-lookup"><span data-stu-id="98d71-105">224</span></span>|  
|<span data-ttu-id="98d71-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="98d71-106">Keywords</span></span>|<span data-ttu-id="98d71-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="98d71-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="98d71-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="98d71-108">Level</span></span>|<span data-ttu-id="98d71-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="98d71-109">Warning</span></span>|  
|<span data-ttu-id="98d71-110">Канал</span><span class="sxs-lookup"><span data-stu-id="98d71-110">Channel</span></span>|<span data-ttu-id="98d71-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="98d71-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="98d71-112">Описание</span><span class="sxs-lookup"><span data-stu-id="98d71-112">Description</span></span>  
 <span data-ttu-id="98d71-113">При превышении одного из основных ограничителей службы создается событие `MessageThrottleExceeded`.</span><span class="sxs-lookup"><span data-stu-id="98d71-113">When one of the main service throttles has been exceeded, the `MessageThrottleExceeded` event is emitted.</span></span> <span data-ttu-id="98d71-114">Если всплеск активности уменьшился и текущее значение ограничителя составляет 70 процентов от текущего предела, то создается это событие.</span><span class="sxs-lookup"><span data-stu-id="98d71-114">When the spike of activity slows and the current value of the throttle is at 70 percent of the current limit then this event is emitted.</span></span> <span data-ttu-id="98d71-115">Обратите внимание, что это событие создается только один раз при замедлении активности.</span><span class="sxs-lookup"><span data-stu-id="98d71-115">Note that this event is only emitted once as the activity is slowing.</span></span> <span data-ttu-id="98d71-116">Если текущее значение находится вблизи отметки 70 процентов (например, 70, 69, 70, 71, 69), то только первое значение 70 процентов приводит к созданию события.</span><span class="sxs-lookup"><span data-stu-id="98d71-116">If the current value hovers at the 70 percent mark, (for example, 70,69,70,71,70,69), only the first occurrence of 70 percent results in an event.</span></span> <span data-ttu-id="98d71-117">После возникновения события все последующие превышения предела регулирования приводят к возникновению события `MessageThrottleExceeded`.</span><span class="sxs-lookup"><span data-stu-id="98d71-117">After this event is emitted, future occurrences of exceeding the throttle's limit result in a `MessageThrottleExceeded` event.</span></span>  
  
## <a name="message"></a><span data-ttu-id="98d71-118">Сообщение</span><span class="sxs-lookup"><span data-stu-id="98d71-118">Message</span></span>  
 <span data-ttu-id="98d71-119">Предел ограничителя %1 из %2 находится на отметке 70%%.</span><span class="sxs-lookup"><span data-stu-id="98d71-119">The '%1' throttle limit of '%2' is at 70%%.</span></span>  
  
## <a name="details"></a><span data-ttu-id="98d71-120">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="98d71-120">Details</span></span>  
  
|<span data-ttu-id="98d71-121">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="98d71-121">Data Item Name</span></span>|<span data-ttu-id="98d71-122">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="98d71-122">Data Item Type</span></span>|<span data-ttu-id="98d71-123">Описание</span><span class="sxs-lookup"><span data-stu-id="98d71-123">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="98d71-124">Throttle Name</span><span class="sxs-lookup"><span data-stu-id="98d71-124">Throttle Name</span></span>|`xs:string`|<span data-ttu-id="98d71-125">Имя превышенного ограничителя.</span><span class="sxs-lookup"><span data-stu-id="98d71-125">The name of the throttle that has been exceeded.</span></span> <span data-ttu-id="98d71-126">`MaxConcurrentCalls`, `MaxConcurrentInstances` либо `MaxConcurrentSessions`,</span><span class="sxs-lookup"><span data-stu-id="98d71-126">Either `MaxConcurrentCalls`, `MaxConcurrentInstances`, or `MaxConcurrentSessions`,</span></span>|  
|<span data-ttu-id="98d71-127">Limit</span><span class="sxs-lookup"><span data-stu-id="98d71-127">Limit</span></span>|`xs:long`|<span data-ttu-id="98d71-128">Заданный в данный момент предел ограничителя.</span><span class="sxs-lookup"><span data-stu-id="98d71-128">The currently configured limit of the throttle.</span></span>|  
|<span data-ttu-id="98d71-129">HostReference</span><span class="sxs-lookup"><span data-stu-id="98d71-129">HostReference</span></span>|`xs:string`|<span data-ttu-id="98d71-130">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="98d71-130">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="98d71-131">Ее формат определяется как "веб-сайт имя виртуальный путь приложения &#124; Виртуальный путь службы &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="98d71-131">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="98d71-132">Пример: "по умолчанию веб-сайта или CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService ".</span><span class="sxs-lookup"><span data-stu-id="98d71-132">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="98d71-133">AppDomain</span><span class="sxs-lookup"><span data-stu-id="98d71-133">AppDomain</span></span>|`xs:string`|<span data-ttu-id="98d71-134">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="98d71-134">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
