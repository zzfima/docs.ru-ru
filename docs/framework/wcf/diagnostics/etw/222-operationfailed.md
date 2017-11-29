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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1c76b502c9c1a767898b1e857c2e943c26fad5c1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="222---operationfailed"></a><span data-ttu-id="676ee-102">222 - OperationFailed</span><span class="sxs-lookup"><span data-stu-id="676ee-102">222 - OperationFailed</span></span>
## <a name="properties"></a><span data-ttu-id="676ee-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="676ee-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="676ee-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="676ee-104">ID</span></span>|<span data-ttu-id="676ee-105">222</span><span class="sxs-lookup"><span data-stu-id="676ee-105">222</span></span>|  
|<span data-ttu-id="676ee-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="676ee-106">Keywords</span></span>|<span data-ttu-id="676ee-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="676ee-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="676ee-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="676ee-108">Level</span></span>|<span data-ttu-id="676ee-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="676ee-109">Warning</span></span>|  
|<span data-ttu-id="676ee-110">Канал</span><span class="sxs-lookup"><span data-stu-id="676ee-110">Channel</span></span>|<span data-ttu-id="676ee-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="676ee-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="676ee-112">Описание</span><span class="sxs-lookup"><span data-stu-id="676ee-112">Description</span></span>  
 <span data-ttu-id="676ee-113">Это событие создается в том случае, когда `OperationInvoker` модели службы по умолчанию обнаруживает исключение при вызове его метода.</span><span class="sxs-lookup"><span data-stu-id="676ee-113">This event is emitted when the Service Model's default `OperationInvoker` has encountered an exception while invoking its method.</span></span> <span data-ttu-id="676ee-114">Обратите внимание, что исключения, производные от `FaultException`, не вызывают это событие.</span><span class="sxs-lookup"><span data-stu-id="676ee-114">Note that exceptions that derive from `FaultException` cause this event to not be emitted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="676ee-115">Сообщение</span><span class="sxs-lookup"><span data-stu-id="676ee-115">Message</span></span>  
 <span data-ttu-id="676ee-116">Метод «%1» вызвал необработанное исключение после того, как был вызван OperationInvoker.</span><span class="sxs-lookup"><span data-stu-id="676ee-116">The '%1' method threw an unhandled exception when invoked by the OperationInvoker.</span></span> <span data-ttu-id="676ee-117">Длительность вызова метода составила «%2» мс.</span><span class="sxs-lookup"><span data-stu-id="676ee-117">The method call duration was '%2' ms.</span></span>  
  
## <a name="details"></a><span data-ttu-id="676ee-118">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="676ee-118">Details</span></span>  
  
|<span data-ttu-id="676ee-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="676ee-119">Data Item Name</span></span>|<span data-ttu-id="676ee-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="676ee-120">Data Item Type</span></span>|<span data-ttu-id="676ee-121">Описание</span><span class="sxs-lookup"><span data-stu-id="676ee-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="676ee-122">Имя метода</span><span class="sxs-lookup"><span data-stu-id="676ee-122">Method Name</span></span>|`xs:string`|<span data-ttu-id="676ee-123">Имя CLR метода, который был вызван `OperationInvoker`.</span><span class="sxs-lookup"><span data-stu-id="676ee-123">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="676ee-124">Длительность</span><span class="sxs-lookup"><span data-stu-id="676ee-124">Duration</span></span>|`xs:long`|<span data-ttu-id="676ee-125">Время в миллисекундах, которое потребовалось `OperationInvoker`, чтобы вызвать метод.</span><span class="sxs-lookup"><span data-stu-id="676ee-125">The time, in milliseconds, that it took the `OperationInvoker` to invoke the method.</span></span>|  
|<span data-ttu-id="676ee-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="676ee-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="676ee-127">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="676ee-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="676ee-128">Ее формат определяется как "веб-сайт имя виртуальный путь приложения &#124; Виртуальный путь службы &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="676ee-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="676ee-129">Пример: "по умолчанию веб-сайта или CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService ".</span><span class="sxs-lookup"><span data-stu-id="676ee-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="676ee-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="676ee-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="676ee-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="676ee-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
