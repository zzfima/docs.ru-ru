---
title: ICorProfilerInfo9::GetILToNativeMapping3
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo9.GetILToNativeMapping3
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 1a5a259e6604d906e55166b3fcb770bc37d346c5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444730"
---
# <a name="icorprofilerinfo9getiltonativemapping3-method"></a><span data-ttu-id="9fb1c-102">Метод ICorProfilerInfo9:: GetILToNativeMapping3</span><span class="sxs-lookup"><span data-stu-id="9fb1c-102">ICorProfilerInfo9::GetILToNativeMapping3 Method</span></span>

<span data-ttu-id="9fb1c-103">С учетом начального адреса машинного кода возвращает сведения о сопоставлении IL для этой откомпилированной версии кода.</span><span class="sxs-lookup"><span data-stu-id="9fb1c-103">Given the native code start address, returns the native to IL mapping information for this jitted version of the code.</span></span>

## <a name="syntax"></a><span data-ttu-id="9fb1c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9fb1c-104">Syntax</span></span>

```cpp
HRESULT GetILToNativeMapping3( [in]  UINT_PTR pNativeCodeStartAddress,
                               [in]  ULONG32 cMap,
                               [out] ULONG32 *pcMap,
                               [out] COR_DEBUG_IL_TO_NATIVE_MAP map[]);
```

#### <a name="parameters"></a><span data-ttu-id="9fb1c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9fb1c-105">Parameters</span></span>

`pNativeCodeStartAddress` \
<span data-ttu-id="9fb1c-106">окне Указатель на начало собственной функции.</span><span class="sxs-lookup"><span data-stu-id="9fb1c-106">[in] A pointer to the start of a native function.</span></span>

`cMap` \
<span data-ttu-id="9fb1c-107">[in] Максимальный размер массива `map`.</span><span class="sxs-lookup"><span data-stu-id="9fb1c-107">[in] The maximum size of the `map` array.</span></span>

`pcMap` \
<span data-ttu-id="9fb1c-108">[out] Общее количество доступных структур COR_DEBUG_IL_TO_NATIVE_MAP.</span><span class="sxs-lookup"><span data-stu-id="9fb1c-108">[out] The total number of available COR_DEBUG_IL_TO_NATIVE_MAP structures.</span></span>

`map` \
<span data-ttu-id="9fb1c-109">заполняет Массив структур [COR_DEBUG_IL_TO_NATIVE_MAP](../debugging/cor-debug-il-to-native-map-structure.md) , каждый из которых задает смещения.</span><span class="sxs-lookup"><span data-stu-id="9fb1c-109">[out] An array of [COR_DEBUG_IL_TO_NATIVE_MAP](../debugging/cor-debug-il-to-native-map-structure.md) structures, each of which specifies the offsets.</span></span> <span data-ttu-id="9fb1c-110">После возврата метода `GetILToNativeMapping3` параметр `map` будет содержать все или некоторые из структур `COR_DEBUG_IL_TO_NATIVE_MAP`.</span><span class="sxs-lookup"><span data-stu-id="9fb1c-110">After the `GetILToNativeMapping3` method returns, `map` will contain some or all of the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span>

## <a name="remarks"></a><span data-ttu-id="9fb1c-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="9fb1c-111">Remarks</span></span>

<span data-ttu-id="9fb1c-112">Если включена многоуровневая компиляция, метод может иметь более одного тела машинного кода.</span><span class="sxs-lookup"><span data-stu-id="9fb1c-112">When tiered compilation is enabled, a method may have more than one native code body.</span></span> <span data-ttu-id="9fb1c-113">[ICorProfilerInfo9:: жетнативекодестартаддрессес](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-getnativecodestartaddresses-method.md) будет возвращать начальные адреса для всех частей машинного кода.</span><span class="sxs-lookup"><span data-stu-id="9fb1c-113">[ICorProfilerInfo9::GetNativeCodeStartAddresses](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-getnativecodestartaddresses-method.md) will return the start addresses for all of the native code bodies.</span></span>

## <a name="requirements"></a><span data-ttu-id="9fb1c-114">Требования</span><span class="sxs-lookup"><span data-stu-id="9fb1c-114">Requirements</span></span>

<span data-ttu-id="9fb1c-115">**Платформы:** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="9fb1c-115">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="9fb1c-116">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9fb1c-116">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="9fb1c-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9fb1c-117">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="9fb1c-118">**Версии платформы .NET Framework:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9fb1c-118">**.NET Framework Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="9fb1c-119">См. также</span><span class="sxs-lookup"><span data-stu-id="9fb1c-119">See also</span></span>

- [<span data-ttu-id="9fb1c-120">Интерфейс ICorProfilerInfo9</span><span class="sxs-lookup"><span data-stu-id="9fb1c-120">ICorProfilerInfo9 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-interface.md)
