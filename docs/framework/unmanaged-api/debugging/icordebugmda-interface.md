---
title: Интерфейс ICorDebugMDA
ms.date: 03/30/2017
api_name:
- ICorDebugMDA
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA
helpviewer_keywords:
- ICorDebugMDA interface [.NET Framework debugging]
ms.assetid: 8ecbb854-295c-4dd4-b9fc-01ebeac46e06
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a662185bb84e9a66573b43b26ffcd256ecb943f5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69909850"
---
# <a name="icordebugmda-interface"></a>Интерфейс ICorDebugMDA
Представляет сообщение управляемого помощника по отладке (MDA).  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetDescription](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getdescription-method.md)|Возвращает строку, содержащую описание этого MDA.|  
|[Метод GetFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getflags-method.md)|Возвращает флаги, связанные с этим MDA.|  
|[Метод GetName](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getname-method.md)|Возвращает строку, содержащую имя этого MDA.|  
|[Метод GetOSThreadId](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getosthreadid-method.md)|Возвращает идентификатор потока операционной системы, в котором выполняется этот MDA.|  
|[Метод GetXML](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getxml-method.md)|Возвращает полный XML-поток, связанный с этим MDA.|  
  
## <a name="remarks"></a>Примечания  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug. idl, CorDebug. h  
  
 **Библиотечная** Коргуидс. lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Диагностика ошибок посредством помощников по отладке управляемого кода](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
