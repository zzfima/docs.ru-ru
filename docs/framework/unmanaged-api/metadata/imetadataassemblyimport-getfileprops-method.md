---
title: Метод IMetaDataAssemblyImport::GetFileProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetFileProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetFileProps
helpviewer_keywords:
- GetFileProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetFileProps method [.NET Framework metadata]
ms.assetid: c5e6216f-ae3d-4697-9688-66b69c1251ec
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4f3883b0cd1b7aca6265b738eace483c81eb37b9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760141"
---
# <a name="imetadataassemblyimportgetfileprops-method"></a>Метод IMetaDataAssemblyImport::GetFileProps
Получает свойства файла с заданной подписью метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetFileProps (  
    [in]  mdFile      mdf,   
    [out] LPWSTR      szName,   
    [in]  ULONG       cchName,   
    [out] ULONG       *pchName,   
    [out] const void  **ppbHashValue,   
    [out] ULONG       *pcbHashValue,   
    [out] DWORD       *pdwFileFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `mdf`  
 [in] `mdFile` Маркер метаданных, представляющий файл, для которого нужно получить свойства.  
  
 `szName`  
 [out] Простое имя файла.  
  
 `cchName`  
 [in] Размер, в расширенных символах из `szName`.  
  
 `pchName`  
 [out] Число расширенных символов, фактически возвращенных в `szName`.  
  
 `ppbHashValue`  
 [out] Указатель на хэш-значения. Это хэш, с помощью алгоритма SHA-1, файла.  
  
 `pcbHashValue`  
 [out] Число расширенных символов в возвращенное хэш-значение.  
  
 `pdwFileFlags`  
 [out] Указатель на флаги, описывающие метаданные, применяемые к файлу. Значение флагов представляет собой сочетание одного или нескольких [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) значения.  
  
## <a name="requirements"></a>Требования  
 **Платформа:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Используется как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
