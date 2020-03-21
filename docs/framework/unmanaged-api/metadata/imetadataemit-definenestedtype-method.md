---
title: Метод IMetaDataEmit::DefineNestedType
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineNestedType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineNestedType
helpviewer_keywords:
- IMetaDataEmit::DefineNestedType method [.NET Framework metadata]
- DefineNestedType method [.NET Framework metadata]
ms.assetid: 1e994de6-4628-459c-b967-b34be1e9fe4f
topic_type:
- apiref
ms.openlocfilehash: 3b8fd9876563bace52a6088747d1ca4ed26ea872
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175815"
---
# <a name="imetadataemitdefinenestedtype-method"></a><span data-ttu-id="941ee-102">Метод IMetaDataEmit::DefineNestedType</span><span class="sxs-lookup"><span data-stu-id="941ee-102">IMetaDataEmit::DefineNestedType Method</span></span>
<span data-ttu-id="941ee-103">Создает подпись метаданных определения типа, `mdTypeDef` возвращает маркер для этого типа и указывает, что определенный тип является членом типа, на который ссылается `tdEncloser` параметр.</span><span class="sxs-lookup"><span data-stu-id="941ee-103">Creates the metadata signature of a type definition, returns an `mdTypeDef` token for that type, and specifies that the defined type is a member of the type referenced by the `tdEncloser` parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="941ee-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="941ee-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineNestedType (
    [in]  LPCWSTR     szTypeDef,  
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[],
    [in]  mdTypeDef   tdEncloser,
    [out] mdTypeDef   *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="941ee-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="941ee-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="941ee-106">(в) Название типа в Unicode.</span><span class="sxs-lookup"><span data-stu-id="941ee-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="941ee-107">(в) `TypeDef` атрибуты.</span><span class="sxs-lookup"><span data-stu-id="941ee-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="941ee-108">Это битмаска ценностей. `CorTypeAttr`</span><span class="sxs-lookup"><span data-stu-id="941ee-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="941ee-109">(в) Токен базового класса.</span><span class="sxs-lookup"><span data-stu-id="941ee-109">[in] The token of the base class.</span></span> <span data-ttu-id="941ee-110">Это либо `mdTypeDef` знак, `mdTypeRef` либо жетон.</span><span class="sxs-lookup"><span data-stu-id="941ee-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 <span data-ttu-id="941ee-111">`rtkImplements`[]</span><span class="sxs-lookup"><span data-stu-id="941ee-111">`rtkImplements`[]</span></span>  
 <span data-ttu-id="941ee-112">(в) Массив токенов, определяющих интерфейсы, реализуемые этим классом или интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="941ee-112">[in] An array of tokens that specify the interfaces that this class or interface implements.</span></span>  
  
 `tdEncloser`  
 <span data-ttu-id="941ee-113">(в) Токен типа прилагаемого.</span><span class="sxs-lookup"><span data-stu-id="941ee-113">[in] The token of the enclosing type.</span></span> <span data-ttu-id="941ee-114">Последний элемент массива `mdTokenNil`должен быть.</span><span class="sxs-lookup"><span data-stu-id="941ee-114">The last element of the array must be `mdTokenNil`.</span></span>  
  
 `ptd`  
 <span data-ttu-id="941ee-115">(ваут) Назначенный `mdTypeDef` маркер.</span><span class="sxs-lookup"><span data-stu-id="941ee-115">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="941ee-116">Требования</span><span class="sxs-lookup"><span data-stu-id="941ee-116">Requirements</span></span>  
 <span data-ttu-id="941ee-117">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="941ee-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="941ee-118">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="941ee-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="941ee-119">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="941ee-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="941ee-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="941ee-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="941ee-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="941ee-121">See also</span></span>

- [<span data-ttu-id="941ee-122">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="941ee-122">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="941ee-123">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="941ee-123">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
