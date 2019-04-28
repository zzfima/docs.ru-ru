---
title: 1017 - ScheduleCancelActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 864546ab-d65c-4989-8fcb-537ba03a3cdd
ms.openlocfilehash: 186b012cdd554ec7dd0d195b460619cca04eddcb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924492"
---
# <a name="1017---schedulecancelactivityworkitem"></a><span data-ttu-id="01ef0-102">1017 - ScheduleCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="01ef0-102">1017 - ScheduleCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="01ef0-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="01ef0-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="01ef0-104">ID</span><span class="sxs-lookup"><span data-stu-id="01ef0-104">ID</span></span>|<span data-ttu-id="01ef0-105">1017</span><span class="sxs-lookup"><span data-stu-id="01ef0-105">1017</span></span>|  
|<span data-ttu-id="01ef0-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="01ef0-106">Keywords</span></span>|<span data-ttu-id="01ef0-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="01ef0-107">WFRuntime</span></span>|  
|<span data-ttu-id="01ef0-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="01ef0-108">Level</span></span>|<span data-ttu-id="01ef0-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="01ef0-109">Verbose</span></span>|  
|<span data-ttu-id="01ef0-110">Канал</span><span class="sxs-lookup"><span data-stu-id="01ef0-110">Channel</span></span>|<span data-ttu-id="01ef0-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="01ef0-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="01ef0-112">Описание</span><span class="sxs-lookup"><span data-stu-id="01ef0-112">Description</span></span>  
 <span data-ttu-id="01ef0-113">Указывает, что элемент CancelActivityWorkItem был запланирован.</span><span class="sxs-lookup"><span data-stu-id="01ef0-113">Indicates a CancelActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="01ef0-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="01ef0-114">Message</span></span>  
 <span data-ttu-id="01ef0-115">CancelActivityWorkItem запланирован для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="01ef0-115">A CancelActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="01ef0-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="01ef0-116">Details</span></span>  
  
|<span data-ttu-id="01ef0-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="01ef0-117">Data Item Name</span></span>|<span data-ttu-id="01ef0-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="01ef0-118">Data Item Type</span></span>|<span data-ttu-id="01ef0-119">Описание</span><span class="sxs-lookup"><span data-stu-id="01ef0-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="01ef0-120">Действие</span><span class="sxs-lookup"><span data-stu-id="01ef0-120">Activity</span></span>|<span data-ttu-id="01ef0-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="01ef0-121">xs:string</span></span>|<span data-ttu-id="01ef0-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="01ef0-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="01ef0-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="01ef0-123">DisplayName</span></span>|<span data-ttu-id="01ef0-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="01ef0-124">xs:string</span></span>|<span data-ttu-id="01ef0-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="01ef0-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="01ef0-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="01ef0-126">InstanceId</span></span>|<span data-ttu-id="01ef0-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="01ef0-127">xs:string</span></span>|<span data-ttu-id="01ef0-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="01ef0-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="01ef0-129">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="01ef0-129">AppDomain</span></span>|<span data-ttu-id="01ef0-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="01ef0-130">xs:string</span></span>|<span data-ttu-id="01ef0-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="01ef0-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
