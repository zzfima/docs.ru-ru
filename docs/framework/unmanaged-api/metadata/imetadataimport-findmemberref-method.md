---
title: Метод IMetaDataImport::FindMemberRef
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMemberRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMemberRef
helpviewer_keywords:
- IMetaDataImport::FindMemberRef method [.NET Framework metadata]
- FindMemberRef method [.NET Framework metadata]
ms.assetid: 1ccda329-d752-4d89-abe8-511af3c3f4c9
topic_type:
- apiref
ms.openlocfilehash: 59512cc1c1b280d7fe6deb2f9d721ad53547e356
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437953"
---
# <a name="imetadataimportfindmemberref-method"></a><span data-ttu-id="21692-102">Метод IMetaDataImport::FindMemberRef</span><span class="sxs-lookup"><span data-stu-id="21692-102">IMetaDataImport::FindMemberRef Method</span></span>
<span data-ttu-id="21692-103">Gets a pointer to the MemberRef token for the member reference that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span><span class="sxs-lookup"><span data-stu-id="21692-103">Gets a pointer to the MemberRef token for the member reference that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21692-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="21692-104">Syntax</span></span>  
  
```cpp  
HRESULT FindMemberRef (  
   [in]  mdTypeRef          td,  
   [in]  LPCWSTR            szName,   
   [in]  PCCOR_SIGNATURE    pvSigBlob,   
   [in]  ULONG              cbSigBlob,   
   [out] mdMemberRef        *pmr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="21692-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="21692-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="21692-106">[in] The TypeRef token for the class or interface that encloses the member reference to search for.</span><span class="sxs-lookup"><span data-stu-id="21692-106">[in] The TypeRef token for the class or interface that encloses the member reference to search for.</span></span> <span data-ttu-id="21692-107">If this value is `mdTokenNil`, the lookup is done for a global variable or a global-function reference.</span><span class="sxs-lookup"><span data-stu-id="21692-107">If this value is `mdTokenNil`, the lookup is done for a global variable or a global-function reference.</span></span>  
  
 `szName`  
 <span data-ttu-id="21692-108">[in] The name of the member reference to search for.</span><span class="sxs-lookup"><span data-stu-id="21692-108">[in] The name of the member reference to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="21692-109">[in] A pointer to the binary metadata signature of the member reference.</span><span class="sxs-lookup"><span data-stu-id="21692-109">[in] A pointer to the binary metadata signature of the member reference.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="21692-110">[in] The size in bytes of `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="21692-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="21692-111">[out] A pointer to the matching MemberRef token.</span><span class="sxs-lookup"><span data-stu-id="21692-111">[out] A pointer to the matching MemberRef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21692-112">Заметки</span><span class="sxs-lookup"><span data-stu-id="21692-112">Remarks</span></span>  
 <span data-ttu-id="21692-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span><span class="sxs-lookup"><span data-stu-id="21692-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span>  
  
 <span data-ttu-id="21692-114">The signature passed to `FindMemberRef` must have been generated in the current scope, because signatures are bound to a particular scope.</span><span class="sxs-lookup"><span data-stu-id="21692-114">The signature passed to `FindMemberRef` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="21692-115">A signature can embed a token that identifies the enclosing class or value type.</span><span class="sxs-lookup"><span data-stu-id="21692-115">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="21692-116">The token is an index into the local TypeDef table.</span><span class="sxs-lookup"><span data-stu-id="21692-116">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="21692-117">You cannot build a run-time signature outside the context of the current scope and use that signature as input to `FindMemberRef`.</span><span class="sxs-lookup"><span data-stu-id="21692-117">You cannot build a run-time signature outside the context of the current scope and use that signature as input to `FindMemberRef`.</span></span>  
  
 <span data-ttu-id="21692-118">`FindMemberRef` finds only member references that were defined directly in the class or interface; it does not find inherited member references.</span><span class="sxs-lookup"><span data-stu-id="21692-118">`FindMemberRef` finds only member references that were defined directly in the class or interface; it does not find inherited member references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21692-119">Требования</span><span class="sxs-lookup"><span data-stu-id="21692-119">Requirements</span></span>  
 <span data-ttu-id="21692-120">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21692-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21692-121">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="21692-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="21692-122">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="21692-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="21692-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21692-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21692-124">См. также</span><span class="sxs-lookup"><span data-stu-id="21692-124">See also</span></span>

- [<span data-ttu-id="21692-125">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="21692-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="21692-126">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="21692-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
