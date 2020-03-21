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
ms.openlocfilehash: e59e7695246b2c83171e77352e16464258516f8d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177466"
---
# <a name="imetadataemitsettypedefprops-method"></a><span data-ttu-id="b4463-102">Метод IMetaDataEmit::SetTypeDefProps</span><span class="sxs-lookup"><span data-stu-id="b4463-102">IMetaDataEmit::SetTypeDefProps Method</span></span>
<span data-ttu-id="b4463-103">Устанавливает функции типа, определяемого предыдущим вызовом на [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="b4463-103">Sets features of a type defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4463-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b4463-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTypeDefProps (  
    [in]  mdTypeDef   td,
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[]
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4463-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b4463-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="b4463-106">(в) Токен, `mdTypeDef` полученный от оригинального вызова на [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="b4463-106">[in] An `mdTypeDef` token obtained from original call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="b4463-107">(в) `TypeDef` атрибуты.</span><span class="sxs-lookup"><span data-stu-id="b4463-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="b4463-108">Это битмаска ценностей. `CorTypeAttr`</span><span class="sxs-lookup"><span data-stu-id="b4463-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="b4463-109">(в) Базовый `mdToken` класс.</span><span class="sxs-lookup"><span data-stu-id="b4463-109">[in] The `mdToken` of the base class.</span></span> <span data-ttu-id="b4463-110">Получено от предыдущего звонка к [IMetaDataEmit::DefineИмпортТип](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md), или `null`.</span><span class="sxs-lookup"><span data-stu-id="b4463-110">Obtained from a previous call to [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md), or `null`.</span></span>  
  
 `rtkImplements[]`  
 <span data-ttu-id="b4463-111">(в) Массив токенов для интерфейсов, которые реализует этот тип.</span><span class="sxs-lookup"><span data-stu-id="b4463-111">[in] An array of tokens for the interfaces that this type implements.</span></span> <span data-ttu-id="b4463-112">Эти `mdTypeRef` токены получены с помощью [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md).</span><span class="sxs-lookup"><span data-stu-id="b4463-112">These `mdTypeRef` tokens are obtained using [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md).</span></span> <span data-ttu-id="b4463-113">Последний элемент массива должен `mdTokenNil`быть.</span><span class="sxs-lookup"><span data-stu-id="b4463-113">The last element of the array is must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4463-114">Требования</span><span class="sxs-lookup"><span data-stu-id="b4463-114">Requirements</span></span>  
 <span data-ttu-id="b4463-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4463-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4463-116">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b4463-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b4463-117">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b4463-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b4463-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4463-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4463-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b4463-119">See also</span></span>

- [<span data-ttu-id="b4463-120">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="b4463-120">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="b4463-121">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="b4463-121">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
