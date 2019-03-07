---
title: Метод ICorProfilerInfo::GetClassFromToken
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassFromToken
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassFromToken
helpviewer_keywords:
- ICorProfilerInfo::GetClassFromToken method [.NET Framework profiling]
- GetClassFromToken method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 0afc1197-2a5b-424f-8b82-9cb59a7e00db
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a74e99e0b669c1b3d8e36d881391f27ef71ae306
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57493548"
---
# <a name="icorprofilerinfogetclassfromtoken-method"></a><span data-ttu-id="9d702-102">Метод ICorProfilerInfo::GetClassFromToken</span><span class="sxs-lookup"><span data-stu-id="9d702-102">ICorProfilerInfo::GetClassFromToken Method</span></span>
<span data-ttu-id="9d702-103">Получает идентификатор класса, заданным токеном метаданных.</span><span class="sxs-lookup"><span data-stu-id="9d702-103">Gets the ID of the class, given the metadata token.</span></span> <span data-ttu-id="9d702-104">Этот метод является устаревшим в .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="9d702-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="9d702-105">Используйте [ICorProfilerInfo2::GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) вместо этого.</span><span class="sxs-lookup"><span data-stu-id="9d702-105">Use [ICorProfilerInfo2::GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d702-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9d702-106">Syntax</span></span>  
  
```  
HRESULT GetClassFromToken(  
    [in]  ModuleID  moduleId,  
    [in]  mdTypeDef typeDef,  
    [out] ClassID   *pClassId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d702-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="9d702-107">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="9d702-108">[in] Идентификатор модуля, содержащего класса.</span><span class="sxs-lookup"><span data-stu-id="9d702-108">[in] The ID of the module that contains the class.</span></span>  
  
 `typeDef`  
 <span data-ttu-id="9d702-109">[in] `mdTypeDef` Токен метаданных, который ссылается на класс.</span><span class="sxs-lookup"><span data-stu-id="9d702-109">[in] An `mdTypeDef` metadata token that references the class.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="9d702-110">[out] Указатель на идентификатор класса.</span><span class="sxs-lookup"><span data-stu-id="9d702-110">[out] A pointer to the class ID.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d702-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="9d702-111">Remarks</span></span>  
 <span data-ttu-id="9d702-112">Этот метод является устаревшим. Вместо этого используйте `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` для всех типов.</span><span class="sxs-lookup"><span data-stu-id="9d702-112">This method is obsolete; instead, use `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` for all types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d702-113">Требования</span><span class="sxs-lookup"><span data-stu-id="9d702-113">Requirements</span></span>  
 <span data-ttu-id="9d702-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d702-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d702-115">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9d702-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9d702-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9d702-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9d702-117">**Версии платформы .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="9d702-117">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d702-118">См. также</span><span class="sxs-lookup"><span data-stu-id="9d702-118">See also</span></span>
- [<span data-ttu-id="9d702-119">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="9d702-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
