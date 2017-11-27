---
title: "Интерфейс ICLRDataTarget"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataTarget
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataTarget
helpviewer_keywords: ICLRDataTarget interface [.NET Framework debugging]
ms.assetid: e2f05155-9bef-4e11-b703-7f05890665ca
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6a40276b28f3d20428f0d7eb0556a762fdb56801
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdatatarget-interface"></a>Интерфейс ICLRDataTarget
Предоставляет методы для взаимодействия с целевым элементом среды common language runtime (CLR).  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetCurrentThreadID](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getcurrentthreadid-method.md)|Получает идентификатор операционной системы для текущего потока.|  
|[Метод GetImageBase](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getimagebase-method.md)|Получает базовый адрес памяти для указанного образа.|  
|[Метод GetMachineType](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getmachinetype-method.md)|Получает идентификатор для типа набора инструкций, целевым процессом.|  
|[Метод GetPointerSize](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getpointersize-method.md)|Возвращает размер в байтах, указателя на текущий целевой объект.|  
|[Метод GetThreadContext](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getthreadcontext-method.md)|Возвращает указатель на контекст потока с указанным идентификатором.|  
|[Метод GetTLSValue](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-gettlsvalue-method.md)|Возвращает значение в локальном хранилище потока (TLS) с указанным индексом для заданного потока.|  
|[Метод ReadVirtual](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-readvirtual-method.md)|Считывает данные из указанного адреса виртуальной памяти в указанный буфер.|  
|[Метод запроса](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-request-method.md)|Вызывается службами доступа к данным среды выполнения (CLR) для запроса операции, как определяются реализацией.|  
|[Метод SetThreadContext](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-setthreadcontext-method.md)|Задает текущий контекст заданного потока в целевом процессе.|  
|[Метод SetTLSValue](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-settlsvalue-method.md)|Задает значение в локальном хранилище потока (TLS) заданного потока в целевом процессе.|  
|[Метод WriteVirtual](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-writevirtual-method.md)|Записывает данные из указанного буфера указанного адреса виртуальной памяти.|  
  
## <a name="remarks"></a>Примечания  
 Клиент API (то есть отладчик) должен реализовывать этот интерфейс, по мере необходимости для определенного целевого элемента. Например, реализация активного процесса будет отличаться от реализации дампа памяти.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** ClrData.idl, ClrData.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)  
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
