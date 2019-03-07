---
title: Метод IMetaDataImport2::EnumGenericParamConstraints
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumGenericParamConstraints
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumGenericParamConstraints
helpviewer_keywords:
- EnumGenericParamConstraints method [.NET Framework metadata]
- IMetaDataImport2::EnumGenericParamConstraints method [.NET Framework metadata]
ms.assetid: 8a7d4e40-28fe-4e14-b801-4049880130e7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cdc617039ac8328e0153abc7cc3752c54060a8c4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481473"
---
# <a name="imetadataimport2enumgenericparamconstraints-method"></a><span data-ttu-id="6d51c-102">Метод IMetaDataImport2::EnumGenericParamConstraints</span><span class="sxs-lookup"><span data-stu-id="6d51c-102">IMetaDataImport2::EnumGenericParamConstraints Method</span></span>
<span data-ttu-id="6d51c-103">Получает перечислитель для массива универсальный параметр ограничения, связанные с универсального параметра, представленного указанным токеном.</span><span class="sxs-lookup"><span data-stu-id="6d51c-103">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d51c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6d51c-104">Syntax</span></span>  
  
```  
HRESULT EnumGenericParamConstraints (  
    [in, out] HCORENUM                *phEnum,  
    [in]  mdGenericParam              tk,  
    [out] mdGenericParamConstraint    rGenericParamConstraints[],  
    [in]  ULONG                       cMax,  
    [out] ULONG                       *pcGenericParamConstraints  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d51c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6d51c-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="6d51c-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="6d51c-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="6d51c-107">[in]   Токен, который представляет универсальный параметр, ограничения должны быть перечислены.</span><span class="sxs-lookup"><span data-stu-id="6d51c-107">[in]   A token that represents the generic parameter whose constraints are to be enumerated.</span></span>  
  
 `rGenericParamConstraints`  
 <span data-ttu-id="6d51c-108">[out] Массив ограничений параметра универсального типа для перечисления.</span><span class="sxs-lookup"><span data-stu-id="6d51c-108">[out] The array of generic parameter constraints to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="6d51c-109">[in]   Максимальное число маркеров для размещения в `rGenericParamConstraints`.</span><span class="sxs-lookup"><span data-stu-id="6d51c-109">[in]   The requested maximum number of tokens to place in `rGenericParamConstraints`.</span></span>  
  
 `pcGenericParamConstraints`  
 <span data-ttu-id="6d51c-110">[out] Указатель на число маркеров помещаются в `rGenericParamConstraints`.</span><span class="sxs-lookup"><span data-stu-id="6d51c-110">[out] A pointer to the number of tokens placed in `rGenericParamConstraints`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6d51c-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6d51c-111">Return Value</span></span>  
  
|<span data-ttu-id="6d51c-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6d51c-112">HRESULT</span></span>|<span data-ttu-id="6d51c-113">Описание:</span><span class="sxs-lookup"><span data-stu-id="6d51c-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="6d51c-114">`EnumGenericParameterConstraints` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="6d51c-114">`EnumGenericParameterConstraints` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="6d51c-115">`phEnum` не имеет члена элементов.</span><span class="sxs-lookup"><span data-stu-id="6d51c-115">`phEnum` has no member elements.</span></span> <span data-ttu-id="6d51c-116">В этом случае `pcGenericParameterConstraints` имеет значение 0 (ноль).</span><span class="sxs-lookup"><span data-stu-id="6d51c-116">In this case, `pcGenericParameterConstraints` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6d51c-117">Требования</span><span class="sxs-lookup"><span data-stu-id="6d51c-117">Requirements</span></span>  
 <span data-ttu-id="6d51c-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d51c-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d51c-119">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6d51c-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6d51c-120">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6d51c-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6d51c-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d51c-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d51c-122">См. также</span><span class="sxs-lookup"><span data-stu-id="6d51c-122">See also</span></span>
- [<span data-ttu-id="6d51c-123">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="6d51c-123">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="6d51c-124">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="6d51c-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
