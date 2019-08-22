---
title: ICorProfilerInfo9::GetCodeInfo4
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo9.GetCodeInfo4
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: e6708971909c1035e41786f4d8dad1cf9afdffaf
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69665619"
---
# <a name="icorprofilerinfo9getcodeinfo4-method"></a><span data-ttu-id="038ca-102">Метод ICorProfilerInfo9:: GetCodeInfo4</span><span class="sxs-lookup"><span data-stu-id="038ca-102">ICorProfilerInfo9::GetCodeInfo4 Method</span></span>

<span data-ttu-id="038ca-103">При наличии начального адреса машинного кода возвращает блоки виртуальной памяти, в которых хранится этот код.</span><span class="sxs-lookup"><span data-stu-id="038ca-103">Given the native code start address, returns the blocks of virtual memory that store this code.</span></span>

## <a name="syntax"></a><span data-ttu-id="038ca-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="038ca-104">Syntax</span></span>

```cpp
HRESULT GetCodeInfo4( [in]  UINT_PTR pNativeCodeStartAddress,
                      [in]  ULONG32 cCodeInfos,
                      [out] ULONG32* pcCodeInfos,
                      [out] COR_PRF_CODE_INFO codeInfos[]);
```

#### <a name="parameters"></a><span data-ttu-id="038ca-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="038ca-105">Parameters</span></span>

`pNativeCodeStartAddress` \
<span data-ttu-id="038ca-106">окне Указатель на начало собственной функции.</span><span class="sxs-lookup"><span data-stu-id="038ca-106">[in] A pointer to the start of a native function.</span></span>

`cCodeInfos` \
<span data-ttu-id="038ca-107">[in] Размер массива `codeInfos`.</span><span class="sxs-lookup"><span data-stu-id="038ca-107">[in] The size of the `codeInfos` array.</span></span>

`pcCodeInfos` \
<span data-ttu-id="038ca-108">заполняет Указатель на общее число доступных структур [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="038ca-108">[out] A pointer to the total number of [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures available.</span></span>

`codeInfos` \
<span data-ttu-id="038ca-109">[out] Буфер, предоставляемый вызывающим объектом.</span><span class="sxs-lookup"><span data-stu-id="038ca-109">[out] A caller-provided buffer.</span></span> <span data-ttu-id="038ca-110">После возврата метода он содержит массив структур `COR_PRF_CODE_INFO`, каждая из которых описывает блок машинного кода.</span><span class="sxs-lookup"><span data-stu-id="038ca-110">After the method returns, it contains an array of `COR_PRF_CODE_INFO` structures, each of which describes a block of native code.</span></span>

## <a name="remarks"></a><span data-ttu-id="038ca-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="038ca-111">Remarks</span></span>

<span data-ttu-id="038ca-112">Метод `GetCodeInfo4` аналогичен [GetCodeInfo3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getcodeinfo3-method.md), за исключением того, что он может искать информацию о коде для различных версий метода.</span><span class="sxs-lookup"><span data-stu-id="038ca-112">The `GetCodeInfo4` method is similar to [GetCodeInfo3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getcodeinfo3-method.md), except that it can look up code information for different native versions of a method.</span></span>

> [!NOTE]
> <span data-ttu-id="038ca-113">`GetCodeInfo4`может запустить сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="038ca-113">`GetCodeInfo4` can trigger a garbage collection.</span></span>

<span data-ttu-id="038ca-114">Расширения сортируются в порядке возрастания смещения общих промежуточного языка (CIL).</span><span class="sxs-lookup"><span data-stu-id="038ca-114">The extents are sorted in order of increasing Common Intermediate Language (CIL) offset.</span></span>

<span data-ttu-id="038ca-115">После `GetCodeInfo4` возврата необходимо убедиться `codeInfos` , что буфер достаточно велик, чтобы вместить все структуры [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="038ca-115">After `GetCodeInfo4` returns, you must verify that the `codeInfos` buffer was large enough to contain all the [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures.</span></span> <span data-ttu-id="038ca-116">Для этого сравните значение параметра `cCodeInfos` со значением параметра `cchName`.</span><span class="sxs-lookup"><span data-stu-id="038ca-116">To do this, compare the value of `cCodeInfos` with the value of the `cchName` parameter.</span></span> <span data-ttu-id="038ca-117">При `cCodeInfos` делении на размер `pcCodeInfos`структуры [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) меньше, выделяет буфер большего `codeInfos` размера, обновляет `cCodeInfos` новый, больший размер и вызывается `GetCodeInfo4` снова.</span><span class="sxs-lookup"><span data-stu-id="038ca-117">If `cCodeInfos` divided by the size of a [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structure is smaller than `pcCodeInfos`, allocate a larger `codeInfos` buffer, update `cCodeInfos` with the new, larger size, and call `GetCodeInfo4` again.</span></span>

<span data-ttu-id="038ca-118">Кроме того, сначала можно вызвать метод `GetCodeInfo4` с буфером `codeInfos` нулевой длины для получения правильного размера буфера.</span><span class="sxs-lookup"><span data-stu-id="038ca-118">Alternatively, you can first call `GetCodeInfo4` with a zero-length `codeInfos` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="038ca-119">Затем можно `codeInfos` задать размер буфера равным значению, возвращенному `pcCodeInfos`в, умноженному на размер структуры [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) и вызывать `GetCodeInfo4` повторно.</span><span class="sxs-lookup"><span data-stu-id="038ca-119">You can then set the `codeInfos` buffer size to the value returned in `pcCodeInfos`, multiplied by the size of a [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structure, and call `GetCodeInfo4` again.</span></span>

## <a name="requirements"></a><span data-ttu-id="038ca-120">Требования</span><span class="sxs-lookup"><span data-stu-id="038ca-120">Requirements</span></span>

<span data-ttu-id="038ca-121">**Платформ** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span><span class="sxs-lookup"><span data-stu-id="038ca-121">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>

<span data-ttu-id="038ca-122">**Заголовок.** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="038ca-122">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="038ca-123">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="038ca-123">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="038ca-124">**Версии .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="038ca-124">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="038ca-125">См. также</span><span class="sxs-lookup"><span data-stu-id="038ca-125">See also</span></span>

- [<span data-ttu-id="038ca-126">Интерфейс ICorProfilerInfo9</span><span class="sxs-lookup"><span data-stu-id="038ca-126">ICorProfilerInfo9 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/ICorProfilerInfo9-interface.md)
