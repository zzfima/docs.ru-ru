---
title: 219 - ServiceException
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 81e2efac-39aa-4ed2-85a9-97eb8793b844
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fceff5c748076c75c942f515e2621edff5106f4e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="219---serviceexception"></a><span data-ttu-id="391ac-102">219 - ServiceException</span><span class="sxs-lookup"><span data-stu-id="391ac-102">219 - ServiceException</span></span>
## <a name="properties"></a><span data-ttu-id="391ac-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="391ac-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="391ac-104">ID</span><span class="sxs-lookup"><span data-stu-id="391ac-104">ID</span></span>|<span data-ttu-id="391ac-105">219</span><span class="sxs-lookup"><span data-stu-id="391ac-105">219</span></span>|  
|<span data-ttu-id="391ac-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="391ac-106">Keywords</span></span>|<span data-ttu-id="391ac-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="391ac-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="391ac-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="391ac-108">Level</span></span>|<span data-ttu-id="391ac-109">Ошибка</span><span class="sxs-lookup"><span data-stu-id="391ac-109">Error</span></span>|  
|<span data-ttu-id="391ac-110">Канал</span><span class="sxs-lookup"><span data-stu-id="391ac-110">Channel</span></span>|<span data-ttu-id="391ac-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="391ac-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="391ac-112">Описание:</span><span class="sxs-lookup"><span data-stu-id="391ac-112">Description</span></span>  
 <span data-ttu-id="391ac-113">Это событие создается при обнаружении службой WCF необработанного исключения.</span><span class="sxs-lookup"><span data-stu-id="391ac-113">This event is emitted when a WCF service encounters an unhandled exception.</span></span> <span data-ttu-id="391ac-114">В число необработанных входят исключения, возникшие во время активации, обработки сообщений и выполнения пользовательского кода.</span><span class="sxs-lookup"><span data-stu-id="391ac-114">This includes unhandled exceptions during activation, during message processing, and in user code.</span></span>  
  
## <a name="message"></a><span data-ttu-id="391ac-115">Сообщение</span><span class="sxs-lookup"><span data-stu-id="391ac-115">Message</span></span>  
 <span data-ttu-id="391ac-116">Во время обработки сообщения возникло необработанное исключение типа «%2».</span><span class="sxs-lookup"><span data-stu-id="391ac-116">There was an unhandled exception of type '%2' during message processing.</span></span> <span data-ttu-id="391ac-117">Полное исключение ToString: %1.</span><span class="sxs-lookup"><span data-stu-id="391ac-117">Full Exception ToString: %1.</span></span>  
  
## <a name="details"></a><span data-ttu-id="391ac-118">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="391ac-118">Details</span></span>  
  
|<span data-ttu-id="391ac-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="391ac-119">Data Item Name</span></span>|<span data-ttu-id="391ac-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="391ac-120">Data Item Type</span></span>|<span data-ttu-id="391ac-121">Описание:</span><span class="sxs-lookup"><span data-stu-id="391ac-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="391ac-122">ExceptionToString</span><span class="sxs-lookup"><span data-stu-id="391ac-122">ExceptionToString</span></span>|`xs:string`|<span data-ttu-id="391ac-123">Результат вызова метода `ToString`() относительно исключения CLR.</span><span class="sxs-lookup"><span data-stu-id="391ac-123">The result of calling `ToString`() on the CLR exception.</span></span>|  
|<span data-ttu-id="391ac-124">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="391ac-124">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="391ac-125">Имя CLR FullName типа исключения.</span><span class="sxs-lookup"><span data-stu-id="391ac-125">The CLR FullName of the exception's type.</span></span>|  
|<span data-ttu-id="391ac-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="391ac-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="391ac-127">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="391ac-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="391ac-128">Ее формат определяется как "веб-сайт имя виртуальный путь приложения &#124; Виртуальный путь службы &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="391ac-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="391ac-129">Пример: "по умолчанию веб-сайта или CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService ".</span><span class="sxs-lookup"><span data-stu-id="391ac-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="391ac-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="391ac-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="391ac-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="391ac-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
