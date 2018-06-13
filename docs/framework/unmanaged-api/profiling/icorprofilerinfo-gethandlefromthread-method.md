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
ms.openlocfilehash: 9658ad8a1963d3747fb7c23dce84790a30b17db3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453226"
---
# <a name="icorprofilerinfogethandlefromthread-method"></a><span data-ttu-id="5b6ae-102">Метод ICorProfilerInfo::GetHandleFromThread</span><span class="sxs-lookup"><span data-stu-id="5b6ae-102">ICorProfilerInfo::GetHandleFromThread Method</span></span>
<span data-ttu-id="5b6ae-103">Сопоставляет идентификатор потока дескриптору потока Win32.</span><span class="sxs-lookup"><span data-stu-id="5b6ae-103">Maps the ID of a thread to a Win32 thread handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b6ae-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5b6ae-104">Syntax</span></span>  
  
```  
HRESULT GetHandleFromThread(  
    [in]  ThreadID threadId,  
    [out] HANDLE  *phThread);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5b6ae-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5b6ae-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="5b6ae-106">[in] Идентификатор потока, который должен быть сопоставлен.</span><span class="sxs-lookup"><span data-stu-id="5b6ae-106">[in] The thread ID to be mapped.</span></span>  
  
 `phThread`  
 <span data-ttu-id="5b6ae-107">[out] Указатель на дескриптор потока Win32.</span><span class="sxs-lookup"><span data-stu-id="5b6ae-107">[out] A pointer to a Win32 thread handle.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5b6ae-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="5b6ae-108">Remarks</span></span>  
 <span data-ttu-id="5b6ae-109">Профилировщик должен вызвать Win32 `DuplicateHandle` функция с дескриптором перед его использованием.</span><span class="sxs-lookup"><span data-stu-id="5b6ae-109">The profiler must call the Win32 `DuplicateHandle` function on the handle before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b6ae-110">Требования</span><span class="sxs-lookup"><span data-stu-id="5b6ae-110">Requirements</span></span>  
 <span data-ttu-id="5b6ae-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b6ae-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b6ae-112">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5b6ae-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5b6ae-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5b6ae-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5b6ae-114">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b6ae-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b6ae-115">См. также</span><span class="sxs-lookup"><span data-stu-id="5b6ae-115">See Also</span></span>  
 [<span data-ttu-id="5b6ae-116">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="5b6ae-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
