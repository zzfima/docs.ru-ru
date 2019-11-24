---
title: Метод IMetaDataEmit::MergeEnd
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.MergeEnd
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::MergeEnd
helpviewer_keywords:
- MergeEnd method [.NET Framework metadata]
- IMetaDataEmit::MergeEnd method [.NET Framework metadata]
ms.assetid: 2d64315a-1af1-4c60-aedf-f8a781914aea
topic_type:
- apiref
ms.openlocfilehash: 34ecfc2f01f22971e135358806adeea632e02f8b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448039"
---
# <a name="imetadataemitmergeend-method"></a><span data-ttu-id="8896a-102">Метод IMetaDataEmit::MergeEnd</span><span class="sxs-lookup"><span data-stu-id="8896a-102">IMetaDataEmit::MergeEnd Method</span></span>

<span data-ttu-id="8896a-103">Merges into the current scope all the metadata scopes specified by one or more prior calls to [IMetaDataEmit::Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md).</span><span class="sxs-lookup"><span data-stu-id="8896a-103">Merges into the current scope all the metadata scopes specified by one or more prior calls to [IMetaDataEmit::Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="8896a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8896a-104">Syntax</span></span>

```cppcpp
HRESULT MergeEnd ();
```

## <a name="parameters"></a><span data-ttu-id="8896a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8896a-105">Parameters</span></span>

<span data-ttu-id="8896a-106">This method takes no parameters.</span><span class="sxs-lookup"><span data-stu-id="8896a-106">This method takes no parameters.</span></span>

## <a name="remarks"></a><span data-ttu-id="8896a-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="8896a-107">Remarks</span></span>

<span data-ttu-id="8896a-108">This routine triggers the actual merge of metadata, of all import scopes specified by preceding calls to `IMetaDataEmit::Merge`, into the current output scope.</span><span class="sxs-lookup"><span data-stu-id="8896a-108">This routine triggers the actual merge of metadata, of all import scopes specified by preceding calls to `IMetaDataEmit::Merge`, into the current output scope.</span></span>

<span data-ttu-id="8896a-109">The following special conditions apply to the merge:</span><span class="sxs-lookup"><span data-stu-id="8896a-109">The following special conditions apply to the merge:</span></span>

- <span data-ttu-id="8896a-110">A module version identifier (MVID) is never imported, because it is unique to the metadata in the import scope.</span><span class="sxs-lookup"><span data-stu-id="8896a-110">A module version identifier (MVID) is never imported, because it is unique to the metadata in the import scope.</span></span>

- <span data-ttu-id="8896a-111">No existing module-wide properties are overwritten.</span><span class="sxs-lookup"><span data-stu-id="8896a-111">No existing module-wide properties are overwritten.</span></span>

  <span data-ttu-id="8896a-112">If module properties were already set for the current scope, no module properties are imported.</span><span class="sxs-lookup"><span data-stu-id="8896a-112">If module properties were already set for the current scope, no module properties are imported.</span></span> <span data-ttu-id="8896a-113">However, if module properties have not been set in the current scope, they are imported only once, when they are first encountered.</span><span class="sxs-lookup"><span data-stu-id="8896a-113">However, if module properties have not been set in the current scope, they are imported only once, when they are first encountered.</span></span> <span data-ttu-id="8896a-114">If those module properties are encountered again, they are duplicates.</span><span class="sxs-lookup"><span data-stu-id="8896a-114">If those module properties are encountered again, they are duplicates.</span></span> <span data-ttu-id="8896a-115">If the values of all module properties (except MVID) are compared and no duplicates are found, an error is raised.</span><span class="sxs-lookup"><span data-stu-id="8896a-115">If the values of all module properties (except MVID) are compared and no duplicates are found, an error is raised.</span></span>

- <span data-ttu-id="8896a-116">For type definitions (`TypeDef`), no duplicates are merged into the current scope.</span><span class="sxs-lookup"><span data-stu-id="8896a-116">For type definitions (`TypeDef`), no duplicates are merged into the current scope.</span></span> <span data-ttu-id="8896a-117">`TypeDef` objects are checked for duplicates against each *fully-qualified object name* + *GUID* + *version number*.</span><span class="sxs-lookup"><span data-stu-id="8896a-117">`TypeDef` objects are checked for duplicates against each *fully-qualified object name* + *GUID* + *version number*.</span></span> <span data-ttu-id="8896a-118">If there is a match on either name or GUID, and any of the other two elements is different, an error is raised.</span><span class="sxs-lookup"><span data-stu-id="8896a-118">If there is a match on either name or GUID, and any of the other two elements is different, an error is raised.</span></span> <span data-ttu-id="8896a-119">Otherwise, if all three items match, `MergeEnd` does a cursory check to ensure the entries are indeed duplicates; if not, an error is raised.</span><span class="sxs-lookup"><span data-stu-id="8896a-119">Otherwise, if all three items match, `MergeEnd` does a cursory check to ensure the entries are indeed duplicates; if not, an error is raised.</span></span> <span data-ttu-id="8896a-120">This cursory check looks for:</span><span class="sxs-lookup"><span data-stu-id="8896a-120">This cursory check looks for:</span></span>

  - <span data-ttu-id="8896a-121">The same member declarations, occurring in the same order.</span><span class="sxs-lookup"><span data-stu-id="8896a-121">The same member declarations, occurring in the same order.</span></span> <span data-ttu-id="8896a-122">Members that are flagged as `mdPrivateScope` (see the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration) are not included in this check; they are merged specially.</span><span class="sxs-lookup"><span data-stu-id="8896a-122">Members that are flagged as `mdPrivateScope` (see the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration) are not included in this check; they are merged specially.</span></span>

  - <span data-ttu-id="8896a-123">The same class layout.</span><span class="sxs-lookup"><span data-stu-id="8896a-123">The same class layout.</span></span>

  <span data-ttu-id="8896a-124">This means that a `TypeDef` object must always be fully and consistently defined in every metadata scope in which it is declared; if its member implementations (for a class) are spread across multiple compilation units, the full definition is assumed to be present in every scope and not incremental to each scope.</span><span class="sxs-lookup"><span data-stu-id="8896a-124">This means that a `TypeDef` object must always be fully and consistently defined in every metadata scope in which it is declared; if its member implementations (for a class) are spread across multiple compilation units, the full definition is assumed to be present in every scope and not incremental to each scope.</span></span> <span data-ttu-id="8896a-125">For example, if parameter names are relevant to the contract, they must be emitted the same way into every scope; if they are not relevant, they should not be emitted into metadata.</span><span class="sxs-lookup"><span data-stu-id="8896a-125">For example, if parameter names are relevant to the contract, they must be emitted the same way into every scope; if they are not relevant, they should not be emitted into metadata.</span></span>

  <span data-ttu-id="8896a-126">The exception is that a `TypeDef` object can have incremental members flagged as `mdPrivateScope`.</span><span class="sxs-lookup"><span data-stu-id="8896a-126">The exception is that a `TypeDef` object can have incremental members flagged as `mdPrivateScope`.</span></span> <span data-ttu-id="8896a-127">On encountering these, `MergeEnd` incrementally adds them to the current scope without regard for duplicates.</span><span class="sxs-lookup"><span data-stu-id="8896a-127">On encountering these, `MergeEnd` incrementally adds them to the current scope without regard for duplicates.</span></span> <span data-ttu-id="8896a-128">Because the compiler understands the private scope, the compiler must be responsible for enforcing rules.</span><span class="sxs-lookup"><span data-stu-id="8896a-128">Because the compiler understands the private scope, the compiler must be responsible for enforcing rules.</span></span>

- <span data-ttu-id="8896a-129">Relative virtual addresses (RVAs) are not imported or merged; the compiler is expected to re-emit this information.</span><span class="sxs-lookup"><span data-stu-id="8896a-129">Relative virtual addresses (RVAs) are not imported or merged; the compiler is expected to re-emit this information.</span></span>

- <span data-ttu-id="8896a-130">Custom attributes are merged only when the item to which they are attached is merged.</span><span class="sxs-lookup"><span data-stu-id="8896a-130">Custom attributes are merged only when the item to which they are attached is merged.</span></span> <span data-ttu-id="8896a-131">For example, custom attributes associated with a class are merged when the class is first encountered.</span><span class="sxs-lookup"><span data-stu-id="8896a-131">For example, custom attributes associated with a class are merged when the class is first encountered.</span></span> <span data-ttu-id="8896a-132">If custom attributes are associated with a `TypeDef` or `MemberDef` that is specific to the compilation unit (such as the time stamp of a member compile), they are not merged and it is up to the compiler to remove or update such metadata.</span><span class="sxs-lookup"><span data-stu-id="8896a-132">If custom attributes are associated with a `TypeDef` or `MemberDef` that is specific to the compilation unit (such as the time stamp of a member compile), they are not merged and it is up to the compiler to remove or update such metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="8896a-133">Требования</span><span class="sxs-lookup"><span data-stu-id="8896a-133">Requirements</span></span>

<span data-ttu-id="8896a-134">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8896a-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="8896a-135">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8896a-135">**Header:** Cor.h</span></span>

<span data-ttu-id="8896a-136">**Library:** Used as a resource in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8896a-136">**Library:** Used as a resource in MSCorEE.dll</span></span>

<span data-ttu-id="8896a-137">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8896a-137">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="8896a-138">См. также</span><span class="sxs-lookup"><span data-stu-id="8896a-138">See also</span></span>

- [<span data-ttu-id="8896a-139">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="8896a-139">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="8896a-140">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="8896a-140">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
