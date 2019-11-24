---
title: Метод IMetaDataImport::EnumUnresolvedMethods
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumUnresolvedMethods
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumUnresolvedMethods
helpviewer_keywords:
- EnumUnresolvedMethods method [.NET Framework metadata]
- IMetaDataImport::EnumUnresolvedMethods method [.NET Framework metadata]
ms.assetid: eb3187d7-74cf-44b1-aeeb-7a8d2b60e3b7
topic_type:
- apiref
ms.openlocfilehash: ff9827174e43fd62f3a995e9f477c6fff66b227a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449952"
---
# <a name="imetadataimportenumunresolvedmethods-method"></a><span data-ttu-id="3284b-102">Метод IMetaDataImport::EnumUnresolvedMethods</span><span class="sxs-lookup"><span data-stu-id="3284b-102">IMetaDataImport::EnumUnresolvedMethods Method</span></span>
<span data-ttu-id="3284b-103">Перечисляет токены MemberDef, представляющие неразрешенные методы в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="3284b-103">Enumerates MemberDef tokens representing the unresolved methods in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3284b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3284b-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumUnresolvedMethods (  
   [in, out] HCORENUM    *phEnum,  
   [out]     mdToken     rMethods[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3284b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3284b-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="3284b-106">[in, out] A pointer to the enumerator.</span><span class="sxs-lookup"><span data-stu-id="3284b-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="3284b-107">This must be NULL for the first call of this method.</span><span class="sxs-lookup"><span data-stu-id="3284b-107">This must be NULL for the first call of this method.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="3284b-108">[out] The array used to store the MemberDef tokens.</span><span class="sxs-lookup"><span data-stu-id="3284b-108">[out] The array used to store the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="3284b-109">[in] Максимальный размер массива `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="3284b-109">[in] The maximum size of the `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="3284b-110">[out] The number of MemberDef tokens returned in `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="3284b-110">[out] The number of MemberDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3284b-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3284b-111">Return Value</span></span>  
  
|<span data-ttu-id="3284b-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3284b-112">HRESULT</span></span>|<span data-ttu-id="3284b-113">Описание</span><span class="sxs-lookup"><span data-stu-id="3284b-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="3284b-114">`EnumUnresolvedMethods` returned successfully.</span><span class="sxs-lookup"><span data-stu-id="3284b-114">`EnumUnresolvedMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="3284b-115">There are no tokens to enumerate.</span><span class="sxs-lookup"><span data-stu-id="3284b-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="3284b-116">In that case, `pcTokens` is zero.</span><span class="sxs-lookup"><span data-stu-id="3284b-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3284b-117">Заметки</span><span class="sxs-lookup"><span data-stu-id="3284b-117">Remarks</span></span>  
 <span data-ttu-id="3284b-118">An unresolved method is one that has been declared but not implemented.</span><span class="sxs-lookup"><span data-stu-id="3284b-118">An unresolved method is one that has been declared but not implemented.</span></span> <span data-ttu-id="3284b-119">A method is included in the enumeration if the method is marked `miForwardRef` and either `mdPinvokeImpl` or `miRuntime` is set to zero.</span><span class="sxs-lookup"><span data-stu-id="3284b-119">A method is included in the enumeration if the method is marked `miForwardRef` and either `mdPinvokeImpl` or `miRuntime` is set to zero.</span></span> <span data-ttu-id="3284b-120">In other words, an unresolved method is a class method that is marked `miForwardRef` but which is not implemented in unmanaged code (reached via PInvoke) nor implemented internally by the runtime itself</span><span class="sxs-lookup"><span data-stu-id="3284b-120">In other words, an unresolved method is a class method that is marked `miForwardRef` but which is not implemented in unmanaged code (reached via PInvoke) nor implemented internally by the runtime itself</span></span>  
  
 <span data-ttu-id="3284b-121">The enumeration excludes all methods that are defined either at module scope (globals) or in interfaces or abstract classes.</span><span class="sxs-lookup"><span data-stu-id="3284b-121">The enumeration excludes all methods that are defined either at module scope (globals) or in interfaces or abstract classes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3284b-122">Требования</span><span class="sxs-lookup"><span data-stu-id="3284b-122">Requirements</span></span>  
 <span data-ttu-id="3284b-123">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3284b-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3284b-124">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3284b-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3284b-125">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3284b-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3284b-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3284b-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3284b-127">См. также</span><span class="sxs-lookup"><span data-stu-id="3284b-127">See also</span></span>

- [<span data-ttu-id="3284b-128">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="3284b-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="3284b-129">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="3284b-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
