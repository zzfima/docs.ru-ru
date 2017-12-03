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
ms.openlocfilehash: 029b1832259451beb458f8cbed4b0a3c44fdc490
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="1104---workflowactivityresume"></a><span data-ttu-id="e0b2c-102">1104 - WorkflowActivityResume</span><span class="sxs-lookup"><span data-stu-id="e0b2c-102">1104 - WorkflowActivityResume</span></span>
## <a name="properties"></a><span data-ttu-id="e0b2c-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="e0b2c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e0b2c-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="e0b2c-104">ID</span></span>|<span data-ttu-id="e0b2c-105">1104</span><span class="sxs-lookup"><span data-stu-id="e0b2c-105">1104</span></span>|  
|<span data-ttu-id="e0b2c-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="e0b2c-106">Keywords</span></span>|<span data-ttu-id="e0b2c-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="e0b2c-107">WFRuntime</span></span>|  
|<span data-ttu-id="e0b2c-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="e0b2c-108">Level</span></span>|<span data-ttu-id="e0b2c-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="e0b2c-109">Information</span></span>|  
|<span data-ttu-id="e0b2c-110">Канал</span><span class="sxs-lookup"><span data-stu-id="e0b2c-110">Channel</span></span>|<span data-ttu-id="e0b2c-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="e0b2c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e0b2c-112">Описание</span><span class="sxs-lookup"><span data-stu-id="e0b2c-112">Description</span></span>  
 <span data-ttu-id="e0b2c-113">Указывает, что действие рабочего процесса возобновлено.</span><span class="sxs-lookup"><span data-stu-id="e0b2c-113">Indicates a workflow activity has been resumed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e0b2c-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="e0b2c-114">Message</span></span>  
 <span data-ttu-id="e0b2c-115">Элемент WorkflowInstance с идентификатором «%1», действие E2E</span><span class="sxs-lookup"><span data-stu-id="e0b2c-115">WorkflowInstance Id: '%1' E2E Activity</span></span>  
  
## <a name="details"></a><span data-ttu-id="e0b2c-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="e0b2c-116">Details</span></span>  
  
|<span data-ttu-id="e0b2c-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="e0b2c-117">Data Item Name</span></span>|<span data-ttu-id="e0b2c-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="e0b2c-118">Data Item Type</span></span>|<span data-ttu-id="e0b2c-119">Описание</span><span class="sxs-lookup"><span data-stu-id="e0b2c-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e0b2c-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="e0b2c-120">WorkflowInstanceId</span></span>|<span data-ttu-id="e0b2c-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="e0b2c-121">xs:string</span></span>|<span data-ttu-id="e0b2c-122">Идентификатор экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="e0b2c-122">The workflow instance id.</span></span>|  
|<span data-ttu-id="e0b2c-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e0b2c-123">AppDomain</span></span>|<span data-ttu-id="e0b2c-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="e0b2c-124">xs:string</span></span>|<span data-ttu-id="e0b2c-125">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="e0b2c-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
