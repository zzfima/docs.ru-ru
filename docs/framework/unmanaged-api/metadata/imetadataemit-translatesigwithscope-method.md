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
ms.openlocfilehash: 0ddaddbbd050dc079fcf20551e90c895d2f4ef59
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446347"
---
# <a name="imetadataemittranslatesigwithscope-method"></a><span data-ttu-id="12e5c-102">Метод IMetaDataEmit::TranslateSigWithScope</span><span class="sxs-lookup"><span data-stu-id="12e5c-102">IMetaDataEmit::TranslateSigWithScope Method</span></span>
<span data-ttu-id="12e5c-103">Импортирует сборку в текущую область и получает новую подпись метаданных для объединяемой области.</span><span class="sxs-lookup"><span data-stu-id="12e5c-103">Imports an assembly into the current scope and gets a new metadata signature for the merged scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12e5c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="12e5c-104">Syntax</span></span>  
  
```  
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
  
#### <a name="parameters"></a><span data-ttu-id="12e5c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="12e5c-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="12e5c-106">[in] Интерфейс для сборки импорта (в котором определен подпись).</span><span class="sxs-lookup"><span data-stu-id="12e5c-106">[in] The interface for import assembly (where the signature is defined).</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="12e5c-107">[in] Хэш-blob для сборки.</span><span class="sxs-lookup"><span data-stu-id="12e5c-107">[in] The hash blob for the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="12e5c-108">[in] Число байт в `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="12e5c-108">[in] The count of bytes in `pbHashValue`.</span></span>  
  
 `import`  
 <span data-ttu-id="12e5c-109">[in] Интерфейс для импорта области метаданных.</span><span class="sxs-lookup"><span data-stu-id="12e5c-109">[in] The interface for import metadata scope.</span></span>  
  
 `pbSigBlob`  
 <span data-ttu-id="12e5c-110">[in] Сигнатура для импорта.</span><span class="sxs-lookup"><span data-stu-id="12e5c-110">[in] The signature to be imported.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="12e5c-111">[in] Размер в байтах для `pbSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="12e5c-111">[in] The size, in bytes, of `pbSigBlob`.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="12e5c-112">[in] Интерфейс для экспорта сборки.</span><span class="sxs-lookup"><span data-stu-id="12e5c-112">[in] The interface for export assembly.</span></span>  
  
 `emit`  
 <span data-ttu-id="12e5c-113">[in] Интерфейс для экспорта области метаданных.</span><span class="sxs-lookup"><span data-stu-id="12e5c-113">[in] The interface for export metadata scope.</span></span>  
  
 `pvTranslatedSig`  
 <span data-ttu-id="12e5c-114">[out] Буфер для хранения BLOB-объекта переведенные подписи.</span><span class="sxs-lookup"><span data-stu-id="12e5c-114">[out] The buffer to hold the translated signature blob.</span></span>  
  
 `cbTranslatedSigMax`  
 <span data-ttu-id="12e5c-115">[in] Размер в байтах для `pvTranslatedSig`.</span><span class="sxs-lookup"><span data-stu-id="12e5c-115">[in] The capacity, in bytes, of `pvTranslatedSig`.</span></span>  
  
 `pcbTranslatedSig`  
 <span data-ttu-id="12e5c-116">[out] Число фактические байты в сигнатуре преобразованием.</span><span class="sxs-lookup"><span data-stu-id="12e5c-116">[out] The number of actual bytes in the translated signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12e5c-117">Требования</span><span class="sxs-lookup"><span data-stu-id="12e5c-117">Requirements</span></span>  
 <span data-ttu-id="12e5c-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12e5c-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12e5c-119">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="12e5c-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="12e5c-120">**Библиотека:** используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="12e5c-120">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="12e5c-121">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12e5c-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12e5c-122">См. также</span><span class="sxs-lookup"><span data-stu-id="12e5c-122">See Also</span></span>  
 [<span data-ttu-id="12e5c-123">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="12e5c-123">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)  
 [<span data-ttu-id="12e5c-124">Интерфейс IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="12e5c-124">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)  
 [<span data-ttu-id="12e5c-125">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="12e5c-125">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="12e5c-126">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="12e5c-126">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="12e5c-127">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="12e5c-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
