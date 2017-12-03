---
title: 209 - MessageInspectorBeforeSendInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7d710875-fb77-4463-978b-bc86d59d84cd
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3341f9ae5600536a7d824034582bf232f5be90ad
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="209---messageinspectorbeforesendinvoked"></a><span data-ttu-id="e0df9-102">209 - MessageInspectorBeforeSendInvoked</span><span class="sxs-lookup"><span data-stu-id="e0df9-102">209 - MessageInspectorBeforeSendInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="e0df9-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="e0df9-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e0df9-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="e0df9-104">ID</span></span>|<span data-ttu-id="e0df9-105">209</span><span class="sxs-lookup"><span data-stu-id="e0df9-105">209</span></span>|  
|<span data-ttu-id="e0df9-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="e0df9-106">Keywords</span></span>|<span data-ttu-id="e0df9-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e0df9-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="e0df9-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="e0df9-108">Level</span></span>|<span data-ttu-id="e0df9-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="e0df9-109">Information</span></span>|  
|<span data-ttu-id="e0df9-110">Канал</span><span class="sxs-lookup"><span data-stu-id="e0df9-110">Channel</span></span>|<span data-ttu-id="e0df9-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="e0df9-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e0df9-112">Описание</span><span class="sxs-lookup"><span data-stu-id="e0df9-112">Description</span></span>  
 <span data-ttu-id="e0df9-113">Это событие создается после того, как модель службы вызвала метод `BeforeSend` для инспектора сообщений.</span><span class="sxs-lookup"><span data-stu-id="e0df9-113">This event is emitted after the Service Model has invoked the `BeforeSend` method on a message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e0df9-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="e0df9-114">Message</span></span>  
 <span data-ttu-id="e0df9-115">Диспетчер вызвал BeforeSendRequest для MessageInspector типа «%1».</span><span class="sxs-lookup"><span data-stu-id="e0df9-115">The Dispatcher invoked 'BeforeSendRequest' on a MessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e0df9-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="e0df9-116">Details</span></span>  
  
|<span data-ttu-id="e0df9-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="e0df9-117">Data Item Name</span></span>|<span data-ttu-id="e0df9-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="e0df9-118">Data Item Type</span></span>|<span data-ttu-id="e0df9-119">Описание</span><span class="sxs-lookup"><span data-stu-id="e0df9-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e0df9-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="e0df9-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="e0df9-121">Имя CLR FullName типа вызванного инспектора `MessageInspector`.</span><span class="sxs-lookup"><span data-stu-id="e0df9-121">The CLR FullName of the type of the invoked `MessageInspector`.</span></span>|  
|<span data-ttu-id="e0df9-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="e0df9-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="e0df9-123">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="e0df9-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="e0df9-124">Ее формат определяется как "веб-сайт имя виртуальный путь приложения &#124; Виртуальный путь службы &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="e0df9-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="e0df9-125">Пример: "по умолчанию веб-сайта или CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService ".</span><span class="sxs-lookup"><span data-stu-id="e0df9-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="e0df9-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e0df9-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="e0df9-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="e0df9-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
