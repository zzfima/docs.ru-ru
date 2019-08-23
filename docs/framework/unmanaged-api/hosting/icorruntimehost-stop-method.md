---
title: Метод ICorRuntimeHost::Stop
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.Stop
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::Stop
helpviewer_keywords:
- Stop method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::Stop method [.NET Framework hosting]
ms.assetid: 46a0d450-b516-4bef-8b71-8d3bf265cbed
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca51b87e7afc8e9e48d541a32b3bd60a19a5ff70
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965971"
---
# <a name="icorruntimehoststop-method"></a><span data-ttu-id="68168-102">Метод ICorRuntimeHost::Stop</span><span class="sxs-lookup"><span data-stu-id="68168-102">ICorRuntimeHost::Stop Method</span></span>
<span data-ttu-id="68168-103">Останавливает выполнение кода в среде выполнения для текущего процесса.</span><span class="sxs-lookup"><span data-stu-id="68168-103">Stops the execution of code in the runtime for the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68168-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="68168-104">Syntax</span></span>  
  
```cpp  
HRESULT Stop ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="68168-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="68168-105">Return Value</span></span>  
  
|<span data-ttu-id="68168-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="68168-106">HRESULT</span></span>|<span data-ttu-id="68168-107">Описание</span><span class="sxs-lookup"><span data-stu-id="68168-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="68168-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="68168-108">S_OK</span></span>|<span data-ttu-id="68168-109">Операция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="68168-109">The operation was successful.</span></span>|  
|<span data-ttu-id="68168-110">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="68168-110">S_FALSE</span></span>|<span data-ttu-id="68168-111">Не удалось завершить операцию.</span><span class="sxs-lookup"><span data-stu-id="68168-111">The operation failed to complete.</span></span>|  
|<span data-ttu-id="68168-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="68168-112">E_FAIL</span></span>|<span data-ttu-id="68168-113">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="68168-113">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="68168-114">Если метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="68168-114">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="68168-115">Последующие вызовы любых API размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="68168-115">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="68168-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="68168-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="68168-117">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="68168-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="68168-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="68168-118">Remarks</span></span>  
 <span data-ttu-id="68168-119">Как правило, вызов `Stop` метода не требуется, поскольку код прекращает выполнение при завершении процесса.</span><span class="sxs-lookup"><span data-stu-id="68168-119">It is typically unnecessary to call the `Stop` method, because the code stops executing when the process exits.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="68168-120">После вызова `Stop`среда CLR не может быть инициализирована в том же процессе.</span><span class="sxs-lookup"><span data-stu-id="68168-120">After a call to `Stop`, the CLR cannot be reinitialized into the same process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68168-121">Требования</span><span class="sxs-lookup"><span data-stu-id="68168-121">Requirements</span></span>  
 <span data-ttu-id="68168-122">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68168-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68168-123">**Заголовок.** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="68168-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="68168-124">**Библиотечная** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="68168-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="68168-125">**.NET Framework версии:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="68168-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68168-126">См. также</span><span class="sxs-lookup"><span data-stu-id="68168-126">See also</span></span>

- [<span data-ttu-id="68168-127">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="68168-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
