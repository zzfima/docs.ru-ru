---
title: 499 - TransferEmitted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 07a26434-a7a0-40fc-b5d0-3520a04328ae
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1a0bbe31095a59be4b091de6974ae0173753e240
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="499---transferemitted"></a><span data-ttu-id="d6a64-102">499 - TransferEmitted</span><span class="sxs-lookup"><span data-stu-id="d6a64-102">499 - TransferEmitted</span></span>
## <a name="properties"></a><span data-ttu-id="d6a64-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="d6a64-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d6a64-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="d6a64-104">ID</span></span>|<span data-ttu-id="d6a64-105">499</span><span class="sxs-lookup"><span data-stu-id="d6a64-105">499</span></span>|  
|<span data-ttu-id="d6a64-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="d6a64-106">Keywords</span></span>|<span data-ttu-id="d6a64-107">Troubleshooting, UserEvents, EndToEndMonitoring, ServiceModel, WFTracking, ServiceHost, WCFMessageLogging</span><span class="sxs-lookup"><span data-stu-id="d6a64-107">Troubleshooting, UserEvents, EndToEndMonitoring, ServiceModel, WFTracking, ServiceHost, WCFMessageLogging</span></span>|  
|<span data-ttu-id="d6a64-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="d6a64-108">Level</span></span>|<span data-ttu-id="d6a64-109">LogAlways</span><span class="sxs-lookup"><span data-stu-id="d6a64-109">LogAlways</span></span>|  
|<span data-ttu-id="d6a64-110">Канал</span><span class="sxs-lookup"><span data-stu-id="d6a64-110">Channel</span></span>|<span data-ttu-id="d6a64-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="d6a64-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d6a64-112">Описание</span><span class="sxs-lookup"><span data-stu-id="d6a64-112">Description</span></span>  
 <span data-ttu-id="d6a64-113">Это событие формируется при возникновении события передачи.</span><span class="sxs-lookup"><span data-stu-id="d6a64-113">This event is emitted when the transfer event takes place.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d6a64-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="d6a64-114">Message</span></span>  
 <span data-ttu-id="d6a64-115">Произошло событие передачи.</span><span class="sxs-lookup"><span data-stu-id="d6a64-115">Transfer event emitted.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d6a64-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="d6a64-116">Details</span></span>  
  
|<span data-ttu-id="d6a64-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="d6a64-117">Data Item Name</span></span>|<span data-ttu-id="d6a64-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="d6a64-118">Data Item Type</span></span>|<span data-ttu-id="d6a64-119">Описание</span><span class="sxs-lookup"><span data-stu-id="d6a64-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d6a64-120">HostReference</span><span class="sxs-lookup"><span data-stu-id="d6a64-120">HostReference</span></span>|`xs:string`|<span data-ttu-id="d6a64-121">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="d6a64-121">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="d6a64-122">Ее формат определяется как "веб-сайт имя виртуальный путь приложения &#124; Виртуальный путь службы &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="d6a64-122">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="d6a64-123">Пример: "по умолчанию веб-сайта или CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService ".</span><span class="sxs-lookup"><span data-stu-id="d6a64-123">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="d6a64-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d6a64-124">AppDomain</span></span>|`xs:string`|<span data-ttu-id="d6a64-125">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="d6a64-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
