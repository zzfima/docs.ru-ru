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
ms.openlocfilehash: 4ebd4e9beca315ef8284c915800afec6bdb78c78
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59183239"
---
# <a name="imetadataemitdefinenestedtype-method"></a><span data-ttu-id="f5cde-102">Метод IMetaDataEmit::DefineNestedType</span><span class="sxs-lookup"><span data-stu-id="f5cde-102">IMetaDataEmit::DefineNestedType Method</span></span>
<span data-ttu-id="f5cde-103">Создает подпись метаданных определения типа, возвращает `mdTypeDef` маркеров для этого типа и указывает, что определенный тип является членом типа, который ссылается `tdEncloser` параметра.</span><span class="sxs-lookup"><span data-stu-id="f5cde-103">Creates the metadata signature of a type definition, returns an `mdTypeDef` token for that type, and specifies that the defined type is a member of the type referenced by the `tdEncloser` parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5cde-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f5cde-104">Syntax</span></span>  
  
```  
HRESULT DefineNestedType (   
    [in]  LPCWSTR     szTypeDef,  
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[],   
    [in]  mdTypeDef   tdEncloser,   
    [out] mdTypeDef   *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5cde-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f5cde-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="f5cde-106">[in] Имя типа в формате Юникод.</span><span class="sxs-lookup"><span data-stu-id="f5cde-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="f5cde-107">[in] `TypeDef` атрибуты.</span><span class="sxs-lookup"><span data-stu-id="f5cde-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="f5cde-108">Это битовая маска `CorTypeAttr` значения.</span><span class="sxs-lookup"><span data-stu-id="f5cde-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="f5cde-109">[in] Токен базового класса.</span><span class="sxs-lookup"><span data-stu-id="f5cde-109">[in] The token of the base class.</span></span> <span data-ttu-id="f5cde-110">Это может быть либо `mdTypeDef` или `mdTypeRef` токена.</span><span class="sxs-lookup"><span data-stu-id="f5cde-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 `rtkImplements`<span data-ttu-id="f5cde-111">[]</span><span class="sxs-lookup"><span data-stu-id="f5cde-111">[]</span></span>  
 <span data-ttu-id="f5cde-112">[in] Массив токенов, которые указывают интерфейсы, реализуемые этот класс или интерфейс.</span><span class="sxs-lookup"><span data-stu-id="f5cde-112">[in] An array of tokens that specify the interfaces that this class or interface implements.</span></span>  
  
 `tdEncloser`  
 <span data-ttu-id="f5cde-113">[in] Токен данного включающего типа.</span><span class="sxs-lookup"><span data-stu-id="f5cde-113">[in] The token of the enclosing type.</span></span> <span data-ttu-id="f5cde-114">Последний элемент массива должен быть `mdTokenNil`.</span><span class="sxs-lookup"><span data-stu-id="f5cde-114">The last element of the array must be `mdTokenNil`.</span></span>  
  
 `ptd`  
 <span data-ttu-id="f5cde-115">[out] `mdTypeDef` Маркер, назначенный.</span><span class="sxs-lookup"><span data-stu-id="f5cde-115">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5cde-116">Требования</span><span class="sxs-lookup"><span data-stu-id="f5cde-116">Requirements</span></span>  
 <span data-ttu-id="f5cde-117">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5cde-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5cde-118">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f5cde-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f5cde-119">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f5cde-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="f5cde-120">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f5cde-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f5cde-121">См. также</span><span class="sxs-lookup"><span data-stu-id="f5cde-121">See also</span></span>

- [<span data-ttu-id="f5cde-122">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="f5cde-122">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="f5cde-123">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="f5cde-123">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
