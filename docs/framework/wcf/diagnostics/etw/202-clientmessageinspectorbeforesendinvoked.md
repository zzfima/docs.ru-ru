---
title: 202 - ClientMessageInspectorBeforeSendInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0b02ca82-8a55-45e3-b2e2-ddfe28a7269c
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f6d737a7334098961cccb73a114be9be5bb71727
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="202---clientmessageinspectorbeforesendinvoked"></a><span data-ttu-id="59972-102">202 - ClientMessageInspectorBeforeSendInvoked</span><span class="sxs-lookup"><span data-stu-id="59972-102">202 - ClientMessageInspectorBeforeSendInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="59972-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="59972-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="59972-104">ID</span><span class="sxs-lookup"><span data-stu-id="59972-104">ID</span></span>|<span data-ttu-id="59972-105">202</span><span class="sxs-lookup"><span data-stu-id="59972-105">202</span></span>|  
|<span data-ttu-id="59972-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="59972-106">Keywords</span></span>|<span data-ttu-id="59972-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="59972-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="59972-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="59972-108">Level</span></span>|<span data-ttu-id="59972-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="59972-109">Information</span></span>|  
|<span data-ttu-id="59972-110">Канал</span><span class="sxs-lookup"><span data-stu-id="59972-110">Channel</span></span>|<span data-ttu-id="59972-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="59972-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="59972-112">Описание:</span><span class="sxs-lookup"><span data-stu-id="59972-112">Description</span></span>  
 <span data-ttu-id="59972-113">Это событие создается после того, как модель службы вызывает метод `BeforeSendRequest` для инспектора сообщений клиента.</span><span class="sxs-lookup"><span data-stu-id="59972-113">This event is emitted after the Service Model has invoked the `BeforeSendRequest` method on a client message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="59972-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="59972-114">Message</span></span>  
 <span data-ttu-id="59972-115">Диспетчер вызвал BeforeSendRequest для ClientMessageInspector типа «%1».</span><span class="sxs-lookup"><span data-stu-id="59972-115">The Dispatcher invoked 'BeforeSendRequest' on a ClientMessageInspector of type  '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="59972-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="59972-116">Details</span></span>  
  
|<span data-ttu-id="59972-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="59972-117">Data Item Name</span></span>|<span data-ttu-id="59972-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="59972-118">Data Item Type</span></span>|<span data-ttu-id="59972-119">Описание</span><span class="sxs-lookup"><span data-stu-id="59972-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="59972-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="59972-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="59972-121">Имя CLR FullName типа вызванного инспектора.</span><span class="sxs-lookup"><span data-stu-id="59972-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="59972-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="59972-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="59972-123">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="59972-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="59972-124">Ее формат определяется как "веб-сайт имя виртуальный путь приложения &#124; Виртуальный путь службы &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="59972-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="59972-125">Пример: "по умолчанию веб-сайта или CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService ".</span><span class="sxs-lookup"><span data-stu-id="59972-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="59972-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="59972-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="59972-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="59972-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
