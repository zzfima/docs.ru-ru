---
title: Метод IMetaDataAssemblyImport::GetAssemblyProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetAssemblyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyProps
helpviewer_keywords:
- GetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetAssemblyProps method [.NET Framework metadata]
ms.assetid: 0eaa4aa9-9441-444a-920c-e4b2a2db899e
topic_type:
- apiref
ms.openlocfilehash: c3c57074ae53e2e1d8d41aa04cb6eb6089db58b5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449440"
---
# <a name="imetadataassemblyimportgetassemblyprops-method"></a>Метод IMetaDataAssemblyImport::GetAssemblyProps
Возвращает набор свойств для сборки с указанной сигнатурой метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetAssemblyProps (  
    [in]  mdAssembly          mda,  
    [out] const void          **ppbPublicKey,   
    [out] ULONG               *pcbPublicKey,  
    [out] ULONG               *pulHashAlgId,  
    [out] LPWSTR              szName,  
    [in] ULONG                cchName,  
    [out] ULONG               *pchName,  
    [out] ASSEMBLYMETADATA    *pMetaData,  
    [out] DWORD               *pdwAssemblyFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `mda`  
 [in]. `mdAssembly` маркер метаданных, представляющий сборку, для которой необходимо получить свойства.  
  
 `ppbPublicKey`  
 заполняет Указатель на открытый ключ или маркер метаданных.  
  
 `pcbPublicKey`  
 заполняет Число байтов в возвращенном открытом ключе.  
  
 `pulHashAlgId`  
 заполняет Указатель на алгоритм, используемый для хэширования файлов в сборке.  
  
 `szName`  
 заполняет Простое имя сборки.  
  
 `cchName`  
 окне Размер `szName`в расширенных символах.  
  
 `pchName`  
 заполняет Число расширенных символов, фактически возвращаемых в `szName`.  
  
 `pMetaData`  
 заполняет Указатель на структуру ASSEMBLYMETADATA, содержащую метаданные сборки.  
  
 `pdwAssemblyFlags`  
 заполняет Флаги, описывающие метаданные, применяемые к сборке. Это значение представляет собой сочетание одного или нескольких значений [корассемблифлагс](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
