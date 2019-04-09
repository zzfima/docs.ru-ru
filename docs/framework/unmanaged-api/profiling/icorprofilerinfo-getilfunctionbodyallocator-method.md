---
title: Метод ICorProfilerInfo::GetILFunctionBodyAllocator
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetILFunctionBodyAllocator
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetILFunctionBodyAllocator
helpviewer_keywords:
- GetILFunctionBodyAllocator method [.NET Framework profiling]
- ICorProfilerInfo::GetILFunctionBodyAllocator method [.NET Framework profiling]
ms.assetid: 5da1bf3d-dddf-4892-b266-578ee54d570b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2cd66a895f99d62e8deaa45afab12d963aee2901
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59109126"
---
# <a name="icorprofilerinfogetilfunctionbodyallocator-method"></a><span data-ttu-id="ff3ba-102">Метод ICorProfilerInfo::GetILFunctionBodyAllocator</span><span class="sxs-lookup"><span data-stu-id="ff3ba-102">ICorProfilerInfo::GetILFunctionBodyAllocator Method</span></span>
<span data-ttu-id="ff3ba-103">Возвращает интерфейс, который предоставляет метод для выделения памяти, используемый для замены в тело метода в код на промежуточном языке (MSIL).</span><span class="sxs-lookup"><span data-stu-id="ff3ba-103">Gets an interface that provides a method to allocate memory to be used for swapping out the body of a method in Microsoft intermediate language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff3ba-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ff3ba-104">Syntax</span></span>  
  
```  
HRESULT GetILFunctionBodyAllocator(  
    [in]  ModuleID      moduleId,  
    [out] IMethodMalloc **ppMalloc);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff3ba-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ff3ba-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="ff3ba-106">[in] Идентификатор модуля, в котором находится метод.</span><span class="sxs-lookup"><span data-stu-id="ff3ba-106">[in] The ID of the module in which the method resides.</span></span>  
  
 `ppMalloc`  
 <span data-ttu-id="ff3ba-107">[out] Указатель на [IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md) интерфейс, который предоставляет метод для выделения памяти.</span><span class="sxs-lookup"><span data-stu-id="ff3ba-107">[out] A pointer to an [IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md) interface that provides a method to allocate the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff3ba-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="ff3ba-108">Remarks</span></span>  
 <span data-ttu-id="ff3ba-109">Тело метода в коде MSIL должна располагаться как относительный виртуальный адрес (RVA), по отношению к загруженного модуля, это означает, что в файле модуля в 4 ГБ.</span><span class="sxs-lookup"><span data-stu-id="ff3ba-109">A method body in MSIL code must be located as a relative virtual address (RVA), relative to the loaded module, which means that it follows the module within 4 GB.</span></span> <span data-ttu-id="ff3ba-110">Чтобы упростить средства тела метода, `GetILFunctionBodyAllocator` метод гарантирует, что память выделяется в пределах диапазона.</span><span class="sxs-lookup"><span data-stu-id="ff3ba-110">To make it easier for a tool to swap out the body of a method, the `GetILFunctionBodyAllocator` method ensures that memory is allocated within that range.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff3ba-111">Требования</span><span class="sxs-lookup"><span data-stu-id="ff3ba-111">Requirements</span></span>  
 <span data-ttu-id="ff3ba-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff3ba-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff3ba-113">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ff3ba-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ff3ba-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ff3ba-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="ff3ba-115">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="ff3ba-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ff3ba-116">См. также</span><span class="sxs-lookup"><span data-stu-id="ff3ba-116">See also</span></span>

- [<span data-ttu-id="ff3ba-117">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="ff3ba-117">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
