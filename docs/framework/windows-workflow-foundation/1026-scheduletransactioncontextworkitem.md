---
title: 1026 - ScheduleTransactionContextWorkItem
ms.date: 03/30/2017
ms.assetid: 0d5f86ba-ec21-4129-a726-5432e425384c
ms.openlocfilehash: 6d0b43208f86c52e8863d4415a64466b0531832c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924635"
---
# <a name="1026---scheduletransactioncontextworkitem"></a><span data-ttu-id="60be3-102">1026 - ScheduleTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="60be3-102">1026 - ScheduleTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="60be3-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="60be3-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="60be3-104">ID</span><span class="sxs-lookup"><span data-stu-id="60be3-104">ID</span></span>|<span data-ttu-id="60be3-105">1026</span><span class="sxs-lookup"><span data-stu-id="60be3-105">1026</span></span>|  
|<span data-ttu-id="60be3-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="60be3-106">Keywords</span></span>|<span data-ttu-id="60be3-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="60be3-107">WFRuntime</span></span>|  
|<span data-ttu-id="60be3-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="60be3-108">Level</span></span>|<span data-ttu-id="60be3-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="60be3-109">Verbose</span></span>|  
|<span data-ttu-id="60be3-110">Канал</span><span class="sxs-lookup"><span data-stu-id="60be3-110">Channel</span></span>|<span data-ttu-id="60be3-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="60be3-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="60be3-112">Описание</span><span class="sxs-lookup"><span data-stu-id="60be3-112">Description</span></span>  
 <span data-ttu-id="60be3-113">Указывает, что TransactionContextWorkItem было запланировано.</span><span class="sxs-lookup"><span data-stu-id="60be3-113">Indicates a TransactionContextWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="60be3-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="60be3-114">Message</span></span>  
 <span data-ttu-id="60be3-115">TransactionContextWorkItem запланирован для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="60be3-115">A TransactionContextWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="60be3-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="60be3-116">Details</span></span>  
  
|<span data-ttu-id="60be3-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="60be3-117">Data Item Name</span></span>|<span data-ttu-id="60be3-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="60be3-118">Data Item Type</span></span>|<span data-ttu-id="60be3-119">Описание</span><span class="sxs-lookup"><span data-stu-id="60be3-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="60be3-120">Действие</span><span class="sxs-lookup"><span data-stu-id="60be3-120">Activity</span></span>|<span data-ttu-id="60be3-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="60be3-121">xs:string</span></span>|<span data-ttu-id="60be3-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="60be3-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="60be3-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="60be3-123">DisplayName</span></span>|<span data-ttu-id="60be3-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="60be3-124">xs:string</span></span>|<span data-ttu-id="60be3-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="60be3-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="60be3-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="60be3-126">InstanceId</span></span>|<span data-ttu-id="60be3-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="60be3-127">xs:string</span></span>|<span data-ttu-id="60be3-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="60be3-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="60be3-129">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="60be3-129">AppDomain</span></span>|<span data-ttu-id="60be3-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="60be3-130">xs:string</span></span>|<span data-ttu-id="60be3-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="60be3-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
