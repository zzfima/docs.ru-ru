---
title: Интерфейс ICLRDataTarget
ms.date: 03/30/2017
api_name:
- ICLRDataTarget
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget
helpviewer_keywords:
- ICLRDataTarget interface [.NET Framework debugging]
ms.assetid: e2f05155-9bef-4e11-b703-7f05890665ca
topic_type:
- apiref
ms.openlocfilehash: 51b246e45b8bbdf809f5e90ac2bc29ca724751fc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73113495"
---
# <a name="iclrdatatarget-interface"></a>Интерфейс ICLRDataTarget
Предоставляет методы для взаимодействия с целевым элементом общеязыковой среды выполнения (CLR).  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetCurrentThreadID](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getcurrentthreadid-method.md)|Возвращает идентификатор операционной системы для текущего потока.|  
|[Метод GetImageBase](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getimagebase-method.md)|Возвращает адрес базовой памяти для указанного образа.|  
|[Метод GetMachineType](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getmachinetype-method.md)|Возвращает идентификатор для типа набора инструкций, используемого целевым процессом.|  
|[Метод GetPointerSize](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getpointersize-method.md)|Возвращает размер (в байтах) указателя на текущий целевой объект.|  
|[Метод GetThreadContext](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getthreadcontext-method.md)|Возвращает указатель на контекст потока с указанным идентификатором.|  
|[Метод GetTLSValue](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-gettlsvalue-method.md)|Возвращает значение в локальном хранилище потока (TLS) по указанному индексу для указанного потока.|  
|[Метод ReadVirtual](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-readvirtual-method.md)|Считывает данные из указанного адреса виртуальной памяти в указанный буфер.|  
|[Метод Request](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-request-method.md)|Вызывается службами доступа к данным среды CLR для запроса операции, как определено в реализации.|  
|[Метод SetThreadContext](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-setthreadcontext-method.md)|Задает текущий контекст указанного потока в целевом процессе.|  
|[Метод SetTLSValue](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-settlsvalue-method.md)|Задает значение в локальном хранилище потока (TLS) указанного потока в целевом процессе.|  
|[Метод WriteVirtual](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-writevirtual-method.md)|Записывает данные из указанного буфера в указанный адрес виртуальной памяти.|  
  
## <a name="remarks"></a>Заметки  
 Клиент API (то есть отладчик) должен реализовать этот интерфейс в соответствии с конкретным целевым элементом. Например, реализация активного процесса будет отличаться от реализации дампа памяти.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Клрдата. idl, Клрдата. h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
