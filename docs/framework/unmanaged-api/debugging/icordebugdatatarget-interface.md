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
ms.openlocfilehash: f9a87ae4381ec5bc0d8c416ef4ee4c13b04a862f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64606902"
---
# <a name="icordebugdatatarget-interface"></a>Интерфейс ICorDebugDataTarget
Предоставляет интерфейс обратного вызова, обеспечивающий доступ к конкретному целевому процессу.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md)|Сведения о платформе, включая архитектуру процессора и операционной системы, на котором выполняется целевой процесс.|  
|[Метод ReadVirtual](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-readvirtual-method.md)|Получает блок непрерывной памяти, начиная с указанного адреса и возвращает его в указанный буфер.|  
|[Метод GetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getthreadcontext-method.md)|Запрашивает текущий контекст потока для указанного потока.|  
  
## <a name="remarks"></a>Примечания  
 `ICorDebugDataTarget` и его методы имеют следующие характеристики:  
  
- Службы отладки вызывать методы на этом интерфейсе, для доступа к памяти и другие данные в целевом процессе.  
  
- Клиент отладчика должен реализовывать этот интерфейс, подходящие для конкретного целевого объекта (например, активный процесс или дамп памяти).  
  
- `ICorDebugDataTarget` Методы могут вызываться только из методов, реализованных в других `ICorDebug*` интерфейсов. Это гарантирует, что клиент отладчика имеет элемент управления, на каком потоке он вызывается и когда.  
  
- `ICorDebugDataTarget` Реализация должна всегда возвращать последние сведения о цели.  
  
 Целевой процесс следует останавливать и не изменяется при `ICorDebug*` интерфейсы (и, следовательно `ICorDebugDataTarget` методы) вызываются. Если цель — активного процесса и изменения своего состояния [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) метод должен вызываться снова, чтобы предоставить экземпляр ICorDebugProcess замены.  
  
> [!NOTE]
>  Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
