---
title: 1032 - ScheduleRuntimeWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 54688101-becf-42f3-80ca-f53a7b527620
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 81cc73a5ab58e90f1a0ee5bdaf9a491d20206fb3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="1032---scheduleruntimeworkitem"></a><span data-ttu-id="8b5be-102">1032 - ScheduleRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="8b5be-102">1032 - ScheduleRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="8b5be-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="8b5be-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8b5be-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="8b5be-104">ID</span></span>|<span data-ttu-id="8b5be-105">1032</span><span class="sxs-lookup"><span data-stu-id="8b5be-105">1032</span></span>|  
|<span data-ttu-id="8b5be-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="8b5be-106">Keywords</span></span>|<span data-ttu-id="8b5be-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="8b5be-107">WFRuntime</span></span>|  
|<span data-ttu-id="8b5be-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="8b5be-108">Level</span></span>|<span data-ttu-id="8b5be-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="8b5be-109">Verbose</span></span>|  
|<span data-ttu-id="8b5be-110">Канал</span><span class="sxs-lookup"><span data-stu-id="8b5be-110">Channel</span></span>|<span data-ttu-id="8b5be-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="8b5be-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8b5be-112">Описание</span><span class="sxs-lookup"><span data-stu-id="8b5be-112">Description</span></span>  
 <span data-ttu-id="8b5be-113">Указывает, что элемент RuntimeWorkItem был запланирован.</span><span class="sxs-lookup"><span data-stu-id="8b5be-113">Indicates a RuntimeWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8b5be-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="8b5be-114">Message</span></span>  
 <span data-ttu-id="8b5be-115">Рабочий элемент среды выполнения запланирован для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="8b5be-115">A runtime work item has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8b5be-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="8b5be-116">Details</span></span>  
  
|<span data-ttu-id="8b5be-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="8b5be-117">Data Item Name</span></span>|<span data-ttu-id="8b5be-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="8b5be-118">Data Item Type</span></span>|<span data-ttu-id="8b5be-119">Описание</span><span class="sxs-lookup"><span data-stu-id="8b5be-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8b5be-120">Действие</span><span class="sxs-lookup"><span data-stu-id="8b5be-120">Activity</span></span>|<span data-ttu-id="8b5be-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="8b5be-121">xs:string</span></span>|<span data-ttu-id="8b5be-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="8b5be-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="8b5be-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="8b5be-123">DisplayName</span></span>|<span data-ttu-id="8b5be-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="8b5be-124">xs:string</span></span>|<span data-ttu-id="8b5be-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="8b5be-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="8b5be-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="8b5be-126">InstanceId</span></span>|<span data-ttu-id="8b5be-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="8b5be-127">xs:string</span></span>|<span data-ttu-id="8b5be-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="8b5be-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="8b5be-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8b5be-129">AppDomain</span></span>|<span data-ttu-id="8b5be-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="8b5be-130">xs:string</span></span>|<span data-ttu-id="8b5be-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="8b5be-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
