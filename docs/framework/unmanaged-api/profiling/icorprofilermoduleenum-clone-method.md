---
title: Метод ICorProfilerModuleEnum::Clone
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum.Clone Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerModuleEnum interface [.NET Framework profiling]
- ICorProfilerModuleEnum::Clone method [.NET Framework profiling]
ms.assetid: 7dec7e36-8d88-416d-b437-abf98b76c1df
topic_type:
- apiref
ms.openlocfilehash: a6b36883ec0914426b4f4c937390c1622faead25
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868295"
---
# <a name="icorprofilermoduleenumclone-method"></a><span data-ttu-id="c7bb8-102">Метод ICorProfilerModuleEnum::Clone</span><span class="sxs-lookup"><span data-stu-id="c7bb8-102">ICorProfilerModuleEnum::Clone Method</span></span>
<span data-ttu-id="c7bb8-103">Получает указатель интерфейса на копию этого интерфейса [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="c7bb8-103">Gets an interface pointer to a copy of this [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7bb8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c7bb8-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone([out] ICorProfilerObjectEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7bb8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c7bb8-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="c7bb8-106">заполняет Указатель на указатель интерфейса, который, в свою очередь, указывает на копию этого интерфейса [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="c7bb8-106">[out] A pointer to the interface pointer that in turn points to the copy of this [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) interface.</span></span> <span data-ttu-id="c7bb8-107">Копия перечислителя поддерживает собственное состояние перечисления отдельно от этого перечислителя.</span><span class="sxs-lookup"><span data-stu-id="c7bb8-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="c7bb8-108">Однако начальная позиции курсора копии совпадает с текущей позицией курсора этого перечислителя.</span><span class="sxs-lookup"><span data-stu-id="c7bb8-108">However, the copy's initial cursor position is the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7bb8-109">Требования</span><span class="sxs-lookup"><span data-stu-id="c7bb8-109">Requirements</span></span>  
 <span data-ttu-id="c7bb8-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7bb8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7bb8-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c7bb8-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c7bb8-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7bb8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c7bb8-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7bb8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7bb8-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="c7bb8-114">See also</span></span>

- [<span data-ttu-id="c7bb8-115">Интерфейс ICorProfilerModuleEnum</span><span class="sxs-lookup"><span data-stu-id="c7bb8-115">ICorProfilerModuleEnum Interface</span></span>](icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="c7bb8-116">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="c7bb8-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
