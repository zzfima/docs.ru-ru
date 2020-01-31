---
title: 'Метод ICorProfilerInfo7:: ApplyMetaData'
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
ms.openlocfilehash: b9e488a512ad506a8975bfff44ae02cd84c29f74
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861701"
---
# <a name="icorprofilerinfo7applymetadata-method"></a><span data-ttu-id="8a26b-102">Метод ICorProfilerInfo7:: ApplyMetaData</span><span class="sxs-lookup"><span data-stu-id="8a26b-102">ICorProfilerInfo7::ApplyMetaData Method</span></span>
<span data-ttu-id="8a26b-103">[Поддерживается в .NET Framework 4.6.1 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="8a26b-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="8a26b-104">Применяет метаданные, которые недавно задаются `IMetadataEmit::Define*` методами, к указанному модулю.</span><span class="sxs-lookup"><span data-stu-id="8a26b-104">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a26b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8a26b-105">Syntax</span></span>  
  
```cpp
HRESULT ApplyMetaData(  
        [in] ModuleID moduleID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a26b-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="8a26b-106">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="8a26b-107">окне Идентификатор модуля, метаданные которого были изменены.</span><span class="sxs-lookup"><span data-stu-id="8a26b-107">[in] The identifier of the module whose metadata was changed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a26b-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="8a26b-108">Remarks</span></span>  
 <span data-ttu-id="8a26b-109">Если изменения метаданных вносятся после обратного вызова [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) , необходимо вызвать этот метод перед использованием новых метаданных.</span><span class="sxs-lookup"><span data-stu-id="8a26b-109">If metadata changes are made after the [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback, you must call this method before using the new metadata.</span></span>  
  
 <span data-ttu-id="8a26b-110">`ApplyMetaData` поддерживает добавление только следующих типов метаданных:</span><span class="sxs-lookup"><span data-stu-id="8a26b-110">`ApplyMetaData` only supports adding the following types of metadata:</span></span>  
  
- <span data-ttu-id="8a26b-111">`AssemblyRef` записи, которые создаются путем вызова метода [IMetaDataAssemblyEmit::D ефинеассемблиреф](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md).</span><span class="sxs-lookup"><span data-stu-id="8a26b-111">`AssemblyRef` records, which you create by calling the [IMetaDataAssemblyEmit::DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md).</span></span> <span data-ttu-id="8a26b-112">метод.</span><span class="sxs-lookup"><span data-stu-id="8a26b-112">method.</span></span>  
  
- <span data-ttu-id="8a26b-113">`TypeRef` записи, которые создаются путем вызова метода [IMetaDataEmit::D ефинетиперефбинаме](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8a26b-113">`TypeRef` records, which you create by calling the [IMetaDataEmit::DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) method.</span></span>  
  
- <span data-ttu-id="8a26b-114">`TypeSpec` записи, которые создаются путем вызова метода [IMetaDataEmit:: жеттокенфромтипеспек](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8a26b-114">`TypeSpec` records, which you create by calling the [IMetaDataEmit::GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
- <span data-ttu-id="8a26b-115">`MemberRef` записи, которые создаются путем вызова метода [IMetaDataEmit::D ефинемемберреф](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8a26b-115">`MemberRef` records, which you create by calling the [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) method.</span></span>  
  
- <span data-ttu-id="8a26b-116">`MemberSpec` записи, которые создаются путем вызова метода [IMetaDataEmit2::D ефинемесодспек](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8a26b-116">`MemberSpec` records, which you create by calling the [IMetaDataEmit2::DefineMethodSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md) method.</span></span>  
  
- <span data-ttu-id="8a26b-117">`UserString` записи, которые создаются путем вызова метода [IMetaDataEmit::D ефинеусерстринг](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8a26b-117">`UserString` records, which you create by calling the [IMetaDataEmit::DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) method.</span></span>  

<span data-ttu-id="8a26b-118">Начиная с .NET Core 3,0, `ApplyMetaData` также поддерживает следующие типы:</span><span class="sxs-lookup"><span data-stu-id="8a26b-118">Starting with .NET Core 3.0, `ApplyMetaData` also supports the following types:</span></span>

- <span data-ttu-id="8a26b-119">`TypeDef` записи, которые создаются путем вызова метода [IMetaDataEmit::D ефинетипедеф](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8a26b-119">`TypeDef` records, which you create by calling the [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) method.</span></span>

- <span data-ttu-id="8a26b-120">`MethodDef` записи, которые создаются путем вызова метода [IMetaDataEmit::D ефинемесод](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8a26b-120">`MethodDef` records, which you create by calling the [IMetaDataEmit::DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md) method.</span></span> <span data-ttu-id="8a26b-121">Однако добавление виртуальных методов в существующий тип не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="8a26b-121">However, adding virtual methods to an existing type is not supported.</span></span> <span data-ttu-id="8a26b-122">Виртуальные методы должны быть добавлены перед обратным вызовом [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8a26b-122">Virtual methods must be added before the [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>

## <a name="requirements"></a><span data-ttu-id="8a26b-123">Требования</span><span class="sxs-lookup"><span data-stu-id="8a26b-123">Requirements</span></span>  
 <span data-ttu-id="8a26b-124">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a26b-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a26b-125">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8a26b-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8a26b-126">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a26b-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a26b-127">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a26b-127">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a26b-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="8a26b-128">See also</span></span>

- [<span data-ttu-id="8a26b-129">Интерфейс ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="8a26b-129">ICorProfilerInfo7 Interface</span></span>](icorprofilerinfo7-interface.md)
