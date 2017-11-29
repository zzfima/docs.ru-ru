---
title: 1018 - StartCancelActivityWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 68b4fa1d-eee6-4a2a-8c16-7e9d89f08ab9
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f74a133a685699bcefc014269a9ecb3ebea4e505
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="1018---startcancelactivityworkitem"></a><span data-ttu-id="e2db0-102">1018 - StartCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="e2db0-102">1018 - StartCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="e2db0-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="e2db0-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e2db0-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="e2db0-104">ID</span></span>|<span data-ttu-id="e2db0-105">1018</span><span class="sxs-lookup"><span data-stu-id="e2db0-105">1018</span></span>|  
|<span data-ttu-id="e2db0-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="e2db0-106">Keywords</span></span>|<span data-ttu-id="e2db0-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="e2db0-107">WFRuntime</span></span>|  
|<span data-ttu-id="e2db0-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="e2db0-108">Level</span></span>|<span data-ttu-id="e2db0-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="e2db0-109">Verbose</span></span>|  
|<span data-ttu-id="e2db0-110">Канал</span><span class="sxs-lookup"><span data-stu-id="e2db0-110">Channel</span></span>|<span data-ttu-id="e2db0-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="e2db0-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e2db0-112">Описание</span><span class="sxs-lookup"><span data-stu-id="e2db0-112">Description</span></span>  
 <span data-ttu-id="e2db0-113">Указывает, что CancelActivityWorkItem начинает выполнение.</span><span class="sxs-lookup"><span data-stu-id="e2db0-113">Indicates a CancelActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e2db0-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="e2db0-114">Message</span></span>  
 <span data-ttu-id="e2db0-115">Начато выполнение CancelActivityWorkItem для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="e2db0-115">Starting execution of a CancelActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e2db0-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="e2db0-116">Details</span></span>  
  
|<span data-ttu-id="e2db0-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="e2db0-117">Data Item Name</span></span>|<span data-ttu-id="e2db0-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="e2db0-118">Data Item Type</span></span>|<span data-ttu-id="e2db0-119">Описание</span><span class="sxs-lookup"><span data-stu-id="e2db0-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e2db0-120">Действие</span><span class="sxs-lookup"><span data-stu-id="e2db0-120">Activity</span></span>|<span data-ttu-id="e2db0-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="e2db0-121">xs:string</span></span>|<span data-ttu-id="e2db0-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="e2db0-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="e2db0-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="e2db0-123">DisplayName</span></span>|<span data-ttu-id="e2db0-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="e2db0-124">xs:string</span></span>|<span data-ttu-id="e2db0-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="e2db0-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="e2db0-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="e2db0-126">InstanceId</span></span>|<span data-ttu-id="e2db0-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="e2db0-127">xs:string</span></span>|<span data-ttu-id="e2db0-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="e2db0-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="e2db0-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e2db0-129">AppDomain</span></span>|<span data-ttu-id="e2db0-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="e2db0-130">xs:string</span></span>|<span data-ttu-id="e2db0-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="e2db0-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
