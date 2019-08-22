---
title: 'ICorProfilerInfo8:: Исфунктиондинамик'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo8.IsFunctionDynamic
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 046db493db77572904a8454a5b002dcae15b9e1d
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69661157"
---
# <a name="icorprofilerinfo8isfunctiondynamic-method"></a><span data-ttu-id="53b2c-102">Метод ICorProfilerInfo8:: Исфунктиондинамик</span><span class="sxs-lookup"><span data-stu-id="53b2c-102">ICorProfilerInfo8::IsFunctionDynamic Method</span></span>

<span data-ttu-id="53b2c-103">Определяет, имеет ли функция связанные метаданные.</span><span class="sxs-lookup"><span data-stu-id="53b2c-103">Determines if a function does not have associated metadata.</span></span>

## <a name="syntax"></a><span data-ttu-id="53b2c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="53b2c-104">Syntax</span></span>

```cpp
HRESULT IsFunctionDynamic( [in]  FunctionID  functionId,
                           [out] BOOL        *isDynamic);
```

#### <a name="parameters"></a><span data-ttu-id="53b2c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="53b2c-105">Parameters</span></span>

`functionId` \
<span data-ttu-id="53b2c-106">окне  Объект `FunctionID` , определяющий рассматриваемую функцию.</span><span class="sxs-lookup"><span data-stu-id="53b2c-106">[in]  The `FunctionID` that identifies the function in question.</span></span>

`isDynamic` \
<span data-ttu-id="53b2c-107">заполняет Указатель на объект `BOOL` , который будет содержать значение, указывающее, имеет ли функция метаданные.</span><span class="sxs-lookup"><span data-stu-id="53b2c-107">[out] A pointer to a `BOOL` that will contain a value indicating if the function has no metadata.</span></span>

## <a name="remarks"></a><span data-ttu-id="53b2c-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="53b2c-108">Remarks</span></span>

<span data-ttu-id="53b2c-109">Функция считается динамической, если она не имеет метаданных.</span><span class="sxs-lookup"><span data-stu-id="53b2c-109">A function is considered dynamic if it has no metadata.</span></span> <span data-ttu-id="53b2c-110">Некоторые методы, такие как заглушки IL или методы LCG, не имеют связанных метаданных, которые можно получить с помощью API-интерфейсов интерфейса IMetaDataImport.</span><span class="sxs-lookup"><span data-stu-id="53b2c-110">Certain methods like IL Stubs or LCG Methods do not have associated metadata that can be retrieved using the IMetaDataImport APIs.</span></span> <span data-ttu-id="53b2c-111">Эти методы могут быть обнаружены профилировщиками с помощью указателей инструкций или путем прослушивания в [ICorProfilerCallback::D инамикмесоджиткомпилатионстартед](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md).</span><span class="sxs-lookup"><span data-stu-id="53b2c-111">These methods can be encountered by profilers through instruction pointers or by listening to [ICorProfilerCallback::DynamicMethodJITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="53b2c-112">Требования</span><span class="sxs-lookup"><span data-stu-id="53b2c-112">Requirements</span></span>

<span data-ttu-id="53b2c-113">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53b2c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="53b2c-114">**Заголовок.** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="53b2c-114">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="53b2c-115">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="53b2c-115">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="53b2c-116">**.NET Framework версии:** [! ВКЛЮЧИТЬ[net_current_v472plus](../../../../includes/net-current-v472plus.md)</span><span class="sxs-lookup"><span data-stu-id="53b2c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="53b2c-117">См. также</span><span class="sxs-lookup"><span data-stu-id="53b2c-117">See also</span></span>

- [<span data-ttu-id="53b2c-118">Интерфейс ICorProfilerInfo8</span><span class="sxs-lookup"><span data-stu-id="53b2c-118">ICorProfilerInfo8 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md)
