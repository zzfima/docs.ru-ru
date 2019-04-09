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
ms.openlocfilehash: cea8f6827d3e361b3f6498e6612d8b11a2357285
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59098673"
---
# <a name="icordebugmda-interface"></a>Интерфейс ICorDebugMDA
Представляет сообщение управляемого помощника по отладке (MDA).  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetDescription](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getdescription-method.md)|Получает строку, содержащую описание данный MDA.|  
|[Метод GetFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getflags-method.md)|Получает флаги, связанные с данный MDA.|  
|[Метод GetName](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getname-method.md)|Получает строку, содержащую имя данный MDA.|  
|[Метод GetOSThreadId](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getosthreadid-method.md)|Получает идентификатор потока операционной системы, на котором выполняется данный MDA.|  
|[Метод GetXML](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getxml-method.md)|Получает полный XML-потока, связанного с данный MDA.|  
  
## <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Диагностика ошибок посредством управляемых помощников по отладке](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
