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
ms.openlocfilehash: 296c3973403a5b09332efa24961d7a474d814aab
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863352"
---
# <a name="icorprofilerinfosetilfunctionbody-method"></a><span data-ttu-id="1b752-102">Метод ICorProfilerInfo::SetILFunctionBody</span><span class="sxs-lookup"><span data-stu-id="1b752-102">ICorProfilerInfo::SetILFunctionBody Method</span></span>
<span data-ttu-id="1b752-103">Заменяет тело указанной функции в указанном модуле.</span><span class="sxs-lookup"><span data-stu-id="1b752-103">Replaces the body of the specified function in the specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b752-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1b752-104">Syntax</span></span>  
  
```cpp  
HRESULT SetILFunctionBody(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodid,  
    [in] LPCBYTE     pbNewILMethodHeader);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b752-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1b752-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="1b752-106">окне Идентификатор модуля, в котором находится функция.</span><span class="sxs-lookup"><span data-stu-id="1b752-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `methodid`  
 <span data-ttu-id="1b752-107">окне Токен функции, для которой заменяется текст.</span><span class="sxs-lookup"><span data-stu-id="1b752-107">[in] The token of the function for which to replace the body.</span></span>  
  
 `pbNewILMethodHeader`  
 <span data-ttu-id="1b752-108">окне Новый заголовок для функции.</span><span class="sxs-lookup"><span data-stu-id="1b752-108">[in] The new header for the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b752-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="1b752-109">Remarks</span></span>  
 <span data-ttu-id="1b752-110">Метод `SetILFunctionBody` заменяет относительный виртуальный адрес функции в метаданных таким образом, чтобы он указывал на новый текст функции, и при необходимости корректирует все внутренние структуры данных.</span><span class="sxs-lookup"><span data-stu-id="1b752-110">The `SetILFunctionBody` method replaces the relative virtual address of the function in the metadata so that it points to the new function body, and adjusts any internal data structures as required.</span></span>  
  
 <span data-ttu-id="1b752-111">Метод `SetILFunctionBody` можно вызывать только для тех функций, которые не были скомпилированы JIT-компилятором.</span><span class="sxs-lookup"><span data-stu-id="1b752-111">The `SetILFunctionBody` method can be called on only those functions that have never been compiled by a just-in-time (JIT) compiler.</span></span>  
  
 <span data-ttu-id="1b752-112">Используйте метод [ICorProfilerInfo:: GetILFunctionBodyAllocator](icorprofilerinfo-getilfunctionbodyallocator-method.md) , чтобы выделить пространство для нового метода, чтобы обеспечить совместимость буфера.</span><span class="sxs-lookup"><span data-stu-id="1b752-112">Use the [ICorProfilerInfo::GetILFunctionBodyAllocator](icorprofilerinfo-getilfunctionbodyallocator-method.md) method to allocate space for the new method to ensure that the buffer is compatible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b752-113">Требования</span><span class="sxs-lookup"><span data-stu-id="1b752-113">Requirements</span></span>  
 <span data-ttu-id="1b752-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b752-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b752-115">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1b752-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1b752-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1b752-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1b752-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b752-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b752-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="1b752-118">See also</span></span>

- [<span data-ttu-id="1b752-119">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="1b752-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
