---
title: 1026 - ScheduleTransactionContextWorkItem
ms.date: 03/30/2017
ms.assetid: 0d5f86ba-ec21-4129-a726-5432e425384c
ms.openlocfilehash: 6d0b43208f86c52e8863d4415a64466b0531832c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="1026---scheduletransactioncontextworkitem"></a><span data-ttu-id="56be9-102">1026 - ScheduleTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="56be9-102">1026 - ScheduleTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="56be9-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="56be9-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="56be9-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="56be9-104">ID</span></span>|<span data-ttu-id="56be9-105">1026</span><span class="sxs-lookup"><span data-stu-id="56be9-105">1026</span></span>|  
|<span data-ttu-id="56be9-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="56be9-106">Keywords</span></span>|<span data-ttu-id="56be9-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="56be9-107">WFRuntime</span></span>|  
|<span data-ttu-id="56be9-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="56be9-108">Level</span></span>|<span data-ttu-id="56be9-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="56be9-109">Verbose</span></span>|  
|<span data-ttu-id="56be9-110">Канал</span><span class="sxs-lookup"><span data-stu-id="56be9-110">Channel</span></span>|<span data-ttu-id="56be9-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="56be9-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="56be9-112">Описание</span><span class="sxs-lookup"><span data-stu-id="56be9-112">Description</span></span>  
 <span data-ttu-id="56be9-113">Указывает, что TransactionContextWorkItem было запланировано.</span><span class="sxs-lookup"><span data-stu-id="56be9-113">Indicates a TransactionContextWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="56be9-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="56be9-114">Message</span></span>  
 <span data-ttu-id="56be9-115">TransactionContextWorkItem запланирован для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="56be9-115">A TransactionContextWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="56be9-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="56be9-116">Details</span></span>  
  
|<span data-ttu-id="56be9-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="56be9-117">Data Item Name</span></span>|<span data-ttu-id="56be9-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="56be9-118">Data Item Type</span></span>|<span data-ttu-id="56be9-119">Описание</span><span class="sxs-lookup"><span data-stu-id="56be9-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="56be9-120">Действие</span><span class="sxs-lookup"><span data-stu-id="56be9-120">Activity</span></span>|<span data-ttu-id="56be9-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="56be9-121">xs:string</span></span>|<span data-ttu-id="56be9-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="56be9-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="56be9-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="56be9-123">DisplayName</span></span>|<span data-ttu-id="56be9-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="56be9-124">xs:string</span></span>|<span data-ttu-id="56be9-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="56be9-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="56be9-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="56be9-126">InstanceId</span></span>|<span data-ttu-id="56be9-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="56be9-127">xs:string</span></span>|<span data-ttu-id="56be9-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="56be9-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="56be9-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="56be9-129">AppDomain</span></span>|<span data-ttu-id="56be9-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="56be9-130">xs:string</span></span>|<span data-ttu-id="56be9-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="56be9-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
