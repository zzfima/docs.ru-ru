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
ms.openlocfilehash: beb697d80417b937876a0887e4376341185a47d9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447212"
---
# <a name="imetadataassemblyimportgetfileprops-method"></a>Метод IMetaDataAssemblyImport::GetFileProps
Возвращает свойства файла с указанной сигнатурой метаданных.  
  
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
 окне `mdFile` маркер метаданных, представляющий файл, для которого необходимо получить свойства.  
  
 `szName`  
 заполняет Простое имя файла.  
  
 `cchName`  
 окне Размер `szName`в расширенных символах.  
  
 `pchName`  
 заполняет Число расширенных символов, фактически возвращаемых в `szName`.  
  
 `ppbHashValue`  
 заполняет Указатель на хэш-значение. Это хэш-код с использованием алгоритма SHA-1 файла.  
  
 `pcbHashValue`  
 заполняет Число расширенных символов в возвращенном хэш-значении.  
  
 `pdwFileFlags`  
 заполняет Указатель на флаги, описывающие метаданные, примененные к файлу. Значение Flags является сочетанием одного или нескольких значений [корфилефлагс](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) .  
  
## <a name="requirements"></a>Требования  
 **Платформа:** См. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
