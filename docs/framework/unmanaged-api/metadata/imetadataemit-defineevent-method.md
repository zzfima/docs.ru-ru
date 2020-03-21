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
ms.openlocfilehash: a9598be850604f16ee8cc62187e1fed7ecf3a7e4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175854"
---
# <a name="imetadataemitdefineevent-method"></a>Метод IMetaDataEmit::DefineEvent
Создает определение события с указанной подписью метаданных и получает маркер к определению этого события.  
  
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
 (в) Токен для целевого класса или интерфейса. Это либо `mdTypeDef` знак, либо `mdTypeDefNil` маркер.  
  
 `szEvent`  
 [in] Имя события.  
  
 `dwEventFlags`  
 (в) Флаги событий.  
  
 `tkEventType`  
 (в) Токен для класса событий. `mdTypeDef`Это, a `mdTypeRef`, или `mdTokenNil` маркер.  
  
 `mdAddOn`  
 (в) Метод, используемый для подписки на событие, или нулевой.  
  
 `mdRemoveOn`  
 (в) Метод, используемый для отписаться от события или свести на нет.  
  
 `mdFire`  
 (в) Метод, используемый (производным классом) для поднятия события.  
  
 `rmdOtherMethods[]`  
 (в) Массив токенов для других методов, связанных с событием. Массив завершается маркером. `mdMethodDefNil`  
  
 `pmdEvent`  
 (ваут) Токен метаданных, назначенный событию.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** Используется в качестве ресурса в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
