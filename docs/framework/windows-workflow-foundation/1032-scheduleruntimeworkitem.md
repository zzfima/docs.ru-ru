---
title: 1032 - ScheduleRuntimeWorkItem
ms.date: 03/30/2017
ms.assetid: 54688101-becf-42f3-80ca-f53a7b527620
ms.openlocfilehash: 505b852d54e256b2c2bfff8d90944dd4e993e0c0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510251"
---
# <a name="1032---scheduleruntimeworkitem"></a><span data-ttu-id="6dd33-102">1032 - ScheduleRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="6dd33-102">1032 - ScheduleRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="6dd33-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="6dd33-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6dd33-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="6dd33-104">ID</span></span>|<span data-ttu-id="6dd33-105">1032</span><span class="sxs-lookup"><span data-stu-id="6dd33-105">1032</span></span>|  
|<span data-ttu-id="6dd33-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="6dd33-106">Keywords</span></span>|<span data-ttu-id="6dd33-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="6dd33-107">WFRuntime</span></span>|  
|<span data-ttu-id="6dd33-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="6dd33-108">Level</span></span>|<span data-ttu-id="6dd33-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="6dd33-109">Verbose</span></span>|  
|<span data-ttu-id="6dd33-110">Канал</span><span class="sxs-lookup"><span data-stu-id="6dd33-110">Channel</span></span>|<span data-ttu-id="6dd33-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="6dd33-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6dd33-112">Описание</span><span class="sxs-lookup"><span data-stu-id="6dd33-112">Description</span></span>  
 <span data-ttu-id="6dd33-113">Указывает, что элемент RuntimeWorkItem был запланирован.</span><span class="sxs-lookup"><span data-stu-id="6dd33-113">Indicates a RuntimeWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="6dd33-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="6dd33-114">Message</span></span>  
 <span data-ttu-id="6dd33-115">Рабочий элемент среды выполнения запланирован для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="6dd33-115">A runtime work item has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="6dd33-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="6dd33-116">Details</span></span>  
  
|<span data-ttu-id="6dd33-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="6dd33-117">Data Item Name</span></span>|<span data-ttu-id="6dd33-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="6dd33-118">Data Item Type</span></span>|<span data-ttu-id="6dd33-119">Описание</span><span class="sxs-lookup"><span data-stu-id="6dd33-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="6dd33-120">Действие</span><span class="sxs-lookup"><span data-stu-id="6dd33-120">Activity</span></span>|<span data-ttu-id="6dd33-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="6dd33-121">xs:string</span></span>|<span data-ttu-id="6dd33-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="6dd33-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="6dd33-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="6dd33-123">DisplayName</span></span>|<span data-ttu-id="6dd33-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="6dd33-124">xs:string</span></span>|<span data-ttu-id="6dd33-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="6dd33-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="6dd33-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="6dd33-126">InstanceId</span></span>|<span data-ttu-id="6dd33-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="6dd33-127">xs:string</span></span>|<span data-ttu-id="6dd33-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="6dd33-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="6dd33-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="6dd33-129">AppDomain</span></span>|<span data-ttu-id="6dd33-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="6dd33-130">xs:string</span></span>|<span data-ttu-id="6dd33-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="6dd33-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
