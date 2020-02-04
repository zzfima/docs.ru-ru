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
ms.openlocfilehash: 2b5c99e40aabdbc654bdc612729b2756e3ef5bb4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793718"
---
# <a name="iclrdatatarget-interface"></a>Интерфейс ICLRDataTarget
Предоставляет методы для взаимодействия с целевым элементом общеязыковой среды выполнения (CLR).  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetCurrentThreadID](iclrdatatarget-getcurrentthreadid-method.md)|Возвращает идентификатор операционной системы для текущего потока.|  
|[Метод GetImageBase](iclrdatatarget-getimagebase-method.md)|Возвращает адрес базовой памяти для указанного образа.|  
|[Метод GetMachineType](iclrdatatarget-getmachinetype-method.md)|Возвращает идентификатор для типа набора инструкций, используемого целевым процессом.|  
|[Метод GetPointerSize](iclrdatatarget-getpointersize-method.md)|Возвращает размер (в байтах) указателя на текущий целевой объект.|  
|[Метод GetThreadContext](iclrdatatarget-getthreadcontext-method.md)|Возвращает указатель на контекст потока с указанным идентификатором.|  
|[Метод GetTLSValue](iclrdatatarget-gettlsvalue-method.md)|Возвращает значение в локальном хранилище потока (TLS) по указанному индексу для указанного потока.|  
|[Метод ReadVirtual](iclrdatatarget-readvirtual-method.md)|Считывает данные из указанного адреса виртуальной памяти в указанный буфер.|  
|[Метод Request](iclrdatatarget-request-method.md)|Вызывается службами доступа к данным среды CLR для запроса операции, как определено в реализации.|  
|[Метод SetThreadContext](iclrdatatarget-setthreadcontext-method.md)|Задает текущий контекст указанного потока в целевом процессе.|  
|[Метод SetTLSValue](iclrdatatarget-settlsvalue-method.md)|Задает значение в локальном хранилище потока (TLS) указанного потока в целевом процессе.|  
|[Метод WriteVirtual](iclrdatatarget-writevirtual-method.md)|Записывает данные из указанного буфера в указанный адрес виртуальной памяти.|  
  
## <a name="remarks"></a>Заметки  
 Клиент API (то есть отладчик) должен реализовать этот интерфейс в соответствии с конкретным целевым элементом. Например, реализация активного процесса будет отличаться от реализации дампа памяти.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Клрдата. idl, Клрдата. h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICLRDataTarget2](iclrdatatarget2-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
