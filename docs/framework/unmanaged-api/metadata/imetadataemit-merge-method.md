---
title: "Метод IMetaDataEmit::Merge"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.Merge
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::Merge
helpviewer_keywords:
- IMetaDataEmit::Merge method [.NET Framework metadata]
- Merge method [.NET Framework metadata]
ms.assetid: 7596220c-f699-4b6c-8ae7-c83220610650
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 42ebc188dfecde068ef8e2979970118fee91ec4b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitmerge-method"></a>Метод IMetaDataEmit::Merge
Добавляет заданную импортируемую область в список объединяемых областей.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT Merge (   
    [in]  IMetaDataImport  *pImport,   
    [in]  IMapToken        *pHostMapToken,   
    [in]  IUnknown         *pHandler   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pImport`  
 [in] Указатель на [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) объект, определяющий область, импортированных для слияния.  
  
 `pIMap`  
 [in] Указатель на [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) , указывающий повторного сопоставления маркеров.  
  
 `pHandleer`  
 [in] Указатель на <!--<<!--zzxref:IUnknown --> `IUnknown` >-->  `IUnknown` , указывающий ошибки.  
  
## <a name="remarks"></a>Примечания  
 Вызовите [IMetaDataEmit::MergeEnd](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md) для запуска средства слияния метаданных в одной области.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** используется как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [IMetaDataEmit-интерфейс](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
