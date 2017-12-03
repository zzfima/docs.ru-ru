---
title: "3552 – MaxPendingMessagesPerChannelExceeded"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc8309d9-eb3a-4636-a6f0-dd0018c1361d
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5455472a5b9ebdba7aea7d0384ce9cd4a9a2849d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="3552---maxpendingmessagesperchannelexceeded"></a><span data-ttu-id="0aadb-102">3552 – MaxPendingMessagesPerChannelExceeded</span><span class="sxs-lookup"><span data-stu-id="0aadb-102">3552 - MaxPendingMessagesPerChannelExceeded</span></span>
## <a name="properties"></a><span data-ttu-id="0aadb-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="0aadb-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0aadb-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="0aadb-104">ID</span></span>|<span data-ttu-id="0aadb-105">3552</span><span class="sxs-lookup"><span data-stu-id="0aadb-105">3552</span></span>|  
|<span data-ttu-id="0aadb-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="0aadb-106">Keywords</span></span>|<span data-ttu-id="0aadb-107">Quota, WFServices</span><span class="sxs-lookup"><span data-stu-id="0aadb-107">Quota, WFServices</span></span>|  
|<span data-ttu-id="0aadb-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="0aadb-108">Level</span></span>|<span data-ttu-id="0aadb-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="0aadb-109">Warning</span></span>|  
|<span data-ttu-id="0aadb-110">Канал</span><span class="sxs-lookup"><span data-stu-id="0aadb-110">Channel</span></span>|<span data-ttu-id="0aadb-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="0aadb-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0aadb-112">Описание</span><span class="sxs-lookup"><span data-stu-id="0aadb-112">Description</span></span>  
 <span data-ttu-id="0aadb-113">Указывает, что был достигнут предел регулирования «MaxPendingMessagesPerChannel».</span><span class="sxs-lookup"><span data-stu-id="0aadb-113">Indicates the throttle 'MaxPendingMessagesPerChannel' limit was hit.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0aadb-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="0aadb-114">Message</span></span>  
 <span data-ttu-id="0aadb-115">Был достигнут предел регулирования «MaxPendingMessagesPerChannel» «% 1».</span><span class="sxs-lookup"><span data-stu-id="0aadb-115">The throttle 'MaxPendingMessagesPerChannel' limit of  '%1' was hit.</span></span> <span data-ttu-id="0aadb-116">Для увеличения этого предела настройте свойство MaxPendingMessagesPerChannel для поведения BufferedReceiveServiceBehavior.</span><span class="sxs-lookup"><span data-stu-id="0aadb-116">To increase this limit, adjust the MaxPendingMessagesPerChannel property on BufferedReceiveServiceBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0aadb-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="0aadb-117">Details</span></span>  
  
|<span data-ttu-id="0aadb-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="0aadb-118">Data Item Name</span></span>|<span data-ttu-id="0aadb-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="0aadb-119">Data Item Type</span></span>|<span data-ttu-id="0aadb-120">Описание</span><span class="sxs-lookup"><span data-stu-id="0aadb-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0aadb-121">Limit</span><span class="sxs-lookup"><span data-stu-id="0aadb-121">Limit</span></span>|<span data-ttu-id="0aadb-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="0aadb-122">xs:string</span></span>|<span data-ttu-id="0aadb-123">Был достигнут предел регулирования «MaxPendingMessagesPerChannel».</span><span class="sxs-lookup"><span data-stu-id="0aadb-123">The limit of the MaxPendingMessagesPerChannel throttle.</span></span>|  
|<span data-ttu-id="0aadb-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0aadb-124">AppDomain</span></span>|<span data-ttu-id="0aadb-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="0aadb-125">xs:string</span></span>|<span data-ttu-id="0aadb-126">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="0aadb-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
