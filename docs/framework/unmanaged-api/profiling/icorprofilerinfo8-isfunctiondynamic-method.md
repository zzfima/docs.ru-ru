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
ms.openlocfilehash: 71c4e749368dce65d5250b9ab78fd8713e9d61a0
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2019
ms.locfileid: "68973874"
---
# <a name="icorprofilerinfo8isfunctiondynamic-method"></a><span data-ttu-id="1b1b4-102">Метод ICorProfilerInfo8:: Исфунктиондинамик</span><span class="sxs-lookup"><span data-stu-id="1b1b4-102">ICorProfilerInfo8::IsFunctionDynamic Method</span></span>
  
  <span data-ttu-id="1b1b4-103">Определяет, имеет ли функция связанные метаданные.</span><span class="sxs-lookup"><span data-stu-id="1b1b4-103">Determines if a function does not have associated metadata.</span></span>    
  
## <a name="syntax"></a><span data-ttu-id="1b1b4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1b1b4-104">Syntax</span></span>  
  
```cpp
HRESULT IsFunctionDynamic( [in]  FunctionID  functionId,
                           [out] BOOL        *isDynamic);
```  
  
#### <a name="parameters"></a><span data-ttu-id="1b1b4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1b1b4-105">Parameters</span></span>  
 `functionId` \
  <span data-ttu-id="1b1b4-106">окне  Объект `FunctionID` , определяющий рассматриваемую функцию.</span><span class="sxs-lookup"><span data-stu-id="1b1b4-106">[in]  The `FunctionID` that identifies the function in question.</span></span>

  `isDynamic` \
  <span data-ttu-id="1b1b4-107">заполняет Указатель на объект `BOOL` , который будет содержать значение, указывающее, имеет ли функция метаданные.</span><span class="sxs-lookup"><span data-stu-id="1b1b4-107">[out] A pointer to a `BOOL` that will contain a value indicating if the function has no metadata.</span></span>

## <a name="remarks"></a><span data-ttu-id="1b1b4-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="1b1b4-108">Remarks</span></span>  
 <span data-ttu-id="1b1b4-109">Функция считается динамической, если она не имеет метаданных.</span><span class="sxs-lookup"><span data-stu-id="1b1b4-109">A function is considered dynamic if it has no metadata.</span></span> <span data-ttu-id="1b1b4-110">Некоторые методы, такие как заглушки IL или методы LCG, не имеют связанных метаданных, которые можно получить с помощью API-интерфейсов интерфейса IMetaDataImport.</span><span class="sxs-lookup"><span data-stu-id="1b1b4-110">Certain methods like IL Stubs or LCG Methods do not have associated metadata that can be retrieved using the IMetaDataImport APIs.</span></span> <span data-ttu-id="1b1b4-111">Эти методы могут быть обнаружены профилировщиками с помощью указателей инструкций или путем прослушивания в [ICorProfilerCallback::D инамикмесоджиткомпилатионстартед](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md).</span><span class="sxs-lookup"><span data-stu-id="1b1b4-111">These methods can be encountered by profilers through instruction pointers or by listening to [ICorProfilerCallback::DynamicMethodJITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="1b1b4-112">Требования</span><span class="sxs-lookup"><span data-stu-id="1b1b4-112">Requirements</span></span>  
 <span data-ttu-id="1b1b4-113">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b1b4-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b1b4-114">**Заголовок.** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="1b1b4-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1b1b4-115">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="1b1b4-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1b1b4-116">**.NET Framework версии:** [! ВКЛЮЧИТЬ[net_current_v472plus](../../../../includes/net-current-v472plus.md)</span><span class="sxs-lookup"><span data-stu-id="1b1b4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b1b4-117">См. также</span><span class="sxs-lookup"><span data-stu-id="1b1b4-117">See also</span></span>
- [<span data-ttu-id="1b1b4-118">Интерфейс ICorProfilerInfo8</span><span class="sxs-lookup"><span data-stu-id="1b1b4-118">ICorProfilerInfo8 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md)

