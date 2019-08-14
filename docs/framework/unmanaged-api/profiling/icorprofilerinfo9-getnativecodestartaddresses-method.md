---
title: 'ICorProfilerInfo9:: Жетнативекодестартаддрессес'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo9.GetNativeCodeStartAddresses
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: f5c7f11a322e4cf3ed38608e0f380dd632bc8fb6
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2019
ms.locfileid: "68973814"
---
# <a name="icorprofilerinfo9getnativecodestartaddresses-method"></a><span data-ttu-id="413f5-102">Метод ICorProfilerInfo9:: Жетнативекодестартаддрессес</span><span class="sxs-lookup"><span data-stu-id="413f5-102">ICorProfilerInfo9::GetNativeCodeStartAddresses Method</span></span>
  
 <span data-ttu-id="413f5-103">При наличии кода functionId и Режитид перечисляются начальные адреса всех откомпилированных версий этого кода, которые в настоящее время существуют.</span><span class="sxs-lookup"><span data-stu-id="413f5-103">Given a functionId and rejitId, enumerates the native code start address of all jitted versions of this code that currently exist.</span></span>   
  
## <a name="syntax"></a><span data-ttu-id="413f5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="413f5-104">Syntax</span></span>  
  
```cpp
HRESULT GetNativeCodeStartAddresses( [in]  FunctionID functionID,
                                     [in]  ReJITID reJitId,
                                     [in]  ULONG32 cCodeStartAddresses,
                                     [out] ULONG32 *pcCodeStartAddresses,
                                     [out] UINT_PTR codeStartAddresses[]);
```  
  
#### <a name="parameters"></a><span data-ttu-id="413f5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="413f5-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="413f5-106">окне Идентификатор функции, для которой должны возвращаться начальные адреса машинного кода.</span><span class="sxs-lookup"><span data-stu-id="413f5-106">[in] The ID of the function whose native code start addresses should be returned.</span></span>  
  
 `reJitId`  
 <span data-ttu-id="413f5-107">[in] Идентификатор функции, перекомпилированной с помощью JIT-компилятора.</span><span class="sxs-lookup"><span data-stu-id="413f5-107">[in] The identity of the JIT-recompiled function.</span></span> 
  
 `cCodeStartAddresses` \
 <span data-ttu-id="413f5-108">[in] Максимальный размер массива `codeStartAddresses`.</span><span class="sxs-lookup"><span data-stu-id="413f5-108">[in] The maximum size of the `codeStartAddresses` array.</span></span>

 `pcCodeStartAddresses` \
 <span data-ttu-id="413f5-109">заполняет Количество доступных адресов.</span><span class="sxs-lookup"><span data-stu-id="413f5-109">[out] The number of available addresses.</span></span>

 `codeStartAddresses` \
 <span data-ttu-id="413f5-110">заполняет Массив `UINT_PTR`, каждый из которых является начальным адресом для заданной функции в машинном тексте.</span><span class="sxs-lookup"><span data-stu-id="413f5-110">[out] An array of `UINT_PTR`, each one of which is the start address for a native body for the specified function.</span></span> 

## <a name="remarks"></a><span data-ttu-id="413f5-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="413f5-111">Remarks</span></span>  
 <span data-ttu-id="413f5-112">Если включена многоуровневая компиляция, функция может иметь более одного тела машинного кода.</span><span class="sxs-lookup"><span data-stu-id="413f5-112">When tiered compilation is enabled, a function may have more than one native code body.</span></span> 

## <a name="requirements"></a><span data-ttu-id="413f5-113">Требования</span><span class="sxs-lookup"><span data-stu-id="413f5-113">Requirements</span></span>  
 <span data-ttu-id="413f5-114">**Платформ** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span><span class="sxs-lookup"><span data-stu-id="413f5-114">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>  
  
 <span data-ttu-id="413f5-115">**Заголовок.** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="413f5-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="413f5-116">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="413f5-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="413f5-117">**Версии .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="413f5-117">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="413f5-118">См. также</span><span class="sxs-lookup"><span data-stu-id="413f5-118">See also</span></span>
- [<span data-ttu-id="413f5-119">Интерфейс ICorProfilerInfo9</span><span class="sxs-lookup"><span data-stu-id="413f5-119">ICorProfilerInfo9 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-interface.md)

