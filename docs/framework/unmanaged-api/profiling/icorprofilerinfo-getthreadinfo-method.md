---
title: Метод ICorProfilerInfo::GetThreadInfo
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetThreadInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetThreadInfo
helpviewer_keywords:
- ICorProfilerInfo::GetThreadInfo method [.NET Framework profiling]
- GetThreadInfo method [.NET Framework profiling]
ms.assetid: fc994fef-65c9-432a-84cb-66c8141147e7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 405d5ff49ba7bc2e5204f00cf50c30822354e56d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775581"
---
# <a name="icorprofilerinfogetthreadinfo-method"></a><span data-ttu-id="fa083-102">Метод ICorProfilerInfo::GetThreadInfo</span><span class="sxs-lookup"><span data-stu-id="fa083-102">ICorProfilerInfo::GetThreadInfo Method</span></span>
<span data-ttu-id="fa083-103">Возвращает удостоверение текущего потока Win32 для указанного потока.</span><span class="sxs-lookup"><span data-stu-id="fa083-103">Gets the current Win32 thread identity for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa083-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fa083-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadInfo(  
    [in]  ThreadID threadId,  
    [out] DWORD    *pdwWin32ThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa083-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fa083-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="fa083-106">[in] Идентификатор потока, для которого необходимо получить идентификатор текущего Win32</span><span class="sxs-lookup"><span data-stu-id="fa083-106">[in] The ID of the thread for which to get the current Win32 ID.</span></span>  
  
 `pdwWin32ThreadId`  
 <span data-ttu-id="fa083-107">[out] Указатель на текущий поток Win32 указанного потока.</span><span class="sxs-lookup"><span data-stu-id="fa083-107">[out] A pointer to the specified thread's current Win32 thread ID.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa083-108">Требования</span><span class="sxs-lookup"><span data-stu-id="fa083-108">Requirements</span></span>  
 <span data-ttu-id="fa083-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa083-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa083-110">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fa083-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fa083-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa083-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa083-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa083-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa083-113">См. также</span><span class="sxs-lookup"><span data-stu-id="fa083-113">See also</span></span>

- [<span data-ttu-id="fa083-114">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="fa083-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
