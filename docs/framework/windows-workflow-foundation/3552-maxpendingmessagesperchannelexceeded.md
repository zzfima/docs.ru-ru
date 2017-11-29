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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5ba5e4aa8e1338321838e40db7d976107315ef64
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="3552---maxpendingmessagesperchannelexceeded"></a><span data-ttu-id="b81ea-102">3552 – MaxPendingMessagesPerChannelExceeded</span><span class="sxs-lookup"><span data-stu-id="b81ea-102">3552 - MaxPendingMessagesPerChannelExceeded</span></span>
## <a name="properties"></a><span data-ttu-id="b81ea-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="b81ea-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b81ea-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="b81ea-104">ID</span></span>|<span data-ttu-id="b81ea-105">3552</span><span class="sxs-lookup"><span data-stu-id="b81ea-105">3552</span></span>|  
|<span data-ttu-id="b81ea-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="b81ea-106">Keywords</span></span>|<span data-ttu-id="b81ea-107">Quota, WFServices</span><span class="sxs-lookup"><span data-stu-id="b81ea-107">Quota, WFServices</span></span>|  
|<span data-ttu-id="b81ea-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="b81ea-108">Level</span></span>|<span data-ttu-id="b81ea-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="b81ea-109">Warning</span></span>|  
|<span data-ttu-id="b81ea-110">Канал</span><span class="sxs-lookup"><span data-stu-id="b81ea-110">Channel</span></span>|<span data-ttu-id="b81ea-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="b81ea-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b81ea-112">Описание</span><span class="sxs-lookup"><span data-stu-id="b81ea-112">Description</span></span>  
 <span data-ttu-id="b81ea-113">Указывает, что был достигнут предел регулирования «MaxPendingMessagesPerChannel».</span><span class="sxs-lookup"><span data-stu-id="b81ea-113">Indicates the throttle 'MaxPendingMessagesPerChannel' limit was hit.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b81ea-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="b81ea-114">Message</span></span>  
 <span data-ttu-id="b81ea-115">Был достигнут предел регулирования «MaxPendingMessagesPerChannel» «% 1».</span><span class="sxs-lookup"><span data-stu-id="b81ea-115">The throttle 'MaxPendingMessagesPerChannel' limit of  '%1' was hit.</span></span> <span data-ttu-id="b81ea-116">Для увеличения этого предела настройте свойство MaxPendingMessagesPerChannel для поведения BufferedReceiveServiceBehavior.</span><span class="sxs-lookup"><span data-stu-id="b81ea-116">To increase this limit, adjust the MaxPendingMessagesPerChannel property on BufferedReceiveServiceBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b81ea-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="b81ea-117">Details</span></span>  
  
|<span data-ttu-id="b81ea-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="b81ea-118">Data Item Name</span></span>|<span data-ttu-id="b81ea-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="b81ea-119">Data Item Type</span></span>|<span data-ttu-id="b81ea-120">Описание</span><span class="sxs-lookup"><span data-stu-id="b81ea-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b81ea-121">Limit</span><span class="sxs-lookup"><span data-stu-id="b81ea-121">Limit</span></span>|<span data-ttu-id="b81ea-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="b81ea-122">xs:string</span></span>|<span data-ttu-id="b81ea-123">Был достигнут предел регулирования «MaxPendingMessagesPerChannel».</span><span class="sxs-lookup"><span data-stu-id="b81ea-123">The limit of the MaxPendingMessagesPerChannel throttle.</span></span>|  
|<span data-ttu-id="b81ea-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b81ea-124">AppDomain</span></span>|<span data-ttu-id="b81ea-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="b81ea-125">xs:string</span></span>|<span data-ttu-id="b81ea-126">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="b81ea-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
