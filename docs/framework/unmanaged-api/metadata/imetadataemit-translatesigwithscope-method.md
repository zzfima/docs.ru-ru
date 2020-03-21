---
title: Метод IMetaDataEmit::TranslateSigWithScope
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.TranslateSigWithScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::TranslateSigWithScope
helpviewer_keywords:
- TranslateSigWithScope method [.NET Framework metadata]
- IMetaDataEmit::TranslateSigWithScope method [.NET Framework metadata]
ms.assetid: 47915d33-b7bf-409e-b484-4ee1df15de22
topic_type:
- apiref
ms.openlocfilehash: 2662af41fbd2cdc3ce8a6df1e036dfc5b22ff6a3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175555"
---
# <a name="imetadataemittranslatesigwithscope-method"></a><span data-ttu-id="0740b-102">Метод IMetaDataEmit::TranslateSigWithScope</span><span class="sxs-lookup"><span data-stu-id="0740b-102">IMetaDataEmit::TranslateSigWithScope Method</span></span>
<span data-ttu-id="0740b-103">Импортирует сборку в текущую область и получает новую подпись метаданных для объединенной области.</span><span class="sxs-lookup"><span data-stu-id="0740b-103">Imports an assembly into the current scope and gets a new metadata signature for the merged scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0740b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0740b-104">Syntax</span></span>  
  
```cpp  
HRESULT TranslateSigWithScope (
    [in]  IMetaDataAssemblyImport   *pAssemImport,
    [in]  const void                *pbHashValue,
    [in]  ULONG                     cbHashValue,
    [in]  IMetaDataImport           *import,
    [in]  PCCOR_SIGNATURE           pbSigBlob,
    [in]  ULONG                     cbSigBlob,  
    [in]  IMetaDataAssemblyEmit     *pAssemEmit,
    [in]  IMetaDataEmit             *emit,
    [out] PCOR_SIGNATURE            pvTranslatedSig,
    [in]  ULONG                     cbTranslatedSigMax,
    [out] ULONG                     *pcbTranslatedSig
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0740b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0740b-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="0740b-106">(в) Интерфейс для сборки импорта (где определена подпись).</span><span class="sxs-lookup"><span data-stu-id="0740b-106">[in] The interface for import assembly (where the signature is defined).</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="0740b-107">(в) Хэш-капля для сборки.</span><span class="sxs-lookup"><span data-stu-id="0740b-107">[in] The hash blob for the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="0740b-108">(в) Количество байтов `pbHashValue`в .</span><span class="sxs-lookup"><span data-stu-id="0740b-108">[in] The count of bytes in `pbHashValue`.</span></span>  
  
 `import`  
 <span data-ttu-id="0740b-109">(в) Интерфейс для области метаданных импорта.</span><span class="sxs-lookup"><span data-stu-id="0740b-109">[in] The interface for import metadata scope.</span></span>  
  
 `pbSigBlob`  
 <span data-ttu-id="0740b-110">(в) Подпись, которая будет импортирована.</span><span class="sxs-lookup"><span data-stu-id="0740b-110">[in] The signature to be imported.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="0740b-111">(в) Размер, в байтах, из `pbSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="0740b-111">[in] The size, in bytes, of `pbSigBlob`.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="0740b-112">(в) Интерфейс для сборки экспорта.</span><span class="sxs-lookup"><span data-stu-id="0740b-112">[in] The interface for export assembly.</span></span>  
  
 `emit`  
 <span data-ttu-id="0740b-113">(в) Интерфейс для области экспортных метаданных.</span><span class="sxs-lookup"><span data-stu-id="0740b-113">[in] The interface for export metadata scope.</span></span>  
  
 `pvTranslatedSig`  
 <span data-ttu-id="0740b-114">(ваут) Буфер для удержания переведенной подписи капли.</span><span class="sxs-lookup"><span data-stu-id="0740b-114">[out] The buffer to hold the translated signature blob.</span></span>  
  
 `cbTranslatedSigMax`  
 <span data-ttu-id="0740b-115">(в) Емкость, в байтах, `pvTranslatedSig`.</span><span class="sxs-lookup"><span data-stu-id="0740b-115">[in] The capacity, in bytes, of `pvTranslatedSig`.</span></span>  
  
 `pcbTranslatedSig`  
 <span data-ttu-id="0740b-116">(ваут) Количество фактических байтов в переведенной подписи.</span><span class="sxs-lookup"><span data-stu-id="0740b-116">[out] The number of actual bytes in the translated signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0740b-117">Требования</span><span class="sxs-lookup"><span data-stu-id="0740b-117">Requirements</span></span>  
 <span data-ttu-id="0740b-118">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0740b-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0740b-119">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0740b-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0740b-120">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0740b-120">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0740b-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0740b-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0740b-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0740b-122">See also</span></span>

- [<span data-ttu-id="0740b-123">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="0740b-123">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="0740b-124">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="0740b-124">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="0740b-125">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="0740b-125">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="0740b-126">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="0740b-126">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="0740b-127">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="0740b-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
