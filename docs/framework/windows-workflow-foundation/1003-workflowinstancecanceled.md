---
title: 1003 - WorkflowInstanceCanceled
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 64754dc2-c160-4bf3-869a-13d56694e2dc
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b264450703090edfcf99f9584c16d33eb82a76e3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="1003---workflowinstancecanceled"></a><span data-ttu-id="aaa8a-102">1003 - WorkflowInstanceCanceled</span><span class="sxs-lookup"><span data-stu-id="aaa8a-102">1003 - WorkflowInstanceCanceled</span></span>
## <a name="properties"></a><span data-ttu-id="aaa8a-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="aaa8a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="aaa8a-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="aaa8a-104">ID</span></span>|<span data-ttu-id="aaa8a-105">1003</span><span class="sxs-lookup"><span data-stu-id="aaa8a-105">1003</span></span>|  
|<span data-ttu-id="aaa8a-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="aaa8a-106">Keywords</span></span>|<span data-ttu-id="aaa8a-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="aaa8a-107">WFRuntime</span></span>|  
|<span data-ttu-id="aaa8a-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="aaa8a-108">Level</span></span>|<span data-ttu-id="aaa8a-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="aaa8a-109">Information</span></span>|  
|<span data-ttu-id="aaa8a-110">Канал</span><span class="sxs-lookup"><span data-stu-id="aaa8a-110">Channel</span></span>|<span data-ttu-id="aaa8a-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="aaa8a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="aaa8a-112">Описание</span><span class="sxs-lookup"><span data-stu-id="aaa8a-112">Description</span></span>  
 <span data-ttu-id="aaa8a-113">Указывает, что экземпляр рабочего процесса завершено в состоянии Canceled.</span><span class="sxs-lookup"><span data-stu-id="aaa8a-113">Indicates a workflow instance has completed in the Canceled state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="aaa8a-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="aaa8a-114">Message</span></span>  
 <span data-ttu-id="aaa8a-115">Элемент WorkflowInstance с идентификатором «%1» завершил работу в состоянии Canceled.</span><span class="sxs-lookup"><span data-stu-id="aaa8a-115">WorkflowInstance Id: '%1' has completed in the Canceled state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="aaa8a-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="aaa8a-116">Details</span></span>  
  
|<span data-ttu-id="aaa8a-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="aaa8a-117">Data Item Name</span></span>|<span data-ttu-id="aaa8a-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="aaa8a-118">Data Item Type</span></span>|<span data-ttu-id="aaa8a-119">Описание</span><span class="sxs-lookup"><span data-stu-id="aaa8a-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="aaa8a-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="aaa8a-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="aaa8a-121">Идентификатор экземпляра для рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="aaa8a-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="aaa8a-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="aaa8a-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="aaa8a-123">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="aaa8a-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
