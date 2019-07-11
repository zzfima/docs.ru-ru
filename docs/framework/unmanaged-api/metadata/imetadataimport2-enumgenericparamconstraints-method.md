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
ms.openlocfilehash: 2ba9d7f8873d15a7cab2b9893feb8563dfc971b0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778759"
---
# <a name="imetadataimport2enumgenericparamconstraints-method"></a><span data-ttu-id="dd995-102">Метод IMetaDataImport2::EnumGenericParamConstraints</span><span class="sxs-lookup"><span data-stu-id="dd995-102">IMetaDataImport2::EnumGenericParamConstraints Method</span></span>
<span data-ttu-id="dd995-103">Получает перечислитель для массива универсальный параметр ограничения, связанные с универсального параметра, представленного указанным токеном.</span><span class="sxs-lookup"><span data-stu-id="dd995-103">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd995-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dd995-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumGenericParamConstraints (  
    [in, out] HCORENUM                *phEnum,  
    [in]  mdGenericParam              tk,  
    [out] mdGenericParamConstraint    rGenericParamConstraints[],  
    [in]  ULONG                       cMax,  
    [out] ULONG                       *pcGenericParamConstraints  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dd995-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="dd995-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="dd995-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="dd995-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="dd995-107">[in]   Токен, который представляет универсальный параметр, ограничения должны быть перечислены.</span><span class="sxs-lookup"><span data-stu-id="dd995-107">[in]   A token that represents the generic parameter whose constraints are to be enumerated.</span></span>  
  
 `rGenericParamConstraints`  
 <span data-ttu-id="dd995-108">[out] Массив ограничений параметра универсального типа для перечисления.</span><span class="sxs-lookup"><span data-stu-id="dd995-108">[out] The array of generic parameter constraints to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="dd995-109">[in]   Максимальное число маркеров для размещения в `rGenericParamConstraints`.</span><span class="sxs-lookup"><span data-stu-id="dd995-109">[in]   The requested maximum number of tokens to place in `rGenericParamConstraints`.</span></span>  
  
 `pcGenericParamConstraints`  
 <span data-ttu-id="dd995-110">[out] Указатель на число маркеров помещаются в `rGenericParamConstraints`.</span><span class="sxs-lookup"><span data-stu-id="dd995-110">[out] A pointer to the number of tokens placed in `rGenericParamConstraints`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dd995-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="dd995-111">Return Value</span></span>  
  
|<span data-ttu-id="dd995-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dd995-112">HRESULT</span></span>|<span data-ttu-id="dd995-113">Описание</span><span class="sxs-lookup"><span data-stu-id="dd995-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="dd995-114">`EnumGenericParameterConstraints` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="dd995-114">`EnumGenericParameterConstraints` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="dd995-115">`phEnum` не имеет члена элементов.</span><span class="sxs-lookup"><span data-stu-id="dd995-115">`phEnum` has no member elements.</span></span> <span data-ttu-id="dd995-116">В этом случае `pcGenericParameterConstraints` имеет значение 0 (ноль).</span><span class="sxs-lookup"><span data-stu-id="dd995-116">In this case, `pcGenericParameterConstraints` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dd995-117">Требования</span><span class="sxs-lookup"><span data-stu-id="dd995-117">Requirements</span></span>  
 <span data-ttu-id="dd995-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd995-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd995-119">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="dd995-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dd995-120">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dd995-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dd995-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd995-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd995-122">См. также</span><span class="sxs-lookup"><span data-stu-id="dd995-122">See also</span></span>

- [<span data-ttu-id="dd995-123">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="dd995-123">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="dd995-124">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="dd995-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
