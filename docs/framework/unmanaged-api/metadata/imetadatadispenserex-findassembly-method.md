---
title: Метод IMetaDataDispenserEx::FindAssembly
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.FindAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::FindAssembly
helpviewer_keywords:
- FindAssembly method [.NET Framework metadata]
- IMetaDataDispenserEx::FindAssembly method [.NET Framework metadata]
ms.assetid: 3afe7252-5f28-48d9-a74d-1927566c404c
topic_type:
- apiref
ms.openlocfilehash: 2d974b7368dd01062d2d310d076dce05e102eb81
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442293"
---
# <a name="imetadatadispenserexfindassembly-method"></a><span data-ttu-id="f82e8-102">Метод IMetaDataDispenserEx::FindAssembly</span><span class="sxs-lookup"><span data-stu-id="f82e8-102">IMetaDataDispenserEx::FindAssembly Method</span></span>
<span data-ttu-id="f82e8-103">Этот метод не реализован.</span><span class="sxs-lookup"><span data-stu-id="f82e8-103">This method is not implemented.</span></span> <span data-ttu-id="f82e8-104">If called, it returns E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="f82e8-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f82e8-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f82e8-105">Syntax</span></span>  
  
```cpp  
HRESULT FindAssembly(  
    [in]  LPCWSTR  szAppBase,  
    [in]  LPCWSTR  szPrivateBin,  
    [in]  LPCWSTR  szGlobalBin,  
    [in]  LPCWSTR  szAssemblyName,  
    [out] LPCWSTR  szName,  
    [in]  ULONG    cchName,  
    [out] ULONG    *pcName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f82e8-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="f82e8-106">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="f82e8-107">[in] Not used.</span><span class="sxs-lookup"><span data-stu-id="f82e8-107">[in] Not used.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="f82e8-108">[in] Not used.</span><span class="sxs-lookup"><span data-stu-id="f82e8-108">[in] Not used.</span></span>  
  
 `szGlobalBin`  
 <span data-ttu-id="f82e8-109">[in] Not used.</span><span class="sxs-lookup"><span data-stu-id="f82e8-109">[in] Not used.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="f82e8-110">[in] The assembly to be found.</span><span class="sxs-lookup"><span data-stu-id="f82e8-110">[in] The assembly to be found.</span></span>  
  
 `szName`  
 <span data-ttu-id="f82e8-111">[out] The simple name of the assembly.</span><span class="sxs-lookup"><span data-stu-id="f82e8-111">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="f82e8-112">[in] The size, in bytes, of `szName`.</span><span class="sxs-lookup"><span data-stu-id="f82e8-112">[in] The size, in bytes, of `szName`.</span></span>  
  
 `pcName`  
 <span data-ttu-id="f82e8-113">[out] The number of characters actually returned in `szName`.</span><span class="sxs-lookup"><span data-stu-id="f82e8-113">[out] The number of characters actually returned in `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f82e8-114">Требования</span><span class="sxs-lookup"><span data-stu-id="f82e8-114">Requirements</span></span>  
 <span data-ttu-id="f82e8-115">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f82e8-115">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f82e8-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f82e8-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f82e8-117">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f82e8-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f82e8-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f82e8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f82e8-119">См. также</span><span class="sxs-lookup"><span data-stu-id="f82e8-119">See also</span></span>

- [<span data-ttu-id="f82e8-120">Интерфейс IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="f82e8-120">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="f82e8-121">Интерфейс IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="f82e8-121">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
