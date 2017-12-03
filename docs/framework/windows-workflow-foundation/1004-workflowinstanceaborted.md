---
title: "1004 ― WorkflowInstanceAborted"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: edb9ab8c-0b9a-488d-aa96-9c8c7984b53c
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 564e94d94dc5e3579dc4a80d734db78e90db91fb
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="1004---workflowinstanceaborted"></a><span data-ttu-id="b8af2-102">1004 ― WorkflowInstanceAborted</span><span class="sxs-lookup"><span data-stu-id="b8af2-102">1004 - WorkflowInstanceAborted</span></span>
## <a name="properties"></a><span data-ttu-id="b8af2-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="b8af2-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b8af2-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="b8af2-104">ID</span></span>|<span data-ttu-id="b8af2-105">1004</span><span class="sxs-lookup"><span data-stu-id="b8af2-105">1004</span></span>|  
|<span data-ttu-id="b8af2-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="b8af2-106">Keywords</span></span>|<span data-ttu-id="b8af2-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="b8af2-107">WFRuntime</span></span>|  
|<span data-ttu-id="b8af2-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="b8af2-108">Level</span></span>|<span data-ttu-id="b8af2-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="b8af2-109">Information</span></span>|  
|<span data-ttu-id="b8af2-110">Канал</span><span class="sxs-lookup"><span data-stu-id="b8af2-110">Channel</span></span>|<span data-ttu-id="b8af2-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="b8af2-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b8af2-112">Описание</span><span class="sxs-lookup"><span data-stu-id="b8af2-112">Description</span></span>  
 <span data-ttu-id="b8af2-113">Указывает, что экземпляр рабочего процесса был прерван с исключением.</span><span class="sxs-lookup"><span data-stu-id="b8af2-113">Indicates a worfklow instance has aborted with an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b8af2-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="b8af2-114">Message</span></span>  
 <span data-ttu-id="b8af2-115">Выполнение элемента WorkflowInstance с идентификатором «%1» было прервано в результате исключения.</span><span class="sxs-lookup"><span data-stu-id="b8af2-115">WorkflowInstance Id: '%1' was aborted with an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b8af2-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="b8af2-116">Details</span></span>  
  
|<span data-ttu-id="b8af2-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="b8af2-117">Data Item Name</span></span>|<span data-ttu-id="b8af2-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="b8af2-118">Data Item Type</span></span>|<span data-ttu-id="b8af2-119">Описание</span><span class="sxs-lookup"><span data-stu-id="b8af2-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b8af2-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="b8af2-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="b8af2-121">Идентификатор экземпляра для рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="b8af2-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="b8af2-122">Исключение</span><span class="sxs-lookup"><span data-stu-id="b8af2-122">Exception</span></span>|`xs:string`|<span data-ttu-id="b8af2-123">Сведения об исключении</span><span class="sxs-lookup"><span data-stu-id="b8af2-123">The exception details for the exception</span></span>|  
|<span data-ttu-id="b8af2-124">Домен приложения</span><span class="sxs-lookup"><span data-stu-id="b8af2-124">AppDomain</span></span>|`xs:string`|<span data-ttu-id="b8af2-125">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="b8af2-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
