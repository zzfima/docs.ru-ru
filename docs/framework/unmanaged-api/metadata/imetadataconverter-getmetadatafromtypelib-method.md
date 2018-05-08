---
title: Метод IMetaDataConverter::GetMetaDataFromTypeLib
ms.date: 03/30/2017
api_name:
- IMetaDataConverter.GetMetaDataFromTypeLib
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter::GetMetaDataFromTypeLib
helpviewer_keywords:
- IMetaDataConverter::GetMetaDataFromTypeLib method [.NET Framework metadata]
- GetMetaDataFromTypeLib method [.NET Framework metadata]
ms.assetid: 97dc3a56-adfa-431f-889e-06a35ac84d51
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fdd2aeb54e9d3c78c58b1a8b497839e876038dfb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataconvertergetmetadatafromtypelib-method"></a>Метод IMetaDataConverter::GetMetaDataFromTypeLib
Возвращает указатель интерфейса [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) экземпляр, представляющий подпись метаданных для библиотеки типов, представленный указанным `ITypeLib` экземпляра.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetMetaDataFromTypeLib (  
    [in]  ITypeLib        *pITL,   
    [out] IMetaDataImport **ppMDI  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pITL`  
 [in] Указатель на `ITypeLib` , представляющий библиотеку типов.  
  
 `ppMDI`  
 [out] Указатель на расположение, принимающая адрес `IMetaDataImport` экземпляр, представляющий подпись метаданных.  
  
## <a name="requirements"></a>Требования  
 **Платформа:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** используется как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
