---
title: 1035 - RuntimeTransactionSet
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03b37de9-778c-4beb-b0e3-de73ece6088e
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0fcd6662c0f8899b6830dc8e06cee4f56b5ff906
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="1035---runtimetransactionset"></a><span data-ttu-id="b86bf-102">1035 - RuntimeTransactionSet</span><span class="sxs-lookup"><span data-stu-id="b86bf-102">1035 - RuntimeTransactionSet</span></span>
## <a name="properties"></a><span data-ttu-id="b86bf-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="b86bf-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b86bf-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="b86bf-104">ID</span></span>|<span data-ttu-id="b86bf-105">1035</span><span class="sxs-lookup"><span data-stu-id="b86bf-105">1035</span></span>|  
|<span data-ttu-id="b86bf-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="b86bf-106">Keywords</span></span>|<span data-ttu-id="b86bf-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="b86bf-107">WFRuntime</span></span>|  
|<span data-ttu-id="b86bf-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="b86bf-108">Level</span></span>|<span data-ttu-id="b86bf-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="b86bf-109">Verbose</span></span>|  
|<span data-ttu-id="b86bf-110">Канал</span><span class="sxs-lookup"><span data-stu-id="b86bf-110">Channel</span></span>|<span data-ttu-id="b86bf-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="b86bf-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b86bf-112">Описание</span><span class="sxs-lookup"><span data-stu-id="b86bf-112">Description</span></span>  
 <span data-ttu-id="b86bf-113">Указывает, что действие задало транзакцию среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="b86bf-113">Indicates an activity has set the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b86bf-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="b86bf-114">Message</span></span>  
 <span data-ttu-id="b86bf-115">Транзакция среды выполнения задана элементом действия «%1», DisplayName: «%2», InstanceId: «%3».</span><span class="sxs-lookup"><span data-stu-id="b86bf-115">The runtime transaction has been set by Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="b86bf-116">Выполнение изолировано в элементе Activity «%4», DisplayName: «%5», InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="b86bf-116">Execution isolated to Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b86bf-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="b86bf-117">Details</span></span>  
  
|<span data-ttu-id="b86bf-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="b86bf-118">Data Item Name</span></span>|<span data-ttu-id="b86bf-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="b86bf-119">Data Item Type</span></span>|<span data-ttu-id="b86bf-120">Описание</span><span class="sxs-lookup"><span data-stu-id="b86bf-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b86bf-121">Действие</span><span class="sxs-lookup"><span data-stu-id="b86bf-121">Activity</span></span>|<span data-ttu-id="b86bf-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="b86bf-122">xs:string</span></span>|<span data-ttu-id="b86bf-123">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="b86bf-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="b86bf-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="b86bf-124">DisplayName</span></span>|<span data-ttu-id="b86bf-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="b86bf-125">xs:string</span></span>|<span data-ttu-id="b86bf-126">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="b86bf-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="b86bf-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="b86bf-127">InstanceId</span></span>|<span data-ttu-id="b86bf-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="b86bf-128">xs:string</span></span>|<span data-ttu-id="b86bf-129">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="b86bf-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="b86bf-130">IsolatedActivity</span><span class="sxs-lookup"><span data-stu-id="b86bf-130">IsolatedActivity</span></span>|<span data-ttu-id="b86bf-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="b86bf-131">xs:string</span></span>|<span data-ttu-id="b86bf-132">Имя типа для действия, в котором изолирована транзакция.</span><span class="sxs-lookup"><span data-stu-id="b86bf-132">The type name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="b86bf-133">IsolatedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="b86bf-133">IsolatedActivityDisplayName</span></span>|<span data-ttu-id="b86bf-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="b86bf-134">xs:string</span></span>|<span data-ttu-id="b86bf-135">Имя отображаемого имени действия, в котором изолирована транзакция.</span><span class="sxs-lookup"><span data-stu-id="b86bf-135">The display name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="b86bf-136">IsolatedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="b86bf-136">IsolatedActivityInstanceId</span></span>|<span data-ttu-id="b86bf-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="b86bf-137">xs:string</span></span>|<span data-ttu-id="b86bf-138">Идентификатор экземпляра действия, в котором изолирована транзакция.</span><span class="sxs-lookup"><span data-stu-id="b86bf-138">The instance id of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="b86bf-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b86bf-139">AppDomain</span></span>|<span data-ttu-id="b86bf-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="b86bf-140">xs:string</span></span>|<span data-ttu-id="b86bf-141">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="b86bf-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
