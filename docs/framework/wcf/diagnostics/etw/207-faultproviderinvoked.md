---
title: 207 - FaultProviderInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b730d903-01c2-4deb-85a4-da12f8a21fe4
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: fe3698653be04119c84c5f423207458e9d033dc1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="207---faultproviderinvoked"></a><span data-ttu-id="96c06-102">207 - FaultProviderInvoked</span><span class="sxs-lookup"><span data-stu-id="96c06-102">207 - FaultProviderInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="96c06-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="96c06-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="96c06-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="96c06-104">ID</span></span>|<span data-ttu-id="96c06-105">207</span><span class="sxs-lookup"><span data-stu-id="96c06-105">207</span></span>|  
|<span data-ttu-id="96c06-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="96c06-106">Keywords</span></span>|<span data-ttu-id="96c06-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="96c06-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="96c06-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="96c06-108">Level</span></span>|<span data-ttu-id="96c06-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="96c06-109">Information</span></span>|  
|<span data-ttu-id="96c06-110">Канал</span><span class="sxs-lookup"><span data-stu-id="96c06-110">Channel</span></span>|<span data-ttu-id="96c06-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="96c06-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="96c06-112">Описание</span><span class="sxs-lookup"><span data-stu-id="96c06-112">Description</span></span>  
 <span data-ttu-id="96c06-113">Это событие создается после вызова `FaultProvider`.</span><span class="sxs-lookup"><span data-stu-id="96c06-113">This event is emitted after a `FaultProvider` has been invoked.</span></span>  
  
## <a name="message"></a><span data-ttu-id="96c06-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="96c06-114">Message</span></span>  
 <span data-ttu-id="96c06-115">Диспетчер вызвал FaultProvider типа «%1» с исключением типа «%2».</span><span class="sxs-lookup"><span data-stu-id="96c06-115">The Dispatcher invoked a FaultProvider of type '%1' with an exception of type '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="96c06-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="96c06-116">Details</span></span>  
  
|<span data-ttu-id="96c06-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="96c06-117">Data Item Name</span></span>|<span data-ttu-id="96c06-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="96c06-118">Data Item Type</span></span>|<span data-ttu-id="96c06-119">Описание</span><span class="sxs-lookup"><span data-stu-id="96c06-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="96c06-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="96c06-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="96c06-121">Имя CLR FullName типа вызванного инспектора `FaultProvider`.</span><span class="sxs-lookup"><span data-stu-id="96c06-121">The CLR FullName of the type of the invoked `FaultProvider`.</span></span>|  
|<span data-ttu-id="96c06-122">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="96c06-122">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="96c06-123">Имя CLR FullName исключения, обработанного `FaultProvider`.</span><span class="sxs-lookup"><span data-stu-id="96c06-123">The CLR FullName of the exception that the `FaultProvider` has operated on.</span></span>|  
|<span data-ttu-id="96c06-124">HostReference</span><span class="sxs-lookup"><span data-stu-id="96c06-124">HostReference</span></span>|`xs:string`|<span data-ttu-id="96c06-125">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="96c06-125">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="96c06-126">Ее формат определяется как "веб-сайт имя виртуальный путь приложения &#124; Виртуальный путь службы &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="96c06-126">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="96c06-127">Пример: "по умолчанию веб-сайта или CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService ".</span><span class="sxs-lookup"><span data-stu-id="96c06-127">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="96c06-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="96c06-128">AppDomain</span></span>|`xs:string`|<span data-ttu-id="96c06-129">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="96c06-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
