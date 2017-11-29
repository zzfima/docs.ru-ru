---
title: 211 - ParameterInspectorAfterCallInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c0e21297-10b8-4456-a0e1-e019145cd5ac
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a66941a9b505267e976620bed238b02440968f14
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="211---parameterinspectoraftercallinvoked"></a><span data-ttu-id="ebbd5-102">211 - ParameterInspectorAfterCallInvoked</span><span class="sxs-lookup"><span data-stu-id="ebbd5-102">211 - ParameterInspectorAfterCallInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="ebbd5-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="ebbd5-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ebbd5-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="ebbd5-104">ID</span></span>|<span data-ttu-id="ebbd5-105">211</span><span class="sxs-lookup"><span data-stu-id="ebbd5-105">211</span></span>|  
|<span data-ttu-id="ebbd5-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ebbd5-106">Keywords</span></span>|<span data-ttu-id="ebbd5-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ebbd5-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="ebbd5-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="ebbd5-108">Level</span></span>|<span data-ttu-id="ebbd5-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="ebbd5-109">Information</span></span>|  
|<span data-ttu-id="ebbd5-110">Канал</span><span class="sxs-lookup"><span data-stu-id="ebbd5-110">Channel</span></span>|<span data-ttu-id="ebbd5-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="ebbd5-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ebbd5-112">Описание</span><span class="sxs-lookup"><span data-stu-id="ebbd5-112">Description</span></span>  
 <span data-ttu-id="ebbd5-113">Это событие создается после того, как модель службы вызывает метод `AfterCall` для `ParameterInspector`.</span><span class="sxs-lookup"><span data-stu-id="ebbd5-113">This event is emitted after the Service Model has invoked the `AfterCall` method on a `ParameterInspector`.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ebbd5-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="ebbd5-114">Message</span></span>  
 <span data-ttu-id="ebbd5-115">Диспетчер вызвал AfterCall относительно ParameterInspector типа «%1».</span><span class="sxs-lookup"><span data-stu-id="ebbd5-115">The Dispatcher invoked 'AfterCall' on a ParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ebbd5-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="ebbd5-116">Details</span></span>  
  
|<span data-ttu-id="ebbd5-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="ebbd5-117">Data Item Name</span></span>|<span data-ttu-id="ebbd5-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="ebbd5-118">Data Item Type</span></span>|<span data-ttu-id="ebbd5-119">Описание</span><span class="sxs-lookup"><span data-stu-id="ebbd5-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ebbd5-120">Имя типа</span><span class="sxs-lookup"><span data-stu-id="ebbd5-120">Type Name</span></span>|`xs:string`|<span data-ttu-id="ebbd5-121">Имя CLR FullName типа вызванного инспектора `ParameterInspector`.</span><span class="sxs-lookup"><span data-stu-id="ebbd5-121">The CLR FullName of the type of the invoked `ParameterInspector`.</span></span>|  
|<span data-ttu-id="ebbd5-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="ebbd5-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="ebbd5-123">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="ebbd5-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="ebbd5-124">Ее формат определяется как "веб-сайт имя виртуальный путь приложения &#124; Виртуальный путь службы &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="ebbd5-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="ebbd5-125">Пример: "по умолчанию веб-сайта или CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService ".</span><span class="sxs-lookup"><span data-stu-id="ebbd5-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="ebbd5-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ebbd5-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="ebbd5-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="ebbd5-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
