---
title: 303 - UserDefinedInformationEventOccured
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5ed5acaf-3755-4417-92c4-4ebc8e854ca1
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3bd4d94d457793eb036f037cc6dc22bff6d26ee2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="303---userdefinedinformationeventoccured"></a><span data-ttu-id="56102-102">303 - UserDefinedInformationEventOccured</span><span class="sxs-lookup"><span data-stu-id="56102-102">303 - UserDefinedInformationEventOccured</span></span>
## <a name="properties"></a><span data-ttu-id="56102-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="56102-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="56102-104">ID</span><span class="sxs-lookup"><span data-stu-id="56102-104">ID</span></span>|<span data-ttu-id="56102-105">303</span><span class="sxs-lookup"><span data-stu-id="56102-105">303</span></span>|  
|<span data-ttu-id="56102-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="56102-106">Keywords</span></span>|<span data-ttu-id="56102-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span><span class="sxs-lookup"><span data-stu-id="56102-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span></span>|  
|<span data-ttu-id="56102-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="56102-108">Level</span></span>|<span data-ttu-id="56102-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="56102-109">Information</span></span>|  
|<span data-ttu-id="56102-110">Канал</span><span class="sxs-lookup"><span data-stu-id="56102-110">Channel</span></span>|<span data-ttu-id="56102-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="56102-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="56102-112">Описание:</span><span class="sxs-lookup"><span data-stu-id="56102-112">Description</span></span>  
 <span data-ttu-id="56102-113">Это событие создается в пользовательском коде.</span><span class="sxs-lookup"><span data-stu-id="56102-113">This event is emitted from user code.</span></span> <span data-ttu-id="56102-114">Разработчик может создавать это событие при возникновении определенных пользователем информационных событий в его службе.</span><span class="sxs-lookup"><span data-stu-id="56102-114">Developers can emit this event when a custom-defined informational event occurs in their service.</span></span> <span data-ttu-id="56102-115">Это можно сделать при помощи API-интерфейсов <xref:System.Diagnostics.Eventing>.</span><span class="sxs-lookup"><span data-stu-id="56102-115">This can be done using the <xref:System.Diagnostics.Eventing> APIs.</span></span> <span data-ttu-id="56102-116">Помимо этого, есть образец WCF, который включает этот API-интерфейс и показывает, как правильно создать это событие.</span><span class="sxs-lookup"><span data-stu-id="56102-116">Additionally, there is a WCF sample that wraps that API and demonstrates how to properly emit this event.</span></span>  
  
## <a name="message"></a><span data-ttu-id="56102-117">Сообщение</span><span class="sxs-lookup"><span data-stu-id="56102-117">Message</span></span>  
 <span data-ttu-id="56102-118">Имя: «%1», ссылка: «%2», полезные данные: %3</span><span class="sxs-lookup"><span data-stu-id="56102-118">Name:'%1', Reference:'%2', Payload:%3</span></span>  
  
## <a name="details"></a><span data-ttu-id="56102-119">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="56102-119">Details</span></span>  
  
|<span data-ttu-id="56102-120">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="56102-120">Data Item Name</span></span>|<span data-ttu-id="56102-121">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="56102-121">Data Item Type</span></span>|<span data-ttu-id="56102-122">Описание</span><span class="sxs-lookup"><span data-stu-id="56102-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="56102-123">name</span><span class="sxs-lookup"><span data-stu-id="56102-123">Name</span></span>|`xs:string`|<span data-ttu-id="56102-124">Определенное пользователем имя события.</span><span class="sxs-lookup"><span data-stu-id="56102-124">The user-defined name of the event</span></span>|  
|<span data-ttu-id="56102-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="56102-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="56102-126">Для служб, размещенных на веб-узле, это поле служит уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="56102-126">For Web hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="56102-127">Ее формат определяется как "веб-сайт имя виртуальный путь приложения &#124; Виртуальный путь службы &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="56102-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="56102-128">Пример: "по умолчанию веб-сайта или CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService ".</span><span class="sxs-lookup"><span data-stu-id="56102-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="56102-129">Payload</span><span class="sxs-lookup"><span data-stu-id="56102-129">Payload</span></span>|`xs:string`|<span data-ttu-id="56102-130">Определенные пользователем полезные данные события.</span><span class="sxs-lookup"><span data-stu-id="56102-130">The user-defined payload of the event.</span></span>|
