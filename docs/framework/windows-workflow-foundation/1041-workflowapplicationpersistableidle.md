---
title: 1041 - WorkflowApplicationPersistableIdle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 966adf2f-e21d-44df-a3ec-a8e285e0a316
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b321f8c20fbd79b5e748601ee06f975dc75a7d56
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="1041---workflowapplicationpersistableidle"></a><span data-ttu-id="7b266-102">1041 - WorkflowApplicationPersistableIdle</span><span class="sxs-lookup"><span data-stu-id="7b266-102">1041 - WorkflowApplicationPersistableIdle</span></span>
## <a name="properties"></a><span data-ttu-id="7b266-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="7b266-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7b266-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="7b266-104">ID</span></span>|<span data-ttu-id="7b266-105">1041</span><span class="sxs-lookup"><span data-stu-id="7b266-105">1041</span></span>|  
|<span data-ttu-id="7b266-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="7b266-106">Keywords</span></span>|<span data-ttu-id="7b266-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="7b266-107">WFRuntime</span></span>|  
|<span data-ttu-id="7b266-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="7b266-108">Level</span></span>|<span data-ttu-id="7b266-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="7b266-109">Information</span></span>|  
|<span data-ttu-id="7b266-110">Канал</span><span class="sxs-lookup"><span data-stu-id="7b266-110">Channel</span></span>|<span data-ttu-id="7b266-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="7b266-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7b266-112">Описание</span><span class="sxs-lookup"><span data-stu-id="7b266-112">Description</span></span>  
 <span data-ttu-id="7b266-113">Указывает, что приложение рабочего процесса бездействует и является сохраняемым.</span><span class="sxs-lookup"><span data-stu-id="7b266-113">Indicates that a workflow application is idle and persistable.</span></span> <span data-ttu-id="7b266-114">Приложение рабочего процесса будет бездействующим или сохраняемым.</span><span class="sxs-lookup"><span data-stu-id="7b266-114">The workflow application will be idled or persisted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="7b266-115">Сообщение</span><span class="sxs-lookup"><span data-stu-id="7b266-115">Message</span></span>  
 <span data-ttu-id="7b266-116">WorkflowApplication с идентификатором: «%1» бездействует и является сохраняемым.</span><span class="sxs-lookup"><span data-stu-id="7b266-116">WorkflowApplication Id: '%1' is idle and persistable.</span></span>  <span data-ttu-id="7b266-117">Будут выполнены следующие действия: %2.</span><span class="sxs-lookup"><span data-stu-id="7b266-117">The following action will be taken: %2.</span></span>  
  
## <a name="details"></a><span data-ttu-id="7b266-118">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="7b266-118">Details</span></span>  
  
|<span data-ttu-id="7b266-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="7b266-119">Data Item Name</span></span>|<span data-ttu-id="7b266-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="7b266-120">Data Item Type</span></span>|<span data-ttu-id="7b266-121">Описание</span><span class="sxs-lookup"><span data-stu-id="7b266-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="7b266-122">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="7b266-122">WorkflowApplicationId</span></span>|<span data-ttu-id="7b266-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="7b266-123">xs:string</span></span>|<span data-ttu-id="7b266-124">Идентификатор приложения рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="7b266-124">The workflow application id</span></span>|  
|<span data-ttu-id="7b266-125">ActionTaken</span><span class="sxs-lookup"><span data-stu-id="7b266-125">ActionTaken</span></span>|<span data-ttu-id="7b266-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="7b266-126">xs:string</span></span>|<span data-ttu-id="7b266-127">Действие, которое будет выполняться в приложении рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="7b266-127">The action that will be taken on the workflow application.</span></span>|  
|<span data-ttu-id="7b266-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="7b266-128">AppDomain</span></span>|<span data-ttu-id="7b266-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="7b266-129">xs:string</span></span>|<span data-ttu-id="7b266-130">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="7b266-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
