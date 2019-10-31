---
title: Перечисление EMemoryCriticalLevel
ms.date: 03/30/2017
api_name:
- EMemoryCriticalLevel
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EMemoryCriticalLevel
helpviewer_keywords:
- EMemoryCriticalLevel enumeration [.NET Framework hosting]
ms.assetid: 2ca8a7a2-7b54-4ba3-8e73-277c7df485f3
topic_type:
- apiref
ms.openlocfilehash: 8364d38f7ab81b73fd8b47d2251bc0ff1b2c71e8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138249"
---
# <a name="ememorycriticallevel-enumeration"></a><span data-ttu-id="cac70-102">Перечисление EMemoryCriticalLevel</span><span class="sxs-lookup"><span data-stu-id="cac70-102">EMemoryCriticalLevel Enumeration</span></span>
<span data-ttu-id="cac70-103">Содержит значения, которые указывают на влияние сбоя при запросе определенного выделения памяти, но не могут быть удовлетворены.</span><span class="sxs-lookup"><span data-stu-id="cac70-103">Contains values that indicate the impact of a failure when a specific memory allocation has been requested but cannot be satisfied.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cac70-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cac70-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eTaskCritical      = 0,  
    eAppDomainCritical = 1,  
    eProcessCritical   = 2  
} EMemoryCriticalLevel;  
```  
  
## <a name="members"></a><span data-ttu-id="cac70-105">Члены</span><span class="sxs-lookup"><span data-stu-id="cac70-105">Members</span></span>  
  
|<span data-ttu-id="cac70-106">Член</span><span class="sxs-lookup"><span data-stu-id="cac70-106">Member</span></span>|<span data-ttu-id="cac70-107">Описание</span><span class="sxs-lookup"><span data-stu-id="cac70-107">Description</span></span>|  
|------------|-----------------|  
|`eAppDomainCritical`|<span data-ttu-id="cac70-108">Указывает, что выделение является критически важным для исполнения управляемого кода в домене, который запросил выделение.</span><span class="sxs-lookup"><span data-stu-id="cac70-108">Indicates that the allocation is critical for executing managed code in the domain that has requested the allocation.</span></span> <span data-ttu-id="cac70-109">Если память не может быть выделена, среда CLR не может гарантировать, что домен будет использоваться.</span><span class="sxs-lookup"><span data-stu-id="cac70-109">If memory cannot be allocated, the CLR cannot guarantee that the domain is still usable.</span></span> <span data-ttu-id="cac70-110">Основное приложение принимает решение, какое действие следует предпринять, если выделение не может быть удовлетворено.</span><span class="sxs-lookup"><span data-stu-id="cac70-110">The host decides what action to take when the allocation cannot be satisfied.</span></span> <span data-ttu-id="cac70-111">Он может дать среде CLR команду на автоматическое прерывание `AppDomain` или разрешить ее выполнение путем вызова методов в [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="cac70-111">It can instruct the CLR to abort the `AppDomain` automatically, or allow it to keep running by calling methods on [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md).</span></span>|  
|`eProcessCritical`|<span data-ttu-id="cac70-112">Указывает, что выделение является критически важным для выполнения управляемого кода в процессе.</span><span class="sxs-lookup"><span data-stu-id="cac70-112">Indicates that the allocation is critical to the execution of managed code in the process.</span></span> <span data-ttu-id="cac70-113">Это значение используется при запуске и при запуске методов завершения.</span><span class="sxs-lookup"><span data-stu-id="cac70-113">This value is used during startup and when running finalizers.</span></span> <span data-ttu-id="cac70-114">Если память не может быть выделена, среда CLR не может работать в процессе.</span><span class="sxs-lookup"><span data-stu-id="cac70-114">If memory cannot be allocated, the CLR cannot operate in the process.</span></span> <span data-ttu-id="cac70-115">Если выделение завершается неудачей, среда CLR фактически отключается.</span><span class="sxs-lookup"><span data-stu-id="cac70-115">If the allocation fails, the CLR is effectively disabled.</span></span> <span data-ttu-id="cac70-116">Все последующие вызовы среды CLR завершаются сбоем с HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="cac70-116">All subsequent calls into the CLR fail with HOST_E_CLRNOTAVAILABLE.</span></span>|  
|`eTaskCritical`|<span data-ttu-id="cac70-117">Указывает, что выделение является критически важным для выполнения задачи, которая запросила выделение.</span><span class="sxs-lookup"><span data-stu-id="cac70-117">Indicates that the allocation is critical to running the task that has requested the allocation.</span></span> <span data-ttu-id="cac70-118">Если память не может быть выделена, среда CLR не может гарантировать, что задача может быть выполнена.</span><span class="sxs-lookup"><span data-stu-id="cac70-118">If memory cannot be allocated, the CLR cannot guarantee that the task can be executed.</span></span> <span data-ttu-id="cac70-119">В случае сбоя среда CLR вызывает <xref:System.Threading.ThreadAbortException> в системном потоке физической операции.</span><span class="sxs-lookup"><span data-stu-id="cac70-119">In the event of failure, the CLR raises a <xref:System.Threading.ThreadAbortException> on the physical operation system thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cac70-120">Заметки</span><span class="sxs-lookup"><span data-stu-id="cac70-120">Remarks</span></span>  
 <span data-ttu-id="cac70-121">Методы выделения памяти, определенные в интерфейсах [IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md) и [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) , принимают параметр этого типа.</span><span class="sxs-lookup"><span data-stu-id="cac70-121">The memory allocation methods defined in the [IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md) and [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) interfaces take a parameter of this type.</span></span> <span data-ttu-id="cac70-122">В зависимости от серьезности сбоя узел может решить, следует ли немедленно выполнить запрос на выделение или подождать, пока он не будет удовлетворен.</span><span class="sxs-lookup"><span data-stu-id="cac70-122">Depending upon the severity of a failure, a host can decide whether to fail the allocation request immediately or to wait until it can be satisfied.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cac70-123">Требования</span><span class="sxs-lookup"><span data-stu-id="cac70-123">Requirements</span></span>  
 <span data-ttu-id="cac70-124">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cac70-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cac70-125">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="cac70-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cac70-126">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="cac70-126">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cac70-127">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cac70-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cac70-128">См. также</span><span class="sxs-lookup"><span data-stu-id="cac70-128">See also</span></span>

- [<span data-ttu-id="cac70-129">Интерфейс ICLRMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="cac70-129">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
- [<span data-ttu-id="cac70-130">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="cac70-130">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
