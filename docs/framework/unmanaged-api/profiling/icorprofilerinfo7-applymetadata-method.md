---
title: "Метод ICorProfilerInfo7::ApplyMetaData"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
api_name: ICorProfilerInfo7.ApplyMetaData
api_location: mscorwks.dll
api_type: COM
ms.assetid: a1bfb649-4584-4d35-b3e6-8fe59b53992a
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e3724555df58392e5ab59ccb4f52dd2de860b8d4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfo7applymetadata-method"></a><span data-ttu-id="537a3-102">Метод ICorProfilerInfo7::ApplyMetaData</span><span class="sxs-lookup"><span data-stu-id="537a3-102">ICorProfilerInfo7::ApplyMetaData Method</span></span>
<span data-ttu-id="537a3-103">[Поддерживается в .NET Framework 4.6.1 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="537a3-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="537a3-104">Применяет метаданные, определяемые вновь `IMetadataEmit::Define*` методы для указанного модуля.</span><span class="sxs-lookup"><span data-stu-id="537a3-104">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="537a3-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="537a3-105">Syntax</span></span>  
  
```cpp
HRESULT ApplyMetaData(  
        [in] ModuleID moduleID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="537a3-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="537a3-106">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="537a3-107">[in] Идентификатор модуля, метаданные которого было изменено.</span><span class="sxs-lookup"><span data-stu-id="537a3-107">[in] The identifier of the module whose metadata was changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="537a3-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="537a3-108">Remarks</span></span>  
 <span data-ttu-id="537a3-109">При изменении метаданных после [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) обратного вызова, необходимо вызвать этот метод, прежде чем использовать новые метаданные.</span><span class="sxs-lookup"><span data-stu-id="537a3-109">If metadata changes are made after the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback, you must call this method before using the new metadata.</span></span>  
  
 <span data-ttu-id="537a3-110">`ApplyMetaData`поддерживает только добавление следующие метаданные:</span><span class="sxs-lookup"><span data-stu-id="537a3-110">`ApplyMetaData` only supports adding the following types of metadata:</span></span>  
  
-   <span data-ttu-id="537a3-111">`AssemblyRef`записи, которые создаются путем вызова [IMetaDataAssemblyEmit::DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md).</span><span class="sxs-lookup"><span data-stu-id="537a3-111">`AssemblyRef` records, which you create by calling the [IMetaDataAssemblyEmit::DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md).</span></span> <span data-ttu-id="537a3-112">метод.</span><span class="sxs-lookup"><span data-stu-id="537a3-112">method.</span></span>  
  
-   <span data-ttu-id="537a3-113">`TypeRef`записи, которые создаются путем вызова [IMetaDataEmit::DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="537a3-113">`TypeRef` records, which you create by calling the [IMetaDataEmit::DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) method.</span></span>  
  
-   <span data-ttu-id="537a3-114">`TypeSpec`записи, которые создаются путем вызова [IMetaDataEmit::GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="537a3-114">`TypeSpec` records, which you create by calling the [IMetaDataEmit::GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
-   <span data-ttu-id="537a3-115">`MemberRef`записи, которые создаются путем вызова [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="537a3-115">`MemberRef` records, which you create by calling the [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) method.</span></span>  
  
-   <span data-ttu-id="537a3-116">`MemberSpec`записи, которые создаются путем вызова [IMetaDataEmit2::DefineMethodSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="537a3-116">`MemberSpec` records, which you create by calling the [IMetaDataEmit2::DefineMethodSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md) method.</span></span>  
  
-   <span data-ttu-id="537a3-117">`UserString`записи, которые создаются путем вызова [IMetaDataEmit::DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="537a3-117">`UserString` records, which you create by calling the [IMetaDataEmit::DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="537a3-118">Требования</span><span class="sxs-lookup"><span data-stu-id="537a3-118">Requirements</span></span>  
 <span data-ttu-id="537a3-119">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="537a3-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="537a3-120">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="537a3-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="537a3-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="537a3-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="537a3-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="537a3-122">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="537a3-123">См. также</span><span class="sxs-lookup"><span data-stu-id="537a3-123">See Also</span></span>  
 [<span data-ttu-id="537a3-124">Интерфейс ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="537a3-124">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
