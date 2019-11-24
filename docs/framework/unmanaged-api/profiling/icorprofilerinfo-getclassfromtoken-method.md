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
ms.openlocfilehash: 6999821412b3cdd614cb30858a0616c9f27a6baa
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448107"
---
# <a name="icorprofilerinfogetclassfromtoken-method"></a><span data-ttu-id="99fa7-102">Метод ICorProfilerInfo::GetClassFromToken</span><span class="sxs-lookup"><span data-stu-id="99fa7-102">ICorProfilerInfo::GetClassFromToken Method</span></span>
<span data-ttu-id="99fa7-103">Gets the ID of the class, given the metadata token.</span><span class="sxs-lookup"><span data-stu-id="99fa7-103">Gets the ID of the class, given the metadata token.</span></span> <span data-ttu-id="99fa7-104">This method is obsolete in the .NET Framework version 2.0.</span><span class="sxs-lookup"><span data-stu-id="99fa7-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="99fa7-105">Use [ICorProfilerInfo2::GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) instead.</span><span class="sxs-lookup"><span data-stu-id="99fa7-105">Use [ICorProfilerInfo2::GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99fa7-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="99fa7-106">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromToken(  
    [in]  ModuleID  moduleId,  
    [in]  mdTypeDef typeDef,  
    [out] ClassID   *pClassId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99fa7-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="99fa7-107">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="99fa7-108">[in] The ID of the module that contains the class.</span><span class="sxs-lookup"><span data-stu-id="99fa7-108">[in] The ID of the module that contains the class.</span></span>  
  
 `typeDef`  
 <span data-ttu-id="99fa7-109">[in] An `mdTypeDef` metadata token that references the class.</span><span class="sxs-lookup"><span data-stu-id="99fa7-109">[in] An `mdTypeDef` metadata token that references the class.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="99fa7-110">[out] A pointer to the class ID.</span><span class="sxs-lookup"><span data-stu-id="99fa7-110">[out] A pointer to the class ID.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99fa7-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="99fa7-111">Remarks</span></span>  
 <span data-ttu-id="99fa7-112">This method is obsolete; instead, use `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` for all types.</span><span class="sxs-lookup"><span data-stu-id="99fa7-112">This method is obsolete; instead, use `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` for all types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99fa7-113">Требования</span><span class="sxs-lookup"><span data-stu-id="99fa7-113">Requirements</span></span>  
 <span data-ttu-id="99fa7-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99fa7-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99fa7-115">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="99fa7-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="99fa7-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="99fa7-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="99fa7-117">**.NET Framework Versions:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="99fa7-117">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99fa7-118">См. также</span><span class="sxs-lookup"><span data-stu-id="99fa7-118">See also</span></span>

- [<span data-ttu-id="99fa7-119">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="99fa7-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
