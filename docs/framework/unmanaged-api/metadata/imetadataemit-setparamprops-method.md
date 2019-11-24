---
title: Метод IMetaDataEmit::SetParamProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetParamProps
helpviewer_keywords:
- IMetaDataEmit::SetParamProps method [.NET Framework metadata]
- SetParamProps method [.NET Framework metadata]
ms.assetid: a95a3908-9f87-4084-937e-8e01ef03ad63
topic_type:
- apiref
ms.openlocfilehash: 813460aa027b259866b168d426fd28502b5c4465
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432493"
---
# <a name="imetadataemitsetparamprops-method"></a><span data-ttu-id="73e6f-102">Метод IMetaDataEmit::SetParamProps</span><span class="sxs-lookup"><span data-stu-id="73e6f-102">IMetaDataEmit::SetParamProps Method</span></span>
<span data-ttu-id="73e6f-103">Sets or changes features of a method parameter that was defined by a prior call to [IMetaDataEmit::DefineParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md).</span><span class="sxs-lookup"><span data-stu-id="73e6f-103">Sets or changes features of a method parameter that was defined by a prior call to [IMetaDataEmit::DefineParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73e6f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="73e6f-104">Syntax</span></span>  
  
```cpp  
HRESULT SetParamProps (   
    [in]  mdParamDef  pd,   
    [in]  LPCWSTR     szName,   
    [in]  DWORD       dwParamFlags,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,   
    [in]  ULONG       cchValue   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="73e6f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="73e6f-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="73e6f-106">[in] The token for the target parameter.</span><span class="sxs-lookup"><span data-stu-id="73e6f-106">[in] The token for the target parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="73e6f-107">[in] The name of the parameter in Unicode.</span><span class="sxs-lookup"><span data-stu-id="73e6f-107">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="73e6f-108">[in] The flags for the parameter.</span><span class="sxs-lookup"><span data-stu-id="73e6f-108">[in] The flags for the parameter.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="73e6f-109">[in] The ELEMENT_TYPE_\* for the constant value.</span><span class="sxs-lookup"><span data-stu-id="73e6f-109">[in] The ELEMENT_TYPE_\* for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="73e6f-110">[in] The constant value for the parameter.</span><span class="sxs-lookup"><span data-stu-id="73e6f-110">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="73e6f-111">[in] The size in (Unicode) characters of `pValue`.</span><span class="sxs-lookup"><span data-stu-id="73e6f-111">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73e6f-112">Требования</span><span class="sxs-lookup"><span data-stu-id="73e6f-112">Requirements</span></span>  
 <span data-ttu-id="73e6f-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73e6f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73e6f-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="73e6f-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="73e6f-115">**Library:** Used as a resource in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="73e6f-115">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="73e6f-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73e6f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73e6f-117">См. также</span><span class="sxs-lookup"><span data-stu-id="73e6f-117">See also</span></span>

- [<span data-ttu-id="73e6f-118">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="73e6f-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="73e6f-119">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="73e6f-119">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
