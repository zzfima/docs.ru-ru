---
title: 1008 - WorkflowApplicationUnloaded
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a605b780-4a7e-43ab-92e7-0a3b01d053b0
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 26491c1e2b20f4285aaedbcd12947cad3562f041
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="1008---workflowapplicationunloaded"></a><span data-ttu-id="5fd26-102">1008 - WorkflowApplicationUnloaded</span><span class="sxs-lookup"><span data-stu-id="5fd26-102">1008 - WorkflowApplicationUnloaded</span></span>
## <a name="properties"></a><span data-ttu-id="5fd26-103">Свойства</span><span class="sxs-lookup"><span data-stu-id="5fd26-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5fd26-104">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="5fd26-104">ID</span></span>|<span data-ttu-id="5fd26-105">1008</span><span class="sxs-lookup"><span data-stu-id="5fd26-105">1008</span></span>|  
|<span data-ttu-id="5fd26-106">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="5fd26-106">Keywords</span></span>|<span data-ttu-id="5fd26-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="5fd26-107">WFRuntime</span></span>|  
|<span data-ttu-id="5fd26-108">Уровень</span><span class="sxs-lookup"><span data-stu-id="5fd26-108">Level</span></span>|<span data-ttu-id="5fd26-109">Сведения</span><span class="sxs-lookup"><span data-stu-id="5fd26-109">Information</span></span>|  
|<span data-ttu-id="5fd26-110">Канал</span><span class="sxs-lookup"><span data-stu-id="5fd26-110">Channel</span></span>|<span data-ttu-id="5fd26-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="5fd26-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5fd26-112">Описание</span><span class="sxs-lookup"><span data-stu-id="5fd26-112">Description</span></span>  
 <span data-ttu-id="5fd26-113">Указывает, что приложение рабочего процесса выгружено.</span><span class="sxs-lookup"><span data-stu-id="5fd26-113">Indicates a workflow application has unloaded.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5fd26-114">Сообщение</span><span class="sxs-lookup"><span data-stu-id="5fd26-114">Message</span></span>  
 <span data-ttu-id="5fd26-115">Элемент WorkflowInstance с идентификатором «%1» выгружен из памяти.</span><span class="sxs-lookup"><span data-stu-id="5fd26-115">WorkflowInstance Id: '%1' was Unloaded.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5fd26-116">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="5fd26-116">Details</span></span>  
  
|<span data-ttu-id="5fd26-117">Имя элемента данных</span><span class="sxs-lookup"><span data-stu-id="5fd26-117">Data Item Name</span></span>|<span data-ttu-id="5fd26-118">Тип элемента данных</span><span class="sxs-lookup"><span data-stu-id="5fd26-118">Data Item Type</span></span>|<span data-ttu-id="5fd26-119">Описание</span><span class="sxs-lookup"><span data-stu-id="5fd26-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5fd26-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="5fd26-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="5fd26-121">Идентификатор экземпляра для рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="5fd26-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="5fd26-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5fd26-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="5fd26-123">Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="5fd26-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
