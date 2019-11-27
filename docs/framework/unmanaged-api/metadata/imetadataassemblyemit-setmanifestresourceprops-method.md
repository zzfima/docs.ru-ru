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
ms.openlocfilehash: f6b5e12df60663b75e10b04eaa008a75d720d753
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434440"
---
# <a name="imetadataassemblyemitsetmanifestresourceprops-method"></a>Метод IMetaDataAssemblyEmit::SetManifestResourceProps
Изменяет указанную структуру метаданных `ManifestResource`.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetManifestResourceProps (  
    [in] mdManifestResource  mr,  
    [in] mdToken             tkImplementation,   
    [in] DWORD               dwOffset,  
    [in] DWORD               dwResourceFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `mr`  
 окне Токен, указывающий структуру метаданных `ManifestResource`, которую необходимо изменить.  
  
 `tkImplementation`  
 окне Токен типа `File` или `AssemblyRef`, который сопоставляется с поставщиком ресурсов.  
  
 `dwOffset`  
 окне Смещение в начале ресурса в файле.  
  
 `dwResourceFlags`  
 окне Побитовое сочетание значений флагов, задающих атрибуты ресурса.  
  
## <a name="remarks"></a>Примечания  
 Чтобы создать `ManifestResource` структуру метаданных, используйте метод [IMetaDataAssemblyEmit::D ефинеманифестресаурце](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md) .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
