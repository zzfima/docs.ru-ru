---
title: 1011 - ScheduleExecuteActivityWorkItem
ms.date: 03/30/2017
ms.assetid: e503ae46-ad6b-4fcb-8c0e-146d59a8eff1
ms.openlocfilehash: 299d09b7c4db94a2e27378ba0cc3dfeb03734ab4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="1011---scheduleexecuteactivityworkitem"></a><span data-ttu-id="3cc72-102">1011 - ScheduleExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="3cc72-102">1011 - ScheduleExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="3cc72-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="3cc72-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3cc72-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="3cc72-104">ID</span></span>|<span data-ttu-id="3cc72-105">1011</span><span class="sxs-lookup"><span data-stu-id="3cc72-105">1011</span></span>|  
|<span data-ttu-id="3cc72-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="3cc72-106">Keywords</span></span>|<span data-ttu-id="3cc72-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="3cc72-107">WFRuntime</span></span>|  
|<span data-ttu-id="3cc72-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="3cc72-108">Level</span></span>|<span data-ttu-id="3cc72-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="3cc72-109">Verbose</span></span>|  
|<span data-ttu-id="3cc72-110">Канал</span><span class="sxs-lookup"><span data-stu-id="3cc72-110">Channel</span></span>|<span data-ttu-id="3cc72-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="3cc72-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3cc72-112">Описание</span><span class="sxs-lookup"><span data-stu-id="3cc72-112">Description</span></span>  
 <span data-ttu-id="3cc72-113">Указывает, что элемент ExecuteActivityWorkItem запланирован.</span><span class="sxs-lookup"><span data-stu-id="3cc72-113">Indicates an ExecuteActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3cc72-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="3cc72-114">Message</span></span>  
 <span data-ttu-id="3cc72-115">ExecuteActivityWorkItem запланирован для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="3cc72-115">An ExecuteActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3cc72-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="3cc72-116">Details</span></span>  
  
|<span data-ttu-id="3cc72-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="3cc72-117">Data Item Name</span></span>|<span data-ttu-id="3cc72-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="3cc72-118">Data Item Type</span></span>|<span data-ttu-id="3cc72-119">Описание</span><span class="sxs-lookup"><span data-stu-id="3cc72-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3cc72-120">Действие</span><span class="sxs-lookup"><span data-stu-id="3cc72-120">Activity</span></span>|<span data-ttu-id="3cc72-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="3cc72-121">xs:string</span></span>|<span data-ttu-id="3cc72-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="3cc72-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="3cc72-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="3cc72-123">DisplayName</span></span>|<span data-ttu-id="3cc72-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="3cc72-124">xs:string</span></span>|<span data-ttu-id="3cc72-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="3cc72-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="3cc72-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="3cc72-126">InstanceId</span></span>|<span data-ttu-id="3cc72-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="3cc72-127">xs:string</span></span>|<span data-ttu-id="3cc72-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="3cc72-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="3cc72-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3cc72-129">AppDomain</span></span>|<span data-ttu-id="3cc72-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="3cc72-130">xs:string</span></span>|<span data-ttu-id="3cc72-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="3cc72-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
