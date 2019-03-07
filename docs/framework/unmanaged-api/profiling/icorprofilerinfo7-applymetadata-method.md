---
title: Метод ICorProfilerInfo7::ApplyMetaData
ms.date: 02/15/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo7.ApplyMetaData
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: a1bfb649-4584-4d35-b3e6-8fe59b53992a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b7fa8e2f06faa399734c44b1a52b41246296ef3f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57498917"
---
# <a name="icorprofilerinfo7applymetadata-method"></a><span data-ttu-id="06aea-102">Метод ICorProfilerInfo7::ApplyMetaData</span><span class="sxs-lookup"><span data-stu-id="06aea-102">ICorProfilerInfo7::ApplyMetaData Method</span></span>
<span data-ttu-id="06aea-103">[Поддерживается в .NET Framework 4.6.1 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="06aea-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="06aea-104">Применяет метаданные, вновь определением `IMetadataEmit::Define*` методов к указанному модулю.</span><span class="sxs-lookup"><span data-stu-id="06aea-104">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06aea-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="06aea-105">Syntax</span></span>  
  
```cpp
HRESULT ApplyMetaData(  
        [in] ModuleID moduleID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06aea-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="06aea-106">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="06aea-107">[in] Идентификатор модуля, метаданные которого было изменено.</span><span class="sxs-lookup"><span data-stu-id="06aea-107">[in] The identifier of the module whose metadata was changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06aea-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="06aea-108">Remarks</span></span>  
 <span data-ttu-id="06aea-109">При изменении метаданных после [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) обратного вызова, этот метод необходимо вызвать перед использованием новые метаданные.</span><span class="sxs-lookup"><span data-stu-id="06aea-109">If metadata changes are made after the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback, you must call this method before using the new metadata.</span></span>  
  
 <span data-ttu-id="06aea-110">`ApplyMetaData` поддерживает только добавление следующие метаданные:</span><span class="sxs-lookup"><span data-stu-id="06aea-110">`ApplyMetaData` only supports adding the following types of metadata:</span></span>  
  
-   <span data-ttu-id="06aea-111">`AssemblyRef` записи, которые создаются путем вызова [IMetaDataAssemblyEmit::DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md).</span><span class="sxs-lookup"><span data-stu-id="06aea-111">`AssemblyRef` records, which you create by calling the [IMetaDataAssemblyEmit::DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md).</span></span> <span data-ttu-id="06aea-112">метод.</span><span class="sxs-lookup"><span data-stu-id="06aea-112">method.</span></span>  
  
-   <span data-ttu-id="06aea-113">`TypeRef` записи, которые создаются путем вызова [IMetaDataEmit::DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="06aea-113">`TypeRef` records, which you create by calling the [IMetaDataEmit::DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) method.</span></span>  
  
-   <span data-ttu-id="06aea-114">`TypeSpec` записи, которые создаются путем вызова [IMetaDataEmit::GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="06aea-114">`TypeSpec` records, which you create by calling the [IMetaDataEmit::GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
-   <span data-ttu-id="06aea-115">`MemberRef` записи, которые создаются путем вызова [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="06aea-115">`MemberRef` records, which you create by calling the [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) method.</span></span>  
  
-   <span data-ttu-id="06aea-116">`MemberSpec` записи, которые создаются путем вызова [IMetaDataEmit2::DefineMethodSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="06aea-116">`MemberSpec` records, which you create by calling the [IMetaDataEmit2::DefineMethodSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md) method.</span></span>  
  
-   <span data-ttu-id="06aea-117">`UserString` записи, которые создаются путем вызова [IMetaDataEmit::DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="06aea-117">`UserString` records, which you create by calling the [IMetaDataEmit::DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) method.</span></span>  

<span data-ttu-id="06aea-118">Начиная с .NET Core 3.0 — `ApplyMetaData` также поддерживает следующие типы:</span><span class="sxs-lookup"><span data-stu-id="06aea-118">Starting with .NET Core 3.0, `ApplyMetaData` also supports the following types:</span></span>

- <span data-ttu-id="06aea-119">`TypeDef` записи, которые создаются путем вызова [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="06aea-119">`TypeDef` records, which you create by calling the [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) method.</span></span>

- <span data-ttu-id="06aea-120">`MethodDef` записи, которые создаются путем вызова [IMetaDataEmit::DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="06aea-120">`MethodDef` records, which you create by calling the [IMetaDataEmit::DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md) method.</span></span> <span data-ttu-id="06aea-121">Однако добавление виртуальные методы в существующий тип не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="06aea-121">However, adding virtual methods to an existing type is not supported.</span></span> <span data-ttu-id="06aea-122">Виртуальные методы, которые необходимо добавить перед [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="06aea-122">Virtual methods must be added before the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="06aea-123">Требования</span><span class="sxs-lookup"><span data-stu-id="06aea-123">Requirements</span></span>  
 <span data-ttu-id="06aea-124">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06aea-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06aea-125">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="06aea-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="06aea-126">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="06aea-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="06aea-127">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06aea-127">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06aea-128">См. также</span><span class="sxs-lookup"><span data-stu-id="06aea-128">See also</span></span>
- [<span data-ttu-id="06aea-129">Интерфейс ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="06aea-129">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
