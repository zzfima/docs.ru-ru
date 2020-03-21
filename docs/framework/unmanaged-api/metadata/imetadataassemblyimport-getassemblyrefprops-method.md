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
ms.openlocfilehash: 9aef471c1155070af0e9bcca14975a65bc5dc763
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175971"
---
# <a name="imetadataassemblyimportgetassemblyrefprops-method"></a>Метод IMetaDataAssemblyImport::GetAssemblyRefProps
Получает набор свойств для ссылки сборки с указанной подписью метаданных.  
  
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
 (в) Токен `mdAssemblyRef` метаданных, представляющий ссылку сборки для получения свойств.  
  
 `ppbPublicKeyOrToken`  
 (ваут) Указатель на открытый ключ или токен метаданных.  
  
 `pcbPublicKeyOrToken`  
 (ваут) Количество байтов в возвращенном публичном ключе или маркере.  
  
 `szName`  
 (ваут) Простое название сборки.  
  
 `cchName`  
 (в) Размер, в широких chars, . `szName`  
  
 `pchName`  
 (ваут) Указатель на количество широких chars `szName`фактически вернулся в .  
  
 `pMetaData`  
 (ваут) Указатель на структуру ASSEMBLYMETADATA, содержащую метаданные сборки.  
  
 `ppbHashValue`  
 (ваут) Указатель на значение хэша. Это хэш, использующий алгоритм SHA-1, `PublicKey` имущества сборки, на который ссылается, если только не установлен флаг ArfFullOriginator в перечислении [AssemblyRefFlags.](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md)  
  
 `pcbHashValue`  
 (ваут) Количество широких chars в возвращенном значении хэша.  
  
 `pdwAssemblyRefFlags`  
 (ваут) Указатель на флаги, описывающие метаданные, применяемые к сборке. Значение флагов представляет собой сочетание одного или нескольких значений [CorAssemblyFlags.](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md)  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает S_OK, если он преуспевает; в противном случае он возвращает один из кодов ошибок, определенных в файле заголовка Winerror.h.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
