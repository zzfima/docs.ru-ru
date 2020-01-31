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
ms.openlocfilehash: 5c49d75432980d2f3af77ee040bc6eb20886b027
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861675"
---
# <a name="icorprofilerinfo9getiltonativemapping3-method"></a><span data-ttu-id="94fb6-102">Метод ICorProfilerInfo9:: GetILToNativeMapping3</span><span class="sxs-lookup"><span data-stu-id="94fb6-102">ICorProfilerInfo9::GetILToNativeMapping3 Method</span></span>

<span data-ttu-id="94fb6-103">С учетом начального адреса машинного кода возвращает сведения о сопоставлении IL для этой откомпилированной версии кода.</span><span class="sxs-lookup"><span data-stu-id="94fb6-103">Given the native code start address, returns the native to IL mapping information for this jitted version of the code.</span></span>

## <a name="syntax"></a><span data-ttu-id="94fb6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="94fb6-104">Syntax</span></span>

```cpp
HRESULT GetILToNativeMapping3( [in]  UINT_PTR pNativeCodeStartAddress,
                               [in]  ULONG32 cMap,
                               [out] ULONG32 *pcMap,
                               [out] COR_DEBUG_IL_TO_NATIVE_MAP map[]);
```

## <a name="parameters"></a><span data-ttu-id="94fb6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="94fb6-105">Parameters</span></span>

- `pNativeCodeStartAddress`

  <span data-ttu-id="94fb6-106">\[в] указатель на начало собственной функции.</span><span class="sxs-lookup"><span data-stu-id="94fb6-106">\[in] A pointer to the start of a native function.</span></span>

- `cMap`

  <span data-ttu-id="94fb6-107">\[в] максимальный размер массива `map`.</span><span class="sxs-lookup"><span data-stu-id="94fb6-107">\[in] The maximum size of the `map` array.</span></span>

- `pcMap`

  <span data-ttu-id="94fb6-108">\[out] общее число доступных структур COR_DEBUG_IL_TO_NATIVE_MAP.</span><span class="sxs-lookup"><span data-stu-id="94fb6-108">\[out] The total number of available COR_DEBUG_IL_TO_NATIVE_MAP structures.</span></span>

- `map`

  <span data-ttu-id="94fb6-109">\[out] массив структур [COR_DEBUG_IL_TO_NATIVE_MAP](../debugging/cor-debug-il-to-native-map-structure.md) , каждый из которых задает смещения.</span><span class="sxs-lookup"><span data-stu-id="94fb6-109">\[out] An array of [COR_DEBUG_IL_TO_NATIVE_MAP](../debugging/cor-debug-il-to-native-map-structure.md) structures, each of which specifies the offsets.</span></span> <span data-ttu-id="94fb6-110">После возврата метода `GetILToNativeMapping3` параметр `map` будет содержать все или некоторые из структур `COR_DEBUG_IL_TO_NATIVE_MAP`.</span><span class="sxs-lookup"><span data-stu-id="94fb6-110">After the `GetILToNativeMapping3` method returns, `map` will contain some or all of the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span>

## <a name="remarks"></a><span data-ttu-id="94fb6-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="94fb6-111">Remarks</span></span>

<span data-ttu-id="94fb6-112">Если включена многоуровневая компиляция, метод может иметь более одного тела машинного кода.</span><span class="sxs-lookup"><span data-stu-id="94fb6-112">When tiered compilation is enabled, a method may have more than one native code body.</span></span> <span data-ttu-id="94fb6-113">[ICorProfilerInfo9:: жетнативекодестартаддрессес](icorprofilerinfo9-getnativecodestartaddresses-method.md) будет возвращать начальные адреса для всех частей машинного кода.</span><span class="sxs-lookup"><span data-stu-id="94fb6-113">[ICorProfilerInfo9::GetNativeCodeStartAddresses](icorprofilerinfo9-getnativecodestartaddresses-method.md) will return the start addresses for all of the native code bodies.</span></span>

## <a name="requirements"></a><span data-ttu-id="94fb6-114">Требования</span><span class="sxs-lookup"><span data-stu-id="94fb6-114">Requirements</span></span>

<span data-ttu-id="94fb6-115">**Платформы:** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="94fb6-115">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="94fb6-116">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="94fb6-116">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="94fb6-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="94fb6-117">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="94fb6-118">**Версии платформы .NET Framework:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94fb6-118">**.NET Framework Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="94fb6-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="94fb6-119">See also</span></span>

- [<span data-ttu-id="94fb6-120">Интерфейс ICorProfilerInfo9</span><span class="sxs-lookup"><span data-stu-id="94fb6-120">ICorProfilerInfo9 Interface</span></span>](icorprofilerinfo9-interface.md)
