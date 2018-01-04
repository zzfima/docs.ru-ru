---
title: 201 - ClientMessageInspectorAfterReceiveInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9ff637f1-cc26-4400-ab9b-546f70e5057d
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 213808824051c812717e1e5b1f379be63824e255
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="201---clientmessageinspectorafterreceiveinvoked"></a><span data-ttu-id="73a90-102">201 - ClientMessageInspectorAfterReceiveInvoked</span><span class="sxs-lookup"><span data-stu-id="73a90-102">201 - ClientMessageInspectorAfterReceiveInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="73a90-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="73a90-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="73a90-104">ID</span><span class="sxs-lookup"><span data-stu-id="73a90-104">ID</span></span>|<span data-ttu-id="73a90-105">201</span><span class="sxs-lookup"><span data-stu-id="73a90-105">201</span></span>|  
|<span data-ttu-id="73a90-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="73a90-106">Keywords</span></span>|<span data-ttu-id="73a90-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="73a90-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="73a90-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="73a90-108">Level</span></span>|<span data-ttu-id="73a90-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="73a90-109">Information</span></span>|  
|<span data-ttu-id="73a90-110">Канал</span><span class="sxs-lookup"><span data-stu-id="73a90-110">Channel</span></span>|<span data-ttu-id="73a90-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="73a90-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="73a90-112">Описание:</span><span class="sxs-lookup"><span data-stu-id="73a90-112">Description</span></span>  
 <span data-ttu-id="73a90-113">Это событие создается после того, как модель службы вызывает метод `AfterReceiveReply` для инспектора сообщений клиента.</span><span class="sxs-lookup"><span data-stu-id="73a90-113">This event is emitted after the Service Model has invoked the `AfterReceiveReply` method on a client message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="73a90-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="73a90-114">Message</span></span>  
 <span data-ttu-id="73a90-115">Диспетчер вызвал AfterReceiveReply относительно ClientMessageInspector типа «%1».</span><span class="sxs-lookup"><span data-stu-id="73a90-115">The Dispatcher invoked 'AfterReceiveReply' on a ClientMessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="73a90-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="73a90-116">Details</span></span>  
  
|<span data-ttu-id="73a90-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="73a90-117">Data Item Name</span></span>|<span data-ttu-id="73a90-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="73a90-118">Data Item Type</span></span>|<span data-ttu-id="73a90-119">Описание</span><span class="sxs-lookup"><span data-stu-id="73a90-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="73a90-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="73a90-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="73a90-121">Имя CLR FullName типа вызванного инспектора.</span><span class="sxs-lookup"><span data-stu-id="73a90-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="73a90-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="73a90-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="73a90-123">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="73a90-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="73a90-124">Ее формат определяется как "веб-сайт имя виртуальный путь приложения &#124; Виртуальный путь службы &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="73a90-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="73a90-125">Пример: "по умолчанию веб-сайта или CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService ".</span><span class="sxs-lookup"><span data-stu-id="73a90-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="73a90-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="73a90-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="73a90-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="73a90-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
