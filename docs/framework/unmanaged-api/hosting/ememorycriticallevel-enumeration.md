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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: acf4f3f582e417c5e7b814622986427f996796ce
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432535"
---
# <a name="ememorycriticallevel-enumeration"></a><span data-ttu-id="2abc1-102">Перечисление EMemoryCriticalLevel</span><span class="sxs-lookup"><span data-stu-id="2abc1-102">EMemoryCriticalLevel Enumeration</span></span>
<span data-ttu-id="2abc1-103">Содержит значения, указывающие влияние сбоя в случае, когда был запрошен определенного выделения памяти, но не может быть удовлетворен.</span><span class="sxs-lookup"><span data-stu-id="2abc1-103">Contains values that indicate the impact of a failure when a specific memory allocation has been requested but cannot be satisfied.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2abc1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2abc1-104">Syntax</span></span>  
  
```  
typedef enum {  
    eTaskCritical      = 0,  
    eAppDomainCritical = 1,  
    eProcessCritical   = 2  
} EMemoryCriticalLevel;  
```  
  
## <a name="members"></a><span data-ttu-id="2abc1-105">Участники</span><span class="sxs-lookup"><span data-stu-id="2abc1-105">Members</span></span>  
  
|<span data-ttu-id="2abc1-106">Член</span><span class="sxs-lookup"><span data-stu-id="2abc1-106">Member</span></span>|<span data-ttu-id="2abc1-107">Описание</span><span class="sxs-lookup"><span data-stu-id="2abc1-107">Description</span></span>|  
|------------|-----------------|  
|`eAppDomainCritical`|<span data-ttu-id="2abc1-108">Указывает, что выделение крайне важен для выполнения управляемого кода в домене, который запросил распределения.</span><span class="sxs-lookup"><span data-stu-id="2abc1-108">Indicates that the allocation is critical for executing managed code in the domain that has requested the allocation.</span></span> <span data-ttu-id="2abc1-109">Если не удается выделить память, среда CLR не может гарантировать, что домен является по-прежнему можно использовать.</span><span class="sxs-lookup"><span data-stu-id="2abc1-109">If memory cannot be allocated, the CLR cannot guarantee that the domain is still usable.</span></span> <span data-ttu-id="2abc1-110">Основное приложение выбирает, какие действия предпринять, если выделение не может быть удовлетворено.</span><span class="sxs-lookup"><span data-stu-id="2abc1-110">The host decides what action to take when the allocation cannot be satisfied.</span></span> <span data-ttu-id="2abc1-111">Его можно указать среде CLR прерывание `AppDomain` автоматически, или разрешить его выполнение, вызывая методы [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="2abc1-111">It can instruct the CLR to abort the `AppDomain` automatically, or allow it to keep running by calling methods on [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md).</span></span>|  
|`eProcessCritical`|<span data-ttu-id="2abc1-112">Указывает, что выделение крайне важен для выполнения управляемого кода в процессе.</span><span class="sxs-lookup"><span data-stu-id="2abc1-112">Indicates that the allocation is critical to the execution of managed code in the process.</span></span> <span data-ttu-id="2abc1-113">Это значение используется во время запуска и при выполнении методов завершения.</span><span class="sxs-lookup"><span data-stu-id="2abc1-113">This value is used during startup and when running finalizers.</span></span> <span data-ttu-id="2abc1-114">Если не удается выделить память, среда CLR не может работать в процессе.</span><span class="sxs-lookup"><span data-stu-id="2abc1-114">If memory cannot be allocated, the CLR cannot operate in the process.</span></span> <span data-ttu-id="2abc1-115">В случае сбоя, среда CLR полностью отключается.</span><span class="sxs-lookup"><span data-stu-id="2abc1-115">If the allocation fails, the CLR is effectively disabled.</span></span> <span data-ttu-id="2abc1-116">Все последующие вызовы к CLR завершаться значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2abc1-116">All subsequent calls into the CLR fail with HOST_E_CLRNOTAVAILABLE.</span></span>|  
|`eTaskCritical`|<span data-ttu-id="2abc1-117">Указывает, что выделение крайне важен для выполнения задачи, запросившей выделение.</span><span class="sxs-lookup"><span data-stu-id="2abc1-117">Indicates that the allocation is critical to running the task that has requested the allocation.</span></span> <span data-ttu-id="2abc1-118">Если не удается выделить память, среда CLR не гарантирует выполнения задачи.</span><span class="sxs-lookup"><span data-stu-id="2abc1-118">If memory cannot be allocated, the CLR cannot guarantee that the task can be executed.</span></span> <span data-ttu-id="2abc1-119">В случае сбоя, среда CLR вызывает <xref:System.Threading.ThreadAbortException> в потоке физическая операция системы.</span><span class="sxs-lookup"><span data-stu-id="2abc1-119">In the event of failure, the CLR raises a <xref:System.Threading.ThreadAbortException> on the physical operation system thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2abc1-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="2abc1-120">Remarks</span></span>  
 <span data-ttu-id="2abc1-121">Методы распределения памяти, определенные в [IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md) и [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) интерфейсы могут принимать параметр этого типа.</span><span class="sxs-lookup"><span data-stu-id="2abc1-121">The memory allocation methods defined in the [IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md) and [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) interfaces take a parameter of this type.</span></span> <span data-ttu-id="2abc1-122">В зависимости от серьезности сбоя узла можно моментально завершаются ошибкой запросов на выделение или подождите, пока не может быть удовлетворено.</span><span class="sxs-lookup"><span data-stu-id="2abc1-122">Depending upon the severity of a failure, a host can decide whether to fail the allocation request immediately or to wait until it can be satisfied.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2abc1-123">Требования</span><span class="sxs-lookup"><span data-stu-id="2abc1-123">Requirements</span></span>  
 <span data-ttu-id="2abc1-124">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2abc1-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2abc1-125">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2abc1-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2abc1-126">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2abc1-126">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2abc1-127">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2abc1-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2abc1-128">См. также</span><span class="sxs-lookup"><span data-stu-id="2abc1-128">See Also</span></span>  
 [<span data-ttu-id="2abc1-129">Интерфейс ICLRMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="2abc1-129">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)  
 [<span data-ttu-id="2abc1-130">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="2abc1-130">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
