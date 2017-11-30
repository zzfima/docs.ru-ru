---
title: "Метод ICorProfilerCallback::FunctionUnloadStarted"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.FunctionUnloadStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::FunctionUnloadStarted
helpviewer_keywords:
- FunctionUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::FunctionUnloadStarted method [.NET Framework profiling]
ms.assetid: d6a5fa8b-09c6-47a5-b60e-6cf2e355df30
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: efd08eedf6812a46a46135eaa6f0089257f0a209
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackfunctionunloadstarted-method"></a><span data-ttu-id="b7ca2-102">Метод ICorProfilerCallback::FunctionUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="b7ca2-102">ICorProfilerCallback::FunctionUnloadStarted Method</span></span>
<span data-ttu-id="b7ca2-103">Уведомляет профилировщик о том, что среда выполнения начала выгрузку функции.</span><span class="sxs-lookup"><span data-stu-id="b7ca2-103">Notifies the profiler that the runtime has started to unload a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7ca2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b7ca2-104">Syntax</span></span>  
  
```  
HRESULT FunctionUnloadStarted(  
    [in] FunctionID functionId);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="b7ca2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b7ca2-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="b7ca2-106">[in] Идентификатор функции, выгружается.</span><span class="sxs-lookup"><span data-stu-id="b7ca2-106">[in] The ID of the function that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b7ca2-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="b7ca2-107">Remarks</span></span>  
 <span data-ttu-id="b7ca2-108">Значение `functionId` параметр больше не является допустимым, после возврата этого метода в вызывающий объект.</span><span class="sxs-lookup"><span data-stu-id="b7ca2-108">The value of the `functionId` parameter is no longer valid after this method returns to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7ca2-109">Требования</span><span class="sxs-lookup"><span data-stu-id="b7ca2-109">Requirements</span></span>  
 <span data-ttu-id="b7ca2-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7ca2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7ca2-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b7ca2-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b7ca2-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7ca2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7ca2-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7ca2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7ca2-114">См. также</span><span class="sxs-lookup"><span data-stu-id="b7ca2-114">See Also</span></span>  
 [<span data-ttu-id="b7ca2-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="b7ca2-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
