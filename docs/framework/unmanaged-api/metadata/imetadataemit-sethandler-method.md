---
title: Метод IMetaDataEmit::SetHandler
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetHandler
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetHandler
helpviewer_keywords:
- IMetaDataEmit::SetHandler method [.NET Framework metadata]
- SetHandler method [.NET Framework metadata]
ms.assetid: c6c1aaaf-e2cd-407c-b73e-fbe6ffd83bb3
topic_type:
- apiref
ms.openlocfilehash: 6737275fb77e6f177832eb1d96214c37942bcd22
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442152"
---
# <a name="imetadataemitsethandler-method"></a>Метод IMetaDataEmit::SetHandler
Задает метод, на который ссылается указанный указатель `IUnknown` в качестве обратного вызова уведомления для повторного сопоставления токенов.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetHandler (   
    [in]  IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pUnk`  
 окне Регистрируемый обработчик.  
  
## <a name="remarks"></a>Заметки  
 Обработчик метаданных отправляет уведомление с помощью метода, предоставляемого `SetHandler`, компиляторам, которые не создают записи оптимизированным образом и которым требуется оптимизировать сохраненные записи.  
  
 Если метод обратного вызова не предоставляется через `SetHandler`, оптимизация не будет выполняться при сохранении, за исключением случаев, когда несколько областей импорта были объединены с помощью `IMapToken` для каждой области слияния.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
