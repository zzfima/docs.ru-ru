---
title: Метод IMetaDataAssemblyEmit::DefineAssembly
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineAssembly
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineAssembly method [.NET Framework metadata]
- DefineAssembly method [.NET Framework metadata]
ms.assetid: a0637d66-74bf-4f2d-8137-9ff838bccece
topic_type:
- apiref
ms.openlocfilehash: 14bd352099890e4ca36321d550b8e982d4373231
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177888"
---
# <a name="imetadataassemblyemitdefineassembly-method"></a>Метод IMetaDataAssemblyEmit::DefineAssembly
Создает `Assembly` структуру, содержащую метаданные для указанной сборки, и возвращает связанный токен метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DefineAssembly (  
    [in]  void                 *pbPublicKey,  
    [in]  ULONG                cbPublicKey,  
    [in]  ULONG                uHashAlgId,  
    [in]  LPCWSTR              szName,
    [in]  ASSEMBLYMETADATA     *pMetaData,  
    [in]  DWORD                dwAssemblyFlags,  
    [out] mdAssembly           *pmda  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pbPublicKey`  
 (в) Открытый ключ, который идентифицирует издателя сборки, или NULL, если сборка не названа решительно.  
  
 `cbPublicKey`  
 (в) Размер байтов `pbPublicKey`.  
  
 `uHashAlgId`  
 (в) Идентификатор алгоритма хэширования для шифрования файлов в сборке или NULL для указания алгоритма SHA-1.  
  
 `szName`  
 (в) Читаемое человеком текстовое название сборки. Это значение не должно превышать 1024 символов.  
  
 `pMetaData`  
 (в) Указатель на экземпляр ASSEMBLYMETADATA, содержащий информацию о версии, платформе и локализации для сборки.  
  
 `dwAssemblyFlags`  
 (в) Сочетание значений [CorAssemblyFlags,](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) описывающие особенности сборки.  
  
 `pmda`  
 (ваут) Указатель на маркер метаданных.  
  
## <a name="remarks"></a>Remarks  
 Только `Assembly` одна структура метаданных может быть определена в манифесте.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** Включено в качестве ресурса в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
