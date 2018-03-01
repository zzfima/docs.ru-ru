---
title: "Метод ICorProfilerInfo::GetHandleFromThread"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 465fb61d17269873b3a2aa2f323086f209cab946
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfogethandlefromthread-method"></a><span data-ttu-id="69120-102">Метод ICorProfilerInfo::GetHandleFromThread</span><span class="sxs-lookup"><span data-stu-id="69120-102">ICorProfilerInfo::GetHandleFromThread Method</span></span>
<span data-ttu-id="69120-103">Сопоставляет идентификатор потока дескриптору потока Win32.</span><span class="sxs-lookup"><span data-stu-id="69120-103">Maps the ID of a thread to a Win32 thread handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69120-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="69120-104">Syntax</span></span>  
  
```  
HRESULT GetHandleFromThread(  
    [in]  ThreadID threadId,  
    [out] HANDLE  *phThread);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="69120-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="69120-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="69120-106">[in] Идентификатор потока, который должен быть сопоставлен.</span><span class="sxs-lookup"><span data-stu-id="69120-106">[in] The thread ID to be mapped.</span></span>  
  
 `phThread`  
 <span data-ttu-id="69120-107">[out] Указатель на дескриптор потока Win32.</span><span class="sxs-lookup"><span data-stu-id="69120-107">[out] A pointer to a Win32 thread handle.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="69120-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="69120-108">Remarks</span></span>  
 <span data-ttu-id="69120-109">Профилировщик должен вызвать Win32 `DuplicateHandle` функция с дескриптором перед его использованием.</span><span class="sxs-lookup"><span data-stu-id="69120-109">The profiler must call the Win32 `DuplicateHandle` function on the handle before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69120-110">Требования</span><span class="sxs-lookup"><span data-stu-id="69120-110">Requirements</span></span>  
 <span data-ttu-id="69120-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69120-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69120-112">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="69120-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="69120-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="69120-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="69120-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69120-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69120-115">См. также</span><span class="sxs-lookup"><span data-stu-id="69120-115">See Also</span></span>  
 [<span data-ttu-id="69120-116">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="69120-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
