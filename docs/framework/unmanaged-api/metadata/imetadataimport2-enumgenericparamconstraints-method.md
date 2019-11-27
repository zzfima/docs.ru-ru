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
ms.openlocfilehash: d1683965193801dbdee038ab06366178891fd978
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426722"
---
# <a name="imetadataimport2enumgenericparamconstraints-method"></a><span data-ttu-id="24164-102">Метод IMetaDataImport2::EnumGenericParamConstraints</span><span class="sxs-lookup"><span data-stu-id="24164-102">IMetaDataImport2::EnumGenericParamConstraints Method</span></span>
<span data-ttu-id="24164-103">Возвращает перечислитель для массива ограничений универсальных параметров, связанных с универсальным параметром, представленным указанным токеном.</span><span class="sxs-lookup"><span data-stu-id="24164-103">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24164-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="24164-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumGenericParamConstraints (  
    [in, out] HCORENUM                *phEnum,  
    [in]  mdGenericParam              tk,  
    [out] mdGenericParamConstraint    rGenericParamConstraints[],  
    [in]  ULONG                       cMax,  
    [out] ULONG                       *pcGenericParamConstraints  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="24164-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="24164-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="24164-106">[вход, выход] Указатель на перечислитель.</span><span class="sxs-lookup"><span data-stu-id="24164-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="24164-107">окне   Токен, представляющий универсальный параметр, ограничения которого необходимо перечислить.</span><span class="sxs-lookup"><span data-stu-id="24164-107">[in]   A token that represents the generic parameter whose constraints are to be enumerated.</span></span>  
  
 `rGenericParamConstraints`  
 <span data-ttu-id="24164-108">заполняет Массив ограничений универсального параметра для перечисления.</span><span class="sxs-lookup"><span data-stu-id="24164-108">[out] The array of generic parameter constraints to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="24164-109">окне   Запрошенное максимальное число токенов, помещаемых в `rGenericParamConstraints`.</span><span class="sxs-lookup"><span data-stu-id="24164-109">[in]   The requested maximum number of tokens to place in `rGenericParamConstraints`.</span></span>  
  
 `pcGenericParamConstraints`  
 <span data-ttu-id="24164-110">заполняет Указатель на число токенов, помещенных в `rGenericParamConstraints`.</span><span class="sxs-lookup"><span data-stu-id="24164-110">[out] A pointer to the number of tokens placed in `rGenericParamConstraints`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="24164-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="24164-111">Return Value</span></span>  
  
|<span data-ttu-id="24164-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="24164-112">HRESULT</span></span>|<span data-ttu-id="24164-113">Описание</span><span class="sxs-lookup"><span data-stu-id="24164-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="24164-114">`EnumGenericParameterConstraints` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="24164-114">`EnumGenericParameterConstraints` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="24164-115">у `phEnum` нет элементов Member.</span><span class="sxs-lookup"><span data-stu-id="24164-115">`phEnum` has no member elements.</span></span> <span data-ttu-id="24164-116">В этом случае `pcGenericParameterConstraints` имеет значение 0 (ноль).</span><span class="sxs-lookup"><span data-stu-id="24164-116">In this case, `pcGenericParameterConstraints` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="24164-117">Требования</span><span class="sxs-lookup"><span data-stu-id="24164-117">Requirements</span></span>  
 <span data-ttu-id="24164-118">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24164-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24164-119">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="24164-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="24164-120">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="24164-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="24164-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24164-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24164-122">См. также</span><span class="sxs-lookup"><span data-stu-id="24164-122">See also</span></span>

- [<span data-ttu-id="24164-123">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="24164-123">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="24164-124">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="24164-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
