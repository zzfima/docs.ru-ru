---
title: Интерфейс ICorDebugModule2
ms.date: 03/30/2017
api_name:
- ICorDebugModule2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2
helpviewer_keywords:
- ICorDebugModule2 interface [.NET Framework debugging]
ms.assetid: 0847e64f-fdbe-4c96-8168-da20fdc84d80
topic_type:
- apiref
ms.openlocfilehash: 32774aacecf3e56510bc6f0670538a44fde794c9
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792988"
---
# <a name="icordebugmodule2-interface"></a>Интерфейс ICorDebugModule2

Служит логическим расширением интерфейса ICorDebugModule.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод ApplyChanges](icordebugmodule2-applychanges-method.md)|Применяет изменения в метаданных и изменения в коде промежуточного языка MSIL к выполняющемуся процессу.|  
|[Метод GetJITCompilerFlags](icordebugmodule2-getjitcompilerflags-method.md)|Возвращает флаги, управляющие JIT-компиляцией для данного `ICorDebugModule2`.|  
|[Метод ResolveAssembly](icordebugmodule2-resolveassembly-method.md)|Разрешает сборку, на которую ссылается указанный токен метаданных.|  
|[Метод SetJITCompilerFlags](icordebugmodule2-setjitcompilerflags-method.md)|Задает флаги, управляющие JIT-компиляцией для этого `ICorDebugModule2`.|  
|[Метод SetJMCStatus](icordebugmodule2-setjmcstatus-method.md)|Задает для состояния Только мой код (JMC) всех методов всех классов данного `ICorDebugModule2` указанное значение, за исключением тех, которые находятся в массиве `pTokens`, для которого задано обратное значение.|  
  
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
