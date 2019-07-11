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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 781953fe5bf209f195ef4887dff45e1902741f0c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775317"
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
 [in] Имя ресурса.  
  
 `tkImplementation`  
 [in] Маркер метаданных типа `mdtFile` или `mdtAssemblyRef` , сопоставляемый поставщика ресурсов. Значение NULL указывает, что файл, в который внедрены метаданных — поставщик ресурсов.  
  
 `dwOffset`  
 [in] Смещение в начало ресурса в файле. Для ресурсов в отдельных файлах это всегда равно нулю. Если ресурс встроен в файле PE (переносимый исполняемый файл), это смещение большого двоичного ОБЪЕКТА, который начинается в расположении, указанном в файле заголовка cor.h ресурса.  
  
 `dwResourceFlags`  
 [in] Побитовое сочетание значения флага, задайте значения свойств для определения ресурсов.  
  
 `pmdmr`  
 [out] Указатель на токен возвращенные метаданные.  
  
## <a name="remarks"></a>Примечания  
 Один `ManifestResource` структура метаданных должны быть определены для каждого ресурса, который реализуется в каждом из файлов сборки.  
  
## <a name="requirements"></a>Требования  
 **Платформа:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Используется как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
