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
ms.openlocfilehash: ea0484db53a94a3134b85f97b294c5eb7d1dc7e6
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57500568"
---
# <a name="icorprofilerobjectenumclone-method"></a><span data-ttu-id="77fb5-102">Метод ICorProfilerObjectEnum::Clone</span><span class="sxs-lookup"><span data-stu-id="77fb5-102">ICorProfilerObjectEnum::Clone Method</span></span>
<span data-ttu-id="77fb5-103">Получает указатель интерфейса на копию этого [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="77fb5-103">Gets an interface pointer to a copy of this [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77fb5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="77fb5-104">Syntax</span></span>  
  
```  
HRESULT Clone (  
    [out] ICorProfilerObjectEnum   **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="77fb5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="77fb5-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="77fb5-106">[out] Указатель на указатель интерфейса, в свою очередь указывает на копию данного объекта `ICorProfilerObjectEnum` интерфейс.</span><span class="sxs-lookup"><span data-stu-id="77fb5-106">[out] A pointer to the interface pointer that in turn points to the copy of this `ICorProfilerObjectEnum` interface.</span></span> <span data-ttu-id="77fb5-107">Копия хранит собственное состояние перечисления отдельно от этого интерфейса.</span><span class="sxs-lookup"><span data-stu-id="77fb5-107">The copy maintains its own enumeration state separately from this one.</span></span> <span data-ttu-id="77fb5-108">Тем не менее копии Начальная позиция курсора будет таким же, как этот перечислитель текущей позиции курсора.</span><span class="sxs-lookup"><span data-stu-id="77fb5-108">However, the copy's initial cursor position will be the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77fb5-109">Требования</span><span class="sxs-lookup"><span data-stu-id="77fb5-109">Requirements</span></span>  
 <span data-ttu-id="77fb5-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77fb5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77fb5-111">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="77fb5-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="77fb5-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="77fb5-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="77fb5-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77fb5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77fb5-114">См. также</span><span class="sxs-lookup"><span data-stu-id="77fb5-114">See also</span></span>
- [<span data-ttu-id="77fb5-115">Интерфейс ICorProfilerObjectEnum</span><span class="sxs-lookup"><span data-stu-id="77fb5-115">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)
