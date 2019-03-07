---
title: Метод ICorProfilerInfo::GetClassFromObject
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassFromObject
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassFromObject
helpviewer_keywords:
- GetClassFromObject method [.NET Framework profiling]
- ICorProfilerInfo::GetClassFromObject method [.NET Framework profiling]
ms.assetid: b97493fb-713e-49d5-a73e-5688b2ad0700
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d48006011ae50f1157d357a909eb6c93b25baf7e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496057"
---
# <a name="icorprofilerinfogetclassfromobject-method"></a><span data-ttu-id="97cd5-102">Метод ICorProfilerInfo::GetClassFromObject</span><span class="sxs-lookup"><span data-stu-id="97cd5-102">ICorProfilerInfo::GetClassFromObject Method</span></span>
<span data-ttu-id="97cd5-103">Получает `ClassID` объекта, учитывая его `ObjectID`.</span><span class="sxs-lookup"><span data-stu-id="97cd5-103">Gets the `ClassID` of an object, given its `ObjectID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97cd5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="97cd5-104">Syntax</span></span>  
  
```  
HRESULT GetClassFromObject(  
    [in]  ObjectID objectId,  
    [out] ClassID *pClassId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="97cd5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="97cd5-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="97cd5-106">[in] Идентификатор объекта, для которого необходимо получить `ClassID`.</span><span class="sxs-lookup"><span data-stu-id="97cd5-106">[in] The ID of the object for which to get the `ClassID`.</span></span>  
  
 `pClassId`  
 <span data-ttu-id="97cd5-107">[out] Указатель на возвращенный `ClassID`.</span><span class="sxs-lookup"><span data-stu-id="97cd5-107">[out] A pointer to the returned `ClassID`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97cd5-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="97cd5-108">Remarks</span></span>  
 <span data-ttu-id="97cd5-109">Значение null `pClassId` указывает, что `objectId` имеет тип, который выгружается.</span><span class="sxs-lookup"><span data-stu-id="97cd5-109">A null `pClassId` indicates that `objectId` has a type that is unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97cd5-110">Требования</span><span class="sxs-lookup"><span data-stu-id="97cd5-110">Requirements</span></span>  
 <span data-ttu-id="97cd5-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97cd5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97cd5-112">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="97cd5-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="97cd5-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="97cd5-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="97cd5-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97cd5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97cd5-115">См. также</span><span class="sxs-lookup"><span data-stu-id="97cd5-115">See also</span></span>
- [<span data-ttu-id="97cd5-116">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="97cd5-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
