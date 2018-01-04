---
title: 208 - MessageInspectorAfterReceiveInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dfb5f7b0-4346-4949-8104-351726b1f502
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 253daea49ed36e27a23c55f3baf252344c0a34f8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="208---messageinspectorafterreceiveinvoked"></a><span data-ttu-id="dff80-102">208 - MessageInspectorAfterReceiveInvoked</span><span class="sxs-lookup"><span data-stu-id="dff80-102">208 - MessageInspectorAfterReceiveInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="dff80-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="dff80-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dff80-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="dff80-104">ID</span></span>|<span data-ttu-id="dff80-105">208</span><span class="sxs-lookup"><span data-stu-id="dff80-105">208</span></span>|  
|<span data-ttu-id="dff80-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="dff80-106">Keywords</span></span>|<span data-ttu-id="dff80-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="dff80-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="dff80-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="dff80-108">Level</span></span>|<span data-ttu-id="dff80-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="dff80-109">Information</span></span>|  
|<span data-ttu-id="dff80-110">Канал</span><span class="sxs-lookup"><span data-stu-id="dff80-110">Channel</span></span>|<span data-ttu-id="dff80-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="dff80-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="dff80-112">Описание</span><span class="sxs-lookup"><span data-stu-id="dff80-112">Description</span></span>  
 <span data-ttu-id="dff80-113">Это событие создается после того, как модель службы вызвала метод `AfterReceive` для инспектора сообщений.</span><span class="sxs-lookup"><span data-stu-id="dff80-113">This event is emitted after the Service Model has invoked the `AfterReceive` method on a message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="dff80-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="dff80-114">Message</span></span>  
 <span data-ttu-id="dff80-115">Диспетчер вызвал AfterReceiveReply относительно MessageInspector типа «%1».</span><span class="sxs-lookup"><span data-stu-id="dff80-115">The Dispatcher invoked 'AfterReceiveReply' on a MessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="dff80-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="dff80-116">Details</span></span>  
  
|<span data-ttu-id="dff80-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="dff80-117">Data Item Name</span></span>|<span data-ttu-id="dff80-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="dff80-118">Data Item Type</span></span>|<span data-ttu-id="dff80-119">Описание</span><span class="sxs-lookup"><span data-stu-id="dff80-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="dff80-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="dff80-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="dff80-121">Имя CLR FullName типа вызванного инспектора `MessageInspector`.</span><span class="sxs-lookup"><span data-stu-id="dff80-121">The CLR FullName of the type of the invoked `MessageInspector`.</span></span>|  
|<span data-ttu-id="dff80-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="dff80-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="dff80-123">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="dff80-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="dff80-124">Ее формат определяется как "веб-сайт имя виртуальный путь приложения &#124; Виртуальный путь службы &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="dff80-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="dff80-125">Пример: "по умолчанию веб-сайта или CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService ".</span><span class="sxs-lookup"><span data-stu-id="dff80-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="dff80-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="dff80-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="dff80-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="dff80-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
