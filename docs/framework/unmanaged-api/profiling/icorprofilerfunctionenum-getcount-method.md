---
title: Метод ICorProfilerFunctionEnum::GetCount
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum.GetCount Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::GetCount
helpviewer_keywords:
- ICorProfilerFunctionEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 62ec65e3-3e9d-400b-ae61-d24b8963995b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 413b860353d3a9e75771f9349ebf151d8f2e3579
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453300"
---
# <a name="icorprofilerfunctionenumgetcount-method"></a><span data-ttu-id="04c86-102">Метод ICorProfilerFunctionEnum::GetCount</span><span class="sxs-lookup"><span data-stu-id="04c86-102">ICorProfilerFunctionEnum::GetCount Method</span></span>
<span data-ttu-id="04c86-103">Возвращает количество функций, загруженных приложением или принудительно загруженных профилировщиком.</span><span class="sxs-lookup"><span data-stu-id="04c86-103">Gets the number of functions that were loaded by the application or forcibly loaded by the profiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04c86-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="04c86-104">Syntax</span></span>  
  
```  
HRESULT GetCount([out] ULONG * pcelt);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="04c86-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="04c86-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="04c86-106">[out] Число функций, которые были загружены.</span><span class="sxs-lookup"><span data-stu-id="04c86-106">[out] The number of functions that were loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04c86-107">Требования</span><span class="sxs-lookup"><span data-stu-id="04c86-107">Requirements</span></span>  
 <span data-ttu-id="04c86-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04c86-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04c86-109">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="04c86-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="04c86-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="04c86-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="04c86-111">**Версии платформы .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04c86-111">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04c86-112">См. также</span><span class="sxs-lookup"><span data-stu-id="04c86-112">See Also</span></span>  
 [<span data-ttu-id="04c86-113">Интерфейс ICorProfilerFunctionEnum</span><span class="sxs-lookup"><span data-stu-id="04c86-113">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 [<span data-ttu-id="04c86-114">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="04c86-114">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
