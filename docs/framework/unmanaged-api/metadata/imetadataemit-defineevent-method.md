---
title: Метод IMetaDataEmit::DefineEvent
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineEvent
helpviewer_keywords:
- IMetaDataEmit::DefineEvent method [.NET Framework metadata]
- DefineEvent method [.NET Framework metadata]
ms.assetid: cf064bac-9a9f-41c5-9e1d-108ff7af3afe
topic_type:
- apiref
ms.openlocfilehash: 6966d0ad2fefd8401b19d8e8dcf7776799a066b2
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432563"
---
# <a name="imetadataemitdefineevent-method"></a>Метод IMetaDataEmit::DefineEvent
Создает определение для события с указанной сигнатурой метаданных и получает маркер для этого определения события.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
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
  
## <a name="parameters"></a>Параметры  
 `td`  
 окне Токен для целевого класса или интерфейса. Это либо маркер `mdTypeDef`, либо `mdTypeDefNil`.  
  
 `szEvent`  
 окне Имя события.  
  
 `dwEventFlags`  
 окне Флаги событий.  
  
 `tkEventType`  
 окне Токен для класса событий. Это `mdTypeDef`, `mdTypeRef`или токен `mdTokenNil`.  
  
 `mdAddOn`  
 окне Метод, используемый для подписки на событие, или значение null.  
  
 `mdRemoveOn`  
 окне Метод, используемый для отмены подписки на событие или значение null.  
  
 `mdFire`  
 окне Метод, используемый (производным классом) для вызова события.  
  
 `rmdOtherMethods[]`  
 окне Массив токенов для других методов, связанных с событием. Массив завершается маркером `mdMethodDefNil`.  
  
 `pmdEvent`  
 заполняет Маркер метаданных, назначенный событию.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
