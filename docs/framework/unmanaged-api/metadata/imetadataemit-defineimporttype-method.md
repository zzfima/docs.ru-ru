---
title: "Метод IMetaDataEmit::DefineImportType"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineImportType
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineImportType
helpviewer_keywords:
- DefineImportType method [.NET Framework metadata]
- IMetaDataEmit::DefineImportType method [.NET Framework metadata]
ms.assetid: 37fd27af-8062-4904-ace4-51bb78ec600a
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 4b19b291917b0b507f03c66a358b725a29234f76
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdefineimporttype-method"></a><span data-ttu-id="c1a40-102">Метод IMetaDataEmit::DefineImportType</span><span class="sxs-lookup"><span data-stu-id="c1a40-102">IMetaDataEmit::DefineImportType Method</span></span>
<span data-ttu-id="c1a40-103">Создает ссылку для указанного типа, определенные вне текущей области видимости, а также определяет маркер для этой ссылки.</span><span class="sxs-lookup"><span data-stu-id="c1a40-103">Creates a reference to the specified type that is defined outside the current scope, and defines a token for that reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1a40-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c1a40-104">Syntax</span></span>  
  
```  
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
  
#### <a name="parameters"></a><span data-ttu-id="c1a40-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c1a40-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="c1a40-106">[in] [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) интерфейс, который представляет сборки, из которого импортируется в целевой тип.</span><span class="sxs-lookup"><span data-stu-id="c1a40-106">[in] An [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface that represents the assembly from which the target type is imported.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="c1a40-107">[in] Массив, содержащий хэш-код для сборки, определяемой параметром `pAssemImport`.</span><span class="sxs-lookup"><span data-stu-id="c1a40-107">[in] An array that contains the hash for the assembly specified by `pAssemImport`.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="c1a40-108">[in] Число байтов в массиве `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="c1a40-108">[in] The number of bytes in the `pbHashValue` array.</span></span>  
  
 `pImport`  
 <span data-ttu-id="c1a40-109">[in] [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) интерфейс, представляющий область метаданных, из которого импортируется в целевой тип.</span><span class="sxs-lookup"><span data-stu-id="c1a40-109">[in] An [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface that represents the metadata scope from which the target type is imported.</span></span>  
  
 `tdImport`  
 <span data-ttu-id="c1a40-110">[in] `mdTypeDef` Маркер, который указывает тип целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="c1a40-110">[in] An `mdTypeDef` token that specifies the target type.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="c1a40-111">[in] [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) интерфейс, представляющий сборку, в который импортируется в целевой тип.</span><span class="sxs-lookup"><span data-stu-id="c1a40-111">[in] An [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) interface that represents the assembly into which the target type is imported.</span></span>  
  
 `ptr`  
 <span data-ttu-id="c1a40-112">[out] `mdTypeRef` Маркер, который определен в текущей области для ссылки на тип.</span><span class="sxs-lookup"><span data-stu-id="c1a40-112">[out] The `mdTypeRef` token that is defined in the current scope for the type reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c1a40-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="c1a40-113">Remarks</span></span>  
 <span data-ttu-id="c1a40-114">До вызова метода [IMetaDataEmit::DefineImportMember](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md) метод, можно использовать `DefineImportType` метод, чтобы создать ссылку на тип, в текущей области для родительского класса или интерфейса родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="c1a40-114">Prior to calling the [IMetaDataEmit::DefineImportMember](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md) method, you can use the `DefineImportType` method to create a type reference, in the current scope, for the member's parent class or parent interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1a40-115">Требования</span><span class="sxs-lookup"><span data-stu-id="c1a40-115">Requirements</span></span>  
 <span data-ttu-id="c1a40-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1a40-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1a40-117">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c1a40-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c1a40-118">**Библиотека:** используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c1a40-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c1a40-119">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1a40-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1a40-120">См. также</span><span class="sxs-lookup"><span data-stu-id="c1a40-120">See Also</span></span>  
 [<span data-ttu-id="c1a40-121">IMetaDataEmit-интерфейс</span><span class="sxs-lookup"><span data-stu-id="c1a40-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="c1a40-122">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="c1a40-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
