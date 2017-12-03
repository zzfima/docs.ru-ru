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
ms.openlocfilehash: 3bc04837834277dccc9d21d27e89c84f09f36167
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="303---userdefinedinformationeventoccured"></a><span data-ttu-id="a4e4c-102">303 - UserDefinedInformationEventOccured</span><span class="sxs-lookup"><span data-stu-id="a4e4c-102">303 - UserDefinedInformationEventOccured</span></span>
## <a name="properties"></a><span data-ttu-id="a4e4c-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="a4e4c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a4e4c-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="a4e4c-104">ID</span></span>|<span data-ttu-id="a4e4c-105">303</span><span class="sxs-lookup"><span data-stu-id="a4e4c-105">303</span></span>|  
|<span data-ttu-id="a4e4c-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="a4e4c-106">Keywords</span></span>|<span data-ttu-id="a4e4c-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span><span class="sxs-lookup"><span data-stu-id="a4e4c-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span></span>|  
|<span data-ttu-id="a4e4c-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="a4e4c-108">Level</span></span>|<span data-ttu-id="a4e4c-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="a4e4c-109">Information</span></span>|  
|<span data-ttu-id="a4e4c-110">Канал</span><span class="sxs-lookup"><span data-stu-id="a4e4c-110">Channel</span></span>|<span data-ttu-id="a4e4c-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="a4e4c-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a4e4c-112">Описание</span><span class="sxs-lookup"><span data-stu-id="a4e4c-112">Description</span></span>  
 <span data-ttu-id="a4e4c-113">Это событие создается в пользовательском коде.</span><span class="sxs-lookup"><span data-stu-id="a4e4c-113">This event is emitted from user code.</span></span> <span data-ttu-id="a4e4c-114">Разработчик может создавать это событие при возникновении определенных пользователем информационных событий в его службе.</span><span class="sxs-lookup"><span data-stu-id="a4e4c-114">Developers can emit this event when a custom-defined informational event occurs in their service.</span></span> <span data-ttu-id="a4e4c-115">Это можно сделать при помощи API-интерфейсов <xref:System.Diagnostics.Eventing>.</span><span class="sxs-lookup"><span data-stu-id="a4e4c-115">This can be done using the <xref:System.Diagnostics.Eventing> APIs.</span></span> <span data-ttu-id="a4e4c-116">Помимо этого, есть образец WCF, который включает этот API-интерфейс и показывает, как правильно создать это событие.</span><span class="sxs-lookup"><span data-stu-id="a4e4c-116">Additionally, there is a WCF sample that wraps that API and demonstrates how to properly emit this event.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a4e4c-117">Сообщение</span><span class="sxs-lookup"><span data-stu-id="a4e4c-117">Message</span></span>  
 <span data-ttu-id="a4e4c-118">Имя: «%1», ссылка: «%2», полезные данные: %3</span><span class="sxs-lookup"><span data-stu-id="a4e4c-118">Name:'%1', Reference:'%2', Payload:%3</span></span>  
  
## <a name="details"></a><span data-ttu-id="a4e4c-119">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="a4e4c-119">Details</span></span>  
  
|<span data-ttu-id="a4e4c-120">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="a4e4c-120">Data Item Name</span></span>|<span data-ttu-id="a4e4c-121">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="a4e4c-121">Data Item Type</span></span>|<span data-ttu-id="a4e4c-122">Описание</span><span class="sxs-lookup"><span data-stu-id="a4e4c-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a4e4c-123">Имя</span><span class="sxs-lookup"><span data-stu-id="a4e4c-123">Name</span></span>|`xs:string`|<span data-ttu-id="a4e4c-124">Определенное пользователем имя события.</span><span class="sxs-lookup"><span data-stu-id="a4e4c-124">The user-defined name of the event</span></span>|  
|<span data-ttu-id="a4e4c-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="a4e4c-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="a4e4c-126">Для служб, размещенных на веб-узле, это поле служит уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="a4e4c-126">For Web hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="a4e4c-127">Ее формат определяется как "веб-сайт имя виртуальный путь приложения &#124; Виртуальный путь службы &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="a4e4c-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="a4e4c-128">Пример: "по умолчанию веб-сайта или CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService ".</span><span class="sxs-lookup"><span data-stu-id="a4e4c-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="a4e4c-129">Payload</span><span class="sxs-lookup"><span data-stu-id="a4e4c-129">Payload</span></span>|`xs:string`|<span data-ttu-id="a4e4c-130">Определенные пользователем полезные данные события.</span><span class="sxs-lookup"><span data-stu-id="a4e4c-130">The user-defined payload of the event.</span></span>|
