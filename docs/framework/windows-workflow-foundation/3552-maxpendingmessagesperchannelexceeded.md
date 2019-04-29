---
title: 3552 – MaxPendingMessagesPerChannelExceeded
ms.date: 03/30/2017
ms.assetid: fc8309d9-eb3a-4636-a6f0-dd0018c1361d
ms.openlocfilehash: a163ed216cbdfbf2b9d77d25979733d6bdb121d3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945942"
---
# <a name="3552---maxpendingmessagesperchannelexceeded"></a><span data-ttu-id="4287d-102">3552 – MaxPendingMessagesPerChannelExceeded</span><span class="sxs-lookup"><span data-stu-id="4287d-102">3552 - MaxPendingMessagesPerChannelExceeded</span></span>
## <a name="properties"></a><span data-ttu-id="4287d-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="4287d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4287d-104">ID</span><span class="sxs-lookup"><span data-stu-id="4287d-104">ID</span></span>|<span data-ttu-id="4287d-105">3552</span><span class="sxs-lookup"><span data-stu-id="4287d-105">3552</span></span>|  
|<span data-ttu-id="4287d-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="4287d-106">Keywords</span></span>|<span data-ttu-id="4287d-107">Quota, WFServices</span><span class="sxs-lookup"><span data-stu-id="4287d-107">Quota, WFServices</span></span>|  
|<span data-ttu-id="4287d-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="4287d-108">Level</span></span>|<span data-ttu-id="4287d-109">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="4287d-109">Warning</span></span>|  
|<span data-ttu-id="4287d-110">Канал</span><span class="sxs-lookup"><span data-stu-id="4287d-110">Channel</span></span>|<span data-ttu-id="4287d-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="4287d-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4287d-112">Описание</span><span class="sxs-lookup"><span data-stu-id="4287d-112">Description</span></span>  
 <span data-ttu-id="4287d-113">Указывает, что был достигнут предел регулирования «MaxPendingMessagesPerChannel».</span><span class="sxs-lookup"><span data-stu-id="4287d-113">Indicates the throttle 'MaxPendingMessagesPerChannel' limit was hit.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4287d-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="4287d-114">Message</span></span>  
 <span data-ttu-id="4287d-115">Регулирования «MaxPendingMessagesPerChannel» ограничение «%1» был нажат.</span><span class="sxs-lookup"><span data-stu-id="4287d-115">The throttle 'MaxPendingMessagesPerChannel' limit of  '%1' was hit.</span></span> <span data-ttu-id="4287d-116">Для увеличения этого предела настройте свойство MaxPendingMessagesPerChannel для поведения BufferedReceiveServiceBehavior.</span><span class="sxs-lookup"><span data-stu-id="4287d-116">To increase this limit, adjust the MaxPendingMessagesPerChannel property on BufferedReceiveServiceBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4287d-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="4287d-117">Details</span></span>  
  
|<span data-ttu-id="4287d-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="4287d-118">Data Item Name</span></span>|<span data-ttu-id="4287d-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="4287d-119">Data Item Type</span></span>|<span data-ttu-id="4287d-120">Описание</span><span class="sxs-lookup"><span data-stu-id="4287d-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4287d-121">Limit</span><span class="sxs-lookup"><span data-stu-id="4287d-121">Limit</span></span>|<span data-ttu-id="4287d-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="4287d-122">xs:string</span></span>|<span data-ttu-id="4287d-123">Был достигнут предел регулирования «MaxPendingMessagesPerChannel».</span><span class="sxs-lookup"><span data-stu-id="4287d-123">The limit of the MaxPendingMessagesPerChannel throttle.</span></span>|  
|<span data-ttu-id="4287d-124">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="4287d-124">AppDomain</span></span>|<span data-ttu-id="4287d-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="4287d-125">xs:string</span></span>|<span data-ttu-id="4287d-126">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="4287d-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
