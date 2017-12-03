---
title: 302 - UserDefinedWarningOccurred
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8d1f0bf1-0151-45e6-be92-573d397b54de
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 61ec1e341d5220000b928409e006553c71ab379a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="302---userdefinedwarningoccurred"></a><span data-ttu-id="8a3e5-102">302 - UserDefinedWarningOccurred</span><span class="sxs-lookup"><span data-stu-id="8a3e5-102">302 - UserDefinedWarningOccurred</span></span>
## <a name="properties"></a><span data-ttu-id="8a3e5-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="8a3e5-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8a3e5-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="8a3e5-104">ID</span></span>|<span data-ttu-id="8a3e5-105">302</span><span class="sxs-lookup"><span data-stu-id="8a3e5-105">302</span></span>|  
|<span data-ttu-id="8a3e5-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="8a3e5-106">Keywords</span></span>|<span data-ttu-id="8a3e5-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span><span class="sxs-lookup"><span data-stu-id="8a3e5-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span></span>|  
|<span data-ttu-id="8a3e5-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="8a3e5-108">Level</span></span>|<span data-ttu-id="8a3e5-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="8a3e5-109">Warning</span></span>|  
|<span data-ttu-id="8a3e5-110">Канал</span><span class="sxs-lookup"><span data-stu-id="8a3e5-110">Channel</span></span>|<span data-ttu-id="8a3e5-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="8a3e5-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8a3e5-112">Описание</span><span class="sxs-lookup"><span data-stu-id="8a3e5-112">Description</span></span>  
 <span data-ttu-id="8a3e5-113">Это событие создается в пользовательском коде.</span><span class="sxs-lookup"><span data-stu-id="8a3e5-113">This event is emitted from user code.</span></span> <span data-ttu-id="8a3e5-114">Разработчики могут создать это событие, если определенное пользователем событие предупреждения возникло в принадлежащей им службе.</span><span class="sxs-lookup"><span data-stu-id="8a3e5-114">Developers can emit this event when a custom-defined warning event occurs in their service.</span></span> <span data-ttu-id="8a3e5-115">Это можно сделать при помощи API-интерфейсов <xref:System.Diagnostics.Eventing>.</span><span class="sxs-lookup"><span data-stu-id="8a3e5-115">This can be done using the <xref:System.Diagnostics.Eventing> APIs.</span></span> <span data-ttu-id="8a3e5-116">Помимо этого, есть образец WCF, который включает этот API-интерфейс и показывает, как правильно создать это событие.</span><span class="sxs-lookup"><span data-stu-id="8a3e5-116">Additionally, there is a WCF sample that wraps that API and demonstrates how to properly emit this event.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8a3e5-117">Сообщение</span><span class="sxs-lookup"><span data-stu-id="8a3e5-117">Message</span></span>  
 <span data-ttu-id="8a3e5-118">Имя: «%1», ссылка: «%2», полезные данные: %3</span><span class="sxs-lookup"><span data-stu-id="8a3e5-118">Name:'%1', Reference:'%2', Payload:%3</span></span>  
  
## <a name="details"></a><span data-ttu-id="8a3e5-119">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="8a3e5-119">Details</span></span>  
  
|<span data-ttu-id="8a3e5-120">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="8a3e5-120">Data Item Name</span></span>|<span data-ttu-id="8a3e5-121">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="8a3e5-121">Data Item Type</span></span>|<span data-ttu-id="8a3e5-122">Описание</span><span class="sxs-lookup"><span data-stu-id="8a3e5-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8a3e5-123">Имя</span><span class="sxs-lookup"><span data-stu-id="8a3e5-123">Name</span></span>|`xs:string`|<span data-ttu-id="8a3e5-124">Определенное пользователем имя события.</span><span class="sxs-lookup"><span data-stu-id="8a3e5-124">The user-defined name of the event.</span></span>|  
|<span data-ttu-id="8a3e5-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="8a3e5-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="8a3e5-126">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="8a3e5-126">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="8a3e5-127">Ее формат определяется как "веб-сайт имя виртуальный путь приложения &#124; Виртуальный путь службы &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="8a3e5-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="8a3e5-128">Пример: "по умолчанию веб-сайта или CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService ".</span><span class="sxs-lookup"><span data-stu-id="8a3e5-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="8a3e5-129">Payload</span><span class="sxs-lookup"><span data-stu-id="8a3e5-129">Payload</span></span>|`xs:string`|<span data-ttu-id="8a3e5-130">Определенные пользователем полезные данные события.</span><span class="sxs-lookup"><span data-stu-id="8a3e5-130">The user-defined payload of the event.</span></span>|
