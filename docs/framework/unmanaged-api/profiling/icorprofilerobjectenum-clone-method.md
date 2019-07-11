---
title: Метод ICorProfilerObjectEnum::Clone
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.Clone
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerObjectEnum interface [.NET Framework profiling]
- ICorProfilerObjectEnum::Clone method [.NET Framework profiling]
ms.assetid: b0b2facd-5991-4f4c-932d-c4937f45cef9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 72df5a5c2d0ef4bc462eeaa43f2d55a3d2a56fe4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775022"
---
# <a name="icorprofilerobjectenumclone-method"></a><span data-ttu-id="d31ca-102">Метод ICorProfilerObjectEnum::Clone</span><span class="sxs-lookup"><span data-stu-id="d31ca-102">ICorProfilerObjectEnum::Clone Method</span></span>
<span data-ttu-id="d31ca-103">Получает указатель интерфейса на копию этого [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="d31ca-103">Gets an interface pointer to a copy of this [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d31ca-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d31ca-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (  
    [out] ICorProfilerObjectEnum   **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d31ca-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d31ca-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="d31ca-106">[out] Указатель на указатель интерфейса, в свою очередь указывает на копию данного объекта `ICorProfilerObjectEnum` интерфейс.</span><span class="sxs-lookup"><span data-stu-id="d31ca-106">[out] A pointer to the interface pointer that in turn points to the copy of this `ICorProfilerObjectEnum` interface.</span></span> <span data-ttu-id="d31ca-107">Копия хранит собственное состояние перечисления отдельно от этого интерфейса.</span><span class="sxs-lookup"><span data-stu-id="d31ca-107">The copy maintains its own enumeration state separately from this one.</span></span> <span data-ttu-id="d31ca-108">Тем не менее копии Начальная позиция курсора будет таким же, как этот перечислитель текущей позиции курсора.</span><span class="sxs-lookup"><span data-stu-id="d31ca-108">However, the copy's initial cursor position will be the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d31ca-109">Требования</span><span class="sxs-lookup"><span data-stu-id="d31ca-109">Requirements</span></span>  
 <span data-ttu-id="d31ca-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d31ca-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d31ca-111">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d31ca-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d31ca-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d31ca-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d31ca-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d31ca-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d31ca-114">См. также</span><span class="sxs-lookup"><span data-stu-id="d31ca-114">See also</span></span>

- [<span data-ttu-id="d31ca-115">Интерфейс ICorProfilerObjectEnum</span><span class="sxs-lookup"><span data-stu-id="d31ca-115">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)
