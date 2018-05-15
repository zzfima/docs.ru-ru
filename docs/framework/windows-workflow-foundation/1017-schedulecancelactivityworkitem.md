---
title: 1017 - ScheduleCancelActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 864546ab-d65c-4989-8fcb-537ba03a3cdd
ms.openlocfilehash: 186b012cdd554ec7dd0d195b460619cca04eddcb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="1017---schedulecancelactivityworkitem"></a><span data-ttu-id="14a61-102">1017 - ScheduleCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="14a61-102">1017 - ScheduleCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="14a61-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="14a61-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="14a61-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="14a61-104">ID</span></span>|<span data-ttu-id="14a61-105">1017</span><span class="sxs-lookup"><span data-stu-id="14a61-105">1017</span></span>|  
|<span data-ttu-id="14a61-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="14a61-106">Keywords</span></span>|<span data-ttu-id="14a61-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="14a61-107">WFRuntime</span></span>|  
|<span data-ttu-id="14a61-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="14a61-108">Level</span></span>|<span data-ttu-id="14a61-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="14a61-109">Verbose</span></span>|  
|<span data-ttu-id="14a61-110">Канал</span><span class="sxs-lookup"><span data-stu-id="14a61-110">Channel</span></span>|<span data-ttu-id="14a61-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="14a61-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="14a61-112">Описание</span><span class="sxs-lookup"><span data-stu-id="14a61-112">Description</span></span>  
 <span data-ttu-id="14a61-113">Указывает, что элемент CancelActivityWorkItem был запланирован.</span><span class="sxs-lookup"><span data-stu-id="14a61-113">Indicates a CancelActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="14a61-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="14a61-114">Message</span></span>  
 <span data-ttu-id="14a61-115">CancelActivityWorkItem запланирован для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="14a61-115">A CancelActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="14a61-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="14a61-116">Details</span></span>  
  
|<span data-ttu-id="14a61-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="14a61-117">Data Item Name</span></span>|<span data-ttu-id="14a61-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="14a61-118">Data Item Type</span></span>|<span data-ttu-id="14a61-119">Описание</span><span class="sxs-lookup"><span data-stu-id="14a61-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="14a61-120">Действие</span><span class="sxs-lookup"><span data-stu-id="14a61-120">Activity</span></span>|<span data-ttu-id="14a61-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="14a61-121">xs:string</span></span>|<span data-ttu-id="14a61-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="14a61-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="14a61-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="14a61-123">DisplayName</span></span>|<span data-ttu-id="14a61-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="14a61-124">xs:string</span></span>|<span data-ttu-id="14a61-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="14a61-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="14a61-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="14a61-126">InstanceId</span></span>|<span data-ttu-id="14a61-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="14a61-127">xs:string</span></span>|<span data-ttu-id="14a61-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="14a61-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="14a61-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="14a61-129">AppDomain</span></span>|<span data-ttu-id="14a61-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="14a61-130">xs:string</span></span>|<span data-ttu-id="14a61-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="14a61-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
