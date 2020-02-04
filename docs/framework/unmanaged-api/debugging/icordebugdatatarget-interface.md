---
title: Интерфейс ICorDebugDataTarget
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget
helpviewer_keywords:
- ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: df5f05be-bed7-4f3c-bc89-dbb435d79a0b
topic_type:
- apiref
ms.openlocfilehash: 9029d53872108bc1953fd22c584b6e01a6f3c7ab
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788868"
---
# <a name="icordebugdatatarget-interface"></a>Интерфейс ICorDebugDataTarget
Предоставляет интерфейс обратного вызова, обеспечивающий доступ к конкретному целевому процессу.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetPlatform](icordebugdatatarget-getplatform-method.md)|Предоставляет сведения о платформе, включая архитектуру процессора и операционную систему, на которых выполняется целевой процесс.|  
|[Метод ReadVirtual](icordebugdatatarget-readvirtual-method.md)|Возвращает блок непрерывной памяти, начиная с указанного адреса, и возвращает его в указанном буфере.|  
|[Метод GetThreadContext](icordebugdatatarget-getthreadcontext-method.md)|Запрашивает текущий контекст потока для указанного потока.|  
  
## <a name="remarks"></a>Заметки  
 `ICorDebugDataTarget` и его методы имеют следующие характеристики.  
  
- Службы отладки вызывают методы этого интерфейса для доступа к памяти и другим данным в целевом процессе.  
  
- Клиент отладчика должен реализовать этот интерфейс в соответствии с конкретным целевым объектом (например, в реальном процессе или дампе памяти).  
  
- `ICorDebugDataTarget` методы могут вызываться только из методов, реализованных в других интерфейсах `ICorDebug*`. Это гарантирует, что клиент отладчика будет контролировать, в каком потоке он вызывается, и когда.  
  
- `ICorDebugDataTarget`ная реализация всегда должна возвращать актуальные сведения о целевом объекте.  
  
 Целевой процесс должен быть остановлен и не изменяется каким-либо образом при `ICorDebug*` интерфейсах (и, следовательно, `ICorDebugDataTarget` методах). Если целевой объект является динамическим процессом и изменяется его состояние, метод [ICLRDebugging:: OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) необходимо вызвать снова, чтобы предоставить экземпляр ICorDebugProcess для замены.  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
