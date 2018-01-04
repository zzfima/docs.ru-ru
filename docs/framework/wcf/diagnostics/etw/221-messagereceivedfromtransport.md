---
title: 221 - MessageReceivedFromTransport
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4995f0d5-c182-4d97-981f-6951da6df1fb
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 139ca9e0fbe4d3f59d3d593f7785d5fb65e64702
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="221---messagereceivedfromtransport"></a><span data-ttu-id="f06a4-102">221 - MessageReceivedFromTransport</span><span class="sxs-lookup"><span data-stu-id="f06a4-102">221 - MessageReceivedFromTransport</span></span>
## <a name="properties"></a><span data-ttu-id="f06a4-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="f06a4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f06a4-104">ID</span><span class="sxs-lookup"><span data-stu-id="f06a4-104">ID</span></span>|<span data-ttu-id="f06a4-105">221</span><span class="sxs-lookup"><span data-stu-id="f06a4-105">221</span></span>|  
|<span data-ttu-id="f06a4-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="f06a4-106">Keywords</span></span>|<span data-ttu-id="f06a4-107">EndToEndMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f06a4-107">EndToEndMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="f06a4-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="f06a4-108">Level</span></span>|<span data-ttu-id="f06a4-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="f06a4-109">Information</span></span>|  
|<span data-ttu-id="f06a4-110">Канал</span><span class="sxs-lookup"><span data-stu-id="f06a4-110">Channel</span></span>|<span data-ttu-id="f06a4-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="f06a4-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f06a4-112">Описание:</span><span class="sxs-lookup"><span data-stu-id="f06a4-112">Description</span></span>  
 <span data-ttu-id="f06a4-113">Это событие вызывается при получении моделью службы сообщения от транспортной подсистемы.</span><span class="sxs-lookup"><span data-stu-id="f06a4-113">This event is emitted when the Service Model receives a message from the transport.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f06a4-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="f06a4-114">Message</span></span>  
 <span data-ttu-id="f06a4-115">Диспетчер получил сообщение от транспорта.</span><span class="sxs-lookup"><span data-stu-id="f06a4-115">The Dispatcher received a message from the transport.</span></span> <span data-ttu-id="f06a4-116">Идентификатор корреляции == «%1».</span><span class="sxs-lookup"><span data-stu-id="f06a4-116">Correlation ID == '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f06a4-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="f06a4-117">Details</span></span>  
  
|<span data-ttu-id="f06a4-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="f06a4-118">Data Item Name</span></span>|<span data-ttu-id="f06a4-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="f06a4-119">Data Item Type</span></span>|<span data-ttu-id="f06a4-120">Описание:</span><span class="sxs-lookup"><span data-stu-id="f06a4-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f06a4-121">Идентификатор корреляции</span><span class="sxs-lookup"><span data-stu-id="f06a4-121">Correlation ID</span></span>|`xs:GUID`|<span data-ttu-id="f06a4-122">Идентификатор действия, используемый для корреляции события `MessageSentToTransport` из службы или клиента с соответствующим транспортом `MessageReceivedFromTransport` на другом конце.</span><span class="sxs-lookup"><span data-stu-id="f06a4-122">The activity ID used to correlate a `MessageSentToTransport` event from a service or client to its corresponding `MessageReceivedFromTransport` on the other end.</span></span>|  
|<span data-ttu-id="f06a4-123">HostReference</span><span class="sxs-lookup"><span data-stu-id="f06a4-123">HostReference</span></span>|`xs:string`|<span data-ttu-id="f06a4-124">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="f06a4-124">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="f06a4-125">Ее формат определяется как "веб-сайт имя виртуальный путь приложения &#124; Виртуальный путь службы &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="f06a4-125">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="f06a4-126">Пример: "по умолчанию веб-сайта или CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService ".</span><span class="sxs-lookup"><span data-stu-id="f06a4-126">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="f06a4-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f06a4-127">AppDomain</span></span>|`xs:string`|<span data-ttu-id="f06a4-128">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="f06a4-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
