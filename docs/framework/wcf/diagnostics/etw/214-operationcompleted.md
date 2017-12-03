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
ms.openlocfilehash: 09a8dc1994da30c0f0c180640e3f66c8806e4528
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="214---operationcompleted"></a><span data-ttu-id="ec7e1-102">214 - OperationCompleted</span><span class="sxs-lookup"><span data-stu-id="ec7e1-102">214 - OperationCompleted</span></span>
## <a name="properties"></a><span data-ttu-id="ec7e1-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="ec7e1-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ec7e1-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="ec7e1-104">ID</span></span>|<span data-ttu-id="ec7e1-105">214</span><span class="sxs-lookup"><span data-stu-id="ec7e1-105">214</span></span>|  
|<span data-ttu-id="ec7e1-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ec7e1-106">Keywords</span></span>|<span data-ttu-id="ec7e1-107">HealthMonitoring, EndToEndMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ec7e1-107">HealthMonitoring, EndToEndMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="ec7e1-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="ec7e1-108">Level</span></span>|<span data-ttu-id="ec7e1-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="ec7e1-109">Information</span></span>|  
|<span data-ttu-id="ec7e1-110">Канал</span><span class="sxs-lookup"><span data-stu-id="ec7e1-110">Channel</span></span>|<span data-ttu-id="ec7e1-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="ec7e1-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ec7e1-112">Описание</span><span class="sxs-lookup"><span data-stu-id="ec7e1-112">Description</span></span>  
 <span data-ttu-id="ec7e1-113">Данное событие создается, когда `OperationInvoker` по умолчанию модели завершает вызов метода, который не сформировал исключение.</span><span class="sxs-lookup"><span data-stu-id="ec7e1-113">This event is emitted when the Service Model's default `OperationInvoker` has completed a call to a method without that method throwing an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ec7e1-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="ec7e1-114">Message</span></span>  
 <span data-ttu-id="ec7e1-115">OperationInvoker завершил вызов метода «%1».</span><span class="sxs-lookup"><span data-stu-id="ec7e1-115">An OperationInvoker completed the call to the '%1' method.</span></span> <span data-ttu-id="ec7e1-116">Длительность вызова метода составила «%2» мс.</span><span class="sxs-lookup"><span data-stu-id="ec7e1-116">The method call duration was '%2' ms.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ec7e1-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="ec7e1-117">Details</span></span>  
  
|<span data-ttu-id="ec7e1-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="ec7e1-118">Data Item Name</span></span>|<span data-ttu-id="ec7e1-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="ec7e1-119">Data Item Type</span></span>|<span data-ttu-id="ec7e1-120">Описание</span><span class="sxs-lookup"><span data-stu-id="ec7e1-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ec7e1-121">Имя метода</span><span class="sxs-lookup"><span data-stu-id="ec7e1-121">Method Name</span></span>|`xs:string`|<span data-ttu-id="ec7e1-122">Имя CLR метода, который был вызван `OperationInvoker`.</span><span class="sxs-lookup"><span data-stu-id="ec7e1-122">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="ec7e1-123">Длительность</span><span class="sxs-lookup"><span data-stu-id="ec7e1-123">Duration</span></span>|`xs:long`|<span data-ttu-id="ec7e1-124">Время в миллисекундах, которое потребовалось `OperationInvoker`, чтобы вызвать метод.</span><span class="sxs-lookup"><span data-stu-id="ec7e1-124">The time, in milliseconds, that it took the `OperationInvoker` to invoke the method.</span></span>|  
|<span data-ttu-id="ec7e1-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="ec7e1-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="ec7e1-126">Для служб, размещенных на сервере, это поле служит уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="ec7e1-126">For web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="ec7e1-127">Ее формат определяется как "веб-сайт имя виртуальный путь приложения &#124; Виртуальный путь службы &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="ec7e1-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="ec7e1-128">Пример: "по умолчанию веб-сайта или CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService ".</span><span class="sxs-lookup"><span data-stu-id="ec7e1-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="ec7e1-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ec7e1-129">AppDomain</span></span>|`xs:string`|<span data-ttu-id="ec7e1-130">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="ec7e1-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
