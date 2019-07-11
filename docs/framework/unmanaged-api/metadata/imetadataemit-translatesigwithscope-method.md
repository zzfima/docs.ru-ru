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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c571e37d87ffd136687452dc80a823b8ddbe3359
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782062"
---
# <a name="imetadataemittranslatesigwithscope-method"></a><span data-ttu-id="4ab28-102">Метод IMetaDataEmit::TranslateSigWithScope</span><span class="sxs-lookup"><span data-stu-id="4ab28-102">IMetaDataEmit::TranslateSigWithScope Method</span></span>
<span data-ttu-id="4ab28-103">Импортирует сборки в текущей области и возвращает новую подпись метаданных для объединенных области.</span><span class="sxs-lookup"><span data-stu-id="4ab28-103">Imports an assembly into the current scope and gets a new metadata signature for the merged scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ab28-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4ab28-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="4ab28-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4ab28-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="4ab28-106">[in] Интерфейс для импорта сборки (в котором определен подпись).</span><span class="sxs-lookup"><span data-stu-id="4ab28-106">[in] The interface for import assembly (where the signature is defined).</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="4ab28-107">[in] Большой двоичный объект хэша для сборки.</span><span class="sxs-lookup"><span data-stu-id="4ab28-107">[in] The hash blob for the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="4ab28-108">[in] Число байт в `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="4ab28-108">[in] The count of bytes in `pbHashValue`.</span></span>  
  
 `import`  
 <span data-ttu-id="4ab28-109">[in] Интерфейс для области импорта метаданных.</span><span class="sxs-lookup"><span data-stu-id="4ab28-109">[in] The interface for import metadata scope.</span></span>  
  
 `pbSigBlob`  
 <span data-ttu-id="4ab28-110">[in] Сигнатура для импорта.</span><span class="sxs-lookup"><span data-stu-id="4ab28-110">[in] The signature to be imported.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="4ab28-111">[in] Размер в байтах из `pbSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="4ab28-111">[in] The size, in bytes, of `pbSigBlob`.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="4ab28-112">[in] Интерфейс для экспорта сборки.</span><span class="sxs-lookup"><span data-stu-id="4ab28-112">[in] The interface for export assembly.</span></span>  
  
 `emit`  
 <span data-ttu-id="4ab28-113">[in] Интерфейс для области экспорта метаданных.</span><span class="sxs-lookup"><span data-stu-id="4ab28-113">[in] The interface for export metadata scope.</span></span>  
  
 `pvTranslatedSig`  
 <span data-ttu-id="4ab28-114">[out] Буфер для хранения больших двоичных объектов переведенные подписи.</span><span class="sxs-lookup"><span data-stu-id="4ab28-114">[out] The buffer to hold the translated signature blob.</span></span>  
  
 `cbTranslatedSigMax`  
 <span data-ttu-id="4ab28-115">[in] Емкость, в байтах из `pvTranslatedSig`.</span><span class="sxs-lookup"><span data-stu-id="4ab28-115">[in] The capacity, in bytes, of `pvTranslatedSig`.</span></span>  
  
 `pcbTranslatedSig`  
 <span data-ttu-id="4ab28-116">[out] Число фактические байты в переведенные подписи.</span><span class="sxs-lookup"><span data-stu-id="4ab28-116">[out] The number of actual bytes in the translated signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ab28-117">Требования</span><span class="sxs-lookup"><span data-stu-id="4ab28-117">Requirements</span></span>  
 <span data-ttu-id="4ab28-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ab28-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ab28-119">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4ab28-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4ab28-120">**Библиотека:** Используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4ab28-120">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4ab28-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ab28-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ab28-122">См. также</span><span class="sxs-lookup"><span data-stu-id="4ab28-122">See also</span></span>

- [<span data-ttu-id="4ab28-123">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="4ab28-123">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="4ab28-124">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="4ab28-124">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="4ab28-125">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="4ab28-125">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="4ab28-126">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="4ab28-126">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="4ab28-127">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="4ab28-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
