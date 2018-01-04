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
ms.workload: dotnet
ms.openlocfilehash: 1efc32ed0304d5b0d222054e5c65abe279ef93ae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="1041---workflowapplicationpersistableidle"></a><span data-ttu-id="630c4-102">1041 - WorkflowApplicationPersistableIdle</span><span class="sxs-lookup"><span data-stu-id="630c4-102">1041 - WorkflowApplicationPersistableIdle</span></span>
## <a name="properties"></a><span data-ttu-id="630c4-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="630c4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="630c4-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="630c4-104">ID</span></span>|<span data-ttu-id="630c4-105">1041</span><span class="sxs-lookup"><span data-stu-id="630c4-105">1041</span></span>|  
|<span data-ttu-id="630c4-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="630c4-106">Keywords</span></span>|<span data-ttu-id="630c4-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="630c4-107">WFRuntime</span></span>|  
|<span data-ttu-id="630c4-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="630c4-108">Level</span></span>|<span data-ttu-id="630c4-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="630c4-109">Information</span></span>|  
|<span data-ttu-id="630c4-110">Канал</span><span class="sxs-lookup"><span data-stu-id="630c4-110">Channel</span></span>|<span data-ttu-id="630c4-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="630c4-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="630c4-112">Описание</span><span class="sxs-lookup"><span data-stu-id="630c4-112">Description</span></span>  
 <span data-ttu-id="630c4-113">Указывает, что приложение рабочего процесса бездействует и является сохраняемым.</span><span class="sxs-lookup"><span data-stu-id="630c4-113">Indicates that a workflow application is idle and persistable.</span></span> <span data-ttu-id="630c4-114">Приложение рабочего процесса будет бездействующим или сохраняемым.</span><span class="sxs-lookup"><span data-stu-id="630c4-114">The workflow application will be idled or persisted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="630c4-115">Сообщение</span><span class="sxs-lookup"><span data-stu-id="630c4-115">Message</span></span>  
 <span data-ttu-id="630c4-116">WorkflowApplication с идентификатором: «%1» бездействует и является сохраняемым.</span><span class="sxs-lookup"><span data-stu-id="630c4-116">WorkflowApplication Id: '%1' is idle and persistable.</span></span>  <span data-ttu-id="630c4-117">Будут выполнены следующие действия: %2.</span><span class="sxs-lookup"><span data-stu-id="630c4-117">The following action will be taken: %2.</span></span>  
  
## <a name="details"></a><span data-ttu-id="630c4-118">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="630c4-118">Details</span></span>  
  
|<span data-ttu-id="630c4-119">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="630c4-119">Data Item Name</span></span>|<span data-ttu-id="630c4-120">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="630c4-120">Data Item Type</span></span>|<span data-ttu-id="630c4-121">Описание</span><span class="sxs-lookup"><span data-stu-id="630c4-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="630c4-122">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="630c4-122">WorkflowApplicationId</span></span>|<span data-ttu-id="630c4-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="630c4-123">xs:string</span></span>|<span data-ttu-id="630c4-124">Идентификатор приложения рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="630c4-124">The workflow application id</span></span>|  
|<span data-ttu-id="630c4-125">ActionTaken</span><span class="sxs-lookup"><span data-stu-id="630c4-125">ActionTaken</span></span>|<span data-ttu-id="630c4-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="630c4-126">xs:string</span></span>|<span data-ttu-id="630c4-127">Действие, которое будет выполняться в приложении рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="630c4-127">The action that will be taken on the workflow application.</span></span>|  
|<span data-ttu-id="630c4-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="630c4-128">AppDomain</span></span>|<span data-ttu-id="630c4-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="630c4-129">xs:string</span></span>|<span data-ttu-id="630c4-130">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="630c4-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
