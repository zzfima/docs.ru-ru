---
title: 223 - OperationFaulted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2f7d89d7-3a6a-40fe-9610-5424eb6bbf61
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a04ed11db97d02a90e016ee1825b303375a23412
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="223---operationfaulted"></a><span data-ttu-id="9c747-102">223 - OperationFaulted</span><span class="sxs-lookup"><span data-stu-id="9c747-102">223 - OperationFaulted</span></span>
## <a name="properties"></a><span data-ttu-id="9c747-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="9c747-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9c747-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="9c747-104">ID</span></span>|<span data-ttu-id="9c747-105">223</span><span class="sxs-lookup"><span data-stu-id="9c747-105">223</span></span>|  
|<span data-ttu-id="9c747-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="9c747-106">Keywords</span></span>|<span data-ttu-id="9c747-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="9c747-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="9c747-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="9c747-108">Level</span></span>|<span data-ttu-id="9c747-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="9c747-109">Warning</span></span>|  
|<span data-ttu-id="9c747-110">Канал</span><span class="sxs-lookup"><span data-stu-id="9c747-110">Channel</span></span>|<span data-ttu-id="9c747-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="9c747-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9c747-112">Описание</span><span class="sxs-lookup"><span data-stu-id="9c747-112">Description</span></span>  
 <span data-ttu-id="9c747-113">Это событие вызывается в том случае, если при вызове `OperationInvoker` модели службы по умолчанию обнаружено исключение, производное от `FaultException`.</span><span class="sxs-lookup"><span data-stu-id="9c747-113">This event is emitted when the Service Model's default `OperationInvoker` has encountered an exception deriving from `FaultException` while invoking its method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9c747-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="9c747-114">Message</span></span>  
 <span data-ttu-id="9c747-115">Метод «%1» вызывал исключение FaultException после того, как был вызван OperationInvoker.</span><span class="sxs-lookup"><span data-stu-id="9c747-115">The '%1' method threw a FaultException when invoked by the OperationInvoker.</span></span> <span data-ttu-id="9c747-116">Длительность вызова метода составила «%2» мс.</span><span class="sxs-lookup"><span data-stu-id="9c747-116">The method call duration was '%2' ms.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9c747-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="9c747-117">Details</span></span>  
  
|<span data-ttu-id="9c747-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="9c747-118">Data Item Name</span></span>|<span data-ttu-id="9c747-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="9c747-119">Data Item Type</span></span>|<span data-ttu-id="9c747-120">Описание</span><span class="sxs-lookup"><span data-stu-id="9c747-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9c747-121">MethodName</span><span class="sxs-lookup"><span data-stu-id="9c747-121">MethodName</span></span>|`xs:string`|<span data-ttu-id="9c747-122">Имя CLR метода, который был вызван `OperationInvoker`.</span><span class="sxs-lookup"><span data-stu-id="9c747-122">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="9c747-123">Длительность</span><span class="sxs-lookup"><span data-stu-id="9c747-123">Duration</span></span>|`xs:long`|<span data-ttu-id="9c747-124">Время в миллисекундах, которое потребовалось `OperationInvoker`, чтобы вызвать метод.</span><span class="sxs-lookup"><span data-stu-id="9c747-124">The time, in milliseconds, that it took the `OperationInvoker` to invoke the method.</span></span>|  
|<span data-ttu-id="9c747-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="9c747-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="9c747-126">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="9c747-126">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="9c747-127">Ее формат определяется как "веб-сайт имя виртуальный путь приложения &#124; Виртуальный путь службы &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="9c747-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="9c747-128">Пример: "по умолчанию веб-сайта или CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService ".</span><span class="sxs-lookup"><span data-stu-id="9c747-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="9c747-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="9c747-129">AppDomain</span></span>|`xs:string`|<span data-ttu-id="9c747-130">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="9c747-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
