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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4d881f1be4e809cf45f100b966d6013ae8fa88f9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="1026---scheduletransactioncontextworkitem"></a><span data-ttu-id="08151-102">1026 - ScheduleTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="08151-102">1026 - ScheduleTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="08151-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="08151-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="08151-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="08151-104">ID</span></span>|<span data-ttu-id="08151-105">1026</span><span class="sxs-lookup"><span data-stu-id="08151-105">1026</span></span>|  
|<span data-ttu-id="08151-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="08151-106">Keywords</span></span>|<span data-ttu-id="08151-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="08151-107">WFRuntime</span></span>|  
|<span data-ttu-id="08151-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="08151-108">Level</span></span>|<span data-ttu-id="08151-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="08151-109">Verbose</span></span>|  
|<span data-ttu-id="08151-110">Канал</span><span class="sxs-lookup"><span data-stu-id="08151-110">Channel</span></span>|<span data-ttu-id="08151-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="08151-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="08151-112">Описание</span><span class="sxs-lookup"><span data-stu-id="08151-112">Description</span></span>  
 <span data-ttu-id="08151-113">Указывает, что TransactionContextWorkItem было запланировано.</span><span class="sxs-lookup"><span data-stu-id="08151-113">Indicates a TransactionContextWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="08151-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="08151-114">Message</span></span>  
 <span data-ttu-id="08151-115">TransactionContextWorkItem запланирован для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="08151-115">A TransactionContextWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="08151-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="08151-116">Details</span></span>  
  
|<span data-ttu-id="08151-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="08151-117">Data Item Name</span></span>|<span data-ttu-id="08151-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="08151-118">Data Item Type</span></span>|<span data-ttu-id="08151-119">Описание</span><span class="sxs-lookup"><span data-stu-id="08151-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="08151-120">Действие</span><span class="sxs-lookup"><span data-stu-id="08151-120">Activity</span></span>|<span data-ttu-id="08151-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="08151-121">xs:string</span></span>|<span data-ttu-id="08151-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="08151-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="08151-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="08151-123">DisplayName</span></span>|<span data-ttu-id="08151-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="08151-124">xs:string</span></span>|<span data-ttu-id="08151-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="08151-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="08151-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="08151-126">InstanceId</span></span>|<span data-ttu-id="08151-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="08151-127">xs:string</span></span>|<span data-ttu-id="08151-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="08151-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="08151-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="08151-129">AppDomain</span></span>|<span data-ttu-id="08151-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="08151-130">xs:string</span></span>|<span data-ttu-id="08151-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="08151-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
