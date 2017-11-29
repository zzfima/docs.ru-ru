---
title: "Метод IMetaDataEmit::TranslateSigWithScope"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.TranslateSigWithScope
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::TranslateSigWithScope
helpviewer_keywords:
- TranslateSigWithScope method [.NET Framework metadata]
- IMetaDataEmit::TranslateSigWithScope method [.NET Framework metadata]
ms.assetid: 47915d33-b7bf-409e-b484-4ee1df15de22
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5127defc97423283b52b7b5bd8c6b7a31104fbc2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemittranslatesigwithscope-method"></a><span data-ttu-id="0753b-102">Метод IMetaDataEmit::TranslateSigWithScope</span><span class="sxs-lookup"><span data-stu-id="0753b-102">IMetaDataEmit::TranslateSigWithScope Method</span></span>
<span data-ttu-id="0753b-103">Импортирует сборку в текущую область и получает новую подпись метаданных для объединяемой области.</span><span class="sxs-lookup"><span data-stu-id="0753b-103">Imports an assembly into the current scope and gets a new metadata signature for the merged scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0753b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0753b-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="0753b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0753b-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="0753b-106">[in] Интерфейс для сборки импорта (в котором определен подпись).</span><span class="sxs-lookup"><span data-stu-id="0753b-106">[in] The interface for import assembly (where the signature is defined).</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="0753b-107">[in] Хэш-blob для сборки.</span><span class="sxs-lookup"><span data-stu-id="0753b-107">[in] The hash blob for the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="0753b-108">[in] Число байт в `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="0753b-108">[in] The count of bytes in `pbHashValue`.</span></span>  
  
 `import`  
 <span data-ttu-id="0753b-109">[in] Интерфейс для импорта области метаданных.</span><span class="sxs-lookup"><span data-stu-id="0753b-109">[in] The interface for import metadata scope.</span></span>  
  
 `pbSigBlob`  
 <span data-ttu-id="0753b-110">[in] Сигнатура для импорта.</span><span class="sxs-lookup"><span data-stu-id="0753b-110">[in] The signature to be imported.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="0753b-111">[in] Размер в байтах для `pbSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="0753b-111">[in] The size, in bytes, of `pbSigBlob`.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="0753b-112">[in] Интерфейс для экспорта сборки.</span><span class="sxs-lookup"><span data-stu-id="0753b-112">[in] The interface for export assembly.</span></span>  
  
 `emit`  
 <span data-ttu-id="0753b-113">[in] Интерфейс для экспорта области метаданных.</span><span class="sxs-lookup"><span data-stu-id="0753b-113">[in] The interface for export metadata scope.</span></span>  
  
 `pvTranslatedSig`  
 <span data-ttu-id="0753b-114">[out] Буфер для хранения BLOB-объекта переведенные подписи.</span><span class="sxs-lookup"><span data-stu-id="0753b-114">[out] The buffer to hold the translated signature blob.</span></span>  
  
 `cbTranslatedSigMax`  
 <span data-ttu-id="0753b-115">[in] Размер в байтах для `pvTranslatedSig`.</span><span class="sxs-lookup"><span data-stu-id="0753b-115">[in] The capacity, in bytes, of `pvTranslatedSig`.</span></span>  
  
 `pcbTranslatedSig`  
 <span data-ttu-id="0753b-116">[out] Число фактические байты в сигнатуре преобразованием.</span><span class="sxs-lookup"><span data-stu-id="0753b-116">[out] The number of actual bytes in the translated signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0753b-117">Требования</span><span class="sxs-lookup"><span data-stu-id="0753b-117">Requirements</span></span>  
 <span data-ttu-id="0753b-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0753b-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0753b-119">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0753b-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0753b-120">**Библиотека:** используется как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0753b-120">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0753b-121">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0753b-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0753b-122">См. также</span><span class="sxs-lookup"><span data-stu-id="0753b-122">See Also</span></span>  
 [<span data-ttu-id="0753b-123">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="0753b-123">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)  
 [<span data-ttu-id="0753b-124">Imetadataassemblyimport-интерфейс</span><span class="sxs-lookup"><span data-stu-id="0753b-124">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)  
 [<span data-ttu-id="0753b-125">IMetaDataEmit-интерфейс</span><span class="sxs-lookup"><span data-stu-id="0753b-125">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="0753b-126">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="0753b-126">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="0753b-127">IMetaDataImport-интерфейс</span><span class="sxs-lookup"><span data-stu-id="0753b-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
