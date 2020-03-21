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
ms.openlocfilehash: 5aa5d78faa8ca9261594e2a649b11088e1d78ee7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177860"
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
 (в) Токен метаданных типа `mdtFile` `mdtAssemblyRef` или карты поставщика ресурсов. Значение NULL указывает на то, что файл, в который встроены метаданные, является поставщиком ресурсов.  
  
 `dwOffset`  
 (в) Смещение до начала ресурса в файле. Для ресурсов в автономных файлах этот вопрос всегда будет равен нулю. Если ресурс встроен в файл PE (портативный исполняемый) файл, это смещение ресурса BLOB, которое начинается в месте, указанном в файле заголовка cor.h.  
  
 `dwResourceFlags`  
 (в) Битовая комбинация значений флага, определяющих параметры свойств для определения ресурса.  
  
 `pmdmr`  
 (ваут) Указатель на токен возвращенных метаданных.  
  
## <a name="remarks"></a>Remarks  
 Для `ManifestResource` каждого ресурса, реализованного в файлах сборки, должна быть определена одна структура метаданных.  
  
## <a name="requirements"></a>Требования  
 **Платформа:** Смотрите [системные требования](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
