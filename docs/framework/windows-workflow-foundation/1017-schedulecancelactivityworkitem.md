---
title: 1017 - ScheduleCancelActivityWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 864546ab-d65c-4989-8fcb-537ba03a3cdd
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a632d59ddd75b375ff5e828a9f35aeecb0118f1c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="1017---schedulecancelactivityworkitem"></a><span data-ttu-id="bd5c2-102">1017 - ScheduleCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="bd5c2-102">1017 - ScheduleCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="bd5c2-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="bd5c2-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bd5c2-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="bd5c2-104">ID</span></span>|<span data-ttu-id="bd5c2-105">1017</span><span class="sxs-lookup"><span data-stu-id="bd5c2-105">1017</span></span>|  
|<span data-ttu-id="bd5c2-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="bd5c2-106">Keywords</span></span>|<span data-ttu-id="bd5c2-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="bd5c2-107">WFRuntime</span></span>|  
|<span data-ttu-id="bd5c2-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="bd5c2-108">Level</span></span>|<span data-ttu-id="bd5c2-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="bd5c2-109">Verbose</span></span>|  
|<span data-ttu-id="bd5c2-110">Канал</span><span class="sxs-lookup"><span data-stu-id="bd5c2-110">Channel</span></span>|<span data-ttu-id="bd5c2-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="bd5c2-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="bd5c2-112">Описание</span><span class="sxs-lookup"><span data-stu-id="bd5c2-112">Description</span></span>  
 <span data-ttu-id="bd5c2-113">Указывает, что элемент CancelActivityWorkItem был запланирован.</span><span class="sxs-lookup"><span data-stu-id="bd5c2-113">Indicates a CancelActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="bd5c2-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="bd5c2-114">Message</span></span>  
 <span data-ttu-id="bd5c2-115">CancelActivityWorkItem запланирован для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="bd5c2-115">A CancelActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="bd5c2-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="bd5c2-116">Details</span></span>  
  
|<span data-ttu-id="bd5c2-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="bd5c2-117">Data Item Name</span></span>|<span data-ttu-id="bd5c2-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="bd5c2-118">Data Item Type</span></span>|<span data-ttu-id="bd5c2-119">Описание</span><span class="sxs-lookup"><span data-stu-id="bd5c2-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="bd5c2-120">Действие</span><span class="sxs-lookup"><span data-stu-id="bd5c2-120">Activity</span></span>|<span data-ttu-id="bd5c2-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="bd5c2-121">xs:string</span></span>|<span data-ttu-id="bd5c2-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="bd5c2-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="bd5c2-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="bd5c2-123">DisplayName</span></span>|<span data-ttu-id="bd5c2-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="bd5c2-124">xs:string</span></span>|<span data-ttu-id="bd5c2-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="bd5c2-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="bd5c2-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="bd5c2-126">InstanceId</span></span>|<span data-ttu-id="bd5c2-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="bd5c2-127">xs:string</span></span>|<span data-ttu-id="bd5c2-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="bd5c2-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="bd5c2-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="bd5c2-129">AppDomain</span></span>|<span data-ttu-id="bd5c2-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="bd5c2-130">xs:string</span></span>|<span data-ttu-id="bd5c2-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="bd5c2-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
