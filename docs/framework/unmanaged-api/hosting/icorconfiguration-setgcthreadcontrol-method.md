---
title: Метод ICorConfiguration::SetGCThreadControl
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetGCThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCThreadControl
helpviewer_keywords:
- ICorConfiguration::SetGCThreadControl method [.NET Framework hosting]
- SetGCThreadControl method [.NET Framework hosting]
ms.assetid: 72e38e61-3d56-4ae3-b8f6-0ab7922aaf11
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b50c87efeb8ad2311a75886da677a9dc901bca1b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763234"
---
# <a name="icorconfigurationsetgcthreadcontrol-method"></a><span data-ttu-id="bda63-102">Метод ICorConfiguration::SetGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="bda63-102">ICorConfiguration::SetGCThreadControl Method</span></span>
<span data-ttu-id="bda63-103">Задает интерфейс обратного вызова для планирования потоков без выполнения задач, которые в противном случае был бы заблокирован для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="bda63-103">Sets the callback interface for scheduling threads for non-runtime tasks that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bda63-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bda63-104">Syntax</span></span>  
  
```  
HRESULT SetGCThreadControl (  
    [in] IGCThreadControl* pGCThreadControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bda63-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bda63-105">Parameters</span></span>  
 `pGCThreadControl`  
 <span data-ttu-id="bda63-106">[in] Указатель на [IGCThreadControl](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md) объект, который уведомляет ведущее приложение о приостановки потоков для задач, отличных от среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="bda63-106">[in] A pointer to an [IGCThreadControl](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md) object that notifies the host about the suspension of threads for non-runtime tasks.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bda63-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="bda63-107">Remarks</span></span>  
 <span data-ttu-id="bda63-108">Выбрать узел в [IGCThreadControl::ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md) обратного вызова необходимость повторного планирования потока.</span><span class="sxs-lookup"><span data-stu-id="bda63-108">The host may choose within the [IGCThreadControl::ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md) callback whether to reschedule a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bda63-109">Требования</span><span class="sxs-lookup"><span data-stu-id="bda63-109">Requirements</span></span>  
 <span data-ttu-id="bda63-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bda63-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bda63-111">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bda63-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bda63-112">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bda63-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bda63-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bda63-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bda63-114">См. также</span><span class="sxs-lookup"><span data-stu-id="bda63-114">See also</span></span>

- [<span data-ttu-id="bda63-115">Интерфейс ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="bda63-115">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
