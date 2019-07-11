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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7676c83e8b231606896cb6d1224633b4fa15e725
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777568"
---
# <a name="imetadataemitdefinenestedtype-method"></a><span data-ttu-id="4deef-102">Метод IMetaDataEmit::DefineNestedType</span><span class="sxs-lookup"><span data-stu-id="4deef-102">IMetaDataEmit::DefineNestedType Method</span></span>
<span data-ttu-id="4deef-103">Создает подпись метаданных определения типа, возвращает `mdTypeDef` маркеров для этого типа и указывает, что определенный тип является членом типа, который ссылается `tdEncloser` параметра.</span><span class="sxs-lookup"><span data-stu-id="4deef-103">Creates the metadata signature of a type definition, returns an `mdTypeDef` token for that type, and specifies that the defined type is a member of the type referenced by the `tdEncloser` parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4deef-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4deef-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="4deef-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4deef-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="4deef-106">[in] Имя типа в формате Юникод.</span><span class="sxs-lookup"><span data-stu-id="4deef-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="4deef-107">[in] `TypeDef` атрибуты.</span><span class="sxs-lookup"><span data-stu-id="4deef-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="4deef-108">Это битовая маска `CorTypeAttr` значения.</span><span class="sxs-lookup"><span data-stu-id="4deef-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="4deef-109">[in] Токен базового класса.</span><span class="sxs-lookup"><span data-stu-id="4deef-109">[in] The token of the base class.</span></span> <span data-ttu-id="4deef-110">Это может быть либо `mdTypeDef` или `mdTypeRef` токена.</span><span class="sxs-lookup"><span data-stu-id="4deef-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 <span data-ttu-id="4deef-111">`rtkImplements`[]</span><span class="sxs-lookup"><span data-stu-id="4deef-111">`rtkImplements`[]</span></span>  
 <span data-ttu-id="4deef-112">[in] Массив токенов, которые указывают интерфейсы, реализуемые этот класс или интерфейс.</span><span class="sxs-lookup"><span data-stu-id="4deef-112">[in] An array of tokens that specify the interfaces that this class or interface implements.</span></span>  
  
 `tdEncloser`  
 <span data-ttu-id="4deef-113">[in] Токен данного включающего типа.</span><span class="sxs-lookup"><span data-stu-id="4deef-113">[in] The token of the enclosing type.</span></span> <span data-ttu-id="4deef-114">Последний элемент массива должен быть `mdTokenNil`.</span><span class="sxs-lookup"><span data-stu-id="4deef-114">The last element of the array must be `mdTokenNil`.</span></span>  
  
 `ptd`  
 <span data-ttu-id="4deef-115">[out] `mdTypeDef` Маркер, назначенный.</span><span class="sxs-lookup"><span data-stu-id="4deef-115">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4deef-116">Требования</span><span class="sxs-lookup"><span data-stu-id="4deef-116">Requirements</span></span>  
 <span data-ttu-id="4deef-117">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4deef-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4deef-118">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4deef-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4deef-119">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4deef-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4deef-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4deef-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4deef-121">См. также</span><span class="sxs-lookup"><span data-stu-id="4deef-121">See also</span></span>

- [<span data-ttu-id="4deef-122">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="4deef-122">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="4deef-123">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="4deef-123">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
