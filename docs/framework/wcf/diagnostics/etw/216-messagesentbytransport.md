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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7b35f46ae7a214ab45e4062928de82c4da6541a1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="216---messagesentbytransport"></a><span data-ttu-id="e7fed-102">216 - MessageSentByTransport</span><span class="sxs-lookup"><span data-stu-id="e7fed-102">216 - MessageSentByTransport</span></span>
## <a name="properties"></a><span data-ttu-id="e7fed-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="e7fed-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e7fed-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="e7fed-104">ID</span></span>|<span data-ttu-id="e7fed-105">216</span><span class="sxs-lookup"><span data-stu-id="e7fed-105">216</span></span>|  
|<span data-ttu-id="e7fed-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="e7fed-106">Keywords</span></span>|<span data-ttu-id="e7fed-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e7fed-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="e7fed-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="e7fed-108">Level</span></span>|<span data-ttu-id="e7fed-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="e7fed-109">Information</span></span>|  
|<span data-ttu-id="e7fed-110">Канал</span><span class="sxs-lookup"><span data-stu-id="e7fed-110">Channel</span></span>|<span data-ttu-id="e7fed-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="e7fed-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e7fed-112">Описание</span><span class="sxs-lookup"><span data-stu-id="e7fed-112">Description</span></span>  
 <span data-ttu-id="e7fed-113">Это событие возникает при отправке сообщения транспортом на основе TCP.</span><span class="sxs-lookup"><span data-stu-id="e7fed-113">This event occurs when a TCP-based transport sends a message.</span></span> <span data-ttu-id="e7fed-114">Обратите внимание, что в рамках одной операции между клиентом и службой может быть передано несколько сообщений уровня транспорта.</span><span class="sxs-lookup"><span data-stu-id="e7fed-114">Note that at the transport level multiple messages can be exchanged between clients and services for a single operation.</span></span> <span data-ttu-id="e7fed-115">Это может быть вызвано особенностями инфраструктуры (и требования безопасности - хороший пример).</span><span class="sxs-lookup"><span data-stu-id="e7fed-115">This may be due to infrastructure behavior, security being a good example.</span></span> <span data-ttu-id="e7fed-116">Таким образом, число **MessageSentByTransport** создаваемых событий зависит от привязки службы и его конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e7fed-116">Therefore, the number of **MessageSentByTransport** events that are emitted vary based on your service's binding and its configuration.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e7fed-117">Сообщение</span><span class="sxs-lookup"><span data-stu-id="e7fed-117">Message</span></span>  
 <span data-ttu-id="e7fed-118">Транспорт отправил сообщение «%1».</span><span class="sxs-lookup"><span data-stu-id="e7fed-118">The transport sent a message to '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e7fed-119">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="e7fed-119">Details</span></span>  
  
|<span data-ttu-id="e7fed-120">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="e7fed-120">Data Item Name</span></span>|<span data-ttu-id="e7fed-121">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="e7fed-121">Data Item Type</span></span>|<span data-ttu-id="e7fed-122">Описание</span><span class="sxs-lookup"><span data-stu-id="e7fed-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e7fed-123">DestinationAddress</span><span class="sxs-lookup"><span data-stu-id="e7fed-123">DestinationAddress</span></span>|`xs:string`|<span data-ttu-id="e7fed-124">Адрес, на который было отправлено сообщение запроса.</span><span class="sxs-lookup"><span data-stu-id="e7fed-124">The address that the request message was sent to.</span></span>|  
|<span data-ttu-id="e7fed-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="e7fed-125">HostReference</span></span>|<span data-ttu-id="e7fed-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="e7fed-126">xs:string</span></span>|<span data-ttu-id="e7fed-127">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="e7fed-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="e7fed-128">Ее формат определяется как "веб-сайт имя виртуальный путь приложения &#124; Виртуальный путь службы &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="e7fed-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="e7fed-129">Пример: "по умолчанию веб-сайта или CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService ".</span><span class="sxs-lookup"><span data-stu-id="e7fed-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="e7fed-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e7fed-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="e7fed-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="e7fed-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
