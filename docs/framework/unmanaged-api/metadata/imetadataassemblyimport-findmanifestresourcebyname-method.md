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
ms.openlocfilehash: f0c390509a698fdc4682ba81182d4b407d8718c9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448252"
---
# <a name="imetadataassemblyimportfindmanifestresourcebyname-method"></a>Метод IMetaDataAssemblyImport::FindManifestResourceByName
Gets a pointer to the manifest resource with the specified name.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT FindManifestResourceByName (  
    [in]  LPCWSTR                szName,   
    [out] mdManifestResource     *ptkManifestResource  
);   
```  
  
## <a name="parameters"></a>Параметры  
 `szName`  
 [in] The name of the resource.  
  
 `ptkManifestResource`  
 [out] The array used to store the `mdManifestResource` metadata tokens, each of which represents a manifest resource.  
  
## <a name="remarks"></a>Заметки  
 The `FindManifestResourceByName` method uses the standard rules employed by the common language runtime for resolving references.  
  
## <a name="requirements"></a>Требования  
 **Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Library:** Used as a resource in MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [Обнаружение сборок в среде выполнения](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
