---
title: 213 - ServiceHostStarted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a6f7facc-342f-46bb-9d52-a470178ba6bb
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 61d79adce71be9ef93e9232e01a8cba5f5319f79
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="213---servicehoststarted"></a><span data-ttu-id="aec0f-102">213 - ServiceHostStarted</span><span class="sxs-lookup"><span data-stu-id="aec0f-102">213 - ServiceHostStarted</span></span>
## <a name="properties"></a><span data-ttu-id="aec0f-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="aec0f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="aec0f-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="aec0f-104">ID</span></span>|<span data-ttu-id="aec0f-105">213</span><span class="sxs-lookup"><span data-stu-id="aec0f-105">213</span></span>|  
|<span data-ttu-id="aec0f-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="aec0f-106">Keywords</span></span>|<span data-ttu-id="aec0f-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceHost</span><span class="sxs-lookup"><span data-stu-id="aec0f-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceHost</span></span>|  
|<span data-ttu-id="aec0f-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="aec0f-108">Level</span></span>|<span data-ttu-id="aec0f-109">LogAlways</span><span class="sxs-lookup"><span data-stu-id="aec0f-109">LogAlways</span></span>|  
|<span data-ttu-id="aec0f-110">Канал</span><span class="sxs-lookup"><span data-stu-id="aec0f-110">Channel</span></span>|<span data-ttu-id="aec0f-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="aec0f-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="aec0f-112">Описание</span><span class="sxs-lookup"><span data-stu-id="aec0f-112">Description</span></span>  
 <span data-ttu-id="aec0f-113">Это событие создается при запуске службы, размещенной на веб-сервере.</span><span class="sxs-lookup"><span data-stu-id="aec0f-113">This event is emitted when a Web-hosted service host is started.</span></span> <span data-ttu-id="aec0f-114">Обычно это происходит, когда служба активируется сообщением.</span><span class="sxs-lookup"><span data-stu-id="aec0f-114">This typically happens when the service is activated by a message.</span></span> <span data-ttu-id="aec0f-115">Это также может произойти, если служба настроена для автоматического запуска.</span><span class="sxs-lookup"><span data-stu-id="aec0f-115">It may also happen if the service is configured to be automatically started.</span></span>  
  
## <a name="message"></a><span data-ttu-id="aec0f-116">Сообщение</span><span class="sxs-lookup"><span data-stu-id="aec0f-116">Message</span></span>  
 <span data-ttu-id="aec0f-117">ServiceHost запущена: «%1».</span><span class="sxs-lookup"><span data-stu-id="aec0f-117">ServiceHost started: '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="aec0f-118">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="aec0f-118">Details</span></span>  
  
|<span data-ttu-id="aec0f-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="aec0f-119">Data Item Name</span></span>|<span data-ttu-id="aec0f-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="aec0f-120">Data Item Type</span></span>|<span data-ttu-id="aec0f-121">Описание</span><span class="sxs-lookup"><span data-stu-id="aec0f-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="aec0f-122">Имя типа службы</span><span class="sxs-lookup"><span data-stu-id="aec0f-122">Service Type Name</span></span>|`xs:string`|<span data-ttu-id="aec0f-123">Имя CLR FullName типа реализации службы.</span><span class="sxs-lookup"><span data-stu-id="aec0f-123">The CLR FullName of the type of the service implementation.</span></span>|  
|<span data-ttu-id="aec0f-124">HostReference</span><span class="sxs-lookup"><span data-stu-id="aec0f-124">HostReference</span></span>|`xs:string`|<span data-ttu-id="aec0f-125">Для служб, размещенных на веб-узле, это поле служит уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="aec0f-125">For Web hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="aec0f-126">Ее формат определяется как "веб-сайт имя виртуальный путь приложения &#124; Виртуальный путь службы &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="aec0f-126">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="aec0f-127">Пример: "по умолчанию веб-сайта или CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService ".</span><span class="sxs-lookup"><span data-stu-id="aec0f-127">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="aec0f-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="aec0f-128">AppDomain</span></span>|`xs:string`|<span data-ttu-id="aec0f-129">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="aec0f-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
