---
title: "Метод IMetaDataEmit::SetTypeDefProps"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetTypeDefProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetTypeDefProps
helpviewer_keywords:
- SetTypeDefProps method [.NET Framework metadata]
- IMetaDataEmit::SetTypeDefProps method [.NET Framework metadata]
ms.assetid: 480d596a-759f-4d29-ac1a-3dbff8f3544d
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 50f92d0ff307621695887ee7a0af2d4d19985f51
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitsettypedefprops-method"></a><span data-ttu-id="2e8da-102">Метод IMetaDataEmit::SetTypeDefProps</span><span class="sxs-lookup"><span data-stu-id="2e8da-102">IMetaDataEmit::SetTypeDefProps Method</span></span>
<span data-ttu-id="2e8da-103">Задает тип, определенный в предыдущем вызове функции [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="2e8da-103">Sets features of a type defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e8da-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2e8da-104">Syntax</span></span>  
  
```  
HRESULT SetTypeDefProps (  
    [in]  mdTypeDef   td,   
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[]   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2e8da-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2e8da-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="2e8da-106">[in] `mdTypeDef` Токен, полученный от исходного вызова [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="2e8da-106">[in] An `mdTypeDef` token obtained from original call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="2e8da-107">[in] `TypeDef` атрибуты.</span><span class="sxs-lookup"><span data-stu-id="2e8da-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="2e8da-108">Это битовая маска `CorTypeAttr` значения.</span><span class="sxs-lookup"><span data-stu-id="2e8da-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="2e8da-109">[in] `mdToken` Базового класса.</span><span class="sxs-lookup"><span data-stu-id="2e8da-109">[in] The `mdToken` of the base class.</span></span> <span data-ttu-id="2e8da-110">Полученная из предыдущего вызова [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md), или `null`.</span><span class="sxs-lookup"><span data-stu-id="2e8da-110">Obtained from a previous call to [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md), or `null`.</span></span>  
  
 `rtkImplements[]`  
 <span data-ttu-id="2e8da-111">[in] Массив маркеров для интерфейсов, реализуемых этого типа.</span><span class="sxs-lookup"><span data-stu-id="2e8da-111">[in] An array of tokens for the interfaces that this type implements.</span></span> <span data-ttu-id="2e8da-112">Эти `mdTypeRef` токены получаются с помощью [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md).</span><span class="sxs-lookup"><span data-stu-id="2e8da-112">These `mdTypeRef` tokens are obtained using [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md).</span></span> <span data-ttu-id="2e8da-113">Последний элемент массива должен быть `mdTokenNil`.</span><span class="sxs-lookup"><span data-stu-id="2e8da-113">The last element of the array is must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e8da-114">Требования</span><span class="sxs-lookup"><span data-stu-id="2e8da-114">Requirements</span></span>  
 <span data-ttu-id="2e8da-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e8da-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e8da-116">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2e8da-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2e8da-117">**Библиотека:** используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2e8da-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2e8da-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e8da-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e8da-119">См. также</span><span class="sxs-lookup"><span data-stu-id="2e8da-119">See Also</span></span>  
 [<span data-ttu-id="2e8da-120">IMetaDataEmit-интерфейс</span><span class="sxs-lookup"><span data-stu-id="2e8da-120">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="2e8da-121">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="2e8da-121">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
