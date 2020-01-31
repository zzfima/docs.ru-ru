---
title: Метод ICorProfilerFunctionEnum::Clone
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum.Clone Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::Clone
helpviewer_keywords:
- ICorProfilerFunctionEnum::Clone method [.NET Framework profiling]
- Clone method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 0c3d4835-e111-4e82-af6d-53f140b8f2c9
topic_type:
- apiref
ms.openlocfilehash: 2faa7185202b46e77e501d69bb471391a7c6eb68
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864626"
---
# <a name="icorprofilerfunctionenumclone-method"></a><span data-ttu-id="fa138-102">Метод ICorProfilerFunctionEnum::Clone</span><span class="sxs-lookup"><span data-stu-id="fa138-102">ICorProfilerFunctionEnum::Clone Method</span></span>
<span data-ttu-id="fa138-103">Получает указатель интерфейса на копию этого интерфейса [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="fa138-103">Gets an interface pointer to a copy of this [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa138-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fa138-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone([out] ICorProfilerFunctionEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa138-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fa138-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="fa138-106">заполняет Указатель на указатель интерфейса, который, в свою очередь, указывает на копию этого интерфейса [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="fa138-106">[out] A pointer to the interface pointer, which, in turn, points to the copy of this [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) interface.</span></span> <span data-ttu-id="fa138-107">Копия перечислителя поддерживает собственное состояние перечисления отдельно от этого перечислителя.</span><span class="sxs-lookup"><span data-stu-id="fa138-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="fa138-108">Однако начальная позиции курсора копии совпадает с текущей позицией курсора этого перечислителя.</span><span class="sxs-lookup"><span data-stu-id="fa138-108">However, the copy's initial cursor position is the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa138-109">Требования</span><span class="sxs-lookup"><span data-stu-id="fa138-109">Requirements</span></span>  
 <span data-ttu-id="fa138-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa138-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa138-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fa138-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fa138-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa138-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa138-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa138-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa138-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="fa138-114">See also</span></span>

- [<span data-ttu-id="fa138-115">Интерфейс ICorProfilerFunctionEnum</span><span class="sxs-lookup"><span data-stu-id="fa138-115">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="fa138-116">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="fa138-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
