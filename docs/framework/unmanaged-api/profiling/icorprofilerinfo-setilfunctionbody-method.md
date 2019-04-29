---
title: Метод ICorProfilerInfo::SetILFunctionBody
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetILFunctionBody
helpviewer_keywords:
- ICorProfilerInfo::SetILFunctionBody method [.NET Framework profiling]
- SetILFunctionBody method [.NET Framework profiling]
ms.assetid: b159c712-00f4-4fc7-a990-40bf9f642e8f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d10bb7033688efce9488078d2ef605e2a29382f6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61792657"
---
# <a name="icorprofilerinfosetilfunctionbody-method"></a><span data-ttu-id="549a2-102">Метод ICorProfilerInfo::SetILFunctionBody</span><span class="sxs-lookup"><span data-stu-id="549a2-102">ICorProfilerInfo::SetILFunctionBody Method</span></span>
<span data-ttu-id="549a2-103">Заменяет текст в указанном модуле указанной функции.</span><span class="sxs-lookup"><span data-stu-id="549a2-103">Replaces the body of the specified function in the specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="549a2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="549a2-104">Syntax</span></span>  
  
```  
HRESULT SetILFunctionBody(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodid,  
    [in] LPCBYTE     pbNewILMethodHeader);  
```  
  
## <a name="parameters"></a><span data-ttu-id="549a2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="549a2-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="549a2-106">[in] Идентификатор модуля, в которой находится функция.</span><span class="sxs-lookup"><span data-stu-id="549a2-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `methodid`  
 <span data-ttu-id="549a2-107">[in] Токен функции, для которой заменяемый текст.</span><span class="sxs-lookup"><span data-stu-id="549a2-107">[in] The token of the function for which to replace the body.</span></span>  
  
 `pbNewILMethodHeader`  
 <span data-ttu-id="549a2-108">[in] Новый заголовок для функции.</span><span class="sxs-lookup"><span data-stu-id="549a2-108">[in] The new header for the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="549a2-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="549a2-109">Remarks</span></span>  
 <span data-ttu-id="549a2-110">`SetILFunctionBody` Метод заменяет относительный виртуальный адрес функции в метаданных, так что он указывает на новый тело функции и настраивает все внутренние структуры данных при необходимости.</span><span class="sxs-lookup"><span data-stu-id="549a2-110">The `SetILFunctionBody` method replaces the relative virtual address of the function in the metadata so that it points to the new function body, and adjusts any internal data structures as required.</span></span>  
  
 <span data-ttu-id="549a2-111">`SetILFunctionBody` Метод может вызываться для только для тех функций, которые никогда не были скомпилированы с помощью компилятора just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="549a2-111">The `SetILFunctionBody` method can be called on only those functions that have never been compiled by a just-in-time (JIT) compiler.</span></span>  
  
 <span data-ttu-id="549a2-112">Используйте [ICorProfilerInfo::GetILFunctionBodyAllocator](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbodyallocator-method.md) метод, чтобы выделить место для нового метода обеспечить совместимость буфера.</span><span class="sxs-lookup"><span data-stu-id="549a2-112">Use the [ICorProfilerInfo::GetILFunctionBodyAllocator](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbodyallocator-method.md) method to allocate space for the new method to ensure that the buffer is compatible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="549a2-113">Требования</span><span class="sxs-lookup"><span data-stu-id="549a2-113">Requirements</span></span>  
 <span data-ttu-id="549a2-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="549a2-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="549a2-115">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="549a2-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="549a2-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="549a2-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="549a2-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="549a2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="549a2-118">См. также</span><span class="sxs-lookup"><span data-stu-id="549a2-118">See also</span></span>

- [<span data-ttu-id="549a2-119">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="549a2-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
