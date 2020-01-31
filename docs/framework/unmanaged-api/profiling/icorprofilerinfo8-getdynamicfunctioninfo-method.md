---
title: 'ICorProfilerInfo8:: Жетдинамикфунктионинфо'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo8.GetDynamicFunctionInfo
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 66a08cf60ae4ca9bb6e373d230d0819ee6f9b28c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790013"
---
# <a name="icorprofilerinfo8getdynamicfunctioninfo-method"></a><span data-ttu-id="e581d-102">Метод ICorProfilerInfo8:: Жетдинамикфунктионинфо</span><span class="sxs-lookup"><span data-stu-id="e581d-102">ICorProfilerInfo8::GetDynamicFunctionInfo Method</span></span>

<span data-ttu-id="e581d-103">Извлекает сведения о динамических методах.</span><span class="sxs-lookup"><span data-stu-id="e581d-103">Retrieves information about dynamic methods.</span></span>

## <a name="syntax"></a><span data-ttu-id="e581d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e581d-104">Syntax</span></span>

```cpp
HRESULT GetDynamicFunctionInfo( [in]  FunctionID              functionId,
                                [out] ModuleID                *moduleId,
                                [out] PCCOR_SIGNATURE         *ppvSig,
                                [out] ULONG                   *pbSig,
                                [in]  ULONG                   cchName,
                                [out] ULONG                   *pcchName,
                                [out] WCHAR                   wszName[]);
```

## <a name="parameters"></a><span data-ttu-id="e581d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e581d-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="e581d-106">\[в] идентификатор функции, для которой требуется получить сведения.</span><span class="sxs-lookup"><span data-stu-id="e581d-106">\[in] The ID of the function for which to retrieve information.</span></span>

- `moduleId`

  <span data-ttu-id="e581d-107">\[в] указатель на модуль, в котором определен родительский класс функции.</span><span class="sxs-lookup"><span data-stu-id="e581d-107">\[in] A pointer to the module in which the function's parent class is defined.</span></span>

- `ppvSig`

  <span data-ttu-id="e581d-108">\[out] указатель на сигнатуру для функции.</span><span class="sxs-lookup"><span data-stu-id="e581d-108">\[out] A pointer to the signature for the function.</span></span>

- `pbSig`

  <span data-ttu-id="e581d-109">\[out] указатель на число байтов для сигнатуры функции.</span><span class="sxs-lookup"><span data-stu-id="e581d-109">\[out] A pointer to the count of bytes for the function signature.</span></span>

- `cchName`

  <span data-ttu-id="e581d-110">\[в] максимальный размер массива `wszName`.</span><span class="sxs-lookup"><span data-stu-id="e581d-110">\[in] The maximum size of the `wszName` array.</span></span>

- `pcchName`

  <span data-ttu-id="e581d-111">\[out] число символов в массиве `wszName`.</span><span class="sxs-lookup"><span data-stu-id="e581d-111">\[out] The number of characters in the `wszName` array.</span></span>

- `wszName`

  <span data-ttu-id="e581d-112">\[out] массив `WCHAR`, который является именем функции, если таковая существует.</span><span class="sxs-lookup"><span data-stu-id="e581d-112">\[out] An array of `WCHAR` which is the name of the function, if one exists.</span></span>

## <a name="remarks"></a><span data-ttu-id="e581d-113">Заметки</span><span class="sxs-lookup"><span data-stu-id="e581d-113">Remarks</span></span>

<span data-ttu-id="e581d-114">Некоторые методы, такие как заглушки IL или LCG, не имеют связанных метаданных, которые можно извлечь с помощью интерфейсов API [IMetaDataImport](../metadata/imetadataimport-interface.md) и [IMetaDataImport2](../metadata/imetadataimport2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="e581d-114">Certain methods like IL Stubs or LCG do not have associated metadata that can be retrieved using the [IMetaDataImport](../metadata/imetadataimport-interface.md) and [IMetaDataImport2](../metadata/imetadataimport2-interface.md) APIs.</span></span> <span data-ttu-id="e581d-115">Такие методы могут быть обнаружены профилировщиками с помощью указателей инструкций или путем прослушивания [ICorProfilerCallback8::D инамикмесоджиткомпилатионстартед](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md).</span><span class="sxs-lookup"><span data-stu-id="e581d-115">Such methods can be encountered by profilers through instruction pointers or by listening to [ICorProfilerCallback8::DynamicMethodJITCompilationStarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md).</span></span>

<span data-ttu-id="e581d-116">Этот API можно использовать для получения сведений о динамических методах, включая понятное имя, если оно доступно.</span><span class="sxs-lookup"><span data-stu-id="e581d-116">This API can be used to retrieve information about dynamic methods, including a friendly name, if available.</span></span>

## <a name="requirements"></a><span data-ttu-id="e581d-117">Требования</span><span class="sxs-lookup"><span data-stu-id="e581d-117">Requirements</span></span>

<span data-ttu-id="e581d-118">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e581d-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="e581d-119">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e581d-119">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="e581d-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e581d-120">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="e581d-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e581d-121">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="e581d-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="e581d-122">See also</span></span>

- [<span data-ttu-id="e581d-123">Интерфейс ICorProfilerInfo8</span><span class="sxs-lookup"><span data-stu-id="e581d-123">ICorProfilerInfo8 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md)
