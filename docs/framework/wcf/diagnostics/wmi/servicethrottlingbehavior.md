---
title: ServiceThrottlingBehavior
ms.date: 03/30/2017
ms.assetid: 37b9e517-1f1f-4ec4-9fcb-2b8016794f5b
ms.openlocfilehash: 9a7fbf93dbdbf1a6debcf865b4883b5784e2ff4a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33487611"
---
# <a name="servicethrottlingbehavior"></a><span data-ttu-id="047ef-102">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="047ef-102">ServiceThrottlingBehavior</span></span>
<span data-ttu-id="047ef-103">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="047ef-103">ServiceThrottlingBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="047ef-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="047ef-104">Syntax</span></span>  
  
```  
class ServiceThrottlingBehavior : Behavior  
{  
  sint32 MaxConcurrentCalls;  
  sint32 MaxConcurrentInstances;  
  sint32 MaxConcurrentSessions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="047ef-105">Методы</span><span class="sxs-lookup"><span data-stu-id="047ef-105">Methods</span></span>  
 <span data-ttu-id="047ef-106">Класс ServiceThrottlingBehavior не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="047ef-106">The ServiceThrottlingBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="047ef-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="047ef-107">Properties</span></span>  
 <span data-ttu-id="047ef-108">Класс ServiceThrottlingBehavior имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="047ef-108">The ServiceThrottlingBehavior class has the following properties:</span></span>  
  
### <a name="maxconcurrentcalls"></a><span data-ttu-id="047ef-109">MaxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="047ef-109">MaxConcurrentCalls</span></span>  
 <span data-ttu-id="047ef-110">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="047ef-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="047ef-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="047ef-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="047ef-112">Максимальное количество сообщений, которые могут одновременно обрабатываться во всех объектах диспетчера в узле ServiceHost.</span><span class="sxs-lookup"><span data-stu-id="047ef-112">The maximum number of messages actively processing across all dispatcher objects in a ServiceHost.</span></span>  
  
### <a name="maxconcurrentinstances"></a><span data-ttu-id="047ef-113">MaxConcurrentInstances</span><span class="sxs-lookup"><span data-stu-id="047ef-113">MaxConcurrentInstances</span></span>  
 <span data-ttu-id="047ef-114">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="047ef-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="047ef-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="047ef-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="047ef-116">Максимальное число объектов службы, которые могут выполняться одновременно.</span><span class="sxs-lookup"><span data-stu-id="047ef-116">The maximum number of service objects that can execute at one time.</span></span>  
  
### <a name="maxconcurrentsessions"></a><span data-ttu-id="047ef-117">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="047ef-117">MaxConcurrentSessions</span></span>  
 <span data-ttu-id="047ef-118">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="047ef-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="047ef-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="047ef-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="047ef-120">Максимальное число сеансов, одновременно принимаемых узлом.</span><span class="sxs-lookup"><span data-stu-id="047ef-120">The maximum number of sessions a host can accept at one time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="047ef-121">Требования</span><span class="sxs-lookup"><span data-stu-id="047ef-121">Requirements</span></span>  
  
|<span data-ttu-id="047ef-122">MOF</span><span class="sxs-lookup"><span data-stu-id="047ef-122">MOF</span></span>|<span data-ttu-id="047ef-123">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="047ef-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="047ef-124">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="047ef-124">Namespace</span></span>|<span data-ttu-id="047ef-125">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="047ef-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="047ef-126">См. также</span><span class="sxs-lookup"><span data-stu-id="047ef-126">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
