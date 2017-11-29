---
title: 1019 - CompleteCancelActivityWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 75a4a1ab-e5a3-4f4e-88e4-d19806e671d7
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9f8af4486d4659afd4c98016a6f88719271f1a1b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="1019---completecancelactivityworkitem"></a><span data-ttu-id="76f81-102">1019 - CompleteCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="76f81-102">1019 - CompleteCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="76f81-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="76f81-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="76f81-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="76f81-104">ID</span></span>|<span data-ttu-id="76f81-105">1019</span><span class="sxs-lookup"><span data-stu-id="76f81-105">1019</span></span>|  
|<span data-ttu-id="76f81-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="76f81-106">Keywords</span></span>|<span data-ttu-id="76f81-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="76f81-107">WFRuntime</span></span>|  
|<span data-ttu-id="76f81-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="76f81-108">Level</span></span>|<span data-ttu-id="76f81-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="76f81-109">Verbose</span></span>|  
|<span data-ttu-id="76f81-110">Канал</span><span class="sxs-lookup"><span data-stu-id="76f81-110">Channel</span></span>|<span data-ttu-id="76f81-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="76f81-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="76f81-112">Описание</span><span class="sxs-lookup"><span data-stu-id="76f81-112">Description</span></span>  
 <span data-ttu-id="76f81-113">Указывает, что CancelActivityWorkItem завершено.</span><span class="sxs-lookup"><span data-stu-id="76f81-113">Indicates a CancelActivityWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="76f81-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="76f81-114">Message</span></span>  
 <span data-ttu-id="76f81-115">CancelActivityWorkItem завершен для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="76f81-115">A CancelActivityWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="76f81-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="76f81-116">Details</span></span>  
  
|<span data-ttu-id="76f81-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="76f81-117">Data Item Name</span></span>|<span data-ttu-id="76f81-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="76f81-118">Data Item Type</span></span>|<span data-ttu-id="76f81-119">Описание</span><span class="sxs-lookup"><span data-stu-id="76f81-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="76f81-120">Действие</span><span class="sxs-lookup"><span data-stu-id="76f81-120">Activity</span></span>|<span data-ttu-id="76f81-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="76f81-121">xs:string</span></span>|<span data-ttu-id="76f81-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="76f81-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="76f81-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="76f81-123">DisplayName</span></span>|<span data-ttu-id="76f81-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="76f81-124">xs:string</span></span>|<span data-ttu-id="76f81-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="76f81-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="76f81-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="76f81-126">InstanceId</span></span>|<span data-ttu-id="76f81-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="76f81-127">xs:string</span></span>|<span data-ttu-id="76f81-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="76f81-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="76f81-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="76f81-129">AppDomain</span></span>|<span data-ttu-id="76f81-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="76f81-130">xs:string</span></span>|<span data-ttu-id="76f81-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="76f81-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
