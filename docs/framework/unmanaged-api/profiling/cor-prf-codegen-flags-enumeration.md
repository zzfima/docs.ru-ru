---
title: Перечисление COR_PRF_CODEGEN_FLAGS
ms.date: 03/30/2017
api_name:
- COR_PRF_CODEGEN_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_CODEGEN_FLAGS
helpviewer_keywords:
- COR_PRF_CODEGEN_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 3e184022-0247-4824-a23d-6b29593d8d01
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 321318b63368ed6e57d235cf97d94485352f8686
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775132"
---
# <a name="corprfcodegenflags-enumeration"></a><span data-ttu-id="4e1ab-102">Перечисление COR_PRF_CODEGEN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="4e1ab-102">COR_PRF_CODEGEN_FLAGS Enumeration</span></span>
<span data-ttu-id="4e1ab-103">Определяет флаги создания кода, которые могут устанавливаться с [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="4e1ab-103">Defines the code generation flags that can be set with the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e1ab-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4e1ab-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_CODEGEN_DISABLE_INLINING =          0x0001,  
    COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS = 0x0002,  
} COR_PRF_CODEGEN_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="4e1ab-105">Участники</span><span class="sxs-lookup"><span data-stu-id="4e1ab-105">Members</span></span>  
  
|<span data-ttu-id="4e1ab-106">Член</span><span class="sxs-lookup"><span data-stu-id="4e1ab-106">Member</span></span>|<span data-ttu-id="4e1ab-107">Описание</span><span class="sxs-lookup"><span data-stu-id="4e1ab-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_CODEGEN_DISABLE_INLINING`|<span data-ttu-id="4e1ab-108">Нет функций, будет встроенным в теле этой функции.</span><span class="sxs-lookup"><span data-stu-id="4e1ab-108">No functions will be inlined into this function’s body.</span></span> <span data-ttu-id="4e1ab-109">Однако сама функция может быть в его вызывающие объекты.</span><span class="sxs-lookup"><span data-stu-id="4e1ab-109">However, the function itself may be inlined into its callers.</span></span>|  
|`COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS`|<span data-ttu-id="4e1ab-110">Все оптимизации будет отключена для тела функции.</span><span class="sxs-lookup"><span data-stu-id="4e1ab-110">All optimizations will be disabled for this function’s body.</span></span> <span data-ttu-id="4e1ab-111">Однако сама функция по-прежнему может быть в его вызывающие объекты.</span><span class="sxs-lookup"><span data-stu-id="4e1ab-111">However, the function itself may still be inlined into its callers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e1ab-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="4e1ab-112">Remarks</span></span>  
 <span data-ttu-id="4e1ab-113">`COR_PRF_CODEGEN_FLAGS` Перечисление, используемое [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) метод для включения профилировщика для управления создание кода для функции перекомпиляции JIT.</span><span class="sxs-lookup"><span data-stu-id="4e1ab-113">The `COR_PRF_CODEGEN_FLAGS` enumeration is used by the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) method to enable the profiler to control the code generation for the JIT-recompiled function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e1ab-114">Требования</span><span class="sxs-lookup"><span data-stu-id="4e1ab-114">Requirements</span></span>  
 <span data-ttu-id="4e1ab-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e1ab-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e1ab-116">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4e1ab-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4e1ab-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4e1ab-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4e1ab-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e1ab-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e1ab-119">См. также</span><span class="sxs-lookup"><span data-stu-id="4e1ab-119">See also</span></span>

- [<span data-ttu-id="4e1ab-120">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="4e1ab-120">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
