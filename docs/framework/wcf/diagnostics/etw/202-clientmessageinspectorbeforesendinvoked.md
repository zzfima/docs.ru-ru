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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: baf466bf63dcb9335a20eed8b563c222e09c7055
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="202---clientmessageinspectorbeforesendinvoked"></a><span data-ttu-id="80fec-102">202 - ClientMessageInspectorBeforeSendInvoked</span><span class="sxs-lookup"><span data-stu-id="80fec-102">202 - ClientMessageInspectorBeforeSendInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="80fec-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="80fec-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="80fec-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="80fec-104">ID</span></span>|<span data-ttu-id="80fec-105">202</span><span class="sxs-lookup"><span data-stu-id="80fec-105">202</span></span>|  
|<span data-ttu-id="80fec-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="80fec-106">Keywords</span></span>|<span data-ttu-id="80fec-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="80fec-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="80fec-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="80fec-108">Level</span></span>|<span data-ttu-id="80fec-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="80fec-109">Information</span></span>|  
|<span data-ttu-id="80fec-110">Канал</span><span class="sxs-lookup"><span data-stu-id="80fec-110">Channel</span></span>|<span data-ttu-id="80fec-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="80fec-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="80fec-112">Описание</span><span class="sxs-lookup"><span data-stu-id="80fec-112">Description</span></span>  
 <span data-ttu-id="80fec-113">Это событие создается после того, как модель службы вызывает метод `BeforeSendRequest` для инспектора сообщений клиента.</span><span class="sxs-lookup"><span data-stu-id="80fec-113">This event is emitted after the Service Model has invoked the `BeforeSendRequest` method on a client message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="80fec-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="80fec-114">Message</span></span>  
 <span data-ttu-id="80fec-115">Диспетчер вызвал BeforeSendRequest для ClientMessageInspector типа «%1».</span><span class="sxs-lookup"><span data-stu-id="80fec-115">The Dispatcher invoked 'BeforeSendRequest' on a ClientMessageInspector of type  '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="80fec-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="80fec-116">Details</span></span>  
  
|<span data-ttu-id="80fec-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="80fec-117">Data Item Name</span></span>|<span data-ttu-id="80fec-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="80fec-118">Data Item Type</span></span>|<span data-ttu-id="80fec-119">Описание</span><span class="sxs-lookup"><span data-stu-id="80fec-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="80fec-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="80fec-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="80fec-121">Имя CLR FullName типа вызванного инспектора.</span><span class="sxs-lookup"><span data-stu-id="80fec-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="80fec-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="80fec-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="80fec-123">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="80fec-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="80fec-124">Ее формат определяется как "веб-сайт имя виртуальный путь приложения &#124; Виртуальный путь службы &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="80fec-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="80fec-125">Пример: "по умолчанию веб-сайта или CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService ".</span><span class="sxs-lookup"><span data-stu-id="80fec-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="80fec-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="80fec-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="80fec-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="80fec-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
