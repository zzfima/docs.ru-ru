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
ms.openlocfilehash: 5434aa2d12bd9a29a8c2fc784421442469ceb1ce
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440564"
---
# <a name="imetadataassemblyemitsetassemblyrefprops-method"></a>Метод IMetaDataAssemblyEmit::SetAssemblyRefProps
Изменяет указанную структуру метаданных `AssemblyRef`.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
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
 окне Маркер метаданных, указывающий структуру метаданных `AssemblyRef`, которую необходимо изменить.  
  
 `pbPublicKeyOrToken`  
 окне Открытый ключ издателя сборки, на которую указывает ссылка.  
  
 `cbPublicKeyOrToken`  
 окне Размер в байтах `pbPublicKeyOrToken`.  
  
 `szName`  
 окне Понятное для человека текстовое имя сборки.  
  
 `pMetaData`  
 окне Указатель на экземпляр ASSEMBLYMETADATA, содержащий сведения о версии, платформе и локали для сборки.  
  
 `pbHashValue`  
 окне Указатель на хэш-данные, связанные со сборкой.  
  
 `cbHashValue`  
 окне Размер в байтах `pbHashValue`.  
  
 `dwAssemblyRefFlags`  
 окне Побитовое сочетание значений [ассемблиреффлагс](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) , задающих атрибуты упоминаемой сборки.  
  
## <a name="remarks"></a>Примечания  
 Чтобы создать `AssemblyRef` структуру метаданных, используйте метод [IMetaDataAssemblyEmit::D ефинеассемблиреф](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md) .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
