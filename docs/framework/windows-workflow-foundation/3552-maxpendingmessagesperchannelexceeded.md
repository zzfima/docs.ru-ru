---
title: 3552 – MaxPendingMessagesPerChannelExceeded
ms.date: 03/30/2017
ms.assetid: fc8309d9-eb3a-4636-a6f0-dd0018c1361d
ms.openlocfilehash: a163ed216cbdfbf2b9d77d25979733d6bdb121d3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="3552---maxpendingmessagesperchannelexceeded"></a><span data-ttu-id="4e7b7-102">3552 – MaxPendingMessagesPerChannelExceeded</span><span class="sxs-lookup"><span data-stu-id="4e7b7-102">3552 - MaxPendingMessagesPerChannelExceeded</span></span>
## <a name="properties"></a><span data-ttu-id="4e7b7-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="4e7b7-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4e7b7-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="4e7b7-104">ID</span></span>|<span data-ttu-id="4e7b7-105">3552</span><span class="sxs-lookup"><span data-stu-id="4e7b7-105">3552</span></span>|  
|<span data-ttu-id="4e7b7-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="4e7b7-106">Keywords</span></span>|<span data-ttu-id="4e7b7-107">Quota, WFServices</span><span class="sxs-lookup"><span data-stu-id="4e7b7-107">Quota, WFServices</span></span>|  
|<span data-ttu-id="4e7b7-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="4e7b7-108">Level</span></span>|<span data-ttu-id="4e7b7-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="4e7b7-109">Warning</span></span>|  
|<span data-ttu-id="4e7b7-110">Канал</span><span class="sxs-lookup"><span data-stu-id="4e7b7-110">Channel</span></span>|<span data-ttu-id="4e7b7-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="4e7b7-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4e7b7-112">Описание</span><span class="sxs-lookup"><span data-stu-id="4e7b7-112">Description</span></span>  
 <span data-ttu-id="4e7b7-113">Указывает, что был достигнут предел регулирования «MaxPendingMessagesPerChannel».</span><span class="sxs-lookup"><span data-stu-id="4e7b7-113">Indicates the throttle 'MaxPendingMessagesPerChannel' limit was hit.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4e7b7-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="4e7b7-114">Message</span></span>  
 <span data-ttu-id="4e7b7-115">Был достигнут предел регулирования «MaxPendingMessagesPerChannel» «% 1».</span><span class="sxs-lookup"><span data-stu-id="4e7b7-115">The throttle 'MaxPendingMessagesPerChannel' limit of  '%1' was hit.</span></span> <span data-ttu-id="4e7b7-116">Для увеличения этого предела настройте свойство MaxPendingMessagesPerChannel для поведения BufferedReceiveServiceBehavior.</span><span class="sxs-lookup"><span data-stu-id="4e7b7-116">To increase this limit, adjust the MaxPendingMessagesPerChannel property on BufferedReceiveServiceBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4e7b7-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="4e7b7-117">Details</span></span>  
  
|<span data-ttu-id="4e7b7-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="4e7b7-118">Data Item Name</span></span>|<span data-ttu-id="4e7b7-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="4e7b7-119">Data Item Type</span></span>|<span data-ttu-id="4e7b7-120">Описание</span><span class="sxs-lookup"><span data-stu-id="4e7b7-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4e7b7-121">Limit</span><span class="sxs-lookup"><span data-stu-id="4e7b7-121">Limit</span></span>|<span data-ttu-id="4e7b7-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="4e7b7-122">xs:string</span></span>|<span data-ttu-id="4e7b7-123">Был достигнут предел регулирования «MaxPendingMessagesPerChannel».</span><span class="sxs-lookup"><span data-stu-id="4e7b7-123">The limit of the MaxPendingMessagesPerChannel throttle.</span></span>|  
|<span data-ttu-id="4e7b7-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4e7b7-124">AppDomain</span></span>|<span data-ttu-id="4e7b7-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="4e7b7-125">xs:string</span></span>|<span data-ttu-id="4e7b7-126">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="4e7b7-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
