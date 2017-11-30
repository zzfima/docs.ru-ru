---
title: "Перечисление COR_PRF_CODEGEN_FLAGS"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_CODEGEN_FLAGS
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_CODEGEN_FLAGS
helpviewer_keywords: COR_PRF_CODEGEN_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 3e184022-0247-4824-a23d-6b29593d8d01
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c2c97510077fefd730827ac00326d267fd1c62ef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="corprfcodegenflags-enumeration"></a><span data-ttu-id="c6fc4-102">Перечисление COR_PRF_CODEGEN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="c6fc4-102">COR_PRF_CODEGEN_FLAGS Enumeration</span></span>
<span data-ttu-id="c6fc4-103">Определяет флаги создания кода, которые могут быть установлены с [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="c6fc4-103">Defines the code generation flags that can be set with the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6fc4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c6fc4-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_CODEGEN_DISABLE_INLINING =          0x0001,  
    COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS = 0x0002,  
} COR_PRF_CODEGEN_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="c6fc4-105">Члены</span><span class="sxs-lookup"><span data-stu-id="c6fc4-105">Members</span></span>  
  
|<span data-ttu-id="c6fc4-106">Член</span><span class="sxs-lookup"><span data-stu-id="c6fc4-106">Member</span></span>|<span data-ttu-id="c6fc4-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c6fc4-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_CODEGEN_DISABLE_INLINING`|<span data-ttu-id="c6fc4-108">Функции не будет подставляться в основную часть этой функции.</span><span class="sxs-lookup"><span data-stu-id="c6fc4-108">No functions will be inlined into this function’s body.</span></span> <span data-ttu-id="c6fc4-109">Однако сама функция может быть подставляются в вызывающим объектам.</span><span class="sxs-lookup"><span data-stu-id="c6fc4-109">However, the function itself may be inlined into its callers.</span></span>|  
|`COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS`|<span data-ttu-id="c6fc4-110">Будут отключены все оптимизации для тела функции.</span><span class="sxs-lookup"><span data-stu-id="c6fc4-110">All optimizations will be disabled for this function’s body.</span></span> <span data-ttu-id="c6fc4-111">Однако сама функция по-прежнему может быть подставляются в вызывающим объектам.</span><span class="sxs-lookup"><span data-stu-id="c6fc4-111">However, the function itself may still be inlined into its callers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6fc4-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="c6fc4-112">Remarks</span></span>  
 <span data-ttu-id="c6fc4-113">`COR_PRF_CODEGEN_FLAGS` Перечисление используется методом [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) способ включения контроля генерации кода для JIT-компилятора функции профилировщика.</span><span class="sxs-lookup"><span data-stu-id="c6fc4-113">The `COR_PRF_CODEGEN_FLAGS` enumeration is used by the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) method to enable the profiler to control the code generation for the JIT-recompiled function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6fc4-114">Требования</span><span class="sxs-lookup"><span data-stu-id="c6fc4-114">Requirements</span></span>  
 <span data-ttu-id="c6fc4-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6fc4-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6fc4-116">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c6fc4-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c6fc4-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6fc4-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c6fc4-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6fc4-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6fc4-119">См. также</span><span class="sxs-lookup"><span data-stu-id="c6fc4-119">See Also</span></span>  
 [<span data-ttu-id="c6fc4-120">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="c6fc4-120">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
