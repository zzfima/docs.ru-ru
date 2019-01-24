---
title: Метод IMetaDataAssemblyEmit::DefineAssemblyRef
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineAssemblyRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineAssemblyRef
helpviewer_keywords:
- DefineAssemblyRef method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineAssemblyRef method [.NET Framework metadata]
ms.assetid: 0b284b18-0084-4b3a-912a-5ebe9f29c88b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f82fca1d7701921a10c1feb9cce19371729ff01e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54493474"
---
# <a name="imetadataassemblyemitdefineassemblyref-method"></a>Метод IMetaDataAssemblyEmit::DefineAssemblyRef
Создает структуру `AssemblyRef`, содержащую метаданные для сборки, на которую ссылается данная сборка, и возвращает связанный токен метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT DefineAssemblyRef (  
    [in]  void                *pbPublicKeyOrToken,  
    [in]  ULONG               cbPublicKeyOrToken,  
    [in]  LPCWSTR             szName,  
    [in]  ASSEMBLYMETADATA    pMetaData,  
    [in]  void                *pbHashValue,  
    [in]  ULONG               cbHashValue,  
    [in]  DWORD               dwAssemblyRefFlags,  
    [out] mdAssemblyRef       *pmdar  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pbPublicKeyOrToken`  
 [in] Открытый ключ издателя по ссылке сборки. Вспомогательная функция [StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md) может использоваться для получения хэша открытого ключа, передаваемое в качестве этого параметра.  
  
 `cbPublicKeyOrToken`  
 [in] Размер в байтах `pbPublicKeyOrToken`.  
  
 `szName`  
 [in] Понятное текстовое имя сборки. Это значение не должна превышать 1024 символа.  
  
 `pMetaData`  
 [in] Экземпляр ASSEMBLYMETADATA, содержащий сведения о версии, платформы и языка сборки, на которую указывает ссылка.  
  
 `pbHashValue`  
 [in] Хэш данных, связанные со сборкой, на которую указывает ссылка. Необязательный параметр.  
  
 `cbHashValue`  
 [in] Размер в байтах `pbHashValue`.  
  
 `dwAssemblyRefFlags`  
 [in] Побитовое сочетание [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) значения, которые влияют на поведение подсистемы выполнения.  
  
 `pmdar`  
 [out] Указатель на возвращенный `AssemblyRef` токеном метаданных.  
  
## <a name="remarks"></a>Примечания  
 Один `AssemblyRef` структура метаданных должны быть определены для каждой сборки, на которую ссылается данная сборка.  
  
 Во время выполнения сведения о связанной сборке, передаются в котором распознаватель сборок с указанием, что они представляют сведения «при построении». Затем, в котором распознаватель сборок применяет политику.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Используется как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
