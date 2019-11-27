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
ms.openlocfilehash: 3ab29fc8c983b354ad5088d26c547868940ec70a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447718"
---
# <a name="imetadataemitsettypedefprops-method"></a><span data-ttu-id="e9f17-102">Метод IMetaDataEmit::SetTypeDefProps</span><span class="sxs-lookup"><span data-stu-id="e9f17-102">IMetaDataEmit::SetTypeDefProps Method</span></span>
<span data-ttu-id="e9f17-103">Задает функции типа, определенного при предыдущем вызове метода [IMetaDataEmit::D ефинетипедеф](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="e9f17-103">Sets features of a type defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9f17-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e9f17-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTypeDefProps (  
    [in]  mdTypeDef   td,   
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[]   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9f17-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e9f17-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="e9f17-106">окне Маркер `mdTypeDef`, полученный из исходного вызова функции [IMetaDataEmit::D ефинетипедеф](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="e9f17-106">[in] An `mdTypeDef` token obtained from original call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="e9f17-107">[in] `TypeDef` атрибуты.</span><span class="sxs-lookup"><span data-stu-id="e9f17-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="e9f17-108">Это битовая маска `CorTypeAttr` значений.</span><span class="sxs-lookup"><span data-stu-id="e9f17-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="e9f17-109">окне `mdToken` базового класса.</span><span class="sxs-lookup"><span data-stu-id="e9f17-109">[in] The `mdToken` of the base class.</span></span> <span data-ttu-id="e9f17-110">Получено из предыдущего вызова [IMetaDataEmit::D ефинеимпорттипе](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md)или `null`.</span><span class="sxs-lookup"><span data-stu-id="e9f17-110">Obtained from a previous call to [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md), or `null`.</span></span>  
  
 `rtkImplements[]`  
 <span data-ttu-id="e9f17-111">окне Массив токенов для интерфейсов, реализуемых этим типом.</span><span class="sxs-lookup"><span data-stu-id="e9f17-111">[in] An array of tokens for the interfaces that this type implements.</span></span> <span data-ttu-id="e9f17-112">Эти `mdTypeRef` токены получаются с помощью метода [IMetaDataEmit::D ефинеимпорттипе](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md).</span><span class="sxs-lookup"><span data-stu-id="e9f17-112">These `mdTypeRef` tokens are obtained using [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md).</span></span> <span data-ttu-id="e9f17-113">Последний элемент массива должен быть `mdTokenNil`.</span><span class="sxs-lookup"><span data-stu-id="e9f17-113">The last element of the array is must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9f17-114">Требования</span><span class="sxs-lookup"><span data-stu-id="e9f17-114">Requirements</span></span>  
 <span data-ttu-id="e9f17-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9f17-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9f17-116">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="e9f17-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e9f17-117">**Библиотека:** Используется в качестве ресурса в MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e9f17-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e9f17-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9f17-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9f17-119">См. также</span><span class="sxs-lookup"><span data-stu-id="e9f17-119">See also</span></span>

- [<span data-ttu-id="e9f17-120">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="e9f17-120">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="e9f17-121">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="e9f17-121">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
