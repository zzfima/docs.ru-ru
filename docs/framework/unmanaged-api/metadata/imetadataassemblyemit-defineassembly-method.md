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
ms.openlocfilehash: 20628e708261076c6e172ff30c366a0d69c2e0f2
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432118"
---
# <a name="imetadataassemblyemitdefineassembly-method"></a>Метод IMetaDataAssemblyEmit::DefineAssembly
Создает структуру `Assembly`, содержащую метаданные для указанной сборки, и возвращает связанный маркер метаданных.  
  
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
 окне Открытый ключ, определяющий издателя сборки, или значение NULL, если сборка не имеет строгого имени.  
  
 `cbPublicKey`  
 окне Размер в байтах `pbPublicKey`.  
  
 `uHashAlgId`  
 окне Идентификатор алгоритма хэширования, используемого для шифрования файлов в сборке, или значение NULL для указания алгоритма SHA-1.  
  
 `szName`  
 окне Понятное для человека текстовое имя сборки. Это значение не должно превышать 1024 символов.  
  
 `pMetaData`  
 окне Указатель на экземпляр ASSEMBLYMETADATA, содержащий сведения о версии, платформе и локали для сборки.  
  
 `dwAssemblyFlags`  
 окне Сочетание значений [корассемблифлагс](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) , описывающих функции сборки.  
  
 `pmda`  
 заполняет Указатель на маркер метаданных.  
  
## <a name="remarks"></a>Примечания  
 В манифесте может быть определена только одна структура метаданных `Assembly`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
