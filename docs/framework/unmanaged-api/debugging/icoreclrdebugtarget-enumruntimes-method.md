---
title: Метод ICoreClrDebugTarget::EnumRuntimes
ms.date: 03/30/2017
api_name:
- ICoreClrDebugTarget.EnumRuntimes
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget::EnumRuntimes
helpviewer_keywords:
- remote debugging API [Silverlight]
- ICorClrDebugTarget::EnumRuntimes method [Silverlight debugging]
- EnumRuntimes method, ICoreClrDebugTarget interface [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: 316df866-442d-40cc-b049-45e8adcb65d1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 08f34822099468b8c52f1d7ea2c665205f1b6c01
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67774431"
---
# <a name="icoreclrdebugtargetenumruntimes-method"></a><span data-ttu-id="c6ae0-102">Метод ICoreClrDebugTarget::EnumRuntimes</span><span class="sxs-lookup"><span data-stu-id="c6ae0-102">ICoreClrDebugTarget::EnumRuntimes Method</span></span>
<span data-ttu-id="c6ae0-103">Перечисляет среды CLR в указанном процессе, который выполняется на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="c6ae0-103">Enumerates the common language runtimes (CLRs) in the specified process that is running on a remote computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6ae0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c6ae0-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumRuntimes (  
      [in] DWORD       dwInternalProcessID,  
      [out] DWORD*     pcRuntimes,  
      [out] CoreClrDebugRuntimeInfo**    ppRuntimes  
    );  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6ae0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c6ae0-105">Parameters</span></span>  
 `dwInternalProcessID`  
 <span data-ttu-id="c6ae0-106">[in] Внутренний идентификатор процесса, для которого требуется перечислить среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="c6ae0-106">[in] The internal process ID of the process for which you want to enumerate runtimes.</span></span> <span data-ttu-id="c6ae0-107">Это будет `m_dwInternalID` из соответствующего [CoreClrDebugProcInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md).</span><span class="sxs-lookup"><span data-stu-id="c6ae0-107">This will be `m_dwInternalID` from the corresponding [CoreClrDebugProcInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md).</span></span>  
  
 `pcRuntimes`  
 <span data-ttu-id="c6ae0-108">[out] Число сред выполнения, возвращаемых в `ppRuntimes`.</span><span class="sxs-lookup"><span data-stu-id="c6ae0-108">[out] The number of runtimes returned in `ppRuntimes`.</span></span> <span data-ttu-id="c6ae0-109">Это значение может быть 0 (ноль).</span><span class="sxs-lookup"><span data-stu-id="c6ae0-109">This value can be 0 (zero).</span></span>  
  
 `ppRuntimes`  
 <span data-ttu-id="c6ae0-110">[out] Массив [CoreClrDebugRuntimeInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugruntimeinfo-structure.md) структуры, которые представляют среды выполнения, загруженных в удаленном целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="c6ae0-110">[out] An array of [CoreClrDebugRuntimeInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugruntimeinfo-structure.md) structures that represent the runtimes loaded in the remote target process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c6ae0-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c6ae0-111">Return Value</span></span>  
 <span data-ttu-id="c6ae0-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="c6ae0-112">S_OK</span></span>  
 <span data-ttu-id="c6ae0-113">Выполнено.</span><span class="sxs-lookup"><span data-stu-id="c6ae0-113">Success.</span></span>  
  
 <span data-ttu-id="c6ae0-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="c6ae0-114">S_FALSE</span></span>  
 <span data-ttu-id="c6ae0-115">`dwInternalProcessID` не соответствует ни одному процессу, который выполняется на компьютере, возможно потому, что этот процесс был завершен.</span><span class="sxs-lookup"><span data-stu-id="c6ae0-115">`dwInternalProcessID` does not match any process that is running on the computer, probably because the process was terminated.</span></span> <span data-ttu-id="c6ae0-116">`pcRuntimes` и `ppRuntimes` будут иметь значение null.</span><span class="sxs-lookup"><span data-stu-id="c6ae0-116">`pcRuntimes` and `ppRuntimes` will be null.</span></span>  
  
 <span data-ttu-id="c6ae0-117">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="c6ae0-117">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="c6ae0-118">Не удается выделить достаточно памяти для `ppRuntimes`.</span><span class="sxs-lookup"><span data-stu-id="c6ae0-118">Unable to allocate enough memory for `ppRuntimes`.</span></span>  
  
 <span data-ttu-id="c6ae0-119">E_FAIL (или другие коды возврата E_)</span><span class="sxs-lookup"><span data-stu-id="c6ae0-119">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="c6ae0-120">Прочие сбои.</span><span class="sxs-lookup"><span data-stu-id="c6ae0-120">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c6ae0-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="c6ae0-121">Remarks</span></span>  
 <span data-ttu-id="c6ae0-122">Чтобы освободить память, выделенную этим методом, вызовите [ICoreClrDebugTarget::FreeMemory](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="c6ae0-122">To free the memory that was allocated by this method, call the [ICoreClrDebugTarget::FreeMemory](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6ae0-123">Требования</span><span class="sxs-lookup"><span data-stu-id="c6ae0-123">Requirements</span></span>  
 <span data-ttu-id="c6ae0-124">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6ae0-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6ae0-125">**Заголовок.** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="c6ae0-125">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="c6ae0-126">**Library:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="c6ae0-126">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="c6ae0-127">**Версии платформы .NET framework:** 3.5 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="c6ae0-127">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6ae0-128">См. также</span><span class="sxs-lookup"><span data-stu-id="c6ae0-128">See also</span></span>

- [<span data-ttu-id="c6ae0-129">Интерфейс ICoreClrDebugTarget</span><span class="sxs-lookup"><span data-stu-id="c6ae0-129">ICoreClrDebugTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)
