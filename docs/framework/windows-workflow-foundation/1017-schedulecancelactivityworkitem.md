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
ms.workload: dotnet
ms.openlocfilehash: b524f083c49f517c21c77da4f1d1488625a575b8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="1017---schedulecancelactivityworkitem"></a><span data-ttu-id="d57b6-102">1017 - ScheduleCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="d57b6-102">1017 - ScheduleCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="d57b6-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="d57b6-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d57b6-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="d57b6-104">ID</span></span>|<span data-ttu-id="d57b6-105">1017</span><span class="sxs-lookup"><span data-stu-id="d57b6-105">1017</span></span>|  
|<span data-ttu-id="d57b6-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="d57b6-106">Keywords</span></span>|<span data-ttu-id="d57b6-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="d57b6-107">WFRuntime</span></span>|  
|<span data-ttu-id="d57b6-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="d57b6-108">Level</span></span>|<span data-ttu-id="d57b6-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="d57b6-109">Verbose</span></span>|  
|<span data-ttu-id="d57b6-110">Канал</span><span class="sxs-lookup"><span data-stu-id="d57b6-110">Channel</span></span>|<span data-ttu-id="d57b6-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="d57b6-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d57b6-112">Описание</span><span class="sxs-lookup"><span data-stu-id="d57b6-112">Description</span></span>  
 <span data-ttu-id="d57b6-113">Указывает, что элемент CancelActivityWorkItem был запланирован.</span><span class="sxs-lookup"><span data-stu-id="d57b6-113">Indicates a CancelActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d57b6-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="d57b6-114">Message</span></span>  
 <span data-ttu-id="d57b6-115">CancelActivityWorkItem запланирован для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="d57b6-115">A CancelActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d57b6-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="d57b6-116">Details</span></span>  
  
|<span data-ttu-id="d57b6-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="d57b6-117">Data Item Name</span></span>|<span data-ttu-id="d57b6-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="d57b6-118">Data Item Type</span></span>|<span data-ttu-id="d57b6-119">Описание</span><span class="sxs-lookup"><span data-stu-id="d57b6-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d57b6-120">Действие</span><span class="sxs-lookup"><span data-stu-id="d57b6-120">Activity</span></span>|<span data-ttu-id="d57b6-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="d57b6-121">xs:string</span></span>|<span data-ttu-id="d57b6-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="d57b6-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="d57b6-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="d57b6-123">DisplayName</span></span>|<span data-ttu-id="d57b6-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="d57b6-124">xs:string</span></span>|<span data-ttu-id="d57b6-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="d57b6-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="d57b6-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="d57b6-126">InstanceId</span></span>|<span data-ttu-id="d57b6-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="d57b6-127">xs:string</span></span>|<span data-ttu-id="d57b6-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="d57b6-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="d57b6-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d57b6-129">AppDomain</span></span>|<span data-ttu-id="d57b6-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="d57b6-130">xs:string</span></span>|<span data-ttu-id="d57b6-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="d57b6-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
