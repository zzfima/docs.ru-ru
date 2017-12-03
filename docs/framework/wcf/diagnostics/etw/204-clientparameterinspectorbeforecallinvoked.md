---
title: 204 - ClientParameterInspectorBeforeCallInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8253555a-9002-4565-8ede-33d7a33a895f
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2b30e53803692b7127d63a67b2c2c4178dc645db
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="204---clientparameterinspectorbeforecallinvoked"></a><span data-ttu-id="f1c73-102">204 - ClientParameterInspectorBeforeCallInvoked</span><span class="sxs-lookup"><span data-stu-id="f1c73-102">204 - ClientParameterInspectorBeforeCallInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="f1c73-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="f1c73-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f1c73-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="f1c73-104">ID</span></span>|<span data-ttu-id="f1c73-105">204</span><span class="sxs-lookup"><span data-stu-id="f1c73-105">204</span></span>|  
|<span data-ttu-id="f1c73-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="f1c73-106">Keywords</span></span>|<span data-ttu-id="f1c73-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f1c73-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="f1c73-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="f1c73-108">Level</span></span>|<span data-ttu-id="f1c73-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="f1c73-109">Information</span></span>|  
|<span data-ttu-id="f1c73-110">Канал</span><span class="sxs-lookup"><span data-stu-id="f1c73-110">Channel</span></span>|<span data-ttu-id="f1c73-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="f1c73-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f1c73-112">Описание</span><span class="sxs-lookup"><span data-stu-id="f1c73-112">Description</span></span>  
 <span data-ttu-id="f1c73-113">Это событие создается после того, как модель службы вызывает метод `BeforeCall` для инспектора параметров клиента.</span><span class="sxs-lookup"><span data-stu-id="f1c73-113">This event is emitted after the Service Model has invoked the `BeforeCall` method on a client parameter inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f1c73-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="f1c73-114">Message</span></span>  
 <span data-ttu-id="f1c73-115">Диспетчер вызвал BeforeCall для ClientParameterInspector типа «%1».</span><span class="sxs-lookup"><span data-stu-id="f1c73-115">The Dispatcher invoked 'BeforeCall' on a ClientParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f1c73-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="f1c73-116">Details</span></span>  
  
|<span data-ttu-id="f1c73-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="f1c73-117">Data Item Name</span></span>|<span data-ttu-id="f1c73-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="f1c73-118">Data Item Type</span></span>|<span data-ttu-id="f1c73-119">Описание</span><span class="sxs-lookup"><span data-stu-id="f1c73-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f1c73-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="f1c73-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="f1c73-121">Имя CLR FullName типа вызванного инспектора.</span><span class="sxs-lookup"><span data-stu-id="f1c73-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="f1c73-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="f1c73-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="f1c73-123">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="f1c73-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="f1c73-124">Ее формат определяется как "веб-сайт имя виртуальный путь приложения &#124; Виртуальный путь службы &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="f1c73-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="f1c73-125">Пример: "по умолчанию веб-сайта или CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService ".</span><span class="sxs-lookup"><span data-stu-id="f1c73-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="f1c73-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f1c73-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="f1c73-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="f1c73-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
