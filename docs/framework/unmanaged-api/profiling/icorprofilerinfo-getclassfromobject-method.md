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
ms.openlocfilehash: 104dfcaa4120d72f3aa758b66134050f178fef75
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilerinfogetclassfromobject-method"></a><span data-ttu-id="79667-102">Метод ICorProfilerInfo::GetClassFromObject</span><span class="sxs-lookup"><span data-stu-id="79667-102">ICorProfilerInfo::GetClassFromObject Method</span></span>
<span data-ttu-id="79667-103">Возвращает `ClassID` объекта, учитывая его `ObjectID`.</span><span class="sxs-lookup"><span data-stu-id="79667-103">Gets the `ClassID` of an object, given its `ObjectID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79667-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="79667-104">Syntax</span></span>  
  
```  
HRESULT GetClassFromObject(  
    [in]  ObjectID objectId,  
    [out] ClassID *pClassId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="79667-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="79667-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="79667-106">[in] Идентификатор объекта, для которого нужно получить `ClassID`.</span><span class="sxs-lookup"><span data-stu-id="79667-106">[in] The ID of the object for which to get the `ClassID`.</span></span>  
  
 `pClassId`  
 <span data-ttu-id="79667-107">[out] Указатель на возвращаемый `ClassID`.</span><span class="sxs-lookup"><span data-stu-id="79667-107">[out] A pointer to the returned `ClassID`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79667-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="79667-108">Remarks</span></span>  
 <span data-ttu-id="79667-109">Значение null `pClassId` указывает, что `objectId` имеет тип, который будет выгружен.</span><span class="sxs-lookup"><span data-stu-id="79667-109">A null `pClassId` indicates that `objectId` has a type that is unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79667-110">Требования</span><span class="sxs-lookup"><span data-stu-id="79667-110">Requirements</span></span>  
 <span data-ttu-id="79667-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79667-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79667-112">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="79667-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="79667-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="79667-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="79667-114">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79667-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79667-115">См. также</span><span class="sxs-lookup"><span data-stu-id="79667-115">See Also</span></span>  
 [<span data-ttu-id="79667-116">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="79667-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
