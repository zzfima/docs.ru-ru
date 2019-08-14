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
ms.openlocfilehash: 46ceef43806fda9956797935c5eeec61f865dc6e
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2019
ms.locfileid: "68973794"
---
# <a name="icorprofilerinfo9getiltonativemapping3-method"></a><span data-ttu-id="474e7-102">Метод ICorProfilerInfo9:: GetILToNativeMapping3</span><span class="sxs-lookup"><span data-stu-id="474e7-102">ICorProfilerInfo9::GetILToNativeMapping3 Method</span></span>
  
 <span data-ttu-id="474e7-103">С учетом начального адреса машинного кода возвращает сведения о сопоставлении IL для этой откомпилированной версии кода.</span><span class="sxs-lookup"><span data-stu-id="474e7-103">Given the native code start address, returns the native to IL mapping information for this jitted version of the code.</span></span>   
  
## <a name="syntax"></a><span data-ttu-id="474e7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="474e7-104">Syntax</span></span>  
  
```cpp
HRESULT GetILToNativeMapping3( [in]  UINT_PTR pNativeCodeStartAddress,
                               [in]  ULONG32 cMap,
                               [out] ULONG32 *pcMap,
                               [out] COR_DEBUG_IL_TO_NATIVE_MAP map[]);
```  
  
#### <a name="parameters"></a><span data-ttu-id="474e7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="474e7-105">Parameters</span></span>  
 `pNativeCodeStartAddress` \
 <span data-ttu-id="474e7-106">окне Указатель на начало собственной функции.</span><span class="sxs-lookup"><span data-stu-id="474e7-106">[in] A pointer to the start of a native function.</span></span>

 `cMap` \
 <span data-ttu-id="474e7-107">[in] Максимальный размер массива `map`.</span><span class="sxs-lookup"><span data-stu-id="474e7-107">[in] The maximum size of the `map` array.</span></span> 

 `pcMap` \
 <span data-ttu-id="474e7-108">заполняет Общее число доступных структур COR_DEBUG_IL_TO_NATIVE_MAP.</span><span class="sxs-lookup"><span data-stu-id="474e7-108">[out] The total number of available COR_DEBUG_IL_TO_NATIVE_MAP structures.</span></span>

 `map` \
 <span data-ttu-id="474e7-109">заполняет Массив структур [COR_DEBUG_IL_TO_NATIVE_MAP](../debugging/cor-debug-il-to-native-map-structure.md) , каждый из которых задает смещения.</span><span class="sxs-lookup"><span data-stu-id="474e7-109">[out] An array of [COR_DEBUG_IL_TO_NATIVE_MAP](../debugging/cor-debug-il-to-native-map-structure.md) structures, each of which specifies the offsets.</span></span> <span data-ttu-id="474e7-110">После возврата метода `GetILToNativeMapping3` параметр `map` будет содержать все или некоторые из структур `COR_DEBUG_IL_TO_NATIVE_MAP`.</span><span class="sxs-lookup"><span data-stu-id="474e7-110">After the `GetILToNativeMapping3` method returns, `map` will contain some or all of the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span>

## <a name="remarks"></a><span data-ttu-id="474e7-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="474e7-111">Remarks</span></span>  
 <span data-ttu-id="474e7-112">Если включена многоуровневая компиляция, метод может иметь более одного тела машинного кода.</span><span class="sxs-lookup"><span data-stu-id="474e7-112">When tiered compilation is enabled, a method may have more than one native code body.</span></span> <span data-ttu-id="474e7-113">[ICorProfilerInfo9:: жетнативекодестартаддрессес](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-getnativecodestartaddresses-method.md) будет возвращать начальные адреса для всех частей машинного кода.</span><span class="sxs-lookup"><span data-stu-id="474e7-113">[ICorProfilerInfo9::GetNativeCodeStartAddresses](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-getnativecodestartaddresses-method.md) will return the start addresses for all of the native code bodies.</span></span>

## <a name="requirements"></a><span data-ttu-id="474e7-114">Требования</span><span class="sxs-lookup"><span data-stu-id="474e7-114">Requirements</span></span>  
 <span data-ttu-id="474e7-115">**Платформ** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span><span class="sxs-lookup"><span data-stu-id="474e7-115">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>  
  
 <span data-ttu-id="474e7-116">**Заголовок.** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="474e7-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="474e7-117">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="474e7-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="474e7-118">**Версии платформы .NET Framework:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="474e7-118">**.NET Framework Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="474e7-119">См. также</span><span class="sxs-lookup"><span data-stu-id="474e7-119">See also</span></span>
- [<span data-ttu-id="474e7-120">Интерфейс ICorProfilerInfo9</span><span class="sxs-lookup"><span data-stu-id="474e7-120">ICorProfilerInfo9 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-interface.md)

