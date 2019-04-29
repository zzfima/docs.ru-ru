---
title: 57398 - MaxInstancesExceeded
ms.date: 03/30/2017
ms.assetid: f943d209-dfeb-43e5-b572-c9a06217936e
ms.openlocfilehash: d644c25ec2dee06eea4a5fb66c30792bb650f252
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945968"
---
# <a name="57398---maxinstancesexceeded"></a><span data-ttu-id="e1dee-102">57398 - MaxInstancesExceeded</span><span class="sxs-lookup"><span data-stu-id="e1dee-102">57398 - MaxInstancesExceeded</span></span>
## <a name="properties"></a><span data-ttu-id="e1dee-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="e1dee-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e1dee-104">ID</span><span class="sxs-lookup"><span data-stu-id="e1dee-104">ID</span></span>|<span data-ttu-id="e1dee-105">57398</span><span class="sxs-lookup"><span data-stu-id="e1dee-105">57398</span></span>|  
|<span data-ttu-id="e1dee-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="e1dee-106">Keywords</span></span>|<span data-ttu-id="e1dee-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="e1dee-107">WFServices</span></span>|  
|<span data-ttu-id="e1dee-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="e1dee-108">Level</span></span>|<span data-ttu-id="e1dee-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="e1dee-109">Warning</span></span>|  
|<span data-ttu-id="e1dee-110">Канал</span><span class="sxs-lookup"><span data-stu-id="e1dee-110">Channel</span></span>|<span data-ttu-id="e1dee-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="e1dee-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e1dee-112">Описание</span><span class="sxs-lookup"><span data-stu-id="e1dee-112">Description</span></span>  
 <span data-ttu-id="e1dee-113">Указывает, что система достигла предела, заданного для ограничителя MaxConcurrentInstances.</span><span class="sxs-lookup"><span data-stu-id="e1dee-113">Indicates the system hit the limit set for throttle 'MaxConcurrentInstances'.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e1dee-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="e1dee-114">Message</span></span>  
 <span data-ttu-id="e1dee-115">Система достигла предела, заданного для ограничителя «MaxConcurrentInstances».</span><span class="sxs-lookup"><span data-stu-id="e1dee-115">The system hit the limit set for throttle 'MaxConcurrentInstances'.</span></span> <span data-ttu-id="e1dee-116">Для этого ограничителя был задан предел %1.</span><span class="sxs-lookup"><span data-stu-id="e1dee-116">Limit for this throttle was set to %1.</span></span> <span data-ttu-id="e1dee-117">Значение ограничителя можно изменить, изменив атрибут maxConcurrentInstances в элементе serviceThrottle или свойство MaxConcurrentInstances для поведения ServiceThrottlingBehavior.</span><span class="sxs-lookup"><span data-stu-id="e1dee-117">Throttle value can be changed by modifying attribute 'maxConcurrentInstances' in serviceThrottle element or by modifying 'MaxConcurrentInstances' property on behavior ServiceThrottlingBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e1dee-118">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="e1dee-118">Details</span></span>  
  
|<span data-ttu-id="e1dee-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="e1dee-119">Data Item Name</span></span>|<span data-ttu-id="e1dee-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="e1dee-120">Data Item Type</span></span>|<span data-ttu-id="e1dee-121">Описание</span><span class="sxs-lookup"><span data-stu-id="e1dee-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e1dee-122">name</span><span class="sxs-lookup"><span data-stu-id="e1dee-122">Name</span></span>|<span data-ttu-id="e1dee-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="e1dee-123">xs:string</span></span>|<span data-ttu-id="e1dee-124">Имя элемента.</span><span class="sxs-lookup"><span data-stu-id="e1dee-124">The name of the item.</span></span>|  
|<span data-ttu-id="e1dee-125">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="e1dee-125">AppDomain</span></span>|<span data-ttu-id="e1dee-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="e1dee-126">xs:string</span></span>|<span data-ttu-id="e1dee-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="e1dee-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
