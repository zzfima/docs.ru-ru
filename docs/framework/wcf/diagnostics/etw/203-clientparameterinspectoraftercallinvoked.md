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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b736d9e2827708caea54fbe230b0b638492adb96
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="203---clientparameterinspectoraftercallinvoked"></a><span data-ttu-id="8bc40-102">203 - ClientParameterInspectorAfterCallInvoked</span><span class="sxs-lookup"><span data-stu-id="8bc40-102">203 - ClientParameterInspectorAfterCallInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="8bc40-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="8bc40-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8bc40-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="8bc40-104">ID</span></span>|<span data-ttu-id="8bc40-105">203</span><span class="sxs-lookup"><span data-stu-id="8bc40-105">203</span></span>|  
|<span data-ttu-id="8bc40-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="8bc40-106">Keywords</span></span>|<span data-ttu-id="8bc40-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="8bc40-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="8bc40-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="8bc40-108">Level</span></span>|<span data-ttu-id="8bc40-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="8bc40-109">Information</span></span>|  
|<span data-ttu-id="8bc40-110">Канал</span><span class="sxs-lookup"><span data-stu-id="8bc40-110">Channel</span></span>|<span data-ttu-id="8bc40-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="8bc40-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8bc40-112">Описание</span><span class="sxs-lookup"><span data-stu-id="8bc40-112">Description</span></span>  
 <span data-ttu-id="8bc40-113">Это событие создается после того, как модель службы вызывает метод `AfterCall` для инспектора параметров клиента.</span><span class="sxs-lookup"><span data-stu-id="8bc40-113">This event is emitted after the Service Model has invoked the `AfterCall` method on a client parameter inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8bc40-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="8bc40-114">Message</span></span>  
 <span data-ttu-id="8bc40-115">Диспетчер вызвал «AfterCall» для ClientParameterInspector типа «%1».</span><span class="sxs-lookup"><span data-stu-id="8bc40-115">The Dispatcher invoked 'AfterCall' on a ClientParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8bc40-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="8bc40-116">Details</span></span>  
  
|<span data-ttu-id="8bc40-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="8bc40-117">Data Item Name</span></span>|<span data-ttu-id="8bc40-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="8bc40-118">Data Item Type</span></span>|<span data-ttu-id="8bc40-119">Описание</span><span class="sxs-lookup"><span data-stu-id="8bc40-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8bc40-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="8bc40-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="8bc40-121">Имя CLR FullName типа вызванного инспектора.</span><span class="sxs-lookup"><span data-stu-id="8bc40-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="8bc40-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="8bc40-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="8bc40-123">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="8bc40-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="8bc40-124">Ее формат определяется как "веб-сайт имя виртуальный путь приложения &#124; Виртуальный путь службы &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="8bc40-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="8bc40-125">Пример: "по умолчанию веб-сайта или CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService ".</span><span class="sxs-lookup"><span data-stu-id="8bc40-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="8bc40-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8bc40-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="8bc40-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="8bc40-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
