---
title: Метод IMetaDataAssemblyEmit::DefineManifestResource
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineManifestResource
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineManifestResource
helpviewer_keywords:
- DefineManifestResource method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineManifestResource method [.NET Framework metadata]
ms.assetid: 27f6d295-0fe9-4cda-b77e-6e7d5c53df09
topic_type:
- apiref
ms.openlocfilehash: 83170815f4aa65988bb6a6394bd466a0ba376ebf
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432055"
---
# <a name="imetadataassemblyemitdefinemanifestresource-method"></a>Метод IMetaDataAssemblyEmit::DefineManifestResource
Создает структуру `ManifestResource`, содержащую метаданные для указанного ресурса манифеста, и возвращает связанный токен метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DefineManifestResource (  
    [in] LPCWSTR                szName,   
    [in] mdToken                tkImplementation,   
    [in] DWORD                  dwOffset,   
    [in] DWORD                  dwResourceFlags,  
    [out] mdManifestResource    *pmdmr  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `szName`  
 окне Имя ресурса.  
  
 `tkImplementation`  
 окне Токен метаданных типа `mdtFile` или `mdtAssemblyRef`, который сопоставляется с поставщиком ресурсов. Значение NULL указывает, что файл, в котором внедрены метаданные, является поставщиком ресурсов.  
  
 `dwOffset`  
 окне Смещение в начале ресурса в файле. Для ресурсов в отдельных файлах это значение всегда будет равно нулю. Если ресурс внедряется в PE-файл, это смещение большого двоичного объекта ресурса, которое начинается в расположении, указанном в файле заголовка COR. h.  
  
 `dwResourceFlags`  
 окне Побитовое сочетание значений флагов, задающих настройки свойств для определения ресурса.  
  
 `pmdmr`  
 заполняет Указатель на возвращаемый маркер метаданных.  
  
## <a name="remarks"></a>Примечания  
 Для каждого ресурса, реализованного в каждом файле сборки, необходимо определить одну `ManifestResource` структуру метаданных.  
  
## <a name="requirements"></a>Требования  
 **Платформа:** См. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
