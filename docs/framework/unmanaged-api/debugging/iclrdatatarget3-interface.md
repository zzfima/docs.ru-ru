---
title: Интерфейс ICLRDataTarget3
ms.date: 03/30/2017
api_name:
- ICLRDataTarget3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: d2711bdf-64b3-404c-a0c3-01ba4907f703
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 54d6535e2b2c4761eb3c67a990c62f2c311cf133
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="iclrdatatarget3-interface"></a>Интерфейс ICLRDataTarget3
Подкласс [ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md) , предоставляющий доступ к информации об исключении.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetExceptionRecord](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionrecord-method.md)|Вызывается службами доступа к данным среды CLR для извлечения записи исключения, связанной с целевым процессом.|  
|[Метод GetExceptionContextRecord](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptioncontextrecord-method.md)|Вызывается службами доступа к данным среды CLR для извлечения записи контекста, связанной с целевым процессом.|  
|[Метод GetExceptionThreadID](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionthreadid-method.md)|Вызывается службами доступа к данным среды CLR для получения идентификатора потока, вызвавшего исключение.|  
  
## <a name="remarks"></a>Примечания  
 Клиент API (то есть отладчик) должен реализовывать этот интерфейс для определенного целевого процесса по мере необходимости. Например, реализация активного процесса будет отличаться от реализации дампа памяти. Целевой объект может не поддерживать изменение областей его памяти.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** ClrData.idl, ClrData.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)  
 [Интерфейс ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)  
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
