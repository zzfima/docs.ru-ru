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
ms.openlocfilehash: 1ef6af11851acbe0f7e9469c9432ff09f9228608
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792510"
---
# <a name="icordebugprocess2-interface"></a>Интерфейс ICorDebugProcess2
Логическое расширение интерфейса ICorDebugProcess, представляющее процесс, выполняющий управляемый код.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод ClearUnmanagedBreakpoint](icordebugprocess2-clearunmanagedbreakpoint-method.md)|Удаляет точку останова с указанным смещением, которое было задано предыдущим вызовом метода `ICorDebugProcess2::SetUnmanagedBreakpoint`.|  
|[Метод GetDesiredNGENCompilerFlags](icordebugprocess2-getdesiredngencompilerflags-method.md)|Возвращает флаги, которые должны быть установлены в среде CLR для загрузки изображения в процесс, на который ссылается этот `ICorDebugProcess2`.|  
|[Метод GetReferenceValueFromGCHandle](icordebugprocess2-getreferencevaluefromgchandle-method.md)|Возвращает указатель ссылки на указанный управляемый объект, который имеет обработчик сборки мусора.|  
|[Метод GetThreadForTaskID](icordebugprocess2-getthreadfortaskid-method.md)|Возвращает поток, в котором выполняется задача с указанным идентификатором.|  
|[Метод GetVersion](icordebugprocess2-getversion-method.md)|Возвращает версию среды CLR, на основе которой выполняется отлаживаемый процесс.|  
|[Метод SetDesiredNGENCompilerFlags](icordebugprocess2-setdesiredngencompilerflags-method.md)|Задает флаги, которые требуются для JIT-компилятора при загрузке изображения в отлаживаемый процесс.|  
|[Метод SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md)|Задает неуправляемую точку останова в указанном смещении машинного образа.|  
  
## <a name="remarks"></a>Заметки  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейсы отладки](debugging-interfaces.md)
