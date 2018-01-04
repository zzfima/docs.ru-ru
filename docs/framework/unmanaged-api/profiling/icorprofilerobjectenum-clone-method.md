---
title: "Метод ICorProfilerObjectEnum::Clone"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerObjectEnum.Clone
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerObjectEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerObjectEnum interface [.NET Framework profiling]
- ICorProfilerObjectEnum::Clone method [.NET Framework profiling]
ms.assetid: b0b2facd-5991-4f4c-932d-c4937f45cef9
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2d8e478eb9165b4aa5bf019f02f4f128931d928b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerobjectenumclone-method"></a><span data-ttu-id="5a8f2-102">Метод ICorProfilerObjectEnum::Clone</span><span class="sxs-lookup"><span data-stu-id="5a8f2-102">ICorProfilerObjectEnum::Clone Method</span></span>
<span data-ttu-id="5a8f2-103">Получает указатель интерфейса на копию этого [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) интерфейса.</span><span class="sxs-lookup"><span data-stu-id="5a8f2-103">Gets an interface pointer to a copy of this [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a8f2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5a8f2-104">Syntax</span></span>  
  
```  
HRESULT Clone (  
    [out] ICorProfilerObjectEnum   **ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5a8f2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5a8f2-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="5a8f2-106">[out] Указатель на указатель интерфейса, который в свою очередь указывает на копию этого `ICorProfilerObjectEnum` интерфейса.</span><span class="sxs-lookup"><span data-stu-id="5a8f2-106">[out] A pointer to the interface pointer that in turn points to the copy of this `ICorProfilerObjectEnum` interface.</span></span> <span data-ttu-id="5a8f2-107">Копия хранит собственное состояние перечисления отдельно от этого интерфейса.</span><span class="sxs-lookup"><span data-stu-id="5a8f2-107">The copy maintains its own enumeration state separately from this one.</span></span> <span data-ttu-id="5a8f2-108">Тем не менее копии Начальная позиция курсора будет совпадать с текущей позиции курсора этот перечислитель.</span><span class="sxs-lookup"><span data-stu-id="5a8f2-108">However, the copy's initial cursor position will be the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a8f2-109">Требования</span><span class="sxs-lookup"><span data-stu-id="5a8f2-109">Requirements</span></span>  
 <span data-ttu-id="5a8f2-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a8f2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a8f2-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5a8f2-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5a8f2-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a8f2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a8f2-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a8f2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a8f2-114">См. также</span><span class="sxs-lookup"><span data-stu-id="5a8f2-114">See Also</span></span>  
 [<span data-ttu-id="5a8f2-115">Интерфейс ICorProfilerObjectEnum</span><span class="sxs-lookup"><span data-stu-id="5a8f2-115">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)
