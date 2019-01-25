---
title: Метод ICorProfilerInfo::GetHandleFromThread
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetHandleFromThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetHandleFromThread
helpviewer_keywords:
- GetHandleFromThread method [.NET Framework profiling]
- ICorProfilerInfo::GetHandleFromThread method [.NET Framework profiling]
ms.assetid: 36cdc9f5-7579-4cd2-aa36-fc05c741584c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8f1eb2354536a436bd6ae41cf70bf11549982d5e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54612597"
---
# <a name="icorprofilerinfogethandlefromthread-method"></a><span data-ttu-id="0ea97-102">Метод ICorProfilerInfo::GetHandleFromThread</span><span class="sxs-lookup"><span data-stu-id="0ea97-102">ICorProfilerInfo::GetHandleFromThread Method</span></span>
<span data-ttu-id="0ea97-103">Сопоставляет идентификатор потока, поток Win32-дескриптором.</span><span class="sxs-lookup"><span data-stu-id="0ea97-103">Maps the ID of a thread to a Win32 thread handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ea97-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0ea97-104">Syntax</span></span>  
  
```  
HRESULT GetHandleFromThread(  
    [in]  ThreadID threadId,  
    [out] HANDLE  *phThread);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0ea97-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0ea97-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="0ea97-106">[in] Идентификатор потока должны быть сопоставлены.</span><span class="sxs-lookup"><span data-stu-id="0ea97-106">[in] The thread ID to be mapped.</span></span>  
  
 `phThread`  
 <span data-ttu-id="0ea97-107">[out] Указатель на дескриптор потока Win32.</span><span class="sxs-lookup"><span data-stu-id="0ea97-107">[out] A pointer to a Win32 thread handle.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ea97-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="0ea97-108">Remarks</span></span>  
 <span data-ttu-id="0ea97-109">Профилировщик должен вызвать Win32 `DuplicateHandle` функции с дескриптором перед его использованием.</span><span class="sxs-lookup"><span data-stu-id="0ea97-109">The profiler must call the Win32 `DuplicateHandle` function on the handle before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ea97-110">Требования</span><span class="sxs-lookup"><span data-stu-id="0ea97-110">Requirements</span></span>  
 <span data-ttu-id="0ea97-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ea97-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ea97-112">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0ea97-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0ea97-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ea97-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ea97-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ea97-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ea97-115">См. также</span><span class="sxs-lookup"><span data-stu-id="0ea97-115">See also</span></span>
- [<span data-ttu-id="0ea97-116">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="0ea97-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
