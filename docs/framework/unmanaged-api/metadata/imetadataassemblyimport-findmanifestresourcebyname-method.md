---
title: Метод IMetaDataAssemblyImport::FindManifestResourceByName
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.FindManifestResourceByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindManifestResourceByName
helpviewer_keywords:
- FindManifestResourceByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindManifestResourceByName method [.NET Framework metadata]
ms.assetid: 7b72fa11-3866-402b-bdea-2b966b77cfe0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9afc2ecc34131f62f1f8e8e86ca73f8b8b0126b8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443516"
---
# <a name="imetadataassemblyimportfindmanifestresourcebyname-method"></a>Метод IMetaDataAssemblyImport::FindManifestResourceByName
Получает указатель на ресурс манифеста с указанным именем.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT FindManifestResourceByName (  
    [in]  LPCWSTR                szName,   
    [out] mdManifestResource     *ptkManifestResource  
);   
```  
  
#### <a name="parameters"></a>Параметры  
 `szName`  
 [in] Имя ресурса.  
  
 `ptkManifestResource`  
 [out] Массив, используемый для хранения `mdManifestResource` лексемы метаданных, каждый из которых представляет ресурс манифеста.  
  
## <a name="remarks"></a>Примечания  
 `FindManifestResourceByName` Метод использует стандартных правил, применяемых средой CLR для разрешения ссылок.  
  
## <a name="requirements"></a>Требования  
 **Платформа:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** используется как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)  
 [Обнаружение сборок в среде выполнения](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
