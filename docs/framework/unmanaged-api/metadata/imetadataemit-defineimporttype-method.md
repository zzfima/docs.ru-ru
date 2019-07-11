---
title: Метод IMetaDataEmit::DefineImportType
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineImportType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineImportType
helpviewer_keywords:
- DefineImportType method [.NET Framework metadata]
- IMetaDataEmit::DefineImportType method [.NET Framework metadata]
ms.assetid: 37fd27af-8062-4904-ace4-51bb78ec600a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ff0660ef2b30e32af540fe7bef5936ab6d0a359f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777624"
---
# <a name="imetadataemitdefineimporttype-method"></a><span data-ttu-id="7be6d-102">Метод IMetaDataEmit::DefineImportType</span><span class="sxs-lookup"><span data-stu-id="7be6d-102">IMetaDataEmit::DefineImportType Method</span></span>
<span data-ttu-id="7be6d-103">Создает ссылку для указанного типа, определенные вне текущей области, а также определяет маркер для этой ссылки.</span><span class="sxs-lookup"><span data-stu-id="7be6d-103">Creates a reference to the specified type that is defined outside the current scope, and defines a token for that reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7be6d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7be6d-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineImportType (   
    [in]  IMetaDataAssemblyImport  *pAssemImport,   
    [in]  const void               *pbHashValue,   
    [in]  ULONG                    cbHashValue,    
    [in]  IMetaDataImport          *pImport,   
    [in]  mdTypeDef                tdImport,   
    [in]  IMetaDataAssemblyEmit    *pAssemEmit,   
    [out] mdTypeRef                *ptr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7be6d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7be6d-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="7be6d-106">[in] [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) интерфейс, представляющий сборку, из которого импортируется в целевой тип.</span><span class="sxs-lookup"><span data-stu-id="7be6d-106">[in] An [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface that represents the assembly from which the target type is imported.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="7be6d-107">[in] Массив, содержащий хэш-код для сборки, определяемой параметром `pAssemImport`.</span><span class="sxs-lookup"><span data-stu-id="7be6d-107">[in] An array that contains the hash for the assembly specified by `pAssemImport`.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="7be6d-108">[in] Число байтов в массиве `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="7be6d-108">[in] The number of bytes in the `pbHashValue` array.</span></span>  
  
 `pImport`  
 <span data-ttu-id="7be6d-109">[in] [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) интерфейс, который представляет область метаданных, из которого импортируется в целевой тип.</span><span class="sxs-lookup"><span data-stu-id="7be6d-109">[in] An [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface that represents the metadata scope from which the target type is imported.</span></span>  
  
 `tdImport`  
 <span data-ttu-id="7be6d-110">[in] `mdTypeDef` Токен, который указывает тип целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="7be6d-110">[in] An `mdTypeDef` token that specifies the target type.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="7be6d-111">[in] [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) интерфейс, представляющий сборку, в который импортируется в целевой тип.</span><span class="sxs-lookup"><span data-stu-id="7be6d-111">[in] An [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) interface that represents the assembly into which the target type is imported.</span></span>  
  
 `ptr`  
 <span data-ttu-id="7be6d-112">[out] `mdTypeRef` Маркер, который определен в текущей области для ссылки на тип.</span><span class="sxs-lookup"><span data-stu-id="7be6d-112">[out] The `mdTypeRef` token that is defined in the current scope for the type reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7be6d-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="7be6d-113">Remarks</span></span>  
 <span data-ttu-id="7be6d-114">До вызова метода [IMetaDataEmit::DefineImportMember](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md) метод, можно использовать `DefineImportType` метод, чтобы создать ссылку на тип, в текущей области, для родительского класса или интерфейса родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="7be6d-114">Prior to calling the [IMetaDataEmit::DefineImportMember](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md) method, you can use the `DefineImportType` method to create a type reference, in the current scope, for the member's parent class or parent interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7be6d-115">Требования</span><span class="sxs-lookup"><span data-stu-id="7be6d-115">Requirements</span></span>  
 <span data-ttu-id="7be6d-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7be6d-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7be6d-117">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7be6d-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7be6d-118">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7be6d-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7be6d-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7be6d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7be6d-120">См. также</span><span class="sxs-lookup"><span data-stu-id="7be6d-120">See also</span></span>

- [<span data-ttu-id="7be6d-121">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="7be6d-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="7be6d-122">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="7be6d-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
