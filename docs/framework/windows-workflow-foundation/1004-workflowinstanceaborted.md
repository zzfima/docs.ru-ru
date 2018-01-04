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
ms.workload: dotnet
ms.openlocfilehash: cc940e1781f821f12efb42c5198e77eb0451a164
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="1004---workflowinstanceaborted"></a><span data-ttu-id="97d10-102">1004 ― WorkflowInstanceAborted</span><span class="sxs-lookup"><span data-stu-id="97d10-102">1004 - WorkflowInstanceAborted</span></span>
## <a name="properties"></a><span data-ttu-id="97d10-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="97d10-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="97d10-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="97d10-104">ID</span></span>|<span data-ttu-id="97d10-105">1004</span><span class="sxs-lookup"><span data-stu-id="97d10-105">1004</span></span>|  
|<span data-ttu-id="97d10-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="97d10-106">Keywords</span></span>|<span data-ttu-id="97d10-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="97d10-107">WFRuntime</span></span>|  
|<span data-ttu-id="97d10-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="97d10-108">Level</span></span>|<span data-ttu-id="97d10-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="97d10-109">Information</span></span>|  
|<span data-ttu-id="97d10-110">Канал</span><span class="sxs-lookup"><span data-stu-id="97d10-110">Channel</span></span>|<span data-ttu-id="97d10-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="97d10-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="97d10-112">Описание</span><span class="sxs-lookup"><span data-stu-id="97d10-112">Description</span></span>  
 <span data-ttu-id="97d10-113">Указывает, что экземпляр рабочего процесса был прерван с исключением.</span><span class="sxs-lookup"><span data-stu-id="97d10-113">Indicates a worfklow instance has aborted with an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="97d10-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="97d10-114">Message</span></span>  
 <span data-ttu-id="97d10-115">Выполнение элемента WorkflowInstance с идентификатором «%1» было прервано в результате исключения.</span><span class="sxs-lookup"><span data-stu-id="97d10-115">WorkflowInstance Id: '%1' was aborted with an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="97d10-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="97d10-116">Details</span></span>  
  
|<span data-ttu-id="97d10-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="97d10-117">Data Item Name</span></span>|<span data-ttu-id="97d10-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="97d10-118">Data Item Type</span></span>|<span data-ttu-id="97d10-119">Описание</span><span class="sxs-lookup"><span data-stu-id="97d10-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="97d10-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="97d10-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="97d10-121">Идентификатор экземпляра для рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="97d10-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="97d10-122">Исключение</span><span class="sxs-lookup"><span data-stu-id="97d10-122">Exception</span></span>|`xs:string`|<span data-ttu-id="97d10-123">Сведения об исключении</span><span class="sxs-lookup"><span data-stu-id="97d10-123">The exception details for the exception</span></span>|  
|<span data-ttu-id="97d10-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="97d10-124">AppDomain</span></span>|`xs:string`|<span data-ttu-id="97d10-125">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="97d10-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
