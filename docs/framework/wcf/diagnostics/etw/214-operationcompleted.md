---
title: 214 - OperationCompleted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a6287eef-023f-4816-813c-1802c82366df
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 823207f4225252d94bd8fba450eb63edd00068ba
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="214---operationcompleted"></a><span data-ttu-id="653cf-102">214 - OperationCompleted</span><span class="sxs-lookup"><span data-stu-id="653cf-102">214 - OperationCompleted</span></span>
## <a name="properties"></a><span data-ttu-id="653cf-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="653cf-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="653cf-104">ID</span><span class="sxs-lookup"><span data-stu-id="653cf-104">ID</span></span>|<span data-ttu-id="653cf-105">214</span><span class="sxs-lookup"><span data-stu-id="653cf-105">214</span></span>|  
|<span data-ttu-id="653cf-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="653cf-106">Keywords</span></span>|<span data-ttu-id="653cf-107">HealthMonitoring, EndToEndMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="653cf-107">HealthMonitoring, EndToEndMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="653cf-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="653cf-108">Level</span></span>|<span data-ttu-id="653cf-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="653cf-109">Information</span></span>|  
|<span data-ttu-id="653cf-110">Канал</span><span class="sxs-lookup"><span data-stu-id="653cf-110">Channel</span></span>|<span data-ttu-id="653cf-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="653cf-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="653cf-112">Описание:</span><span class="sxs-lookup"><span data-stu-id="653cf-112">Description</span></span>  
 <span data-ttu-id="653cf-113">Данное событие создается, когда `OperationInvoker` по умолчанию модели завершает вызов метода, который не сформировал исключение.</span><span class="sxs-lookup"><span data-stu-id="653cf-113">This event is emitted when the Service Model's default `OperationInvoker` has completed a call to a method without that method throwing an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="653cf-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="653cf-114">Message</span></span>  
 <span data-ttu-id="653cf-115">OperationInvoker завершил вызов метода «%1».</span><span class="sxs-lookup"><span data-stu-id="653cf-115">An OperationInvoker completed the call to the '%1' method.</span></span> <span data-ttu-id="653cf-116">Длительность вызова метода составила «%2» мс.</span><span class="sxs-lookup"><span data-stu-id="653cf-116">The method call duration was '%2' ms.</span></span>  
  
## <a name="details"></a><span data-ttu-id="653cf-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="653cf-117">Details</span></span>  
  
|<span data-ttu-id="653cf-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="653cf-118">Data Item Name</span></span>|<span data-ttu-id="653cf-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="653cf-119">Data Item Type</span></span>|<span data-ttu-id="653cf-120">Описание:</span><span class="sxs-lookup"><span data-stu-id="653cf-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="653cf-121">Имя метода</span><span class="sxs-lookup"><span data-stu-id="653cf-121">Method Name</span></span>|`xs:string`|<span data-ttu-id="653cf-122">Имя CLR метода, который был вызван `OperationInvoker`.</span><span class="sxs-lookup"><span data-stu-id="653cf-122">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="653cf-123">Длительность</span><span class="sxs-lookup"><span data-stu-id="653cf-123">Duration</span></span>|`xs:long`|<span data-ttu-id="653cf-124">Время в миллисекундах, которое потребовалось `OperationInvoker`, чтобы вызвать метод.</span><span class="sxs-lookup"><span data-stu-id="653cf-124">The time, in milliseconds, that it took the `OperationInvoker` to invoke the method.</span></span>|  
|<span data-ttu-id="653cf-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="653cf-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="653cf-126">Для служб, размещенных на сервере, это поле служит уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="653cf-126">For web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="653cf-127">Ее формат определяется как "веб-сайт имя виртуальный путь приложения &#124; Виртуальный путь службы &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="653cf-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="653cf-128">Пример: "по умолчанию веб-сайта или CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService ".</span><span class="sxs-lookup"><span data-stu-id="653cf-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="653cf-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="653cf-129">AppDomain</span></span>|`xs:string`|<span data-ttu-id="653cf-130">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="653cf-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
