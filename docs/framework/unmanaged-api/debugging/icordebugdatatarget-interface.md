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
ms.openlocfilehash: 972c650e0fb3b42e943838b72faf2658f65543ae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412907"
---
# <a name="icordebugdatatarget-interface"></a>Интерфейс ICorDebugDataTarget
Предоставляет интерфейс обратного вызова, обеспечивающий доступ к конкретному целевому процессу.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md)|Предоставляет сведения о платформе, включая архитектуру процессора и операционной системы, на котором выполняется целевой процесс.|  
|[Метод ReadVirtual](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-readvirtual-method.md)|Получает блок непрерывной памяти, начиная с указанного адреса и возвращает его в указанный буфер.|  
|[Метод GetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getthreadcontext-method.md)|Запрашивает текущий контекст потока для указанного потока.|  
  
## <a name="remarks"></a>Примечания  
 `ICorDebugDataTarget` и его методы имеют следующие характеристики:  
  
-   Службы отладки вызывают методы этого интерфейса для доступа к памяти и другими данными в целевом процессе.  
  
-   Клиент отладчика должен реализовывать этот интерфейс, в зависимости от конкретного целевого объекта (например, активный процесс или дамп памяти).  
  
-   `ICorDebugDataTarget` Методы могут вызываться только из методов, реализованных в других `ICorDebug*` интерфейсов. Это гарантирует, что клиент отладчика управляет для потока, в который он вызывается и когда.  
  
-   `ICorDebugDataTarget` Реализация должна всегда возвращать актуальные сведения о цели.  
  
 Целевой процесс следует останавливать и не изменяется во всех отношениях `ICorDebug*` интерфейсы (и, следовательно, `ICorDebugDataTarget` методы) вызываются. Если целью является активного процесса и его изменения состояния [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) метод должен вызываться снова, чтобы предоставить экземпляр ICorDebugProcess замены.  
  
> [!NOTE]
>  Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
