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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c3fcd93dbc30b20f7822a54babde8277e32d8335
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="1035---runtimetransactionset"></a><span data-ttu-id="ed58d-102">1035 - RuntimeTransactionSet</span><span class="sxs-lookup"><span data-stu-id="ed58d-102">1035 - RuntimeTransactionSet</span></span>
## <a name="properties"></a><span data-ttu-id="ed58d-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="ed58d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ed58d-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="ed58d-104">ID</span></span>|<span data-ttu-id="ed58d-105">1035</span><span class="sxs-lookup"><span data-stu-id="ed58d-105">1035</span></span>|  
|<span data-ttu-id="ed58d-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ed58d-106">Keywords</span></span>|<span data-ttu-id="ed58d-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="ed58d-107">WFRuntime</span></span>|  
|<span data-ttu-id="ed58d-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="ed58d-108">Level</span></span>|<span data-ttu-id="ed58d-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="ed58d-109">Verbose</span></span>|  
|<span data-ttu-id="ed58d-110">Канал</span><span class="sxs-lookup"><span data-stu-id="ed58d-110">Channel</span></span>|<span data-ttu-id="ed58d-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="ed58d-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ed58d-112">Описание</span><span class="sxs-lookup"><span data-stu-id="ed58d-112">Description</span></span>  
 <span data-ttu-id="ed58d-113">Указывает, что действие задало транзакцию среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="ed58d-113">Indicates an activity has set the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ed58d-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="ed58d-114">Message</span></span>  
 <span data-ttu-id="ed58d-115">Транзакция среды выполнения задана элементом действия «%1», DisplayName: «%2», InstanceId: «%3».</span><span class="sxs-lookup"><span data-stu-id="ed58d-115">The runtime transaction has been set by Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="ed58d-116">Выполнение изолировано в элементе Activity «%4», DisplayName: «%5», InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="ed58d-116">Execution isolated to Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ed58d-117">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="ed58d-117">Details</span></span>  
  
|<span data-ttu-id="ed58d-118">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="ed58d-118">Data Item Name</span></span>|<span data-ttu-id="ed58d-119">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="ed58d-119">Data Item Type</span></span>|<span data-ttu-id="ed58d-120">Описание</span><span class="sxs-lookup"><span data-stu-id="ed58d-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ed58d-121">Действие</span><span class="sxs-lookup"><span data-stu-id="ed58d-121">Activity</span></span>|<span data-ttu-id="ed58d-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="ed58d-122">xs:string</span></span>|<span data-ttu-id="ed58d-123">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="ed58d-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="ed58d-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="ed58d-124">DisplayName</span></span>|<span data-ttu-id="ed58d-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="ed58d-125">xs:string</span></span>|<span data-ttu-id="ed58d-126">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="ed58d-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="ed58d-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="ed58d-127">InstanceId</span></span>|<span data-ttu-id="ed58d-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="ed58d-128">xs:string</span></span>|<span data-ttu-id="ed58d-129">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="ed58d-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="ed58d-130">IsolatedActivity</span><span class="sxs-lookup"><span data-stu-id="ed58d-130">IsolatedActivity</span></span>|<span data-ttu-id="ed58d-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="ed58d-131">xs:string</span></span>|<span data-ttu-id="ed58d-132">Имя типа для действия, в котором изолирована транзакция.</span><span class="sxs-lookup"><span data-stu-id="ed58d-132">The type name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="ed58d-133">IsolatedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="ed58d-133">IsolatedActivityDisplayName</span></span>|<span data-ttu-id="ed58d-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="ed58d-134">xs:string</span></span>|<span data-ttu-id="ed58d-135">Имя отображаемого имени действия, в котором изолирована транзакция.</span><span class="sxs-lookup"><span data-stu-id="ed58d-135">The display name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="ed58d-136">IsolatedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="ed58d-136">IsolatedActivityInstanceId</span></span>|<span data-ttu-id="ed58d-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="ed58d-137">xs:string</span></span>|<span data-ttu-id="ed58d-138">Идентификатор экземпляра действия, в котором изолирована транзакция.</span><span class="sxs-lookup"><span data-stu-id="ed58d-138">The instance id of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="ed58d-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ed58d-139">AppDomain</span></span>|<span data-ttu-id="ed58d-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="ed58d-140">xs:string</span></span>|<span data-ttu-id="ed58d-141">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="ed58d-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
