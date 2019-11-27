---
title: Метод IMetaDataAssemblyImport::GetManifestResourceProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetManifestResourceProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetManifestResourceProps
helpviewer_keywords:
- GetManifestResourceProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetManifestResourceProps method [.NET Framework metadata]
ms.assetid: 00be4789-ac63-4397-b2ec-1629a5c5a585
topic_type:
- apiref
ms.openlocfilehash: c1792ed0f15f8cfb62567593c9694453650f0bb9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436315"
---
# <a name="imetadataassemblyimportgetmanifestresourceprops-method"></a>Метод IMetaDataAssemblyImport::GetManifestResourceProps
Возвращает набор свойств ресурса манифеста с указанной сигнатурой метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetManifestResourceProps (  
    [in]  mdManifestResource   mdmr,   
    [out] LPWSTR               szName,   
    [in]  ULONG                cchName,   
    [out] ULONG                *pchName,   
    [out] mdToken              *ptkImplementation,   
    [out] DWORD                *pdwOffset,   
    [out] DWORD                *pdwResourceFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `mdmr`  
 окне Токен `mdManifestResource`, представляющий ресурс, для которого необходимо получить свойства.  
  
 `szName`  
 заполняет Имя ресурса.  
  
 `cchName`  
 окне Размер `szName`в расширенных символах.  
  
 `pchName`  
 заполняет Указатель на число расширенных символов, фактически возвращаемых в `szName`.  
  
 `ptkImplementation`  
 заполняет Указатель на маркер `mdFile` или маркер `mdAssemblyRef`, представляющий файл или сборку соответственно, который содержит ресурс.  
  
 `pdwOffset`  
 заполняет Указатель на значение, указывающее смещение к началу ресурса в файле.  
  
 `pdwResourceFlags`  
 заполняет Указатель на флаги, описывающие метаданные, применяемые к ресурсу. Значение Flags является сочетанием одного или нескольких значений [корманифестресаурцефлагс](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
