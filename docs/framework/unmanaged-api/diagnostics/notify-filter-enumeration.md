---
title: Перечисление NOTIFY_FILTER
ms.date: 03/30/2017
api_name:
- NOTIFY_FILTER
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- NOTIFY_FILTER
helpviewer_keywords:
- NOTIFY_FILTER enumeration [.NET Framework debugging]
ms.assetid: 4789d08f-8683-45d3-ac30-73d48c61e470
topic_type:
- apiref
ms.openlocfilehash: 92e40dbe8892d48dba1c54d9cd16faa409440b24
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438116"
---
# <a name="notify_filter-enumeration"></a>Перечисление NOTIFY_FILTER
Определяет обратные вызовы для функций отладчика. Дополнительные сведения см. в описании метода [INotifySource2:: сетнотифифилтер](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
enum tagNOTIFY_FILTER  
{  
    NOTIFY_FILTER_ONSYNCCALLOUT    = 0x1,  
    NOTIFY_FILTER_ONSYNCCALLENTER  = 0x2,  
    NOTIFY_FILTER_ONSYNCCALLEXIT   = 0x4,  
    NOTIFY_FILTER_ONSYNCCALLRETURN = 0x8,  
    NOTIFY_FILTER_ALLSYNC = NOTIFY_FILTER_ONSYNCCALLOUT | NOTIFY_FILTER_ONSYNCCALLENTER | NOTIFY_FILTER_ONSYNCCALLEXIT | NOTIFY_FILTER_ONSYNCCALLRETURN,  
    NOTIFY_FILTER_ALL              = 0xffffffff,  
    NOTIFY_FILTER_NONE             = 0  
};  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`NOTIFY_FILTER_ONSYNCCALLOUT`|Указывает, что должен быть вызван метод [INotifySink2:: OnSyncCallOut](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallout-method.md) .|  
|`NOTIFY_FILTER_ONSYNCCALLENTER`|Указывает, что должен быть вызван метод [INotifySink2:: OnSyncCallEnter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallenter-method.md) .|  
|`NOTIFY_FILTER_ONSYNCCALLEXIT`|Указывает, что должен быть вызван метод [INotifySink2:: онсинккаллексит](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallexit-method.md) .|  
|`NOTIFY_FILTER_ONSYNCCALLRETURN`|Указывает, что должен быть вызван метод [INotifySink2:: онсинккаллретурн](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallreturn-method.md) .|  
|`NOTIFY_FILTER_ALLSYNC`|Указывает, что должны быть вызваны все методы [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) .|  
|`NOTIFY_FILTER_ALL`|Активирует все существующие и будущие уведомления.|  
|`NOTIFY_FILTER_NONE`|Указывает, что методы уведомления вызывать не нужно.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** ProtocolNotify2. idl  
  
## <a name="see-also"></a>См. также:

- [Перечисления хранилища символов диагностики](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
