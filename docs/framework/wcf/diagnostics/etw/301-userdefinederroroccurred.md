---
title: 301 - UserDefinedErrorOccurred
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a0285d1c-550f-4c14-9c36-a96e97f1c4e4
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b24d54930a29a24dab97ce403c2808fb74b8cbfe
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="301---userdefinederroroccurred"></a><span data-ttu-id="9706a-102">301 - UserDefinedErrorOccurred</span><span class="sxs-lookup"><span data-stu-id="9706a-102">301 - UserDefinedErrorOccurred</span></span>
## <a name="properties"></a><span data-ttu-id="9706a-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="9706a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9706a-104">ID</span><span class="sxs-lookup"><span data-stu-id="9706a-104">ID</span></span>|<span data-ttu-id="9706a-105">301</span><span class="sxs-lookup"><span data-stu-id="9706a-105">301</span></span>|  
|<span data-ttu-id="9706a-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="9706a-106">Keywords</span></span>|<span data-ttu-id="9706a-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span><span class="sxs-lookup"><span data-stu-id="9706a-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span></span>|  
|<span data-ttu-id="9706a-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="9706a-108">Level</span></span>|<span data-ttu-id="9706a-109">Ошибка</span><span class="sxs-lookup"><span data-stu-id="9706a-109">Error</span></span>|  
|<span data-ttu-id="9706a-110">Канал</span><span class="sxs-lookup"><span data-stu-id="9706a-110">Channel</span></span>|<span data-ttu-id="9706a-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="9706a-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9706a-112">Описание:</span><span class="sxs-lookup"><span data-stu-id="9706a-112">Description</span></span>  
 <span data-ttu-id="9706a-113">Это событие создается в пользовательском коде.</span><span class="sxs-lookup"><span data-stu-id="9706a-113">This event is emitted from user code.</span></span> <span data-ttu-id="9706a-114">Разработчики могут создать это событие, если определенная пользователем ошибка возникает в принадлежащей им службе.</span><span class="sxs-lookup"><span data-stu-id="9706a-114">Developers can emit this event when a custom-defined error occurs in their service.</span></span> <span data-ttu-id="9706a-115">Это можно сделать при помощи API-интерфейсов <xref:System.Diagnostics.Eventing>.</span><span class="sxs-lookup"><span data-stu-id="9706a-115">This can be done using the <xref:System.Diagnostics.Eventing> APIs.</span></span> <span data-ttu-id="9706a-116">Помимо этого, есть образец WCF, который включает этот API-интерфейс и показывает, как правильно создать это событие.</span><span class="sxs-lookup"><span data-stu-id="9706a-116">Additionally, there is a WCF sample that wraps that API and demonstrates how to properly emit this event.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9706a-117">Сообщение</span><span class="sxs-lookup"><span data-stu-id="9706a-117">Message</span></span>  
 <span data-ttu-id="9706a-118">Имя: «%1», ссылка: «%2», полезные данные: %3</span><span class="sxs-lookup"><span data-stu-id="9706a-118">Name:'%1', Reference:'%2', Payload:%3</span></span>  
  
## <a name="details"></a><span data-ttu-id="9706a-119">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="9706a-119">Details</span></span>  
  
|<span data-ttu-id="9706a-120">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="9706a-120">Data Item Name</span></span>|<span data-ttu-id="9706a-121">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="9706a-121">Data Item Type</span></span>|<span data-ttu-id="9706a-122">Описание</span><span class="sxs-lookup"><span data-stu-id="9706a-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9706a-123">name</span><span class="sxs-lookup"><span data-stu-id="9706a-123">Name</span></span>|`xs:string`|<span data-ttu-id="9706a-124">Определенное пользователем имя события.</span><span class="sxs-lookup"><span data-stu-id="9706a-124">The user-defined name of the event.</span></span>|  
|<span data-ttu-id="9706a-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="9706a-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="9706a-126">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="9706a-126">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="9706a-127">Ее формат определяется как "веб-сайт имя виртуальный путь приложения &#124; Виртуальный путь службы &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="9706a-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="9706a-128">Пример: "по умолчанию веб-сайта или CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService ".</span><span class="sxs-lookup"><span data-stu-id="9706a-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="9706a-129">Payload</span><span class="sxs-lookup"><span data-stu-id="9706a-129">Payload</span></span>|`xs:string`|<span data-ttu-id="9706a-130">Определенные пользователем полезные данные события.</span><span class="sxs-lookup"><span data-stu-id="9706a-130">The user-defined payload of the event.</span></span>|
