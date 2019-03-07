---
title: Метод ICorProfilerObjectEnum::GetCount
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.GetCount
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::GetCount
helpviewer_keywords:
- ICorProfilerObjectEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerObjectEnum interface [.NET Framework profiling]
ms.assetid: 166b0761-ed80-4ccd-9973-dc20e61bf8fa
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 65f6067fcfe0e6ef5f01a13865d002afd6da9efb
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474713"
---
# <a name="icorprofilerobjectenumgetcount-method"></a><span data-ttu-id="eeed9-102">Метод ICorProfilerObjectEnum::GetCount</span><span class="sxs-lookup"><span data-stu-id="eeed9-102">ICorProfilerObjectEnum::GetCount Method</span></span>
<span data-ttu-id="eeed9-103">Возвращает общее количество зафиксированных объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="eeed9-103">Gets the total number of frozen objects in the collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eeed9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eeed9-104">Syntax</span></span>  
  
```  
HRESULT GetCount (  
    [out] ULONG   *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eeed9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="eeed9-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="eeed9-106">[out] Указатель на число зафиксированных объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="eeed9-106">[out] A pointer to the number of frozen objects in the collection.</span></span>  
  
 <span data-ttu-id="eeed9-107">Этот метод всегда возвращает ноль в .NET Framework версии 3.5 пакетом обновления 1 (SP1) и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="eeed9-107">This method will always return zero in the .NET Framework version 3.5 Service Pack 1 (SP1) and later versions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eeed9-108">Требования</span><span class="sxs-lookup"><span data-stu-id="eeed9-108">Requirements</span></span>  
 <span data-ttu-id="eeed9-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eeed9-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eeed9-110">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="eeed9-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="eeed9-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eeed9-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eeed9-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eeed9-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eeed9-113">См. также</span><span class="sxs-lookup"><span data-stu-id="eeed9-113">See also</span></span>
- [<span data-ttu-id="eeed9-114">Интерфейс ICorProfilerObjectEnum</span><span class="sxs-lookup"><span data-stu-id="eeed9-114">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)
