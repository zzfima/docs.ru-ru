---
title: "Интерфейс ICorDebugMDA"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugMDA
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugMDA
helpviewer_keywords: ICorDebugMDA interface [.NET Framework debugging]
ms.assetid: 8ecbb854-295c-4dd4-b9fc-01ebeac46e06
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 00a003ee060de59fe0eb8ce8f740a620d77a7c85
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmda-interface"></a>Интерфейс ICorDebugMDA
Представляет сообщение управляемого помощника по отладке (MDA).  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetDescription](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getdescription-method.md)|Возвращает строку, содержащую описание данный MDA.|  
|[Метод GetFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getflags-method.md)|Получает флаги, связанные с этим MDA.|  
|[Метод GetName](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getname-method.md)|Возвращает строку, содержащую имя данного MDA.|  
|[Метод GetOSThreadId](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getosthreadid-method.md)|Получает идентификатор потока операционной системы, на котором выполняется данный MDA.|  
|[Метод GetXML](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getxml-method.md)|Получает полный XML-поток, связанный с этим MDA.|  
  
## <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Диагностика ошибок посредством помощников по отладке управляемого кода](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
