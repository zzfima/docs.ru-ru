---
title: Метод IMetaDataEmit::SetTypeDefProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetTypeDefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetTypeDefProps
helpviewer_keywords:
- SetTypeDefProps method [.NET Framework metadata]
- IMetaDataEmit::SetTypeDefProps method [.NET Framework metadata]
ms.assetid: 480d596a-759f-4d29-ac1a-3dbff8f3544d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 596888a8eb4a55c4cfe594b1911f17f6d32f56d2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992437"
---
# <a name="imetadataemitsettypedefprops-method"></a><span data-ttu-id="f504e-102">Метод IMetaDataEmit::SetTypeDefProps</span><span class="sxs-lookup"><span data-stu-id="f504e-102">IMetaDataEmit::SetTypeDefProps Method</span></span>
<span data-ttu-id="f504e-103">Задает тип, определенный с помощью предыдущего вызова функции [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="f504e-103">Sets features of a type defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f504e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f504e-104">Syntax</span></span>  
  
```  
HRESULT SetTypeDefProps (  
    [in]  mdTypeDef   td,   
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[]   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f504e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f504e-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="f504e-106">[in] `mdTypeDef` Токен, полученный из исходного вызова [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="f504e-106">[in] An `mdTypeDef` token obtained from original call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="f504e-107">[in] `TypeDef` атрибуты.</span><span class="sxs-lookup"><span data-stu-id="f504e-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="f504e-108">Это битовая маска `CorTypeAttr` значения.</span><span class="sxs-lookup"><span data-stu-id="f504e-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="f504e-109">[in] `mdToken` Базового класса.</span><span class="sxs-lookup"><span data-stu-id="f504e-109">[in] The `mdToken` of the base class.</span></span> <span data-ttu-id="f504e-110">Полученный из предыдущего вызова [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md), или `null`.</span><span class="sxs-lookup"><span data-stu-id="f504e-110">Obtained from a previous call to [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md), or `null`.</span></span>  
  
 `rtkImplements[]`  
 <span data-ttu-id="f504e-111">[in] Массив токенов для интерфейсов, реализуемый данным типом.</span><span class="sxs-lookup"><span data-stu-id="f504e-111">[in] An array of tokens for the interfaces that this type implements.</span></span> <span data-ttu-id="f504e-112">Эти `mdTypeRef` маркеры будут получать с помощью [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md).</span><span class="sxs-lookup"><span data-stu-id="f504e-112">These `mdTypeRef` tokens are obtained using [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md).</span></span> <span data-ttu-id="f504e-113">Последний элемент массива должен быть `mdTokenNil`.</span><span class="sxs-lookup"><span data-stu-id="f504e-113">The last element of the array is must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f504e-114">Требования</span><span class="sxs-lookup"><span data-stu-id="f504e-114">Requirements</span></span>  
 <span data-ttu-id="f504e-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f504e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f504e-116">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f504e-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f504e-117">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f504e-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f504e-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f504e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f504e-119">См. также</span><span class="sxs-lookup"><span data-stu-id="f504e-119">See also</span></span>

- [<span data-ttu-id="f504e-120">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="f504e-120">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="f504e-121">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="f504e-121">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
