---
title: Метод IMetaDataAssemblyImport::GetExportedTypeProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetExportedTypeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetExportedTypeProps
helpviewer_keywords:
- GetExportedTypeProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetExportedTypeProps method [.NET Framework metadata]
ms.assetid: 25ca7623-5a55-4f09-b44a-36b03d142278
topic_type:
- apiref
ms.openlocfilehash: 82302124828a2dab73b445128d7d847e112edd36
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448220"
---
# <a name="imetadataassemblyimportgetexportedtypeprops-method"></a>Метод IMetaDataAssemblyImport::GetExportedTypeProps
Возвращает набор свойств экспортированного типа с указанной сигнатурой метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetExportedTypeProps (  
    [in]  mdExportedType    mdct,   
    [out] LPWSTR            szName,   
    [in]  ULONG             cchName,   
    [out] ULONG             *pchName,   
    [out] mdToken           *ptkImplementation,   
    [out] mdTypeDef         *ptkTypeDef,   
    [out] DWORD             *pdwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `mdct`  
 окне Токен метаданных `mdExportedType`, представляющий экспортированный тип.  
  
 `szName`  
 заполняет Имя экспортированного типа.  
  
 `cchName`  
 окне Размер в расширенных символах `szName`.  
  
 `pchName`  
 заполняет Число расширенных символов, фактически возвращаемых в `szName`  
  
 `ptkImplementation`  
 заполняет `mdFile`, `mdAssemblyRef`или `mdExportedType` маркер метаданных, который содержит или разрешает доступ к свойствам экспортируемого типа.  
  
 `ptkTypeDef`  
 заполняет Указатель на маркер `mdTypeDef`, представляющий тип в файле.  
  
 `pdwExportedTypeFlags`  
 заполняет Указатель на флаги, описывающие метаданные, применяемые к экспортируемому типу. Значение Flags может быть одним или несколькими [кортипеаттр](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) значениями.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
