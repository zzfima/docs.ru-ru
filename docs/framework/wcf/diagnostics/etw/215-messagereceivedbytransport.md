---
title: 215 - MessageReceivedByTransport
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bb32aa60-5207-4711-9f08-110e8ac327e5
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 92880fd01f8f61a06c9b2c7d51ecc4a1671c6c85
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="215---messagereceivedbytransport"></a><span data-ttu-id="cb3ca-102">215 - MessageReceivedByTransport</span><span class="sxs-lookup"><span data-stu-id="cb3ca-102">215 - MessageReceivedByTransport</span></span>
## <a name="properties"></a><span data-ttu-id="cb3ca-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="cb3ca-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cb3ca-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="cb3ca-104">ID</span></span>|<span data-ttu-id="cb3ca-105">215</span><span class="sxs-lookup"><span data-stu-id="cb3ca-105">215</span></span>|  
|<span data-ttu-id="cb3ca-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="cb3ca-106">Keywords</span></span>|<span data-ttu-id="cb3ca-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="cb3ca-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="cb3ca-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="cb3ca-108">Level</span></span>|<span data-ttu-id="cb3ca-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="cb3ca-109">Information</span></span>|  
|<span data-ttu-id="cb3ca-110">Канал</span><span class="sxs-lookup"><span data-stu-id="cb3ca-110">Channel</span></span>|<span data-ttu-id="cb3ca-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="cb3ca-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="cb3ca-112">Описание</span><span class="sxs-lookup"><span data-stu-id="cb3ca-112">Description</span></span>  
 <span data-ttu-id="cb3ca-113">Это событие происходит, когда транспорт на основе TCP получает сообщение.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-113">This event occurs when a TCP-based transport receives a message.</span></span> <span data-ttu-id="cb3ca-114">Обратите внимание, что на транспортном уровне для одной операции между клиентом и службой может быть передано несколько сообщений.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-114">Note that at the transport level, multiple messages can be exchanged between clients and services for a single operation.</span></span> <span data-ttu-id="cb3ca-115">Это может зависеть от инфраструктуры, и требования безопасности - хороший пример.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-115">This can be due to infrastructure behavior, security is a good example.</span></span> <span data-ttu-id="cb3ca-116">Следовательно, количество создаваемых событий `MessageReceivedByTransport` может отличаться в зависимости от привязки службы и ее настроек.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-116">Therefore, the number of `MessageReceivedByTransport` events that are emitted vary based on your service's binding and its configuration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cb3ca-117">Это событие не создается для односторонних транспортов.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-117">This event is not emitted for one-way transports.</span></span>  
  
## <a name="message"></a><span data-ttu-id="cb3ca-118">Сообщение</span><span class="sxs-lookup"><span data-stu-id="cb3ca-118">Message</span></span>  
 <span data-ttu-id="cb3ca-119">Диспетчер получил сообщение от «%1».</span><span class="sxs-lookup"><span data-stu-id="cb3ca-119">The transport received a message from '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="cb3ca-120">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="cb3ca-120">Details</span></span>  
  
|<span data-ttu-id="cb3ca-121">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="cb3ca-121">Data Item Name</span></span>|<span data-ttu-id="cb3ca-122">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="cb3ca-122">Data Item Type</span></span>|<span data-ttu-id="cb3ca-123">Описание</span><span class="sxs-lookup"><span data-stu-id="cb3ca-123">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="cb3ca-124">Listen Address</span><span class="sxs-lookup"><span data-stu-id="cb3ca-124">Listen Address</span></span>|`xs:string`|<span data-ttu-id="cb3ca-125">Адрес, получивший сообщение.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-125">The address that received the message.</span></span>|  
|<span data-ttu-id="cb3ca-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="cb3ca-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="cb3ca-127">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="cb3ca-128">Ее формат определяется как "веб-сайт имя виртуальный путь приложения &#124; Виртуальный путь службы &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="cb3ca-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="cb3ca-129">Пример: "по умолчанию веб-сайта или CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService ".</span><span class="sxs-lookup"><span data-stu-id="cb3ca-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="cb3ca-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="cb3ca-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="cb3ca-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
