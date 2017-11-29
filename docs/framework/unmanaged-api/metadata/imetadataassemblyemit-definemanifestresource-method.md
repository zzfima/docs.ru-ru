---
title: "Метод IMetaDataAssemblyEmit::DefineManifestResource"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyEmit.DefineManifestResource
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyEmit::DefineManifestResource
helpviewer_keywords:
- DefineManifestResource method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineManifestResource method [.NET Framework metadata]
ms.assetid: 27f6d295-0fe9-4cda-b77e-6e7d5c53df09
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 516099f0735e83982fcbab62936bb398c4f7b02d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyemitdefinemanifestresource-method"></a>Метод IMetaDataAssemblyEmit::DefineManifestResource
Создает структуру `ManifestResource`, содержащую метаданные для указанного ресурса манифеста, и возвращает связанный токен метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT DefineManifestResource (  
    [in] LPCWSTR                szName,   
    [in] mdToken                tkImplementation,   
    [in] DWORD                  dwOffset,   
    [in] DWORD                  dwResourceFlags,  
    [out] mdManifestResource    *pmdmr  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `szName`  
 [in] Имя ресурса.  
  
 `tkImplementation`  
 [in] Токен метаданных типа `mdtFile` или `mdtAssemblyRef` , сопоставляемый поставщика ресурсов. Значение NULL указывает на то, что файл внедренные метаданные поставщика ресурсов.  
  
 `dwOffset`  
 [in] Смещение в начало ресурса в файле. Для ресурсов в отдельных файлах это всегда будет равно нулю. Если ресурс внедрен в PE-файл (переносимый исполняемый файл), это смещение большого двоичного ОБЪЕКТА, который начинается в расположении, указанном в файле заголовка cor.h ресурса.  
  
 `dwResourceFlags`  
 [in] Побитовая комбинация значений флага, которые определяют параметры свойств для определения ресурса.  
  
 `pmdmr`  
 [out] Указатель на токен возвращенные метаданные.  
  
## <a name="remarks"></a>Примечания  
 Один `ManifestResource` структуру метаданных должны быть определены для каждого ресурса, который реализован в каждом из файлов сборки.  
  
## <a name="requirements"></a>Требования  
 **Платформа:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** используется как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
