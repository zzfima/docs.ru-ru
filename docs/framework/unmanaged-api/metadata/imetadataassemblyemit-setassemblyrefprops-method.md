---
title: Метод IMetaDataAssemblyEmit::SetAssemblyRefProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetAssemblyRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetAssemblyRefProps
helpviewer_keywords:
- SetAssemblyRefProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetAssemblyRefProps method [.NET Framework metadata]
ms.assetid: 70a32bf3-9051-4f96-ae87-11356d06a073
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 25d5e412dc52e4ce26995ff88454b33ccea64c89
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59110101"
---
# <a name="imetadataassemblyemitsetassemblyrefprops-method"></a>Метод IMetaDataAssemblyEmit::SetAssemblyRefProps
Изменяет указанную структуру метаданных `AssemblyRef`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT SetAssemblyRefProps (  
    [in] mdAssemblyRef              ar,  
    [in] const void                 *pbPublicKeyOrToken,  
    [in] ULONG                      cbPublicKeyOrToken,  
    [in] LPCWSTR                    szName,   
    [in] const ASSEMBLYMETADATA     *pMetaData,   
    [in] const void                 *pbHashValue,  
    [in] ULONG                      cbHashValue,  
    [in] DWORD                      dwAssemblyRefFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ar`  
 [in] Токен метаданных, указывающее `AssemblyRef` изменение структуры метаданных.  
  
 `pbPublicKeyOrToken`  
 [in] Открытый ключ издателя по ссылке сборки.  
  
 `cbPublicKeyOrToken`  
 [in] Размер в байтах `pbPublicKeyOrToken`.  
  
 `szName`  
 [in] Понятное текстовое имя сборки.  
  
 `pMetaData`  
 [in] Указатель на экземпляр ASSEMBLYMETADATA, содержащий сведения о версии, платформы и языковой стандарт для сборки.  
  
 `pbHashValue`  
 [in] Указатель на данные хэша, связанные со сборкой.  
  
 `cbHashValue`  
 [in] Размер в байтах `pbHashValue`.  
  
 `dwAssemblyRefFlags`  
 [in] Побитовое сочетание [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) значения, задающие атрибуты сборки, на которую указывает ссылка.  
  
## <a name="remarks"></a>Примечания  
 Чтобы создать `AssemblyRef` структура метаданных, используйте [IMetaDataAssemblyEmit::DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md) метод.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Используется как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
