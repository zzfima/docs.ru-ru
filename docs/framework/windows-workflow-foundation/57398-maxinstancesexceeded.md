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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7417d2e0e850017e65910be32e7449255f0761c3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="57398---maxinstancesexceeded"></a><span data-ttu-id="faf64-102">57398 - MaxInstancesExceeded</span><span class="sxs-lookup"><span data-stu-id="faf64-102">57398 - MaxInstancesExceeded</span></span>
## <a name="properties"></a><span data-ttu-id="faf64-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="faf64-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="faf64-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="faf64-104">ID</span></span>|<span data-ttu-id="faf64-105">57398</span><span class="sxs-lookup"><span data-stu-id="faf64-105">57398</span></span>|  
|<span data-ttu-id="faf64-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="faf64-106">Keywords</span></span>|<span data-ttu-id="faf64-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="faf64-107">WFServices</span></span>|  
|<span data-ttu-id="faf64-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="faf64-108">Level</span></span>|<span data-ttu-id="faf64-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="faf64-109">Warning</span></span>|  
|<span data-ttu-id="faf64-110">Канал</span><span class="sxs-lookup"><span data-stu-id="faf64-110">Channel</span></span>|<span data-ttu-id="faf64-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="faf64-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="faf64-112">Описание</span><span class="sxs-lookup"><span data-stu-id="faf64-112">Description</span></span>  
 <span data-ttu-id="faf64-113">Указывает, что система достигла предела, заданного для ограничителя MaxConcurrentInstances.</span><span class="sxs-lookup"><span data-stu-id="faf64-113">Indicates the system hit the limit set for throttle 'MaxConcurrentInstances'.</span></span>  
  
## <a name="message"></a><span data-ttu-id="faf64-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="faf64-114">Message</span></span>  
 <span data-ttu-id="faf64-115">Система достигла предела, заданного для ограничителя «MaxConcurrentInstances».</span><span class="sxs-lookup"><span data-stu-id="faf64-115">The system hit the limit set for throttle 'MaxConcurrentInstances'.</span></span> <span data-ttu-id="faf64-116">Для этого ограничителя был задан предел %1.</span><span class="sxs-lookup"><span data-stu-id="faf64-116">Limit for this throttle was set to %1.</span></span> <span data-ttu-id="faf64-117">Значение ограничителя можно изменить, изменив атрибут maxConcurrentInstances в элементе serviceThrottle или свойство MaxConcurrentInstances для поведения ServiceThrottlingBehavior.</span><span class="sxs-lookup"><span data-stu-id="faf64-117">Throttle value can be changed by modifying attribute 'maxConcurrentInstances' in serviceThrottle element or by modifying 'MaxConcurrentInstances' property on behavior ServiceThrottlingBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="faf64-118">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="faf64-118">Details</span></span>  
  
|<span data-ttu-id="faf64-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="faf64-119">Data Item Name</span></span>|<span data-ttu-id="faf64-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="faf64-120">Data Item Type</span></span>|<span data-ttu-id="faf64-121">Описание</span><span class="sxs-lookup"><span data-stu-id="faf64-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="faf64-122">Имя</span><span class="sxs-lookup"><span data-stu-id="faf64-122">Name</span></span>|<span data-ttu-id="faf64-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="faf64-123">xs:string</span></span>|<span data-ttu-id="faf64-124">Имя элемента.</span><span class="sxs-lookup"><span data-stu-id="faf64-124">The name of the item.</span></span>|  
|<span data-ttu-id="faf64-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="faf64-125">AppDomain</span></span>|<span data-ttu-id="faf64-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="faf64-126">xs:string</span></span>|<span data-ttu-id="faf64-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="faf64-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
