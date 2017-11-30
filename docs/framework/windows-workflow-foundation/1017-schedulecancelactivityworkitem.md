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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c6d348ec18b4d5eff7156d1e9809eb793ac1681d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="1017---schedulecancelactivityworkitem"></a><span data-ttu-id="8f32e-102">1017 - ScheduleCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="8f32e-102">1017 - ScheduleCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="8f32e-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="8f32e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8f32e-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="8f32e-104">ID</span></span>|<span data-ttu-id="8f32e-105">1017</span><span class="sxs-lookup"><span data-stu-id="8f32e-105">1017</span></span>|  
|<span data-ttu-id="8f32e-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="8f32e-106">Keywords</span></span>|<span data-ttu-id="8f32e-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="8f32e-107">WFRuntime</span></span>|  
|<span data-ttu-id="8f32e-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="8f32e-108">Level</span></span>|<span data-ttu-id="8f32e-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="8f32e-109">Verbose</span></span>|  
|<span data-ttu-id="8f32e-110">Канал</span><span class="sxs-lookup"><span data-stu-id="8f32e-110">Channel</span></span>|<span data-ttu-id="8f32e-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="8f32e-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8f32e-112">Описание</span><span class="sxs-lookup"><span data-stu-id="8f32e-112">Description</span></span>  
 <span data-ttu-id="8f32e-113">Указывает, что элемент CancelActivityWorkItem был запланирован.</span><span class="sxs-lookup"><span data-stu-id="8f32e-113">Indicates a CancelActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8f32e-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="8f32e-114">Message</span></span>  
 <span data-ttu-id="8f32e-115">CancelActivityWorkItem запланирован для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="8f32e-115">A CancelActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8f32e-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="8f32e-116">Details</span></span>  
  
|<span data-ttu-id="8f32e-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="8f32e-117">Data Item Name</span></span>|<span data-ttu-id="8f32e-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="8f32e-118">Data Item Type</span></span>|<span data-ttu-id="8f32e-119">Описание</span><span class="sxs-lookup"><span data-stu-id="8f32e-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8f32e-120">Действие</span><span class="sxs-lookup"><span data-stu-id="8f32e-120">Activity</span></span>|<span data-ttu-id="8f32e-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="8f32e-121">xs:string</span></span>|<span data-ttu-id="8f32e-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="8f32e-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="8f32e-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="8f32e-123">DisplayName</span></span>|<span data-ttu-id="8f32e-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="8f32e-124">xs:string</span></span>|<span data-ttu-id="8f32e-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="8f32e-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="8f32e-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="8f32e-126">InstanceId</span></span>|<span data-ttu-id="8f32e-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="8f32e-127">xs:string</span></span>|<span data-ttu-id="8f32e-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="8f32e-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="8f32e-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8f32e-129">AppDomain</span></span>|<span data-ttu-id="8f32e-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="8f32e-130">xs:string</span></span>|<span data-ttu-id="8f32e-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="8f32e-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
