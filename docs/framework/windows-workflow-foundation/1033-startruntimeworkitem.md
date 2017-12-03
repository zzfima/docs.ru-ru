---
title: 1033 - StartRuntimeWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 172b5346-9f3b-46ae-bc06-39872022376a
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2cc905fbd960b3ed5c36cac40300ba58697f8903
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="1033---startruntimeworkitem"></a><span data-ttu-id="1232b-102">1033 - StartRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="1232b-102">1033 - StartRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="1232b-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="1232b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1232b-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="1232b-104">ID</span></span>|<span data-ttu-id="1232b-105">1033</span><span class="sxs-lookup"><span data-stu-id="1232b-105">1033</span></span>|  
|<span data-ttu-id="1232b-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="1232b-106">Keywords</span></span>|<span data-ttu-id="1232b-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="1232b-107">WFRuntime</span></span>|  
|<span data-ttu-id="1232b-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="1232b-108">Level</span></span>|<span data-ttu-id="1232b-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="1232b-109">Verbose</span></span>|  
|<span data-ttu-id="1232b-110">Канал</span><span class="sxs-lookup"><span data-stu-id="1232b-110">Channel</span></span>|<span data-ttu-id="1232b-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="1232b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1232b-112">Описание</span><span class="sxs-lookup"><span data-stu-id="1232b-112">Description</span></span>  
 <span data-ttu-id="1232b-113">Указывает, что начинается выполнение RuntimeWorkItem.</span><span class="sxs-lookup"><span data-stu-id="1232b-113">Indicates a RuntimeWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1232b-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="1232b-114">Message</span></span>  
 <span data-ttu-id="1232b-115">Начато выполнение рабочего элемента среды выполнения для действия «%1», DisplayName «%2», InstanceId «%3».</span><span class="sxs-lookup"><span data-stu-id="1232b-115">Starting execution of a runtime work item for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="1232b-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="1232b-116">Details</span></span>  
  
|<span data-ttu-id="1232b-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="1232b-117">Data Item Name</span></span>|<span data-ttu-id="1232b-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="1232b-118">Data Item Type</span></span>|<span data-ttu-id="1232b-119">Описание</span><span class="sxs-lookup"><span data-stu-id="1232b-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1232b-120">Действие</span><span class="sxs-lookup"><span data-stu-id="1232b-120">Activity</span></span>|<span data-ttu-id="1232b-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="1232b-121">xs:string</span></span>|<span data-ttu-id="1232b-122">Имя типа действия.</span><span class="sxs-lookup"><span data-stu-id="1232b-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="1232b-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="1232b-123">DisplayName</span></span>|<span data-ttu-id="1232b-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="1232b-124">xs:string</span></span>|<span data-ttu-id="1232b-125">Отображаемое имя действия.</span><span class="sxs-lookup"><span data-stu-id="1232b-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="1232b-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="1232b-126">InstanceId</span></span>|<span data-ttu-id="1232b-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="1232b-127">xs:string</span></span>|<span data-ttu-id="1232b-128">Идентификатор экземпляра действия.</span><span class="sxs-lookup"><span data-stu-id="1232b-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="1232b-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="1232b-129">AppDomain</span></span>|<span data-ttu-id="1232b-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="1232b-130">xs:string</span></span>|<span data-ttu-id="1232b-131">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="1232b-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
