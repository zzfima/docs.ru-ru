---
title: 1032 - ScheduleRuntimeWorkItem
ms.date: 03/30/2017
ms.assetid: 54688101-becf-42f3-80ca-f53a7b527620
ms.openlocfilehash: 505b852d54e256b2c2bfff8d90944dd4e993e0c0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924869"
---
# <a name="1032---scheduleruntimeworkitem"></a><span data-ttu-id="8fd76-102">1032 - ScheduleRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="8fd76-102">1032 - ScheduleRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="8fd76-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="8fd76-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8fd76-104">ID</span><span class="sxs-lookup"><span data-stu-id="8fd76-104">ID</span></span>|<span data-ttu-id="8fd76-105">1032</span><span class="sxs-lookup"><span data-stu-id="8fd76-105">1032</span></span>|  
|<span data-ttu-id="8fd76-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="8fd76-106">Keywords</span></span>|<span data-ttu-id="8fd76-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="8fd76-107">WFRuntime</span></span>|  
|<span data-ttu-id="8fd76-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="8fd76-108">Level</span></span>|<span data-ttu-id="8fd76-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="8fd76-109">Verbose</span></span>|  
|<span data-ttu-id="8fd76-110">Канал</span><span class="sxs-lookup"><span data-stu-id="8fd76-110">Channel</span></span>|<span data-ttu-id="8fd76-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="8fd76-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8fd76-112">Описание</span><span class="sxs-lookup"><span data-stu-id="8fd76-112">Description</span></span>  
 <span data-ttu-id="8fd76-113">Указывает, что элемент RuntimeWorkItem был запланирован.</span><span class="sxs-lookup"><span data-stu-id="8fd76-113">Indicates a RuntimeWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8fd76-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="8fd76-114">Message</span></span>  
 <span data-ttu-id="8fd76-115">Рабочий элемент среды выполнения запланирован для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="8fd76-115">A runtime work item has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8fd76-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="8fd76-116">Details</span></span>  
  
|<span data-ttu-id="8fd76-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="8fd76-117">Data Item Name</span></span>|<span data-ttu-id="8fd76-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="8fd76-118">Data Item Type</span></span>|<span data-ttu-id="8fd76-119">Описание</span><span class="sxs-lookup"><span data-stu-id="8fd76-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8fd76-120">Действие</span><span class="sxs-lookup"><span data-stu-id="8fd76-120">Activity</span></span>|<span data-ttu-id="8fd76-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="8fd76-121">xs:string</span></span>|<span data-ttu-id="8fd76-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="8fd76-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="8fd76-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="8fd76-123">DisplayName</span></span>|<span data-ttu-id="8fd76-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="8fd76-124">xs:string</span></span>|<span data-ttu-id="8fd76-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="8fd76-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="8fd76-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="8fd76-126">InstanceId</span></span>|<span data-ttu-id="8fd76-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="8fd76-127">xs:string</span></span>|<span data-ttu-id="8fd76-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="8fd76-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="8fd76-129">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="8fd76-129">AppDomain</span></span>|<span data-ttu-id="8fd76-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="8fd76-130">xs:string</span></span>|<span data-ttu-id="8fd76-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="8fd76-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
