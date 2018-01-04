---
title: 203 - ClientParameterInspectorAfterCallInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b9592212-07e2-43e0-8b00-affd195cf55a
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1173aaa4bf01b324c8cd6088cd5646bc67f08c72
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="203---clientparameterinspectoraftercallinvoked"></a><span data-ttu-id="9c080-102">203 - ClientParameterInspectorAfterCallInvoked</span><span class="sxs-lookup"><span data-stu-id="9c080-102">203 - ClientParameterInspectorAfterCallInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="9c080-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="9c080-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9c080-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="9c080-104">ID</span></span>|<span data-ttu-id="9c080-105">203</span><span class="sxs-lookup"><span data-stu-id="9c080-105">203</span></span>|  
|<span data-ttu-id="9c080-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="9c080-106">Keywords</span></span>|<span data-ttu-id="9c080-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="9c080-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="9c080-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="9c080-108">Level</span></span>|<span data-ttu-id="9c080-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="9c080-109">Information</span></span>|  
|<span data-ttu-id="9c080-110">Канал</span><span class="sxs-lookup"><span data-stu-id="9c080-110">Channel</span></span>|<span data-ttu-id="9c080-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="9c080-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9c080-112">Описание</span><span class="sxs-lookup"><span data-stu-id="9c080-112">Description</span></span>  
 <span data-ttu-id="9c080-113">Это событие создается после того, как модель службы вызывает метод `AfterCall` для инспектора параметров клиента.</span><span class="sxs-lookup"><span data-stu-id="9c080-113">This event is emitted after the Service Model has invoked the `AfterCall` method on a client parameter inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9c080-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="9c080-114">Message</span></span>  
 <span data-ttu-id="9c080-115">Диспетчер вызвал «AfterCall» для ClientParameterInspector типа «%1».</span><span class="sxs-lookup"><span data-stu-id="9c080-115">The Dispatcher invoked 'AfterCall' on a ClientParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9c080-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="9c080-116">Details</span></span>  
  
|<span data-ttu-id="9c080-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="9c080-117">Data Item Name</span></span>|<span data-ttu-id="9c080-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="9c080-118">Data Item Type</span></span>|<span data-ttu-id="9c080-119">Описание</span><span class="sxs-lookup"><span data-stu-id="9c080-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9c080-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="9c080-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="9c080-121">Имя CLR FullName типа вызванного инспектора.</span><span class="sxs-lookup"><span data-stu-id="9c080-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="9c080-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="9c080-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="9c080-123">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="9c080-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="9c080-124">Ее формат определяется как "веб-сайт имя виртуальный путь приложения &#124; Виртуальный путь службы &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="9c080-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="9c080-125">Пример: "по умолчанию веб-сайта или CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService ".</span><span class="sxs-lookup"><span data-stu-id="9c080-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="9c080-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="9c080-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="9c080-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="9c080-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
