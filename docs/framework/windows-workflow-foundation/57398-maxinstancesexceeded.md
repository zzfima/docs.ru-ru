---
title: 57398 - MaxInstancesExceeded
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f943d209-dfeb-43e5-b572-c9a06217936e
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ba48f19de1be3cfd2461e159b91fa365e24ee750
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="57398---maxinstancesexceeded"></a><span data-ttu-id="42949-102">57398 - MaxInstancesExceeded</span><span class="sxs-lookup"><span data-stu-id="42949-102">57398 - MaxInstancesExceeded</span></span>
## <a name="properties"></a><span data-ttu-id="42949-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="42949-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="42949-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="42949-104">ID</span></span>|<span data-ttu-id="42949-105">57398</span><span class="sxs-lookup"><span data-stu-id="42949-105">57398</span></span>|  
|<span data-ttu-id="42949-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="42949-106">Keywords</span></span>|<span data-ttu-id="42949-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="42949-107">WFServices</span></span>|  
|<span data-ttu-id="42949-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="42949-108">Level</span></span>|<span data-ttu-id="42949-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="42949-109">Warning</span></span>|  
|<span data-ttu-id="42949-110">Канал</span><span class="sxs-lookup"><span data-stu-id="42949-110">Channel</span></span>|<span data-ttu-id="42949-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="42949-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="42949-112">Описание</span><span class="sxs-lookup"><span data-stu-id="42949-112">Description</span></span>  
 <span data-ttu-id="42949-113">Указывает, что система достигла предела, заданного для ограничителя MaxConcurrentInstances.</span><span class="sxs-lookup"><span data-stu-id="42949-113">Indicates the system hit the limit set for throttle 'MaxConcurrentInstances'.</span></span>  
  
## <a name="message"></a><span data-ttu-id="42949-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="42949-114">Message</span></span>  
 <span data-ttu-id="42949-115">Система достигла предела, заданного для ограничителя «MaxConcurrentInstances».</span><span class="sxs-lookup"><span data-stu-id="42949-115">The system hit the limit set for throttle 'MaxConcurrentInstances'.</span></span> <span data-ttu-id="42949-116">Для этого ограничителя был задан предел %1.</span><span class="sxs-lookup"><span data-stu-id="42949-116">Limit for this throttle was set to %1.</span></span> <span data-ttu-id="42949-117">Значение ограничителя можно изменить, изменив атрибут maxConcurrentInstances в элементе serviceThrottle или свойство MaxConcurrentInstances для поведения ServiceThrottlingBehavior.</span><span class="sxs-lookup"><span data-stu-id="42949-117">Throttle value can be changed by modifying attribute 'maxConcurrentInstances' in serviceThrottle element or by modifying 'MaxConcurrentInstances' property on behavior ServiceThrottlingBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="42949-118">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="42949-118">Details</span></span>  
  
|<span data-ttu-id="42949-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="42949-119">Data Item Name</span></span>|<span data-ttu-id="42949-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="42949-120">Data Item Type</span></span>|<span data-ttu-id="42949-121">Описание</span><span class="sxs-lookup"><span data-stu-id="42949-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="42949-122">Имя</span><span class="sxs-lookup"><span data-stu-id="42949-122">Name</span></span>|<span data-ttu-id="42949-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="42949-123">xs:string</span></span>|<span data-ttu-id="42949-124">Имя элемента.</span><span class="sxs-lookup"><span data-stu-id="42949-124">The name of the item.</span></span>|  
|<span data-ttu-id="42949-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="42949-125">AppDomain</span></span>|<span data-ttu-id="42949-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="42949-126">xs:string</span></span>|<span data-ttu-id="42949-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="42949-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
