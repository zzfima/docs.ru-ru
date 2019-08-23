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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c6a8ee1bcc65e640ef871e57acdeef21acd7896
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69930823"
---
# <a name="icordebugdatatarget-interface"></a>Интерфейс ICorDebugDataTarget
Предоставляет интерфейс обратного вызова, обеспечивающий доступ к конкретному целевому процессу.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md)|Предоставляет сведения о платформе, включая архитектуру процессора и операционную систему, на которых выполняется целевой процесс.|  
|[Метод ReadVirtual](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-readvirtual-method.md)|Возвращает блок непрерывной памяти, начиная с указанного адреса, и возвращает его в указанном буфере.|  
|[Метод GetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getthreadcontext-method.md)|Запрашивает текущий контекст потока для указанного потока.|  
  
## <a name="remarks"></a>Примечания  
 `ICorDebugDataTarget`и его методы имеют следующие характеристики.  
  
- Службы отладки вызывают методы этого интерфейса для доступа к памяти и другим данным в целевом процессе.  
  
- Клиент отладчика должен реализовать этот интерфейс в соответствии с конкретным целевым объектом (например, в реальном процессе или дампе памяти).  
  
- Методы могут вызываться только в методах, реализованных в других `ICorDebug*` интерфейсах. `ICorDebugDataTarget` Это гарантирует, что клиент отладчика будет контролировать, в каком потоке он вызывается, и когда.  
  
- `ICorDebugDataTarget` Реализация всегда должна возвращать актуальные сведения о целевом объекте.  
  
 Целевой процесс должен быть остановлен и не изменяется каким-либо образом при `ICorDebug*` вызове интерфейсов `ICorDebugDataTarget` (и, следовательно, методов). Если целевой объект является динамическим процессом и изменяется его состояние, метод [ICLRDebugging:: OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) необходимо вызвать снова, чтобы предоставить экземпляр ICorDebugProcess для замены.  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug. idl, CorDebug. h  
  
 **Библиотечная** Коргуидс. lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
