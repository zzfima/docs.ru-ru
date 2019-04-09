---
title: Метод IMetaDataAssemblyImport::GetAssemblyRefProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetAssemblyRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyRefProps
helpviewer_keywords:
- IMetaDataAssemblyImport::GetAssemblyRefProps method [.NET Framework metadata]
- GetAssemblyRefProps method [.NET Framework metadata]
ms.assetid: 5c6b7fb4-cbca-4479-b650-ab9a99732ea0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e6c550ff7af2dda8bc06afd771024fe290339904
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089787"
---
# <a name="imetadataassemblyimportgetassemblyrefprops-method"></a>Метод IMetaDataAssemblyImport::GetAssemblyRefProps
Получает набор свойств для ссылки на сборку с заданной подписью метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetAssemblyRefProps (  
    [in]  mdAssemblyRef        mdar,   
    [out] const void          **ppbPublicKeyOrToken,   
    [out] ULONG                *pcbPublicKeyOrToken,   
    [out] LPWSTR               szName,   
    [in]  ULONG                cchName,   
    [out] ULONG                *pchName,   
    [out] ASSEMBLYMETADATA     *pMetaData,   
    [out] const void           **ppbHashValue,   
    [out] ULONG                *pcbHashValue,   
    [out] DWORD                *pdwAssemblyRefFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `mdar`  
 [in] `mdAssemblyRef` Маркер метаданных, представляющий ссылку на сборку, для которого нужно получить свойства.  
  
 `ppbPublicKeyOrToken`  
 [out] Указатель на открытый ключ или токен метаданных.  
  
 `pcbPublicKeyOrToken`  
 [out] Число байтов в возвращаемый открытый ключ или маркер.  
  
 `szName`  
 [out] Простое имя сборки.  
  
 `cchName`  
 [in] Размер, в расширенных символах из `szName`.  
  
 `pchName`  
 [out] Указатель на число расширенных символов, фактически возвращенных в `szName`.  
  
 `pMetaData`  
 [out] Указатель на структуру ASSEMBLYMETADATA, которая содержит метаданные сборки.  
  
 `ppbHashValue`  
 [out] Указатель на хэш-значения. Это хэш, с помощью алгоритма SHA-1, из `PublicKey` свойство сборки, на которую выполняется ссылка, если флаг arfFullOriginator [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) имеет значение перечисления.  
  
 `pcbHashValue`  
 [out] Число расширенных символов в возвращенное хэш-значение.  
  
 `pdwAssemblyRefFlags`  
 [out] Указатель на флаги, описывающие метаданные, применяемые к сборке. Значение флагов представляет собой сочетание одного или нескольких [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) значения.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает значение S_OK, если он выполнен успешно; в противном случае возвращается один из кодов ошибок, определенных в файле заголовка Winerror.h.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Используется как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
