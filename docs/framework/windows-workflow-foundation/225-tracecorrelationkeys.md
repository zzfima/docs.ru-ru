---
title: 225 - TraceCorrelationKeys
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9083aaf-3816-4c1c-bae0-2d7f49628345
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9a8d9120c4173d90d7bf6b1ff2054117f80ac96a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="225---tracecorrelationkeys"></a><span data-ttu-id="626f5-102">225 - TraceCorrelationKeys</span><span class="sxs-lookup"><span data-stu-id="626f5-102">225 - TraceCorrelationKeys</span></span>
## <a name="properties"></a><span data-ttu-id="626f5-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="626f5-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="626f5-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="626f5-104">ID</span></span>|<span data-ttu-id="626f5-105">225</span><span class="sxs-lookup"><span data-stu-id="626f5-105">225</span></span>|  
|<span data-ttu-id="626f5-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="626f5-106">Keywords</span></span>|<span data-ttu-id="626f5-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="626f5-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="626f5-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="626f5-108">Level</span></span>|<span data-ttu-id="626f5-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="626f5-109">Information</span></span>|  
|<span data-ttu-id="626f5-110">Канал</span><span class="sxs-lookup"><span data-stu-id="626f5-110">Channel</span></span>|<span data-ttu-id="626f5-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="626f5-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="626f5-112">Описание</span><span class="sxs-lookup"><span data-stu-id="626f5-112">Description</span></span>  
 <span data-ttu-id="626f5-113">Это событие создается, если в качестве службы рабочего процесса используется корреляция на основе содержимого.</span><span class="sxs-lookup"><span data-stu-id="626f5-113">This event is emitted when content-based correlation is used for a workflow service.</span></span> <span data-ttu-id="626f5-114">Оно содержит ключи, применяемые для корреляции сообщения с экземпляром.</span><span class="sxs-lookup"><span data-stu-id="626f5-114">It contains the correlation keys that are applied to correlate a message to an instance.</span></span>  
  
## <a name="message"></a><span data-ttu-id="626f5-115">Сообщение</span><span class="sxs-lookup"><span data-stu-id="626f5-115">Message</span></span>  
 <span data-ttu-id="626f5-116">Вычисленный ключ корреляции «%1» с использованием значений «%2» в родительской области «%3».</span><span class="sxs-lookup"><span data-stu-id="626f5-116">Calculated correlation key '%1' using values '%2' in parent scope '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="626f5-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="626f5-117">Details</span></span>  
  
|<span data-ttu-id="626f5-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="626f5-118">Data Item Name</span></span>|<span data-ttu-id="626f5-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="626f5-119">Data Item Type</span></span>|<span data-ttu-id="626f5-120">Описание</span><span class="sxs-lookup"><span data-stu-id="626f5-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="626f5-121">Instance Key</span><span class="sxs-lookup"><span data-stu-id="626f5-121">Instance Key</span></span>|`xs:GUID`|<span data-ttu-id="626f5-122">Ключ, созданный из значений корреляции.</span><span class="sxs-lookup"><span data-stu-id="626f5-122">The key that was generated from the correlation values.</span></span>|  
|<span data-ttu-id="626f5-123">Значения</span><span class="sxs-lookup"><span data-stu-id="626f5-123">Values</span></span>|`xs:string`|<span data-ttu-id="626f5-124">Значения, использованные для вычисления ключа экземпляра корреляции.</span><span class="sxs-lookup"><span data-stu-id="626f5-124">The values that were used to compute the correlation instance key.</span></span>|  
|<span data-ttu-id="626f5-125">Parent Scope</span><span class="sxs-lookup"><span data-stu-id="626f5-125">Parent Scope</span></span>|`xs:string`||  
|<span data-ttu-id="626f5-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="626f5-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="626f5-127">Для служб, размещенных на веб-узле, это поле служит уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="626f5-127">For Web hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="626f5-128">Ее формат определяется как "веб-сайт имя виртуальный путь приложения &#124; Виртуальный путь службы &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="626f5-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="626f5-129">Пример: "по умолчанию веб-сайта или CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService ".</span><span class="sxs-lookup"><span data-stu-id="626f5-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="626f5-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="626f5-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="626f5-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="626f5-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
