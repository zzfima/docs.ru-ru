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
ms.openlocfilehash: 4149db74adfa26df221eed5c590766a023bb105e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448225"
---
# <a name="imetadataassemblyimportgetassemblyrefprops-method"></a>Метод IMetaDataAssemblyImport::GetAssemblyRefProps
Возвращает набор свойств для ссылки на сборку с указанной сигнатурой метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
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
 окне `mdAssemblyRef` маркер метаданных, представляющий ссылку на сборку, для которой необходимо получить свойства.  
  
 `ppbPublicKeyOrToken`  
 заполняет Указатель на открытый ключ или маркер метаданных.  
  
 `pcbPublicKeyOrToken`  
 заполняет Число байтов в возвращенном открытом ключе или токене.  
  
 `szName`  
 заполняет Простое имя сборки.  
  
 `cchName`  
 окне Размер `szName`в расширенных символах.  
  
 `pchName`  
 заполняет Указатель на число расширенных символов, фактически возвращаемых в `szName`.  
  
 `pMetaData`  
 заполняет Указатель на структуру ASSEMBLYMETADATA, содержащую метаданные сборки.  
  
 `ppbHashValue`  
 заполняет Указатель на хэш-значение. Это хэш с использованием алгоритма SHA-1 `PublicKey` свойства сборки, на которую указывает ссылка, если не задан флаг Арффуллоригинатор перечисления [ассемблиреффлагс](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) .  
  
 `pcbHashValue`  
 заполняет Число расширенных символов в возвращенном хэш-значении.  
  
 `pdwAssemblyRefFlags`  
 заполняет Указатель на флаги, описывающие метаданные, примененные к сборке. Значение Flags является сочетанием одного или нескольких значений [корассемблифлагс](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) .  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает S_OK, если он выполнен. в противном случае возвращается один из кодов ошибок, определенных в файле заголовка Winerror. h.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
