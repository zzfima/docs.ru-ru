---
title: Перечисление EClrOperation
ms.date: 03/30/2017
api_name:
- EClrOperation
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrOperation
helpviewer_keywords:
- EClrOperation enumeration [.NET Framework hosting]
ms.assetid: 5aef6808-5aac-4b2f-a2c7-fee1575c55ed
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6244f01a78f08da839b233c3313f2fd6bff44b12
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54675084"
---
# <a name="eclroperation-enumeration"></a><span data-ttu-id="38fa7-102">Перечисление EClrOperation</span><span class="sxs-lookup"><span data-stu-id="38fa7-102">EClrOperation Enumeration</span></span>
<span data-ttu-id="38fa7-103">Описывает набор операций, для которых узел может применять действия политики.</span><span class="sxs-lookup"><span data-stu-id="38fa7-103">Describes the set of operations for which a host can apply policy actions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38fa7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="38fa7-104">Syntax</span></span>  
  
```  
typedef enum {  
    OPR_ThreadAbort,  
    OPR_ThreadRudeAbortInNonCriticalRegion,  
    OPR_ThreadRudeAbortInCriticalRegion,  
    OPR_AppDomainUnload,  
    OPR_AppDomainRudeUnload,  
    OPR_ProcessExit,  
    OPR_FinalizerRun  
} EClrOperation;  
```  
  
## <a name="members"></a><span data-ttu-id="38fa7-105">Участники</span><span class="sxs-lookup"><span data-stu-id="38fa7-105">Members</span></span>  
  
