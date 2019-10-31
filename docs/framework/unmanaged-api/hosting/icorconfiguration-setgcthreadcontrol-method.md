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
ms.openlocfilehash: f43ee6d9a3832fca1766ec27c9f02d1aab2f5b8d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127761"
---
# <a name="icorconfigurationsetgcthreadcontrol-method"></a><span data-ttu-id="20570-102">Метод ICorConfiguration::SetGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="20570-102">ICorConfiguration::SetGCThreadControl Method</span></span>
<span data-ttu-id="20570-103">Задает интерфейс обратного вызова для потоков планирования для задач, не относящихся к среде выполнения, которые в противном случае были бы заблокированы для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="20570-103">Sets the callback interface for scheduling threads for non-runtime tasks that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20570-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="20570-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCThreadControl (  
    [in] IGCThreadControl* pGCThreadControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20570-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="20570-105">Parameters</span></span>  
 `pGCThreadControl`  
 <span data-ttu-id="20570-106">окне Указатель на объект [IGCThreadControl](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md) , который уведомляет основное приложение о приостановке потоков для задач, не относящихся к среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="20570-106">[in] A pointer to an [IGCThreadControl](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md) object that notifies the host about the suspension of threads for non-runtime tasks.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="20570-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="20570-107">Remarks</span></span>  
 <span data-ttu-id="20570-108">Узел может выбрать один из обратных вызовов [IGCThreadControl:: среадисблоккингфорсуспенсион](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md) , следует ли перепланировать поток.</span><span class="sxs-lookup"><span data-stu-id="20570-108">The host may choose within the [IGCThreadControl::ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md) callback whether to reschedule a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20570-109">Требования</span><span class="sxs-lookup"><span data-stu-id="20570-109">Requirements</span></span>  
 <span data-ttu-id="20570-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20570-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20570-111">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="20570-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="20570-112">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="20570-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="20570-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20570-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20570-114">См. также</span><span class="sxs-lookup"><span data-stu-id="20570-114">See also</span></span>

- [<span data-ttu-id="20570-115">Интерфейс ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="20570-115">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
