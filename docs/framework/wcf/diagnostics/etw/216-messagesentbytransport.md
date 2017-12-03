---
title: 216 - MessageSentByTransport
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 150c3167-4154-4225-8d94-57cc94341233
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1b2bf2841c04dcdc74bf64a0169b95caa6c8a36a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="216---messagesentbytransport"></a><span data-ttu-id="73996-102">216 - MessageSentByTransport</span><span class="sxs-lookup"><span data-stu-id="73996-102">216 - MessageSentByTransport</span></span>
## <a name="properties"></a><span data-ttu-id="73996-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="73996-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="73996-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="73996-104">ID</span></span>|<span data-ttu-id="73996-105">216</span><span class="sxs-lookup"><span data-stu-id="73996-105">216</span></span>|  
|<span data-ttu-id="73996-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="73996-106">Keywords</span></span>|<span data-ttu-id="73996-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="73996-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="73996-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="73996-108">Level</span></span>|<span data-ttu-id="73996-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="73996-109">Information</span></span>|  
|<span data-ttu-id="73996-110">Канал</span><span class="sxs-lookup"><span data-stu-id="73996-110">Channel</span></span>|<span data-ttu-id="73996-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="73996-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="73996-112">Описание</span><span class="sxs-lookup"><span data-stu-id="73996-112">Description</span></span>  
 <span data-ttu-id="73996-113">Это событие возникает при отправке сообщения транспортом на основе TCP.</span><span class="sxs-lookup"><span data-stu-id="73996-113">This event occurs when a TCP-based transport sends a message.</span></span> <span data-ttu-id="73996-114">Обратите внимание, что в рамках одной операции между клиентом и службой может быть передано несколько сообщений уровня транспорта.</span><span class="sxs-lookup"><span data-stu-id="73996-114">Note that at the transport level multiple messages can be exchanged between clients and services for a single operation.</span></span> <span data-ttu-id="73996-115">Это может быть вызвано особенностями инфраструктуры (и требования безопасности - хороший пример).</span><span class="sxs-lookup"><span data-stu-id="73996-115">This may be due to infrastructure behavior, security being a good example.</span></span> <span data-ttu-id="73996-116">Таким образом, число **MessageSentByTransport** создаваемых событий зависит от привязки службы и его конфигурации.</span><span class="sxs-lookup"><span data-stu-id="73996-116">Therefore, the number of **MessageSentByTransport** events that are emitted vary based on your service's binding and its configuration.</span></span>  
  
## <a name="message"></a><span data-ttu-id="73996-117">Сообщение</span><span class="sxs-lookup"><span data-stu-id="73996-117">Message</span></span>  
 <span data-ttu-id="73996-118">Транспорт отправил сообщение «%1».</span><span class="sxs-lookup"><span data-stu-id="73996-118">The transport sent a message to '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="73996-119">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="73996-119">Details</span></span>  
  
|<span data-ttu-id="73996-120">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="73996-120">Data Item Name</span></span>|<span data-ttu-id="73996-121">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="73996-121">Data Item Type</span></span>|<span data-ttu-id="73996-122">Описание</span><span class="sxs-lookup"><span data-stu-id="73996-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="73996-123">DestinationAddress</span><span class="sxs-lookup"><span data-stu-id="73996-123">DestinationAddress</span></span>|`xs:string`|<span data-ttu-id="73996-124">Адрес, на который было отправлено сообщение запроса.</span><span class="sxs-lookup"><span data-stu-id="73996-124">The address that the request message was sent to.</span></span>|  
|<span data-ttu-id="73996-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="73996-125">HostReference</span></span>|<span data-ttu-id="73996-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="73996-126">xs:string</span></span>|<span data-ttu-id="73996-127">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="73996-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="73996-128">Ее формат определяется как "веб-сайт имя виртуальный путь приложения &#124; Виртуальный путь службы &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="73996-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="73996-129">Пример: "по умолчанию веб-сайта или CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService ".</span><span class="sxs-lookup"><span data-stu-id="73996-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="73996-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="73996-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="73996-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="73996-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
