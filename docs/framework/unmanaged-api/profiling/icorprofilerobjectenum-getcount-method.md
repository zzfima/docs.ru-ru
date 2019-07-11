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
ms.openlocfilehash: f08b3d9634362d47615fe14287ab9ec35e78ee65
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775055"
---
# <a name="icorprofilerobjectenumgetcount-method"></a><span data-ttu-id="7f7ce-102">Метод ICorProfilerObjectEnum::GetCount</span><span class="sxs-lookup"><span data-stu-id="7f7ce-102">ICorProfilerObjectEnum::GetCount Method</span></span>
<span data-ttu-id="7f7ce-103">Возвращает общее количество зафиксированных объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="7f7ce-103">Gets the total number of frozen objects in the collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f7ce-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7f7ce-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG   *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f7ce-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7f7ce-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="7f7ce-106">[out] Указатель на число зафиксированных объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="7f7ce-106">[out] A pointer to the number of frozen objects in the collection.</span></span>  
  
 <span data-ttu-id="7f7ce-107">Этот метод всегда возвращает ноль в .NET Framework версии 3.5 пакетом обновления 1 (SP1) и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="7f7ce-107">This method will always return zero in the .NET Framework version 3.5 Service Pack 1 (SP1) and later versions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f7ce-108">Требования</span><span class="sxs-lookup"><span data-stu-id="7f7ce-108">Requirements</span></span>  
 <span data-ttu-id="7f7ce-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f7ce-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f7ce-110">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7f7ce-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7f7ce-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7f7ce-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7f7ce-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f7ce-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f7ce-113">См. также</span><span class="sxs-lookup"><span data-stu-id="7f7ce-113">See also</span></span>

- [<span data-ttu-id="7f7ce-114">Интерфейс ICorProfilerObjectEnum</span><span class="sxs-lookup"><span data-stu-id="7f7ce-114">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)
