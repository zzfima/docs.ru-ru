---
title: "Перечисление EPolicyAction"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EPolicyAction
api_location: mscoree.dll
api_type: COM
f1_keywords: EPolicyAction
helpviewer_keywords: EPolicyAction enumeration [.NET Framework hosting]
ms.assetid: 72dd76ba-239e-45ac-9ded-318fb07d6c6d
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f2c3a4138adfa354de07bc6df4e51d7697598b67
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="epolicyaction-enumeration"></a><span data-ttu-id="ddad5-102">Перечисление EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="ddad5-102">EPolicyAction Enumeration</span></span>
<span data-ttu-id="ddad5-103">Описывает действия политики, основное приложение может задать для операций, описанных [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) и сбоев, описанных [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="ddad5-103">Describes the policy actions the host can set for operations described by [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) and failures described by [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddad5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ddad5-104">Syntax</span></span>  
  
```  
typedef enum {  
    eNoAction,  
    eThrowException,  
    eAbortThread,  
    eRudeAbortThread,  
    eUnloadAppDomain,  
    eRudeUnloadAppDomain,  
    eExitProcess,  
    eFastExitProcess,  
    eRudeExitProcess,  
    eDisableRuntime  
} EPolicyAction;  
```  
  
## <a name="members"></a><span data-ttu-id="ddad5-105">Члены</span><span class="sxs-lookup"><span data-stu-id="ddad5-105">Members</span></span>  
  
|<span data-ttu-id="ddad5-106">Член</span><span class="sxs-lookup"><span data-stu-id="ddad5-106">Member</span></span>|<span data-ttu-id="ddad5-107">Описание</span><span class="sxs-lookup"><span data-stu-id="ddad5-107">Description</span></span>|  
|------------|-----------------|  
|`eAbortThread`|<span data-ttu-id="ddad5-108">Указывает, общеязыковой среды выполнения (CLR) следует прервать надлежащим образом поток.</span><span class="sxs-lookup"><span data-stu-id="ddad5-108">Specifies that the common language runtime (CLR) should abort the thread gracefully.</span></span> <span data-ttu-id="ddad5-109">Прерывание надлежащим образом предполагает попытки выполнить все `finally` блокирует любой `catch` , связанных с прерывания потока и методы завершения.</span><span class="sxs-lookup"><span data-stu-id="ddad5-109">A graceful abort includes attempts to run all `finally` blocks, any `catch` blocks related to thread aborts, and finalizers.</span></span>|  
|`eDisableRuntime`|<span data-ttu-id="ddad5-110">Указывает, что среда CLR должна перейти в отключенное состояние.</span><span class="sxs-lookup"><span data-stu-id="ddad5-110">Specifies that the CLR should enter a disabled state.</span></span> <span data-ttu-id="ddad5-111">Дальнейшая управляемый код может выполняться в соответствующий процесс и потоки блокируются попадающие в CLR.</span><span class="sxs-lookup"><span data-stu-id="ddad5-111">No further managed code can be executed in the affected process, and threads are blocked from entering the CLR.</span></span>|  
|`eExitProcess`|<span data-ttu-id="ddad5-112">Указывает, что среда CLR следует выполнять надлежащего выхода из процесса, включая выполнение методов завершения и очистки и ведение журнала операций.</span><span class="sxs-lookup"><span data-stu-id="ddad5-112">Specifies that the CLR should attempt a graceful exit of the process, including running finalizers and performing cleanup and logging operations.</span></span>|  
|`eFastExitProcess`|<span data-ttu-id="ddad5-113">Указывает, что среда CLR должна выхода из процесса немедленно, без выполнения методов завершения или очистки и ведение журнала операций.</span><span class="sxs-lookup"><span data-stu-id="ddad5-113">Specifies that the CLR should exit the process immediately, without running finalizers or performing cleanup and logging operations.</span></span> <span data-ttu-id="ddad5-114">При этом отладчику отправляется уведомление отладчика.</span><span class="sxs-lookup"><span data-stu-id="ddad5-114">Nowever, notification is sent to the debugger.</span></span>|  
|`eNoAction`|<span data-ttu-id="ddad5-115">Указывает, что никакие действия не выполнены.</span><span class="sxs-lookup"><span data-stu-id="ddad5-115">Specifies that no action should be taken.</span></span>|  
|`eRudeAbortThread`|<span data-ttu-id="ddad5-116">Указывает, что среда CLR выполнение грубое прерывание потока.</span><span class="sxs-lookup"><span data-stu-id="ddad5-116">Specifies that the CLR should perform a rude thread abort.</span></span> <span data-ttu-id="ddad5-117">Только те `catch` и `finally` блоки, отмеченные <xref:System.EnterpriseServices.MustRunInClientContextAttribute> выполняются.</span><span class="sxs-lookup"><span data-stu-id="ddad5-117">Only those `catch` and `finally` blocks marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span>|  
|`eRudeExitProcess`|<span data-ttu-id="ddad5-118">Указывает, что среда CLR должна выхода из процесса без выполнения методов завершения или ведение журнала операций.</span><span class="sxs-lookup"><span data-stu-id="ddad5-118">Specifies that the CLR should exit the process without running finalizers or logging operations.</span></span>|  
|`eRudeUnloadAppDomain`|<span data-ttu-id="ddad5-119">Указывает выполнение с CLR грубые выгрузку <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="ddad5-119">Specifies that the CLR should perform a rude unload of the <xref:System.AppDomain>.</span></span> <span data-ttu-id="ddad5-120">Методы завершения только отмеченные <xref:System.EnterpriseServices.MustRunInClientContextAttribute> выполняются.</span><span class="sxs-lookup"><span data-stu-id="ddad5-120">Only finalizers marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span> <span data-ttu-id="ddad5-121">Аналогичным образом, все потоки с этим <xref:System.AppDomain> их стека получать `ThreadAbortException`, но только те, которые `catch` и `finally` блоки, отмеченные <xref:System.EnterpriseServices.MustRunInClientContextAttribute> выполняются.</span><span class="sxs-lookup"><span data-stu-id="ddad5-121">Similarly, all threads with this <xref:System.AppDomain> in their stack receive a `ThreadAbortException`, but only those `catch` and `finally` blocks marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span>|  
|`eThrowException`|<span data-ttu-id="ddad5-122">Указывает, что соответствующий условию, например о нехватке памяти, переполнение буфера и т. д. должны быть исключение.</span><span class="sxs-lookup"><span data-stu-id="ddad5-122">Specifies that an exception appropriate to the condition, such as out-of-memory, buffer overflow, and so forth, should be thrown.</span></span>|  
|`eUnloadAppDomain`|<span data-ttu-id="ddad5-123">Указывает, что <xref:System.AppDomain> должна быть выгружена.</span><span class="sxs-lookup"><span data-stu-id="ddad5-123">Specifies that the <xref:System.AppDomain> should be unloaded.</span></span> <span data-ttu-id="ddad5-124">Среда CLR пытается запустить методы завершения.</span><span class="sxs-lookup"><span data-stu-id="ddad5-124">The CLR attempts to run finalizers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ddad5-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="ddad5-125">Remarks</span></span>  
 <span data-ttu-id="ddad5-126">Основное приложение задает действия в рамках политики путем вызова методов [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md) интерфейса.</span><span class="sxs-lookup"><span data-stu-id="ddad5-126">The host sets policy actions by calling methods of the [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md) interface.</span></span> <span data-ttu-id="ddad5-127">Сведения о принудительном и надлежащих см. в разделе [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) перечисления.</span><span class="sxs-lookup"><span data-stu-id="ddad5-127">For information about rude and graceful aborts, see the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ddad5-128">Требования</span><span class="sxs-lookup"><span data-stu-id="ddad5-128">Requirements</span></span>  
 <span data-ttu-id="ddad5-129">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ddad5-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ddad5-130">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ddad5-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ddad5-131">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ddad5-131">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ddad5-132">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ddad5-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddad5-133">См. также</span><span class="sxs-lookup"><span data-stu-id="ddad5-133">See Also</span></span>  
 [<span data-ttu-id="ddad5-134">EClrFailure-перечисление</span><span class="sxs-lookup"><span data-stu-id="ddad5-134">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [<span data-ttu-id="ddad5-135">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="ddad5-135">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="ddad5-136">IHostPolicyManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="ddad5-136">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 [<span data-ttu-id="ddad5-137">Перечисления размещения</span><span class="sxs-lookup"><span data-stu-id="ddad5-137">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
