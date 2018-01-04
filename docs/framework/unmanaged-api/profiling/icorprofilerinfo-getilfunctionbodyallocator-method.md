---
title: "Метод ICorProfilerInfo::GetILFunctionBodyAllocator"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetILFunctionBodyAllocator
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetILFunctionBodyAllocator
helpviewer_keywords:
- GetILFunctionBodyAllocator method [.NET Framework profiling]
- ICorProfilerInfo::GetILFunctionBodyAllocator method [.NET Framework profiling]
ms.assetid: 5da1bf3d-dddf-4892-b266-578ee54d570b
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b1feec20f0ddc4f6029490e06d4729b3fdaa7fa8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfogetilfunctionbodyallocator-method"></a><span data-ttu-id="756ad-102">Метод ICorProfilerInfo::GetILFunctionBodyAllocator</span><span class="sxs-lookup"><span data-stu-id="756ad-102">ICorProfilerInfo::GetILFunctionBodyAllocator Method</span></span>
<span data-ttu-id="756ad-103">Возвращает интерфейс, предоставляющий метод выделения памяти, используемый для замены тела метода в код на промежуточном языке (MSIL).</span><span class="sxs-lookup"><span data-stu-id="756ad-103">Gets an interface that provides a method to allocate memory to be used for swapping out the body of a method in Microsoft intermediate language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="756ad-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="756ad-104">Syntax</span></span>  
  
```  
HRESULT GetILFunctionBodyAllocator(  
    [in]  ModuleID      moduleId,  
    [out] IMethodMalloc **ppMalloc);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="756ad-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="756ad-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="756ad-106">[in] Идентификатор модуля, в котором находится данный метод.</span><span class="sxs-lookup"><span data-stu-id="756ad-106">[in] The ID of the module in which the method resides.</span></span>  
  
 `ppMalloc`  
 <span data-ttu-id="756ad-107">[out] Указатель на [IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md) интерфейс, который предоставляет метод для выделения памяти.</span><span class="sxs-lookup"><span data-stu-id="756ad-107">[out] A pointer to an [IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md) interface that provides a method to allocate the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="756ad-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="756ad-108">Remarks</span></span>  
 <span data-ttu-id="756ad-109">Тело метода в коде MSIL должна располагаться как относительный виртуальный адрес (RVA) относительно загруженного модуля, это означает, обусловленные модуля в 4 ГБ.</span><span class="sxs-lookup"><span data-stu-id="756ad-109">A method body in MSIL code must be located as a relative virtual address (RVA), relative to the loaded module, which means that it follows the module within 4 GB.</span></span> <span data-ttu-id="756ad-110">Чтобы упростить инструмента для замены тела метода, `GetILFunctionBodyAllocator` метод гарантирует, что память выделяется в пределах диапазона.</span><span class="sxs-lookup"><span data-stu-id="756ad-110">To make it easier for a tool to swap out the body of a method, the `GetILFunctionBodyAllocator` method ensures that memory is allocated within that range.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="756ad-111">Требования</span><span class="sxs-lookup"><span data-stu-id="756ad-111">Requirements</span></span>  
 <span data-ttu-id="756ad-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="756ad-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="756ad-113">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="756ad-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="756ad-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="756ad-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="756ad-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="756ad-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="756ad-116">См. также</span><span class="sxs-lookup"><span data-stu-id="756ad-116">See Also</span></span>  
 [<span data-ttu-id="756ad-117">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="756ad-117">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
