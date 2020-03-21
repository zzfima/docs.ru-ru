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
ms.openlocfilehash: 6825a5198976cc7ab2c04ebd6e782418dcf4a8f7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177683"
---
# <a name="imetadataemitdefineimporttype-method"></a><span data-ttu-id="f8771-102">Метод IMetaDataEmit::DefineImportType</span><span class="sxs-lookup"><span data-stu-id="f8771-102">IMetaDataEmit::DefineImportType Method</span></span>
<span data-ttu-id="f8771-103">Создает ссылку на указанный тип, который определяется вне текущей области, и определяет маркер для этой ссылки.</span><span class="sxs-lookup"><span data-stu-id="f8771-103">Creates a reference to the specified type that is defined outside the current scope, and defines a token for that reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8771-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f8771-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="f8771-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f8771-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="f8771-106">(в) [Интерфейс IMetaDataAssemblyImport,](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) представляющий сборку, из которой импортируется целевой тип.</span><span class="sxs-lookup"><span data-stu-id="f8771-106">[in] An [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface that represents the assembly from which the target type is imported.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="f8771-107">(в) Массив, содержащий хэш для сборки, `pAssemImport`указанный .</span><span class="sxs-lookup"><span data-stu-id="f8771-107">[in] An array that contains the hash for the assembly specified by `pAssemImport`.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="f8771-108">[in] Число байтов в массиве `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="f8771-108">[in] The number of bytes in the `pbHashValue` array.</span></span>  
  
 `pImport`  
 <span data-ttu-id="f8771-109">(в) Интерфейс [IMetaDataImport,](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) представляющий область метаданных, из которой импортируется целевой тип.</span><span class="sxs-lookup"><span data-stu-id="f8771-109">[in] An [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface that represents the metadata scope from which the target type is imported.</span></span>  
  
 `tdImport`  
 <span data-ttu-id="f8771-110">(в) Токен, `mdTypeDef` опозначавший целевой тип.</span><span class="sxs-lookup"><span data-stu-id="f8771-110">[in] An `mdTypeDef` token that specifies the target type.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="f8771-111">(в) Интерфейс [IMetaDataAssemblyEmit,](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) представляющий сборку, в которую импортируется целевой тип.</span><span class="sxs-lookup"><span data-stu-id="f8771-111">[in] An [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) interface that represents the assembly into which the target type is imported.</span></span>  
  
 `ptr`  
 <span data-ttu-id="f8771-112">(ваут) Токен, `mdTypeRef` определяемый в текущей области для ссылки типа.</span><span class="sxs-lookup"><span data-stu-id="f8771-112">[out] The `mdTypeRef` token that is defined in the current scope for the type reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8771-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="f8771-113">Remarks</span></span>  
 <span data-ttu-id="f8771-114">Перед вызовом метода [IMetaDataEmit::DefineImportMember](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md) можно `DefineImportType` использовать метод для создания ссылки на тип в текущей области для родительского класса или родительского интерфейса участника.</span><span class="sxs-lookup"><span data-stu-id="f8771-114">Prior to calling the [IMetaDataEmit::DefineImportMember](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md) method, you can use the `DefineImportType` method to create a type reference, in the current scope, for the member's parent class or parent interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8771-115">Требования</span><span class="sxs-lookup"><span data-stu-id="f8771-115">Requirements</span></span>  
 <span data-ttu-id="f8771-116">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8771-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8771-117">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f8771-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f8771-118">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f8771-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f8771-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8771-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8771-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f8771-120">See also</span></span>

- [<span data-ttu-id="f8771-121">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="f8771-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="f8771-122">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="f8771-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
