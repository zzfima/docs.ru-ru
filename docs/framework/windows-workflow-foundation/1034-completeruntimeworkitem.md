---
title: 1034 - CompleteRuntimeWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 45620011-8b04-4f87-ab5a-65b24145e17d
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 63ab145b8a0688a7f7bbf7dbcbe8dfe612eab294
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="1034---completeruntimeworkitem"></a><span data-ttu-id="50747-102">1034 - CompleteRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="50747-102">1034 - CompleteRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="50747-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="50747-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="50747-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="50747-104">ID</span></span>|<span data-ttu-id="50747-105">1034</span><span class="sxs-lookup"><span data-stu-id="50747-105">1034</span></span>|  
|<span data-ttu-id="50747-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="50747-106">Keywords</span></span>|<span data-ttu-id="50747-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="50747-107">WFRuntime</span></span>|  
|<span data-ttu-id="50747-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="50747-108">Level</span></span>|<span data-ttu-id="50747-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="50747-109">Verbose</span></span>|  
|<span data-ttu-id="50747-110">Канал</span><span class="sxs-lookup"><span data-stu-id="50747-110">Channel</span></span>|<span data-ttu-id="50747-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="50747-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="50747-112">Описание</span><span class="sxs-lookup"><span data-stu-id="50747-112">Description</span></span>  
 <span data-ttu-id="50747-113">Указывает на завершение RuntimeWorkItem.</span><span class="sxs-lookup"><span data-stu-id="50747-113">Indicates a RuntimeWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="50747-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="50747-114">Message</span></span>  
 <span data-ttu-id="50747-115">Рабочий элемент среды выполнения завершен для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="50747-115">A runtime work item has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="50747-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="50747-116">Details</span></span>  
  
|<span data-ttu-id="50747-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="50747-117">Data Item Name</span></span>|<span data-ttu-id="50747-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="50747-118">Data Item Type</span></span>|<span data-ttu-id="50747-119">Описание</span><span class="sxs-lookup"><span data-stu-id="50747-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="50747-120">Действие</span><span class="sxs-lookup"><span data-stu-id="50747-120">Activity</span></span>|<span data-ttu-id="50747-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="50747-121">xs:string</span></span>|<span data-ttu-id="50747-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="50747-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="50747-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="50747-123">DisplayName</span></span>|<span data-ttu-id="50747-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="50747-124">xs:string</span></span>|<span data-ttu-id="50747-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="50747-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="50747-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="50747-126">InstanceId</span></span>|<span data-ttu-id="50747-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="50747-127">xs:string</span></span>|<span data-ttu-id="50747-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="50747-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="50747-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="50747-129">AppDomain</span></span>|<span data-ttu-id="50747-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="50747-130">xs:string</span></span>|<span data-ttu-id="50747-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="50747-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
