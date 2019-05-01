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
ms.openlocfilehash: 71029d6ebfb3248da791d4371dfe3e39589af443
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049994"
---
# <a name="imetadataemittranslatesigwithscope-method"></a>Метод IMetaDataEmit::TranslateSigWithScope
Импортирует сборки в текущей области и возвращает новую подпись метаданных для объединенных области.  
  
## <a name="syntax"></a>Синтаксис  
  
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
  
## <a name="parameters"></a>Параметры  
 `pAssemImport`  
 [in] Интерфейс для импорта сборки (в котором определен подпись).  
  
 `pbHashValue`  
 [in] Большой двоичный объект хэша для сборки.  
  
 `cbHashValue`  
 [in] Число байт в `pbHashValue`.  
  
 `import`  
 [in] Интерфейс для области импорта метаданных.  
  
 `pbSigBlob`  
 [in] Сигнатура для импорта.  
  
 `cbSigBlob`  
 [in] Размер в байтах из `pbSigBlob`.  
  
 `pAssemEmit`  
 [in] Интерфейс для экспорта сборки.  
  
 `emit`  
 [in] Интерфейс для области экспорта метаданных.  
  
 `pvTranslatedSig`  
 [out] Буфер для хранения больших двоичных объектов переведенные подписи.  
  
 `cbTranslatedSigMax`  
 [in] Емкость, в байтах из `pvTranslatedSig`.  
  
 `pcbTranslatedSig`  
 [out] Число фактические байты в переведенные подписи.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Используется как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [Интерфейс IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
