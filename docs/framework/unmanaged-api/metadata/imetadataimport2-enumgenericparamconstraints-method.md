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
ms.openlocfilehash: fd5d35cb13bb55fc73e160089cbc1050cb3d5c0e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataimport2enumgenericparamconstraints-method"></a><span data-ttu-id="a4a13-102">Метод IMetaDataImport2::EnumGenericParamConstraints</span><span class="sxs-lookup"><span data-stu-id="a4a13-102">IMetaDataImport2::EnumGenericParamConstraints Method</span></span>
<span data-ttu-id="a4a13-103">Получает перечислитель для массива ограничений параметра универсального типа, связанный с универсальным параметром, представленного указанным токеном.</span><span class="sxs-lookup"><span data-stu-id="a4a13-103">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4a13-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a4a13-104">Syntax</span></span>  
  
```  
HRESULT EnumGenericParamConstraints (  
    [in, out] HCORENUM                *phEnum,  
    [in]  mdGenericParam              tk,  
    [out] mdGenericParamConstraint    rGenericParamConstraints[],  
    [in]  ULONG                       cMax,  
    [out] ULONG                       *pcGenericParamConstraints  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a4a13-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a4a13-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="a4a13-106">[in, out] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="a4a13-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="a4a13-107">[in]   Токен, представляющий универсальный параметр, ограничения, подлежащие перечислению.</span><span class="sxs-lookup"><span data-stu-id="a4a13-107">[in]   A token that represents the generic parameter whose constraints are to be enumerated.</span></span>  
  
 `rGenericParamConstraints`  
 <span data-ttu-id="a4a13-108">[out] Массив ограничений для параметра универсального типа для перечисления.</span><span class="sxs-lookup"><span data-stu-id="a4a13-108">[out] The array of generic parameter constraints to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="a4a13-109">[in]   Максимальное количество маркеров для размещения в `rGenericParamConstraints`.</span><span class="sxs-lookup"><span data-stu-id="a4a13-109">[in]   The requested maximum number of tokens to place in `rGenericParamConstraints`.</span></span>  
  
 `pcGenericParamConstraints`  
 <span data-ttu-id="a4a13-110">[out] Указатель на число маркеров помещаются в `rGenericParamConstraints`.</span><span class="sxs-lookup"><span data-stu-id="a4a13-110">[out] A pointer to the number of tokens placed in `rGenericParamConstraints`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a4a13-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a4a13-111">Return Value</span></span>  
  
|<span data-ttu-id="a4a13-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a4a13-112">HRESULT</span></span>|<span data-ttu-id="a4a13-113">Описание</span><span class="sxs-lookup"><span data-stu-id="a4a13-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="a4a13-114">`EnumGenericParameterConstraints` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="a4a13-114">`EnumGenericParameterConstraints` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="a4a13-115">`phEnum` не имеет члена элементов.</span><span class="sxs-lookup"><span data-stu-id="a4a13-115">`phEnum` has no member elements.</span></span> <span data-ttu-id="a4a13-116">В этом случае `pcGenericParameterConstraints` имеет значение 0 (ноль).</span><span class="sxs-lookup"><span data-stu-id="a4a13-116">In this case, `pcGenericParameterConstraints` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a4a13-117">Требования</span><span class="sxs-lookup"><span data-stu-id="a4a13-117">Requirements</span></span>  
 <span data-ttu-id="a4a13-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4a13-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4a13-119">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a4a13-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a4a13-120">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a4a13-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a4a13-121">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4a13-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4a13-122">См. также</span><span class="sxs-lookup"><span data-stu-id="a4a13-122">See Also</span></span>  
 [<span data-ttu-id="a4a13-123">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="a4a13-123">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [<span data-ttu-id="a4a13-124">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="a4a13-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
