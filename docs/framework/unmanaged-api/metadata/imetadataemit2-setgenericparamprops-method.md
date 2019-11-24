---
title: Метод IMetaDataEmit2::SetGenericParamProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SetGenericParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SetGenericParamProps
helpviewer_keywords:
- IMetaDataEmit2::SetGenericParamProps method [.NET Framework metadata]
- SetGenericParamProps method [.NET Framework metadata]
ms.assetid: cd93a48d-1fed-4706-bec6-a05dc3b64fbd
topic_type:
- apiref
ms.openlocfilehash: 7a93bbe0d7a9d9e6ff7505bbc215efa79176ad1f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440440"
---
# <a name="imetadataemit2setgenericparamprops-method"></a><span data-ttu-id="d3a9e-102">Метод IMetaDataEmit2::SetGenericParamProps</span><span class="sxs-lookup"><span data-stu-id="d3a9e-102">IMetaDataEmit2::SetGenericParamProps Method</span></span>
<span data-ttu-id="d3a9e-103">Sets property values for the generic parameter definition referenced by the specified token.</span><span class="sxs-lookup"><span data-stu-id="d3a9e-103">Sets property values for the generic parameter definition referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3a9e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d3a9e-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGenericParamProps (  
    [in] mdGenericParam   gp,   
    [in] DWORD            dwParamFlags,   
    [in] LPCWSTR          szName,   
    [in] DWORD            reserved,   
    [in] mdToken          rtkConstraints[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3a9e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d3a9e-105">Parameters</span></span>  
 `gp`  
 <span data-ttu-id="d3a9e-106">[in] The token for the generic parameter definition for which to set values.</span><span class="sxs-lookup"><span data-stu-id="d3a9e-106">[in] The token for the generic parameter definition for which to set values.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="d3a9e-107">[in] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span><span class="sxs-lookup"><span data-stu-id="d3a9e-107">[in] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="d3a9e-108">[в] Необязательно.</span><span class="sxs-lookup"><span data-stu-id="d3a9e-108">[in] Optional.</span></span> <span data-ttu-id="d3a9e-109">The name of the parameter for which to set values.</span><span class="sxs-lookup"><span data-stu-id="d3a9e-109">The name of the parameter for which to set values.</span></span>  
  
 `reserved`  
 <span data-ttu-id="d3a9e-110">[in] Reserved for future extensibility.</span><span class="sxs-lookup"><span data-stu-id="d3a9e-110">[in] Reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="d3a9e-111">[в] Необязательно.</span><span class="sxs-lookup"><span data-stu-id="d3a9e-111">[in] Optional.</span></span> <span data-ttu-id="d3a9e-112">A zero-terminated array of type constraints.</span><span class="sxs-lookup"><span data-stu-id="d3a9e-112">A zero-terminated array of type constraints.</span></span> <span data-ttu-id="d3a9e-113">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span><span class="sxs-lookup"><span data-stu-id="d3a9e-113">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3a9e-114">Требования</span><span class="sxs-lookup"><span data-stu-id="d3a9e-114">Requirements</span></span>  
 <span data-ttu-id="d3a9e-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3a9e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3a9e-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d3a9e-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d3a9e-117">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d3a9e-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d3a9e-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3a9e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3a9e-119">См. также</span><span class="sxs-lookup"><span data-stu-id="d3a9e-119">See also</span></span>

- [<span data-ttu-id="d3a9e-120">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="d3a9e-120">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="d3a9e-121">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="d3a9e-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
