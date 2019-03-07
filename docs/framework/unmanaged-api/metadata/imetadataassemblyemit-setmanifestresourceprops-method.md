---
title: Метод IMetaDataAssemblyEmit::SetManifestResourceProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetManifestResourceProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetManifestResourceProps
helpviewer_keywords:
- SetManifestResourceProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetManifestResourceProps method [.NET Framework metadata]
ms.assetid: ef77efd1-849c-4e51-ba92-7ee3d2bf0339
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2d3dabd48ed63a023e830e1c2b8c983ef3af4519
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481720"
---
# <a name="imetadataassemblyemitsetmanifestresourceprops-method"></a>Метод IMetaDataAssemblyEmit::SetManifestResourceProps
Изменяет указанную структуру метаданных `ManifestResource`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT SetManifestResourceProps (  
    [in] mdManifestResource  mr,  
    [in] mdToken             tkImplementation,   
    [in] DWORD               dwOffset,  
    [in] DWORD               dwResourceFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `mr`  
 [in] Токен, который указывает `ManifestResource` изменение структуры метаданных.  
  
 `tkImplementation`  
 [in] Токен типа `File` или `AssemblyRef`, который сопоставляет к поставщику ресурсов.  
  
 `dwOffset`  
 [in] Смещение в начало ресурса в файле.  
  
 `dwResourceFlags`  
 [in] Побитовое сочетание значения флагов, определяющих атрибуты ресурса.  
  
## <a name="remarks"></a>Примечания  
 Чтобы создать `ManifestResource` структура метаданных, используйте [IMetaDataAssemblyEmit::DefineManifestResource](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md) метод.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Используется как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
