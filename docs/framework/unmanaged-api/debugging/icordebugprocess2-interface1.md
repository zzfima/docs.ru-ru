---
title: Интерфейс ICorDebugProcess2
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2
helpviewer_keywords:
- ICorDebugProcess2 interface [.NET Framework debugging]
ms.assetid: 73332138-5fea-441f-b893-61af87d45a42
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5519714ff2b4ee67d0e59001bf5b454cdc25d648
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69961084"
---
# <a name="icordebugprocess2-interface"></a>Интерфейс ICorDebugProcess2
Логическое расширение интерфейса ICorDebugProcess, представляющее процесс, выполняющий управляемый код.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод ClearUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-clearunmanagedbreakpoint-method.md)|Удаляет точку останова с указанным смещением, которое было задано предыдущим `ICorDebugProcess2::SetUnmanagedBreakpoint`вызовом метода.|  
|[Метод GetDesiredNGENCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getdesiredngencompilerflags-method.md)|Возвращает флаги, которые должны быть установлены в среде CLR для загрузки изображения в процесс, на который ссылается this `ICorDebugProcess2`.|  
|[Метод GetReferenceValueFromGCHandle](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getreferencevaluefromgchandle-method.md)|Возвращает указатель ссылки на указанный управляемый объект, который имеет обработчик сборки мусора.|  
|[Метод GetThreadForTaskID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getthreadfortaskid-method.md)|Возвращает поток, в котором выполняется задача с указанным идентификатором.|  
|[Метод GetVersion](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getversion-method.md)|Возвращает версию среды CLR, на основе которой выполняется отлаживаемый процесс.|  
|[Метод SetDesiredNGENCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setdesiredngencompilerflags-method.md)|Задает флаги, которые требуются для JIT-компилятора при загрузке изображения в отлаживаемый процесс.|  
|[Метод SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md)|Задает неуправляемую точку останова в указанном смещении машинного образа.|  
  
## <a name="remarks"></a>Примечания  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug. idl, CorDebug. h  
  
 **Библиотечная** Коргуидс. lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
