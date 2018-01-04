---
title: 1104 - WorkflowActivityResume
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7fe95d1e-34bd-43ca-b92e-587d2d248fff
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7d38009ea0f384319938204cae41f64a71203731
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="1104---workflowactivityresume"></a><span data-ttu-id="486cf-102">1104 - WorkflowActivityResume</span><span class="sxs-lookup"><span data-stu-id="486cf-102">1104 - WorkflowActivityResume</span></span>
## <a name="properties"></a><span data-ttu-id="486cf-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="486cf-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="486cf-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="486cf-104">ID</span></span>|<span data-ttu-id="486cf-105">1104</span><span class="sxs-lookup"><span data-stu-id="486cf-105">1104</span></span>|  
|<span data-ttu-id="486cf-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="486cf-106">Keywords</span></span>|<span data-ttu-id="486cf-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="486cf-107">WFRuntime</span></span>|  
|<span data-ttu-id="486cf-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="486cf-108">Level</span></span>|<span data-ttu-id="486cf-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="486cf-109">Information</span></span>|  
|<span data-ttu-id="486cf-110">Канал</span><span class="sxs-lookup"><span data-stu-id="486cf-110">Channel</span></span>|<span data-ttu-id="486cf-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="486cf-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="486cf-112">Описание</span><span class="sxs-lookup"><span data-stu-id="486cf-112">Description</span></span>  
 <span data-ttu-id="486cf-113">Указывает, что действие рабочего процесса возобновлено.</span><span class="sxs-lookup"><span data-stu-id="486cf-113">Indicates a workflow activity has been resumed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="486cf-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="486cf-114">Message</span></span>  
 <span data-ttu-id="486cf-115">Элемент WorkflowInstance с идентификатором «%1», действие E2E</span><span class="sxs-lookup"><span data-stu-id="486cf-115">WorkflowInstance Id: '%1' E2E Activity</span></span>  
  
## <a name="details"></a><span data-ttu-id="486cf-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="486cf-116">Details</span></span>  
  
|<span data-ttu-id="486cf-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="486cf-117">Data Item Name</span></span>|<span data-ttu-id="486cf-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="486cf-118">Data Item Type</span></span>|<span data-ttu-id="486cf-119">Описание</span><span class="sxs-lookup"><span data-stu-id="486cf-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="486cf-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="486cf-120">WorkflowInstanceId</span></span>|<span data-ttu-id="486cf-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="486cf-121">xs:string</span></span>|<span data-ttu-id="486cf-122">Идентификатор экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="486cf-122">The workflow instance id.</span></span>|  
|<span data-ttu-id="486cf-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="486cf-123">AppDomain</span></span>|<span data-ttu-id="486cf-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="486cf-124">xs:string</span></span>|<span data-ttu-id="486cf-125">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="486cf-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
