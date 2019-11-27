---
title: Метод IBindingDisplay::InitializeForProcess
ms.date: 03/30/2017
api_name:
- IBindingDisplay.InitializeForProcess
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IBindingDisplay::InitializeForProcess
helpviewer_keywords:
- IBindingDisplay::InitializeForProcess method [.NET Framework debugging]
- InitializeForProcess method [.NET Framework debugging]
ms.assetid: 59417acb-4e59-46ad-acfe-d827e6ab6078
topic_type:
- apiref
ms.openlocfilehash: bb796a12868cc3e44394ab493f7838dc48ab4dc5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448494"
---
# <a name="ibindingdisplayinitializeforprocess-method"></a>Метод IBindingDisplay::InitializeForProcess
Инициализирует объект [ибиндингдисплай](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT InitializeForProcess (  
    [in] ULONG32   pid  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pid`  
 окне Идентификатор процесса.  
  
## <a name="remarks"></a>Примечания  
 Отладчик вызывает метод `InitializeForProcess` во время создания, чтобы инициализировать отображение привязки. `InitializeForProcess` должны вызываться во время создания до вызова любого другого метода в `IBindingDisplay`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Биндингдисплай. h  
  
 **Библиотека:** Биндингдисплай. idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)
