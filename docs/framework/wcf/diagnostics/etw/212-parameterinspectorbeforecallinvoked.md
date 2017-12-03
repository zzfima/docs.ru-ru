---
title: 212 - ParameterInspectorBeforeCallInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 063fc8d2-ceac-4c18-8368-de84f2c78035
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 64dcdb3a928d2ec05cd7dac557b6db10cb4a6511
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="212---parameterinspectorbeforecallinvoked"></a><span data-ttu-id="224c0-102">212 - ParameterInspectorBeforeCallInvoked</span><span class="sxs-lookup"><span data-stu-id="224c0-102">212 - ParameterInspectorBeforeCallInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="224c0-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="224c0-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="224c0-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="224c0-104">ID</span></span>|<span data-ttu-id="224c0-105">212</span><span class="sxs-lookup"><span data-stu-id="224c0-105">212</span></span>|  
|<span data-ttu-id="224c0-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="224c0-106">Keywords</span></span>|<span data-ttu-id="224c0-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="224c0-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="224c0-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="224c0-108">Level</span></span>|<span data-ttu-id="224c0-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="224c0-109">Information</span></span>|  
|<span data-ttu-id="224c0-110">Канал</span><span class="sxs-lookup"><span data-stu-id="224c0-110">Channel</span></span>|<span data-ttu-id="224c0-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="224c0-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="224c0-112">Описание</span><span class="sxs-lookup"><span data-stu-id="224c0-112">Description</span></span>  
 <span data-ttu-id="224c0-113">Это событие создается после того, как модель службы вызывает метод `BeforeCall` для `ParameterInspector`.</span><span class="sxs-lookup"><span data-stu-id="224c0-113">This event is emitted after the Service Model has invoked the `BeforeCall` method on a `ParameterInspector`.</span></span>  
  
## <a name="message"></a><span data-ttu-id="224c0-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="224c0-114">Message</span></span>  
 <span data-ttu-id="224c0-115">Диспетчер вызвал BeforeCall для ParameterInspector типа «%1».</span><span class="sxs-lookup"><span data-stu-id="224c0-115">The Dispatcher invoked 'BeforeCall' on a ParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="224c0-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="224c0-116">Details</span></span>  
  
|<span data-ttu-id="224c0-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="224c0-117">Data Item Name</span></span>|<span data-ttu-id="224c0-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="224c0-118">Data Item Type</span></span>|<span data-ttu-id="224c0-119">Описание</span><span class="sxs-lookup"><span data-stu-id="224c0-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="224c0-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="224c0-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="224c0-121">Имя CLR FullName типа вызванного инспектора.</span><span class="sxs-lookup"><span data-stu-id="224c0-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="224c0-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="224c0-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="224c0-123">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="224c0-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="224c0-124">Ее формат определяется как "веб-сайт имя виртуальный путь приложения &#124; Виртуальный путь службы &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="224c0-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="224c0-125">Пример: "по умолчанию веб-сайта или CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService ".</span><span class="sxs-lookup"><span data-stu-id="224c0-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="224c0-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="224c0-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="224c0-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="224c0-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
