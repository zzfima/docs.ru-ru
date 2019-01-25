---
title: ServiceThrottlingBehavior
ms.date: 03/30/2017
ms.assetid: 37b9e517-1f1f-4ec4-9fcb-2b8016794f5b
ms.openlocfilehash: 98e8a720e92547ca0a893dd988b91cb7907660b5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54689855"
---
# <a name="servicethrottlingbehavior"></a><span data-ttu-id="702bb-102">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="702bb-102">ServiceThrottlingBehavior</span></span>
<span data-ttu-id="702bb-103">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="702bb-103">ServiceThrottlingBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="702bb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="702bb-104">Syntax</span></span>  
  
```csharp  
class ServiceThrottlingBehavior : Behavior  
{  
  sint32 MaxConcurrentCalls;  
  sint32 MaxConcurrentInstances;  
  sint32 MaxConcurrentSessions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="702bb-105">Методы</span><span class="sxs-lookup"><span data-stu-id="702bb-105">Methods</span></span>  
 <span data-ttu-id="702bb-106">Класс ServiceThrottlingBehavior не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="702bb-106">The ServiceThrottlingBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="702bb-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="702bb-107">Properties</span></span>  
 <span data-ttu-id="702bb-108">Класс ServiceThrottlingBehavior имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="702bb-108">The ServiceThrottlingBehavior class has the following properties:</span></span>  
  
### <a name="maxconcurrentcalls"></a><span data-ttu-id="702bb-109">MaxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="702bb-109">MaxConcurrentCalls</span></span>  
 <span data-ttu-id="702bb-110">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="702bb-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="702bb-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="702bb-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="702bb-112">Максимальное количество сообщений, которые могут одновременно обрабатываться во всех объектах диспетчера в узле ServiceHost.</span><span class="sxs-lookup"><span data-stu-id="702bb-112">The maximum number of messages actively processing across all dispatcher objects in a ServiceHost.</span></span>  
  
### <a name="maxconcurrentinstances"></a><span data-ttu-id="702bb-113">MaxConcurrentInstances</span><span class="sxs-lookup"><span data-stu-id="702bb-113">MaxConcurrentInstances</span></span>  
 <span data-ttu-id="702bb-114">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="702bb-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="702bb-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="702bb-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="702bb-116">Максимальное число объектов службы, которые могут выполняться одновременно.</span><span class="sxs-lookup"><span data-stu-id="702bb-116">The maximum number of service objects that can execute at one time.</span></span>  
  
### <a name="maxconcurrentsessions"></a><span data-ttu-id="702bb-117">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="702bb-117">MaxConcurrentSessions</span></span>  
 <span data-ttu-id="702bb-118">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="702bb-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="702bb-119">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="702bb-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="702bb-120">Максимальное число сеансов, одновременно принимаемых узлом.</span><span class="sxs-lookup"><span data-stu-id="702bb-120">The maximum number of sessions a host can accept at one time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="702bb-121">Требования</span><span class="sxs-lookup"><span data-stu-id="702bb-121">Requirements</span></span>  
  
|<span data-ttu-id="702bb-122">MOF</span><span class="sxs-lookup"><span data-stu-id="702bb-122">MOF</span></span>|<span data-ttu-id="702bb-123">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="702bb-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="702bb-124">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="702bb-124">Namespace</span></span>|<span data-ttu-id="702bb-125">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="702bb-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="702bb-126">См. также</span><span class="sxs-lookup"><span data-stu-id="702bb-126">See also</span></span>
- <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
