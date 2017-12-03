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
ms.openlocfilehash: 7cb6d243177700daa1e653c394e027a6f5428371
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="201---clientmessageinspectorafterreceiveinvoked"></a><span data-ttu-id="38a23-102">201 - ClientMessageInspectorAfterReceiveInvoked</span><span class="sxs-lookup"><span data-stu-id="38a23-102">201 - ClientMessageInspectorAfterReceiveInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="38a23-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="38a23-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="38a23-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="38a23-104">ID</span></span>|<span data-ttu-id="38a23-105">201</span><span class="sxs-lookup"><span data-stu-id="38a23-105">201</span></span>|  
|<span data-ttu-id="38a23-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="38a23-106">Keywords</span></span>|<span data-ttu-id="38a23-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="38a23-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="38a23-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="38a23-108">Level</span></span>|<span data-ttu-id="38a23-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="38a23-109">Information</span></span>|  
|<span data-ttu-id="38a23-110">Канал</span><span class="sxs-lookup"><span data-stu-id="38a23-110">Channel</span></span>|<span data-ttu-id="38a23-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="38a23-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="38a23-112">Описание</span><span class="sxs-lookup"><span data-stu-id="38a23-112">Description</span></span>  
 <span data-ttu-id="38a23-113">Это событие создается после того, как модель службы вызывает метод `AfterReceiveReply` для инспектора сообщений клиента.</span><span class="sxs-lookup"><span data-stu-id="38a23-113">This event is emitted after the Service Model has invoked the `AfterReceiveReply` method on a client message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="38a23-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="38a23-114">Message</span></span>  
 <span data-ttu-id="38a23-115">Диспетчер вызвал AfterReceiveReply относительно ClientMessageInspector типа «%1».</span><span class="sxs-lookup"><span data-stu-id="38a23-115">The Dispatcher invoked 'AfterReceiveReply' on a ClientMessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="38a23-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="38a23-116">Details</span></span>  
  
|<span data-ttu-id="38a23-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="38a23-117">Data Item Name</span></span>|<span data-ttu-id="38a23-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="38a23-118">Data Item Type</span></span>|<span data-ttu-id="38a23-119">Описание</span><span class="sxs-lookup"><span data-stu-id="38a23-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="38a23-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="38a23-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="38a23-121">Имя CLR FullName типа вызванного инспектора.</span><span class="sxs-lookup"><span data-stu-id="38a23-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="38a23-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="38a23-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="38a23-123">Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии.</span><span class="sxs-lookup"><span data-stu-id="38a23-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="38a23-124">Ее формат определяется как "веб-сайт имя виртуальный путь приложения &#124; Виртуальный путь службы &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="38a23-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="38a23-125">Пример: "по умолчанию веб-сайта или CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService ".</span><span class="sxs-lookup"><span data-stu-id="38a23-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="38a23-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="38a23-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="38a23-127">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="38a23-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
