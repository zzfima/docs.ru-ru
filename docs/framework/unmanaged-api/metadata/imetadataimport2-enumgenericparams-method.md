---
title: Метод IMetaDataImport2::EnumGenericParams
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumGenericParams
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumGenericParams
helpviewer_keywords:
- EnumGenericParams method [.NET Framework metadata]
- IMetaDataImport2::EnumGenericParams method [.NET Framework metadata]
ms.assetid: b50488a5-3cf0-483c-82dc-2892a3ec61ac
topic_type:
- apiref
ms.openlocfilehash: d0377ade5265bba9b313d6ed2e91c446497fac6e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428316"
---
# <a name="imetadataimport2enumgenericparams-method"></a><span data-ttu-id="071e1-102">Метод IMetaDataImport2::EnumGenericParams</span><span class="sxs-lookup"><span data-stu-id="071e1-102">IMetaDataImport2::EnumGenericParams Method</span></span>
<span data-ttu-id="071e1-103">Gets an enumerator for an array of generic parameter tokens associated with the specified TypeDef or MethodDef token.</span><span class="sxs-lookup"><span data-stu-id="071e1-103">Gets an enumerator for an array of generic parameter tokens associated with the specified TypeDef or MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="071e1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="071e1-104">Syntax</span></span>  
  
```cpp
HRESULT EnumGenericParams (  
   [in, out] HCORENUM     *phEnum,   
   [in]  mdToken          tk,  
   [out] mdGenericParam   rGenericParams[],   
   [in]  ULONG            cMax,   
   [out] ULONG            *pcGenericParams  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="071e1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="071e1-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="071e1-106">[in, out] A pointer to the enumerator.</span><span class="sxs-lookup"><span data-stu-id="071e1-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="071e1-107">[in] The TypeDef or MethodDef token whose generic parameters are to be enumerated.</span><span class="sxs-lookup"><span data-stu-id="071e1-107">[in] The TypeDef or MethodDef token whose generic parameters are to be enumerated.</span></span>  
  
 `rGenericParams`  
 <span data-ttu-id="071e1-108">[out] The array of generic parameters to enumerate.</span><span class="sxs-lookup"><span data-stu-id="071e1-108">[out] The array of generic parameters to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="071e1-109">[in] The requested maximum number of tokens to place in `rGenericParams`.</span><span class="sxs-lookup"><span data-stu-id="071e1-109">[in] The requested maximum number of tokens to place in `rGenericParams`.</span></span>  
  
 `pcGenericParams`  
 <span data-ttu-id="071e1-110">[out] The returned number of tokens placed in `rGenericParams`.</span><span class="sxs-lookup"><span data-stu-id="071e1-110">[out] The returned number of tokens placed in `rGenericParams`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="071e1-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="071e1-111">Return Value</span></span>  
  
|<span data-ttu-id="071e1-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="071e1-112">HRESULT</span></span>|<span data-ttu-id="071e1-113">Описание</span><span class="sxs-lookup"><span data-stu-id="071e1-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="071e1-114">`EnumGenericParams` returned successfully.</span><span class="sxs-lookup"><span data-stu-id="071e1-114">`EnumGenericParams` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="071e1-115">`phEnum` has no member elements.</span><span class="sxs-lookup"><span data-stu-id="071e1-115">`phEnum` has no member elements.</span></span> <span data-ttu-id="071e1-116">In this case, `pcGenericParams` is set to 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="071e1-116">In this case, `pcGenericParams` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="071e1-117">Требования</span><span class="sxs-lookup"><span data-stu-id="071e1-117">Requirements</span></span>  
 <span data-ttu-id="071e1-118">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="071e1-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="071e1-119">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="071e1-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="071e1-120">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="071e1-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="071e1-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="071e1-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="071e1-122">См. также</span><span class="sxs-lookup"><span data-stu-id="071e1-122">See also</span></span>

- [<span data-ttu-id="071e1-123">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="071e1-123">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="071e1-124">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="071e1-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
