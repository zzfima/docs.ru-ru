---
title: Перечисление EPolicyAction
ms.date: 03/30/2017
api_name:
- EPolicyAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EPolicyAction
helpviewer_keywords:
- EPolicyAction enumeration [.NET Framework hosting]
ms.assetid: 72dd76ba-239e-45ac-9ded-318fb07d6c6d
topic_type:
- apiref
ms.openlocfilehash: eaba6b2166a82cfe825ffb98db515e24d4656462
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138229"
---
# <a name="epolicyaction-enumeration"></a><span data-ttu-id="16108-102">Перечисление EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="16108-102">EPolicyAction Enumeration</span></span>
<span data-ttu-id="16108-103">Описание действий политики, которые узел может задать для операций, описанных в [еклроператион](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) и ошибках, описанных в [еклрфаилуре](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="16108-103">Describes the policy actions the host can set for operations described by [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) and failures described by [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16108-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="16108-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="16108-105">Члены</span><span class="sxs-lookup"><span data-stu-id="16108-105">Members</span></span>  
  
|<span data-ttu-id="16108-106">Член</span><span class="sxs-lookup"><span data-stu-id="16108-106">Member</span></span>|<span data-ttu-id="16108-107">Описание</span><span class="sxs-lookup"><span data-stu-id="16108-107">Description</span></span>|  
|------------|-----------------|  
|`eAbortThread`|<span data-ttu-id="16108-108">Указывает, что среда CLR должна корректно прерывать поток.</span><span class="sxs-lookup"><span data-stu-id="16108-108">Specifies that the common language runtime (CLR) should abort the thread gracefully.</span></span> <span data-ttu-id="16108-109">Корректное прерывание включает попытки запуска всех блоков `finally`, любых блоков `catch`, связанных с пределами потоков и методов завершения.</span><span class="sxs-lookup"><span data-stu-id="16108-109">A graceful abort includes attempts to run all `finally` blocks, any `catch` blocks related to thread aborts, and finalizers.</span></span>|  
|`eDisableRuntime`|<span data-ttu-id="16108-110">Указывает, что среда CLR должна перейти в отключенное состояние.</span><span class="sxs-lookup"><span data-stu-id="16108-110">Specifies that the CLR should enter a disabled state.</span></span> <span data-ttu-id="16108-111">В затронутом процессе не может быть выполнен дальнейший управляемый код, и потокам не удастся войти в среду CLR.</span><span class="sxs-lookup"><span data-stu-id="16108-111">No further managed code can be executed in the affected process, and threads are blocked from entering the CLR.</span></span>|  
|`eExitProcess`|<span data-ttu-id="16108-112">Указывает, что среда CLR должна попытаться корректно выйти из процесса, включая запуск методов завершения и выполнение операций очистки и ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="16108-112">Specifies that the CLR should attempt a graceful exit of the process, including running finalizers and performing cleanup and logging operations.</span></span>|  
|`eFastExitProcess`|<span data-ttu-id="16108-113">Указывает, что среда CLR должна немедленно выйти из процесса, не запуская методы завершения, а также выполнять операции очистки и ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="16108-113">Specifies that the CLR should exit the process immediately, without running finalizers or performing cleanup and logging operations.</span></span> <span data-ttu-id="16108-114">Однако уведомление отправляется в отладчик.</span><span class="sxs-lookup"><span data-stu-id="16108-114">However, notification is sent to the debugger.</span></span>|  
|`eNoAction`|<span data-ttu-id="16108-115">Указывает, что никакие действия не следует предпринимать.</span><span class="sxs-lookup"><span data-stu-id="16108-115">Specifies that no action should be taken.</span></span>|  
|`eRudeAbortThread`|<span data-ttu-id="16108-116">Указывает, что среда CLR должна выполнять грубое прерывание потока.</span><span class="sxs-lookup"><span data-stu-id="16108-116">Specifies that the CLR should perform a rude thread abort.</span></span> <span data-ttu-id="16108-117">Выполняются только блоки `catch` и `finally`, помеченные <xref:System.EnterpriseServices.MustRunInClientContextAttribute>.</span><span class="sxs-lookup"><span data-stu-id="16108-117">Only those `catch` and `finally` blocks marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span>|  
|`eRudeExitProcess`|<span data-ttu-id="16108-118">Указывает, что среда CLR должна выйти из процесса без запуска методов завершения или ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="16108-118">Specifies that the CLR should exit the process without running finalizers or logging operations.</span></span>|  
|`eRudeUnloadAppDomain`|<span data-ttu-id="16108-119">Указывает, что среда CLR должна выполнить грубую выгрузку <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="16108-119">Specifies that the CLR should perform a rude unload of the <xref:System.AppDomain>.</span></span> <span data-ttu-id="16108-120">Выполняются только методы завершения, помеченные <xref:System.EnterpriseServices.MustRunInClientContextAttribute>.</span><span class="sxs-lookup"><span data-stu-id="16108-120">Only finalizers marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span> <span data-ttu-id="16108-121">Аналогично, все потоки с этим <xref:System.AppDomain> в стеке получают `ThreadAbortException`, но выполняются только блоки `catch` и `finally`, помеченные <xref:System.EnterpriseServices.MustRunInClientContextAttribute>.</span><span class="sxs-lookup"><span data-stu-id="16108-121">Similarly, all threads with this <xref:System.AppDomain> in their stack receive a `ThreadAbortException`, but only those `catch` and `finally` blocks marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span>|  
|`eThrowException`|<span data-ttu-id="16108-122">Указывает, что должно быть создано исключение, соответствующее условию, например нехватки памяти, переполнение буфера и т. д.</span><span class="sxs-lookup"><span data-stu-id="16108-122">Specifies that an exception appropriate to the condition, such as out-of-memory, buffer overflow, and so forth, should be thrown.</span></span>|  
|`eUnloadAppDomain`|<span data-ttu-id="16108-123">Указывает, что <xref:System.AppDomain> должны быть выгружены.</span><span class="sxs-lookup"><span data-stu-id="16108-123">Specifies that the <xref:System.AppDomain> should be unloaded.</span></span> <span data-ttu-id="16108-124">Среда CLR пытается запустить методы завершения.</span><span class="sxs-lookup"><span data-stu-id="16108-124">The CLR attempts to run finalizers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="16108-125">Заметки</span><span class="sxs-lookup"><span data-stu-id="16108-125">Remarks</span></span>  
 <span data-ttu-id="16108-126">Узел задает действия политики, вызывая методы интерфейса [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="16108-126">The host sets policy actions by calling methods of the [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md) interface.</span></span> <span data-ttu-id="16108-127">Сведения о принудительном и корректном аварийном завершении см. в разделе Перечисление [еклроператион](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="16108-127">For information about rude and graceful aborts, see the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16108-128">Требования</span><span class="sxs-lookup"><span data-stu-id="16108-128">Requirements</span></span>  
 <span data-ttu-id="16108-129">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16108-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16108-130">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="16108-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="16108-131">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="16108-131">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="16108-132">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16108-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16108-133">См. также</span><span class="sxs-lookup"><span data-stu-id="16108-133">See also</span></span>

- [<span data-ttu-id="16108-134">Перечисление EClrFailure</span><span class="sxs-lookup"><span data-stu-id="16108-134">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="16108-135">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="16108-135">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="16108-136">Интерфейс IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="16108-136">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [<span data-ttu-id="16108-137">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="16108-137">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