|<span data-ttu-id="38fa7-106">Член</span><span class="sxs-lookup"><span data-stu-id="38fa7-106">Member</span></span>|<span data-ttu-id="38fa7-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="38fa7-107">Description</span></span>|  
|------------|-----------------|  
|`OPR_AppDomainRudeUnload`|<span data-ttu-id="38fa7-108">Узел может указать политику действий, выполняемых при <xref:System.AppDomain> выгружается образом ненадлежащими (принудительными).</span><span class="sxs-lookup"><span data-stu-id="38fa7-108">The host can specify policy actions to be taken when an <xref:System.AppDomain> is unloaded in a non-graceful (rude) manner.</span></span>|  
|`OPR_AppDomainUnload`|<span data-ttu-id="38fa7-109">Узел может указать политику действий, выполняемых при <xref:System.AppDomain> выгружается.</span><span class="sxs-lookup"><span data-stu-id="38fa7-109">The host can specify policy actions to be taken when an <xref:System.AppDomain> is unloaded.</span></span>|  
|`OPR_FinalizerRun`|<span data-ttu-id="38fa7-110">Узел может указать действия политики, которые необходимо выполнить при запуске метода завершения.</span><span class="sxs-lookup"><span data-stu-id="38fa7-110">The host can specify policy actions to be taken when finalizers run.</span></span>|  
|`OPR_ProcessExit`|<span data-ttu-id="38fa7-111">Узел может указать действия политики, которые должны выполняться при завершении процесса.</span><span class="sxs-lookup"><span data-stu-id="38fa7-111">The host can specify policy actions to be taken when the process exits.</span></span>|  
|`OPR_ThreadAbort`|<span data-ttu-id="38fa7-112">Узел может указать действия политики, которые должны выполняться при прерывании потока.</span><span class="sxs-lookup"><span data-stu-id="38fa7-112">The host can specify policy actions to be taken when a thread is aborted.</span></span>|  
|`OPR_ThreadRudeAbortInCriticalRegion`|<span data-ttu-id="38fa7-113">Узел может указать действия политики, которые должны выполняться при грубое прерывание потока происходит в критической области кода.</span><span class="sxs-lookup"><span data-stu-id="38fa7-113">The host can specify policy actions to be taken when a rude thread abort occurs in a critical region of code.</span></span>|  
|`OPR_ThreadRudeAbortInNonCriticalRegion`|<span data-ttu-id="38fa7-114">Узел может указать политики действия быть при грубое прерывание потока происходит в некритические области кода.</span><span class="sxs-lookup"><span data-stu-id="38fa7-114">The host can specify policy actions to be take when a rude thread abort occurs in a non-critical region of code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="38fa7-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="38fa7-115">Remarks</span></span>  
 <span data-ttu-id="38fa7-116">Инфраструктуре надежности среды выполнения (CLR) различает прерываний и ресурсов ошибок выделения ресурсов, которые происходят в критических областях кода, и те, которые возникают в некритические областей кода.</span><span class="sxs-lookup"><span data-stu-id="38fa7-116">The common language runtime (CLR) reliability infrastructure distinguishes between aborts and resource allocation failures that occur in critical regions of code and those that occur in non-critical regions of code.</span></span> <span data-ttu-id="38fa7-117">Это различие позволяет основным приложениям задавать различные политики в зависимости от того, где происходит сбой в коде.</span><span class="sxs-lookup"><span data-stu-id="38fa7-117">This distinction is designed to allow hosts to set different policies depending on where a failure occurs in the code.</span></span>  
  
 <span data-ttu-id="38fa7-118">Объект *критической области кода* любого места, где среда CLR не может гарантировать, что прерывание выполнения задачи или сбой при выполнении запроса для ресурсов повлияет только на текущую задачу.</span><span class="sxs-lookup"><span data-stu-id="38fa7-118">A *critical region of code* is any space where the CLR cannot guarantee that aborting a task or failing to complete a request for resources will affect only the current task.</span></span> <span data-ttu-id="38fa7-119">Например, если задача заблокирована и получает значение HRESULT, указывающее на сбой при выполнении запроса на выделение памяти, недостаточно просто прервать эту задачу, чтобы убедиться в стабильной работе <xref:System.AppDomain>, так как <xref:System.AppDomain> может содержать другие элементы задачи, ожидающие ту же блокировку.</span><span class="sxs-lookup"><span data-stu-id="38fa7-119">For example, if a task is holding a lock and receives an HRESULT that indicates failure upon making a memory allocation request, it is insufficient simply to abort that task to ensure the stability of the <xref:System.AppDomain>, because the <xref:System.AppDomain> might contain other tasks waiting for the same lock.</span></span> <span data-ttu-id="38fa7-120">Прекращение выполнения текущей задачи может привести другие задачи, чтобы перестать отвечать на запросы (или зависанию) неопределенное время.</span><span class="sxs-lookup"><span data-stu-id="38fa7-120">To abandon the current task might cause those other tasks to stop responding (or hang) indefinitely.</span></span> <span data-ttu-id="38fa7-121">В этом случае узел должен возможность выгрузить весь <xref:System.AppDomain> вместо того чтобы нестабильной работы риска.</span><span class="sxs-lookup"><span data-stu-id="38fa7-121">In such a case, the host needs the ability to unload the entire <xref:System.AppDomain> rather than risk potential instability.</span></span>  
  
 <span data-ttu-id="38fa7-122">Объект *некритические области кода*, с другой стороны, — это область, в которой среда CLR может гарантировать, что прерывание или сбой повлияют только задачи, на котором произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="38fa7-122">A *non-critical region of code*, on the other hand, is a region where the CLR can guarantee that an abort or a failure will affect only the task upon which the error occurs.</span></span>  
  
 <span data-ttu-id="38fa7-123">Среда CLR также различает нормальные, так и ненадлежащими (принудительными) прерываниями.</span><span class="sxs-lookup"><span data-stu-id="38fa7-123">The CLR also distinguishes between graceful and non-graceful (rude) aborts.</span></span> <span data-ttu-id="38fa7-124">В общем случае обычный или корректное прерывание делает все возможное для выполнения подпрограммы обработки исключений и методы завершения перед прекращением задачу, хотя грубые прерывания не обеспечивает таких.</span><span class="sxs-lookup"><span data-stu-id="38fa7-124">In general, a normal or graceful abort makes every effort to run exception-handling routines and finalizers before aborting a task, while a rude abort makes no such guarantees.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38fa7-125">Требования</span><span class="sxs-lookup"><span data-stu-id="38fa7-125">Requirements</span></span>  
 <span data-ttu-id="38fa7-126">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38fa7-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38fa7-127">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="38fa7-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="38fa7-128">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="38fa7-128">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="38fa7-129">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38fa7-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38fa7-130">См. также</span><span class="sxs-lookup"><span data-stu-id="38fa7-130">See also</span></span>
- [<span data-ttu-id="38fa7-131">Перечисление EClrFailure</span><span class="sxs-lookup"><span data-stu-id="38fa7-131">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="38fa7-132">Перечисление EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="38fa7-132">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="38fa7-133">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="38fa7-133">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="38fa7-134">Интерфейс IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="38fa7-134">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [<span data-ttu-id="38fa7-135">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="38fa7-135">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
