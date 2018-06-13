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
ms.openlocfilehash: b6675d50d3222a43abc8838c3c86cb825d2dad16
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445726"
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
 [in] Открытый ключ издателя по ссылке сборки. Вспомогательная функция [StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md) может использоваться для получения хэша открытого ключа, передаваемый в качестве этого параметра.  
  
 `cbPublicKeyOrToken`  
 [in] Размер в байтах `pbPublicKeyOrToken`.  
  
 `szName`  
 [in] Понятное текстовое имя сборки. Это значение не должно превышать 1024 символа.  
  
 `pMetaData`  
 [in] ASSEMBLYMETADATA экземпляр, который содержит сведения о версии, платформы и языка сборки.  
  
 `pbHashValue`  
 [in] Хэш данных, связанные со сборкой, на которую указывает ссылка. Необязательный.  
  
 `cbHashValue`  
 [in] Размер в байтах `pbHashValue`.  
  
 `dwAssemblyRefFlags`  
 [in] Побитовое сочетание [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) значения, которые влияют на поведение механизма выполнения сборки.  
  
 `pmdar`  
 [out] Указатель на возвращаемый `AssemblyRef` токен метаданных.  
  
## <a name="remarks"></a>Примечания  
 Один `AssemblyRef` структуру метаданных должны быть определены для каждой сборки, на которую ссылается данная сборка.  
  
 Во время выполнения передаются сведения о связанной сборке распознаватель сборок с указанием, что они представляют информацию «в процессе построения». Затем распознаватель сборок применяет политику.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** используется как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
