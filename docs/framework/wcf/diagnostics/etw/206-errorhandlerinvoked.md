---
title: 206 - ErrorHandlerInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 97340f4d-4e09-4e42-a17a-982b3868dbcf
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4ff48217b1430002e1590ec3fdb1707d65075ffe
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="206---errorhandlerinvoked"></a><span data-ttu-id="927f1-102">206 - ErrorHandlerInvoked</span><span class="sxs-lookup"><span data-stu-id="927f1-102">206 - ErrorHandlerInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="927f1-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="927f1-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="927f1-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="927f1-104">ID</span></span>|<span data-ttu-id="927f1-105">206</span><span class="sxs-lookup"><span data-stu-id="927f1-105">206</span></span>|  
|<span data-ttu-id="927f1-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="927f1-106">Keywords</span></span>|<span data-ttu-id="927f1-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="927f1-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="927f1-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="927f1-108">Level</span></span>|<span data-ttu-id="927f1-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="927f1-109">Information</span></span>|  
|<span data-ttu-id="927f1-110">Канал</span><span class="sxs-lookup"><span data-stu-id="927f1-110">Channel</span></span>|<span data-ttu-id="927f1-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="927f1-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="927f1-112">Описание</span><span class="sxs-lookup"><span data-stu-id="927f1-112">Description</span></span>  
 <span data-ttu-id="927f1-113">Это событие создается после того, как обработчик `ErrorHandler` начинает обрабатывать исключение, возникшее в операции службы.</span><span class="sxs-lookup"><span data-stu-id="927f1-113">This event is emitted after an `ErrorHandler` has had an opportunity to handle an exception that occurred in a service operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="927f1-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="927f1-114">Message</span></span>  
 <span data-ttu-id="927f1-115">Диспетчер запустил ErrorHandler типа «%1» с исключением типа «%3».</span><span class="sxs-lookup"><span data-stu-id="927f1-115">The Dispatcher invoked an ErrorHandler of type '%1' with an exception of type '%3'.</span></span> <span data-ttu-id="927f1-116">ErrorHandled == '%2'.</span><span class="sxs-lookup"><span data-stu-id="927f1-116">ErrorHandled == '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="927f1-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="927f1-117">Details</span></span>  
  
|<span data-ttu-id="927f1-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="927f1-118">Data Item Name</span></span>|<span data-ttu-id="927f1-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="927f1-119">Data Item Type</span></span>|<span data-ttu-id="927f1-120">Описание</span><span class="sxs-lookup"><span data-stu-id="927f1-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="927f1-121">TypeName</span><span class="sxs-lookup"><span data-stu-id="927f1-121">TypeName</span></span>|`xs:string`|<span data-ttu-id="927f1-122">Имя CLR FullName типа вызванного инспектора `ErrorHandler`.</span><span class="sxs-lookup"><span data-stu-id="927f1-122">The CLR FullName of the type of the invoked `ErrorHandler`.</span></span>|  
|<span data-ttu-id="927f1-123">Handled</span><span class="sxs-lookup"><span data-stu-id="927f1-123">Handled</span></span>|`xs:unsignedByte`|<span data-ttu-id="927f1-124">Значение `true`, если обработчик ошибок обработал ошибку, в противном случае значение `false`.</span><span class="sxs-lookup"><span data-stu-id="927f1-124">`true` if the error handler handled the error, otherwise `false`.</span></span>|  
|<span data-ttu-id="927f1-125">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="927f1-125">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="927f1-126">Имя CLR FullName обрабатываемого исключения.</span><span class="sxs-lookup"><span data-stu-id="927f1-126">The CLR FullName of the exception that was being handled.</span></span>|  
|<span data-ttu-id="927f1-127">HostReference</span><span class="sxs-lookup"><span data-stu-id="927f1-127">HostReference</span></span>|`xs:string`|<span data-ttu-id="927f1-128">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="927f1-128">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="927f1-129">Ее формат определяется как "веб-сайт имя виртуальный путь приложения &#124; Виртуальный путь службы &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="927f1-129">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="927f1-130">Пример: "по умолчанию веб-сайта или CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService ".</span><span class="sxs-lookup"><span data-stu-id="927f1-130">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="927f1-131">AppDomain</span><span class="sxs-lookup"><span data-stu-id="927f1-131">AppDomain</span></span>|`xs:string`|<span data-ttu-id="927f1-132">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="927f1-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
