---
title: Метод INotifySource2::SetNotifyFilter
ms.date: 03/30/2017
api_name:
- INotifySource2.SetNotifyFilter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySource2::SetNotifyFilter
helpviewer_keywords:
- INotifySource2::SetNotifyFilter method [.NET Framework debugging]
- SetNotifyFilter method [.NET Framework debugging]
ms.assetid: 6351fc92-b126-4af6-9bf3-0a8ce92845fc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: abe1c8881330ebba5f7b68452cf3db0666ac20c3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736234"
---
# <a name="inotifysource2setnotifyfilter-method"></a>Метод INotifySource2::SetNotifyFilter
Назначает фильтр уведомлений для использования с этим источником.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetNotifyFilter  
(  
    [in]  NOTIFY_FILTER   in_NotifyFilter,  
    [in]  USER_THREAD*    in_pUserThreadFilter  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `in_NotifyFilter`  
 [in] Побитовое сочетание [NOTIFY_FILTER](../../../../docs/framework/unmanaged-api/diagnostics/notify-filter-enumeration.md) значений перечисления, определяющих обратные вызовы для API отладки.  
  
 `in_pUserThreadFilter`  
 [in] Указатель на [USER_THREAD](../../../../docs/framework/unmanaged-api/diagnostics/user-thread-structure.md) структура, определяющая потоков для API отладки.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если метод выполнен успешно.  
  
## <a name="requirements"></a>Требования  
 **Заголовок.** ProtocolNotify2.idl  
  
## <a name="see-also"></a>См. также

- [Интерфейс INotifySource2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [Интерфейс INotifyConnection2](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
- [Интерфейс INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
