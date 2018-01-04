---
title: 1028 - CompleteTransactionContextWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 95423f9d-d29a-460e-bcd8-096e80af5bd0
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3cd2ee443d6c521f168a170a1079eb4e9657e2dc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="1028---completetransactioncontextworkitem"></a><span data-ttu-id="e83de-102">1028 - CompleteTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="e83de-102">1028 - CompleteTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="e83de-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="e83de-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e83de-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="e83de-104">ID</span></span>|<span data-ttu-id="e83de-105">1028</span><span class="sxs-lookup"><span data-stu-id="e83de-105">1028</span></span>|  
|<span data-ttu-id="e83de-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="e83de-106">Keywords</span></span>|<span data-ttu-id="e83de-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="e83de-107">WFRuntime</span></span>|  
|<span data-ttu-id="e83de-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="e83de-108">Level</span></span>|<span data-ttu-id="e83de-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="e83de-109">Verbose</span></span>|  
|<span data-ttu-id="e83de-110">Канал</span><span class="sxs-lookup"><span data-stu-id="e83de-110">Channel</span></span>|<span data-ttu-id="e83de-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="e83de-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e83de-112">Описание</span><span class="sxs-lookup"><span data-stu-id="e83de-112">Description</span></span>  
 <span data-ttu-id="e83de-113">Указывает на завершение TransactionContextWorkItem.</span><span class="sxs-lookup"><span data-stu-id="e83de-113">Indicates a TransactionContextWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e83de-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="e83de-114">Message</span></span>  
 <span data-ttu-id="e83de-115">TransactionContextWorkItem завершен для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="e83de-115">A TransactionContextWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e83de-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="e83de-116">Details</span></span>  
  
|<span data-ttu-id="e83de-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="e83de-117">Data Item Name</span></span>|<span data-ttu-id="e83de-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="e83de-118">Data Item Type</span></span>|<span data-ttu-id="e83de-119">Описание</span><span class="sxs-lookup"><span data-stu-id="e83de-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e83de-120">Действие</span><span class="sxs-lookup"><span data-stu-id="e83de-120">Activity</span></span>|<span data-ttu-id="e83de-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="e83de-121">xs:string</span></span>|<span data-ttu-id="e83de-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="e83de-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="e83de-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="e83de-123">DisplayName</span></span>|<span data-ttu-id="e83de-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="e83de-124">xs:string</span></span>|<span data-ttu-id="e83de-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="e83de-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="e83de-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="e83de-126">InstanceId</span></span>|<span data-ttu-id="e83de-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="e83de-127">xs:string</span></span>|<span data-ttu-id="e83de-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="e83de-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="e83de-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e83de-129">AppDomain</span></span>|<span data-ttu-id="e83de-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="e83de-130">xs:string</span></span>|<span data-ttu-id="e83de-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="e83de-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
