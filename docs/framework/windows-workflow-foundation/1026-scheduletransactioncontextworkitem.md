---
title: 1026 - ScheduleTransactionContextWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0d5f86ba-ec21-4129-a726-5432e425384c
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 83c99ddf9c5d4a8fa468303fb198abc349ace6d4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="1026---scheduletransactioncontextworkitem"></a><span data-ttu-id="9a008-102">1026 - ScheduleTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="9a008-102">1026 - ScheduleTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="9a008-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="9a008-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9a008-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="9a008-104">ID</span></span>|<span data-ttu-id="9a008-105">1026</span><span class="sxs-lookup"><span data-stu-id="9a008-105">1026</span></span>|  
|<span data-ttu-id="9a008-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="9a008-106">Keywords</span></span>|<span data-ttu-id="9a008-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="9a008-107">WFRuntime</span></span>|  
|<span data-ttu-id="9a008-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="9a008-108">Level</span></span>|<span data-ttu-id="9a008-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="9a008-109">Verbose</span></span>|  
|<span data-ttu-id="9a008-110">Канал</span><span class="sxs-lookup"><span data-stu-id="9a008-110">Channel</span></span>|<span data-ttu-id="9a008-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="9a008-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9a008-112">Описание</span><span class="sxs-lookup"><span data-stu-id="9a008-112">Description</span></span>  
 <span data-ttu-id="9a008-113">Указывает, что TransactionContextWorkItem было запланировано.</span><span class="sxs-lookup"><span data-stu-id="9a008-113">Indicates a TransactionContextWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9a008-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="9a008-114">Message</span></span>  
 <span data-ttu-id="9a008-115">TransactionContextWorkItem запланирован для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="9a008-115">A TransactionContextWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9a008-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="9a008-116">Details</span></span>  
  
|<span data-ttu-id="9a008-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="9a008-117">Data Item Name</span></span>|<span data-ttu-id="9a008-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="9a008-118">Data Item Type</span></span>|<span data-ttu-id="9a008-119">Описание</span><span class="sxs-lookup"><span data-stu-id="9a008-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9a008-120">Действие</span><span class="sxs-lookup"><span data-stu-id="9a008-120">Activity</span></span>|<span data-ttu-id="9a008-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="9a008-121">xs:string</span></span>|<span data-ttu-id="9a008-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="9a008-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="9a008-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="9a008-123">DisplayName</span></span>|<span data-ttu-id="9a008-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="9a008-124">xs:string</span></span>|<span data-ttu-id="9a008-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="9a008-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="9a008-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="9a008-126">InstanceId</span></span>|<span data-ttu-id="9a008-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="9a008-127">xs:string</span></span>|<span data-ttu-id="9a008-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="9a008-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="9a008-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="9a008-129">AppDomain</span></span>|<span data-ttu-id="9a008-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="9a008-130">xs:string</span></span>|<span data-ttu-id="9a008-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="9a008-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
