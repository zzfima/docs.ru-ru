---
title: ServiceThrottlingBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 37b9e517-1f1f-4ec4-9fcb-2b8016794f5b
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ccf1c167c4d1a072737f725de2fa0c132ca686f7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="servicethrottlingbehavior"></a><span data-ttu-id="64d24-102">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="64d24-102">ServiceThrottlingBehavior</span></span>
<span data-ttu-id="64d24-103">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="64d24-103">ServiceThrottlingBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64d24-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="64d24-104">Syntax</span></span>  
  
```  
class ServiceThrottlingBehavior : Behavior  
{  
  sint32 MaxConcurrentCalls;  
  sint32 MaxConcurrentInstances;  
  sint32 MaxConcurrentSessions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="64d24-105">Методы</span><span class="sxs-lookup"><span data-stu-id="64d24-105">Methods</span></span>  
 <span data-ttu-id="64d24-106">Класс ServiceThrottlingBehavior не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="64d24-106">The ServiceThrottlingBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="64d24-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="64d24-107">Properties</span></span>  
 <span data-ttu-id="64d24-108">Класс ServiceThrottlingBehavior имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="64d24-108">The ServiceThrottlingBehavior class has the following properties:</span></span>  
  
### <a name="maxconcurrentcalls"></a><span data-ttu-id="64d24-109">MaxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="64d24-109">MaxConcurrentCalls</span></span>  
 <span data-ttu-id="64d24-110">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="64d24-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="64d24-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="64d24-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="64d24-112">Максимальное количество сообщений, которые могут одновременно обрабатываться во всех объектах диспетчера в узле ServiceHost.</span><span class="sxs-lookup"><span data-stu-id="64d24-112">The maximum number of messages actively processing across all dispatcher objects in a ServiceHost.</span></span>  
  
### <a name="maxconcurrentinstances"></a><span data-ttu-id="64d24-113">MaxConcurrentInstances</span><span class="sxs-lookup"><span data-stu-id="64d24-113">MaxConcurrentInstances</span></span>  
 <span data-ttu-id="64d24-114">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="64d24-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="64d24-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="64d24-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="64d24-116">Максимальное число объектов службы, которые могут выполняться одновременно.</span><span class="sxs-lookup"><span data-stu-id="64d24-116">The maximum number of service objects that can execute at one time.</span></span>  
  
### <a name="maxconcurrentsessions"></a><span data-ttu-id="64d24-117">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="64d24-117">MaxConcurrentSessions</span></span>  
 <span data-ttu-id="64d24-118">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="64d24-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="64d24-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="64d24-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="64d24-120">Максимальное число сеансов, одновременно принимаемых узлом.</span><span class="sxs-lookup"><span data-stu-id="64d24-120">The maximum number of sessions a host can accept at one time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64d24-121">Требования</span><span class="sxs-lookup"><span data-stu-id="64d24-121">Requirements</span></span>  
  
|<span data-ttu-id="64d24-122">MOF</span><span class="sxs-lookup"><span data-stu-id="64d24-122">MOF</span></span>|<span data-ttu-id="64d24-123">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="64d24-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="64d24-124">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="64d24-124">Namespace</span></span>|<span data-ttu-id="64d24-125">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="64d24-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="64d24-126">См. также</span><span class="sxs-lookup"><span data-stu-id="64d24-126">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
