---
title: "Метод IMetaDataEmit::DefineEvent"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineEvent
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineEvent
helpviewer_keywords:
- IMetaDataEmit::DefineEvent method [.NET Framework metadata]
- DefineEvent method [.NET Framework metadata]
ms.assetid: cf064bac-9a9f-41c5-9e1d-108ff7af3afe
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8f27c0a01dd795cfcc5399c4115cd6d905629fd7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefineevent-method"></a>Метод IMetaDataEmit::DefineEvent
Создает определение события с заданной подписью метаданных и получает маркер для этого определения событий.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT DefineEvent (   
    [in]  mdTypeDef    td,   
    [in]  LPCWSTR      szEvent,   
    [in]  DWORD        dwEventFlags,   
    [in]  mdToken      tkEventType,   
    [in]  mdMethodDef  mdAddOn,   
    [in]  mdMethodDef  mdRemoveOn,   
    [in]  mdMethodDef  mdFire,   
    [in]  mdMethodDef  rmdOtherMethods[],   
    [out] mdEvent      *pmdEvent   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `td`  
 [in] Токен для целевого класса или интерфейса. Это может быть вызвано `mdTypeDef` или `mdTypeDefNil` токена.  
  
 `szEvent`  
 [in] Имя события.  
  
 `dwEventFlags`  
 [in] Флаги событий.  
  
 `tkEventType`  
 [in] Токен для класса событий. Это `mdTypeDef`, `mdTypeRef`, или `mdTokenNil` токена.  
  
 `mdAddOn`  
 [in] Метод, используемый для подписки на событие, или значение null.  
  
 `mdRemoveOn`  
 [in] Метод, используемый для отмены подписки на событие, или значение null.  
  
 `mdFire`  
 [in] Метод, используемый (производным классом), чтобы вызвать это событие.  
  
 `rmdOtherMethods[]`  
 [in] Массив маркеров для других методов, связанный с событием. Заканчивается массива `mdMethodDefNil` токена.  
  
 `pmdEvent`  
 [out] Токен метаданных, присвоенный событию.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** используется как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
