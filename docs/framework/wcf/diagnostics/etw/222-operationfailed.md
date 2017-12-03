---
title: 222 - OperationFailed
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6b530ded-8f20-4d78-8bfe-1875276df6ba
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5d56766dd32acf1ef71f7c06a5c3c94cc7510070
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="222---operationfailed"></a><span data-ttu-id="ba904-102">222 - OperationFailed</span><span class="sxs-lookup"><span data-stu-id="ba904-102">222 - OperationFailed</span></span>
## <a name="properties"></a><span data-ttu-id="ba904-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="ba904-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ba904-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="ba904-104">ID</span></span>|<span data-ttu-id="ba904-105">222</span><span class="sxs-lookup"><span data-stu-id="ba904-105">222</span></span>|  
|<span data-ttu-id="ba904-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ba904-106">Keywords</span></span>|<span data-ttu-id="ba904-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ba904-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="ba904-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="ba904-108">Level</span></span>|<span data-ttu-id="ba904-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="ba904-109">Warning</span></span>|  
|<span data-ttu-id="ba904-110">Канал</span><span class="sxs-lookup"><span data-stu-id="ba904-110">Channel</span></span>|<span data-ttu-id="ba904-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="ba904-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ba904-112">Описание</span><span class="sxs-lookup"><span data-stu-id="ba904-112">Description</span></span>  
 <span data-ttu-id="ba904-113">Это событие создается в том случае, когда `OperationInvoker` модели службы по умолчанию обнаруживает исключение при вызове его метода.</span><span class="sxs-lookup"><span data-stu-id="ba904-113">This event is emitted when the Service Model's default `OperationInvoker` has encountered an exception while invoking its method.</span></span> <span data-ttu-id="ba904-114">Обратите внимание, что исключения, производные от `FaultException`, не вызывают это событие.</span><span class="sxs-lookup"><span data-stu-id="ba904-114">Note that exceptions that derive from `FaultException` cause this event to not be emitted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ba904-115">Сообщение</span><span class="sxs-lookup"><span data-stu-id="ba904-115">Message</span></span>  
 <span data-ttu-id="ba904-116">Метод «%1» вызвал необработанное исключение после того, как был вызван OperationInvoker.</span><span class="sxs-lookup"><span data-stu-id="ba904-116">The '%1' method threw an unhandled exception when invoked by the OperationInvoker.</span></span> <span data-ttu-id="ba904-117">Длительность вызова метода составила «%2» мс.</span><span class="sxs-lookup"><span data-stu-id="ba904-117">The method call duration was '%2' ms.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ba904-118">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="ba904-118">Details</span></span>  
  
|<span data-ttu-id="ba904-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="ba904-119">Data Item Name</span></span>|<span data-ttu-id="ba904-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="ba904-120">Data Item Type</span></span>|<span data-ttu-id="ba904-121">Описание</span><span class="sxs-lookup"><span data-stu-id="ba904-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ba904-122">Имя метода</span><span class="sxs-lookup"><span data-stu-id="ba904-122">Method Name</span></span>|`xs:string`|<span data-ttu-id="ba904-123">Имя CLR метода, который был вызван `OperationInvoker`.</span><span class="sxs-lookup"><span data-stu-id="ba904-123">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="ba904-124">Длительность</span><span class="sxs-lookup"><span data-stu-id="ba904-124">Duration</span></span>|`xs:long`|<span data-ttu-id="ba904-125">Время в миллисекундах, которое потребовалось `OperationInvoker`, чтобы вызвать метод.</span><span class="sxs-lookup"><span data-stu-id="ba904-125">The time, in milliseconds, that it took the `OperationInvoker` to invoke the method.</span></span>|  
|<span data-ttu-id="ba904-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="ba904-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="ba904-127">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="ba904-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="ba904-128">Ее формат определяется как "веб-сайт имя виртуальный путь приложения &#124; Виртуальный путь службы &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="ba904-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="ba904-129">Пример: "по умолчанию веб-сайта или CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService ".</span><span class="sxs-lookup"><span data-stu-id="ba904-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="ba904-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ba904-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="ba904-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="ba904-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
