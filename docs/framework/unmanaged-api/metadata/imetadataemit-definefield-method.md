---
title: Метод IMetaDataEmit::DefineField
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineField
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineField
helpviewer_keywords:
- IMetaDataEmit::DefineField method [.NET Framework metadata]
- DefineField method, IMetaDataEmit interface [.NET Framework metadata
ms.assetid: 6b5be4fc-2e86-499c-8b09-833160bca767
topic_type:
- apiref
ms.openlocfilehash: 40f24a4ea628ce92a27ab1bfe97fc87a57dfa4f0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432545"
---
# <a name="imetadataemitdefinefield-method"></a><span data-ttu-id="590f4-102">Метод IMetaDataEmit::DefineField</span><span class="sxs-lookup"><span data-stu-id="590f4-102">IMetaDataEmit::DefineField Method</span></span>
<span data-ttu-id="590f4-103">Creates a definition for a field with the specified metadata signature, and gets a token to that field definition.</span><span class="sxs-lookup"><span data-stu-id="590f4-103">Creates a definition for a field with the specified metadata signature, and gets a token to that field definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="590f4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="590f4-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineField (   
    [in]  mdTypeDef   td,   
    [in]  LPCWSTR     szName,   
    [in]  DWORD       dwFieldFlags,   
    [in]  PCCOR_SIGNATURE pvSigBlob,   
    [in]  ULONG       cbSigBlob,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,   
    [in]  ULONG       cchValue,   
    [out] mdFieldDef  *pmd   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="590f4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="590f4-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="590f4-106">[in] The `mdTypeDef` token for the enclosing class or interface.</span><span class="sxs-lookup"><span data-stu-id="590f4-106">[in] The `mdTypeDef` token for the enclosing class or interface.</span></span>  
  
 `szName`  
 <span data-ttu-id="590f4-107">[in] The field name in Unicode.</span><span class="sxs-lookup"><span data-stu-id="590f4-107">[in] The field name in Unicode.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="590f4-108">[in] The field attributes.</span><span class="sxs-lookup"><span data-stu-id="590f4-108">[in] The field attributes.</span></span> <span data-ttu-id="590f4-109">This is a bitmask of `CorFieldAttr` values.</span><span class="sxs-lookup"><span data-stu-id="590f4-109">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="590f4-110">[in] The field signature as a BLOB.</span><span class="sxs-lookup"><span data-stu-id="590f4-110">[in] The field signature as a BLOB.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="590f4-111">[in] The count of bytes in `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="590f4-111">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="590f4-112">[in] The `ELEMENT_TYPE_` *\** for the constant value.</span><span class="sxs-lookup"><span data-stu-id="590f4-112">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="590f4-113">This is a `CorElementType` value.</span><span class="sxs-lookup"><span data-stu-id="590f4-113">This is a `CorElementType` value.</span></span> <span data-ttu-id="590f4-114">If not defining a constant value for the field, use `ELEMENT_TYPE_END`.</span><span class="sxs-lookup"><span data-stu-id="590f4-114">If not defining a constant value for the field, use `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="590f4-115">[in] The constant value for the field.</span><span class="sxs-lookup"><span data-stu-id="590f4-115">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="590f4-116">[in] The size in (Unicode) characters of `pValue`.</span><span class="sxs-lookup"><span data-stu-id="590f4-116">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
 `pmd`  
 <span data-ttu-id="590f4-117">[out] The `mdFieldDef` token assigned.</span><span class="sxs-lookup"><span data-stu-id="590f4-117">[out] The `mdFieldDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="590f4-118">Требования</span><span class="sxs-lookup"><span data-stu-id="590f4-118">Requirements</span></span>  
 <span data-ttu-id="590f4-119">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="590f4-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="590f4-120">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="590f4-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="590f4-121">**Library:** Used as a resource in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="590f4-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="590f4-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="590f4-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="590f4-123">См. также</span><span class="sxs-lookup"><span data-stu-id="590f4-123">See also</span></span>

- [<span data-ttu-id="590f4-124">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="590f4-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="590f4-125">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="590f4-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
