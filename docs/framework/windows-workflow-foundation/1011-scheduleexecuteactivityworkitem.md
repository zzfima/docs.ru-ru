---
title: 1011 - ScheduleExecuteActivityWorkItem
ms.date: 03/30/2017
ms.assetid: e503ae46-ad6b-4fcb-8c0e-146d59a8eff1
ms.openlocfilehash: 299d09b7c4db94a2e27378ba0cc3dfeb03734ab4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61982258"
---
# <a name="1011---scheduleexecuteactivityworkitem"></a><span data-ttu-id="0dac1-102">1011 - ScheduleExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="0dac1-102">1011 - ScheduleExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="0dac1-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="0dac1-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0dac1-104">ID</span><span class="sxs-lookup"><span data-stu-id="0dac1-104">ID</span></span>|<span data-ttu-id="0dac1-105">1011</span><span class="sxs-lookup"><span data-stu-id="0dac1-105">1011</span></span>|  
|<span data-ttu-id="0dac1-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="0dac1-106">Keywords</span></span>|<span data-ttu-id="0dac1-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="0dac1-107">WFRuntime</span></span>|  
|<span data-ttu-id="0dac1-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="0dac1-108">Level</span></span>|<span data-ttu-id="0dac1-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="0dac1-109">Verbose</span></span>|  
|<span data-ttu-id="0dac1-110">Канал</span><span class="sxs-lookup"><span data-stu-id="0dac1-110">Channel</span></span>|<span data-ttu-id="0dac1-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="0dac1-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0dac1-112">Описание</span><span class="sxs-lookup"><span data-stu-id="0dac1-112">Description</span></span>  
 <span data-ttu-id="0dac1-113">Указывает, что элемент ExecuteActivityWorkItem запланирован.</span><span class="sxs-lookup"><span data-stu-id="0dac1-113">Indicates an ExecuteActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0dac1-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="0dac1-114">Message</span></span>  
 <span data-ttu-id="0dac1-115">ExecuteActivityWorkItem запланирован для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="0dac1-115">An ExecuteActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0dac1-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="0dac1-116">Details</span></span>  
  
|<span data-ttu-id="0dac1-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="0dac1-117">Data Item Name</span></span>|<span data-ttu-id="0dac1-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="0dac1-118">Data Item Type</span></span>|<span data-ttu-id="0dac1-119">Описание</span><span class="sxs-lookup"><span data-stu-id="0dac1-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0dac1-120">Действие</span><span class="sxs-lookup"><span data-stu-id="0dac1-120">Activity</span></span>|<span data-ttu-id="0dac1-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="0dac1-121">xs:string</span></span>|<span data-ttu-id="0dac1-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="0dac1-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="0dac1-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="0dac1-123">DisplayName</span></span>|<span data-ttu-id="0dac1-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="0dac1-124">xs:string</span></span>|<span data-ttu-id="0dac1-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="0dac1-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="0dac1-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="0dac1-126">InstanceId</span></span>|<span data-ttu-id="0dac1-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="0dac1-127">xs:string</span></span>|<span data-ttu-id="0dac1-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="0dac1-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="0dac1-129">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="0dac1-129">AppDomain</span></span>|<span data-ttu-id="0dac1-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="0dac1-130">xs:string</span></span>|<span data-ttu-id="0dac1-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="0dac1-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
